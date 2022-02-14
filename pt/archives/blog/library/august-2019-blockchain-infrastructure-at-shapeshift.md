---
title: Blockchain Infrastructure at ShapeShift
description: Learn how ShapeShift's engineering team structures blockchain nodes. 
published: false
date: 2021-12-20T23:02:20.719Z
tags: library, bitcoin, developer, cryptocurrency, needs-review
editor: markdown
dateCreated: 2021-12-20T23:02:20.719Z
---

# Blockchain Infrastructure at ShapeShift

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9fbae5efc62b1120b46150_1_F0R4y3MkSpLjbo0bRB10Yw%20(1).png)

Blockchain nodes (coin daemons) are programs that fully validate transactions and blocks. They are the gateways to the cryptocurrencies that we support. [**ShapeShift**](http://shapeshift.com/) relies on blockchain nodes to receive and relay transaction data, which makes them critical to our business operations.

Herding hundreds of nodes is a pain-point with which many in the industry have to contend. In order to scale operations to support more than a couple of hundred transactions, these coin nodes must be run in parallel to reduce the stress placed on them. Some blockchain nodes are not reliable, have severe performance limitations, and often lack proper documentation.

On top of everything, most blockchain nodes require vast amounts of storage capacity in order to store the transaction history. Some of these data volumes can grow to be several Terabytes in size.

We sought to create a framework that would manage the building, deployment, and monitoring of blockchain nodes. This framework would need to meet several requirements:

* Automated builds
* 100% containerization
* Multiple simultaneously deployed versions
* Highly-available/resilient (multi-datacenter)
* Scalable (stand up new nodes quickly)

After repeating the phrase “Coin Daemon Container” one too many times, we decided to name the framework Cointainers.

## Platform Tooling

To build the Cointainers platform, we needed tooling which would let us rapidly iterate on builds and deployments. Docker was an easy choice in this regard, allowing us to create reproducible builds across platforms with very little setup.

To run the Docker builds within production systems, we went with Kubernetes, which has support for [stateful applications](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/) and [storage plugins for all of the major clouds.<br/> ](https://kubernetes.io/docs/concepts/storage/)

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9fbb02efc62b44b7b47b60_1*FHxwJvmHucRhWCvEIUXfKw.png)

We also needed all of the builds and infrastructure to be reproducible, so this meant incorporating some form of infrastructure-as-code (IaC) into the mix. [Terraform](https://www.terraform.io/) is usually the catch-all solution for this, its the largest and most used IaC framework. Hashicorp (the company behind Terraform) also recently announced [first-class support for Kubernetes within Terraform](https://www.hashicorp.com/blog/first-class-kubernetes-support-for-hashicorp-products).

However, Terraform requires learning a new language, the [HCL DSL](https://github.com/hashicorp/hcl). Using it would increase the barrier of entry for our engineers to learn and work on Cointainers. That's where Pulumi comes in.

Pulumi is an infrastructure-as-code framework very similar to Terraform, best described by the company on their [comparison page](https://www.pulumi.com/docs/reference/vs/terraform/):

*Pulumi is like Terraform, in that you create, deploy, and manage infrastructure as code on any cloud. Unlike Terraform, however, you will use familiar general purpose languages and tools to do. Like Terraform, Pulumi is* [*open source on GitHub*](https://github.com/pulumi/pulumi) *and is* [*free to use*](https://www.pulumi.com/docs/quickstart/)*.*

By using Pulumi, we’re able to take advantage of high-level languages that most of our engineers are already comfortable with. It also lets us be more expressive with our IaC by avoiding the limitations of Hashicorp Configuration Language (HCL). This is outlined in the comparison as well.

*Because of the use of real languages, you get familiar constructs like for loops, functions, and classes. This significantly improves the ability to cut down on boilerplate and enforce best practices. Instead of creating a new ecosystem of modules and sharing, Pulumi lets you leverage existing package management tools and techniques.*

## Build

A cointainer starts with a Docker image. Inside, we place the coin daemon's binary (blockchain node software). We also build a second (sidecar) container, which runs alongside the node software to monitor it.<br/> 

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9fbb03533c77038410f85b_1*z9XydSqnB12ApvEF3Gt8fw.png)

Since we need to support multiple versions, our build process looks something like this:

1. Read the list of coin nodes we need to build(e.g. Bitcoin, Dogecoin, Ethereum, etc.)
2. Download the last N* versions of coin daemon (e.g. bitcoin-0.18.0, bitcoin-1.17.1, bitcoin-0.17.0.1, etc.)
3. Build Docker containers for containing coin daemon software
4. Build Docker container for Monitoring nodes
5. Integration Test all Containers
6. Push Containers to Image Repository

** Customizable per coin*

Using the[@pulumi/docker](https://github.com/pulumi/pulumi-docker) module we're able to create Docker container repositories, build our Docker images, and push them to the repositories, all in one workflow.<br/> 

$ make deploy<br/><br/>Previewing deploy<br/><br/>    |   Type                         | Name           | Plan<br/>--------------------------------------------------------------<br/> +   ├─ cointainer:Deploys             ethereum         create<br/> +   │  ├─ container:Deploy            ethereum:2.4.5   create<br/> +   │  |  ├─ container:StatefulSet    ethereum:2.4.5   create<br/> +   │  |  ├─ container:AutoScaler     ethereum:2.4.5   create<br/> +   │  |  ├─ container:IngressRule    ethereum:2.4.5   create<br/> +   │  |  ├─ container:MonitorAlert   ethereum:2.4.5   create<br/> +   │  └─ container:Deploy            ethereum:2.6.5   create<br/> +   │     ├─ container:StatefulSet    ethereum:2.6.5   create<br/> +   │     ├─ container:AutoScaler     ethereum:2.6.5   create<br/> +   │     ├─ container:IngressRule    ethereum:2.6.5   create<br/> +   │     ├─ container:MonitorAlert   ethereum:2.6.5   createResources:<br/>    + 8 resources to create<br/><br/>Do you want to apply to changes?<br/>  yes<br/>> no<br/>  details<br/> 

## Deploy

We also use Pulumi within our deployment process to create the required resources inside our Kubernetes clusters. The[@pulumi/kubernetes](https://github.com/pulumi/pulumi-kubernetes) module lets us create IngressRules, StatefulSets, and HorizontalPodAutoscalers.

In order for our developers to always have the newest versions of nodes available to work against, we’ve set up automation that checks for new versions and deploys them on a recurring basis.

Our deployment workflow creates our resources & monitoring all at once:

1. Find all versions of nodes that we built earlier
2. Deploy the versions that aren’t in the environment
3. Create monitoring and alerts for each deployed version<br/> 

$ make deploy

Previewing deploy   

 |   Type                         | Name           | Plan<br/>--------------------------------------------------------------<br/> +   ├─ cointainer:Deploys             ethereum         create<br/> +   │  ├─ container:Deploy            ethereum:2.4.5   create<br/> +   │  |  ├─ container:StatefulSet    ethereum:2.4.5   create<br/> +   │  |  ├─ container:AutoScaler     ethereum:2.4.5   create<br/> +   │  |  ├─ container:IngressRule    ethereum:2.4.5   create<br/> +   │  |  ├─ container:MonitorAlert   ethereum:2.4.5   create<br/> +   │  └─ container:Deploy            ethereum:2.6.5   create<br/> +   │     ├─ container:StatefulSet    ethereum:2.6.5   create<br/> +   │     ├─ container:AutoScaler     ethereum:2.6.5   create<br/> +   │     ├─ container:IngressRule    ethereum:2.6.5   create<br/> +   │     ├─ container:MonitorAlert   ethereum:2.6.5   createResources:<br/>    + 8 resources to create<br/><br/>Do you want to apply to changes?<br/>  yes<br/>> no<br/>  details<br/> 

Read more about using Pulumi with Kubernetes [here](https://www.pulumi.com/blog/pulumi-a-better-way-to-kubernetes/)

## Architecture

During each node start-up, we check if the data volume has a copy of the blockchain. If it’s a new node replica and has no blocks, or if the chain is too far behind, we download a backup to avoid waiting for the node to manually sync (which can take weeks to complete).<br/> 

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9fbb0354b6e3785920e526_1*zbFYJNWGRzpdYp8GSPu8Qg.png)

<br/>After the backup is downloaded and the node software is launched, our systems wait until it is 100% synced before making it available.

Our monitoring container checks the block height of the node against external block explorers, and also if the node reports that it is still syncing blocks. After the node is fully synced and its block height is above or equal to the block explorer, we place it behind the load-balancer.

If the node falls behind, we take it out of the load-balancer and wait for it to catch-up again before placing it back in service to clients.

<br/> 

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9fbb03efc62b63e2b47b93_1*00OwEzzfIBPJliOyj3wMjA.png)

Traffic only goes to healthy/synced nodes<br/>We maintain a minimum of 3 nodes for each coin version across multiple datacenters: One reserved for backups, and two to maintain reliability. As load increases on the coin nodes, our systems automatically launch more to keep up with demand.

At a higher level, we serve multiple versions of the nodes for our applications. This allows our development teams to switch versions at any time, giving them the ability roll back immediately if needed.<br/> 

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9fbb03df8913769e880eb2_1*3tI4eIfns6iJEmvzUO6q9Q.png)

Multiple Versions of Bitcoin<br/>After all of our apps migrate from the old version to the new one, we decommission it and keep the remaining ones that our applications still depend on.<br/> 

## Monitoring

Using the monitors created in the deployment, our systems check the health of Cointainers every 15 seconds to make sure that they are reachable and respond with data that is valid. We also monitor the amount of node replicas that we run for each coin version. If any coin version has less than 2 nodes active, our monitoring systems sound alarms that notify our engineers and member services teams.

If you’re interested in working on projects like Cointainers, check our [**Careers**](http://shapeshift.com/careers)page! We are searching for: Software Engineers, VP of Marketing, and unicorns 🦄!<br/> 

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9fbb037e6909591b3c32e2_1*0CtbPVcRkofblk3ZXkUuXw.png)

 

---

> This document was originally published on 2019-08-13 by Azamat Mukhiddinov and may have been slightly modified for translation by the Information and Globalization workstream for an ongoing archival project.
>
> Original article can be found [here](https://shapeshift.com/library/blockchain-infrastructure-at-shapeshift).
{.is-success}

---

- bounty: true
- amt: 61
- signedBy: 0xFAc9dD5194098461B627554347f83D5431Fb30e2
- hash: 
{.is-hidden}