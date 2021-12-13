---
title: Looting of the Fox - The Story of Sabotage at ShapeShift
description: This is the story of how ShapeShift, a leading blockchain asset exchange platform, was betrayed. Not once, not twice, but three times in less than a month.
published: false
date: 2021-11-25T21:37:59.038Z
tags: shapeshift, shapeshift history, hacks, funds, archive, looting, stolen funds
editor: markdown
dateCreated: 2021-11-25T18:21:56.126Z
---

# Looting of the Fox - The Story of Sabotage at ShapeShift

> This article/document/post/content was originally published on Apr 19, 2016 by Erik Voorhees and could be slightly modified for translation by the ShapeShift's Information and Globalization workstream for an ongoing archival project.
{.is-success}
---

This is the story of how ShapeShift was betrayed. Not once, not twice, but three times in less than a month.

In total, nearly two-hundred thousand dollars in cryptocurrency was stolen by thieves within and without, not to mention the significant resources expended in its wake. Nevertheless, no customer funds were ever lost or at risk, a milestone for an industry pocked with past tragedy, and ShapeShift itself has adapted and rebuilt, humbled by the experience learned, and ever more resolute in its mission of safe, frictionless asset exchange.

In the spirit of Bitcoin’s openness, we wanted to share this story with the community; may you be informed, entertained, reflective, and ever-diligent in your own affairs.

# The Backstory

Since its inception in the Spring of 2014, ShapeShift has been an evolving creature. What began as a quick experimental way to swap between Bitcoin and Litecoin grew into an advanced engine for the effortless exchange of all major blockchain assets, each one into the other, with no user friction. No user accounts. No signup process. It is the Google Translate of cryptocurrency.

And we’ve always been playing catch-up. Trying to build at the speed of this industry, not only along the vertical of Bitcoin proper, but along the breadth of all crypto, is a challenge.

Last Fall, we realized the “minimum viable product” server architecture established originally for ShapeShift was insufficient. We needed a professional to join the small team, and craft a scalable, and secure, server apparatus upon which our technology could grow.

We hired such a person, and patted ourselves on the back for our proactive decision. On paper, he looked great; the reference we called confirmed his prior role and responsibility. He’d even been into Bitcoin since 2011/2012 and had built miners in his room. Awesome. We’ll call this new employee Bob… indeed his real name starts with a B.

Over the next months, Bob built and managed ShapeShift’s infrastructure. He did okay, nothing special, but we were content to have a professional taking care of devops at least well enough to enable our engineers to build upon the architecture.

In the first quarter of this year, as the market discovered what we already knew – that our world will be one of many blockchain assets each needing liquidity with the other – exchange volumes surged at ShapeShift. Ethereum was on the rise, specifically. Our infrastructure was not ready for the pace of growth. It was like riding a bicycle upon which jet engines suddenly appear full-thrust

Unfortunately, Bob did little to be helpful. He puttered around aimlessly while the team worked long hours to keep the ship together.

Scratch that, actually, Bob was not aimless.

He was preparing to steal from us.

## The Genesis Betrayal

On the morning of March 14th, in the midst of one of our heaviest volume weeks ever, I get a call from our Head of Operations, Greg. “Erik, our hot wallet is missing 315 Bitcoin.” Why did we have so much in a hot wallet, you ask? Well, with volumes surging, our hot wallet would be drained through normal business in an hour at that level, which then required constant manual rebalancing. Are there ways to automate and reduce that risk? Absolutely… but hindsight of one’s development priorities is always 20/20.

So 315 Bitcoin was gone.

To those who have experienced such incidents, the feeling of sickness is profound. It’s a deep, dismal state, that doesn’t stop at the edge of financial loss, but permeates down to one’s core. When systems are breached, systems that one has engineered and cared for deeply, obsessively, that violation of what one considers safe and secure is very, very uncomfortable. And then there’s the loss itself. 315 Bitcoin… roughly $130,000. That’s college tuition, part of a house, food for ten years… a couple months of payroll. It’s a lot of money for a pre-profit startup.

I rushed to the office, hoping there was some mistake. The only comforting thought was that the loss was only our own money. With no customer accounts, neither customer funds nor personal information were at risk from the hack. That was by design from the beginning of ShapeShift; one of our tenets. But even if nobody nearby is harmed, a punch in the face still hurts like hell.

Myself, Greg, and our two lead engineers poured through logs and servers, trying frantically to figure out what had happened. The 315 BTC went to an unfamiliar Bitcoin address, and was sitting there.

Indeed, it sits there still: https://blockchain.info/address/1LchKFYxkugq3EPMoJJp5cvUyTyPMu1qBR

Despite our note to all employees to come into the office urgently, Bob, our head IT guy, the one responsible for security and infrastructure, arrives at 11:30am.

We ask Bob to join our discussion. We reveal the hack to him. We ask him if he had logged in at all that morning, to which he responded no (on several occasions). On the new of the theft, he seems neither particularly shocked nor outraged, yet it was his security that failed us. Immediately, he starts pointing to red herring explanations, “It must be one of the exchanges that got hacked, that happens all the time.” Umm, our exchange accounts are fine, Bob.

“Well, look at the IP address, it happened somewhere off west Africa.” Umm, IP addresses on block explorers indicate only the first node that noticed a transaction, and are generally meaningless in the context of Bitcoin, Bob. (What kind of Bitcoiner doesn’t know that?)

Very quickly, we realize he is pretty much useless. Here we have our “server guy” and he has zero intelligent comments about a hack against his own infrastructure.

While pouring over logs we noticed, however, a couple SSH keys (belonging to Bob) that had logged into the breached server that morning an hour before the rogue transaction, and then logged off two minutes after. Not nefarious, necessarily, for indeed Bob’s keys would be expected to log in periodically, though the timing was strange (6am-ish in the morning). We also discovered the breach occurred over the VPN, meaning someone in the office, or someone with access to our VPN, committed the theft.

We ask everyone with server access to provide the fingerprints of their SSH keys so we can start comparing them to logs. Everyone does so, but another strange thing: the fingerprint of the key handed in by Bob doesn’t appear in any logs. It appears brand new. Strange that the key of the server admin would never have been seen on any server…

Soon after, Bob decides it’s time for his lunch break, and we don’t see him for an hour, during the worst incident in ShapeShift’s history. We frankly didn’t care that much, he wasn’t helpful and suspicions were starting to creep in. He tells all of us that he’s leaving his laptop open to download some logs, and makes sure we see that the laptop is left open. He’s being a little weird.

Upon his return an hour later, he is sitting down with other engineers still investigating what occurred. I’m in the other room on a call. When I finish my call, I come check on the progress. Bob appears to receive a call “from his mother who needs to go to the hospital.” He packs up his stuff, grabs his dog who was at the office, and heads out. We’re all half relieved for his departure and half in awe… did our server admin really just leave for the second time during our investigation, which he should be leading?

He says, “I’ll be back within an hour.” This was at about 3pm, March 14.

We never saw him again

Shortly after he leaves, one of our engineers pulls myself and Greg aside, and says, “While you were on your call, we were all sitting around the table, and we saw in the logs that Bob deleted two SSH keys while he was sitting there with us, then he grep’d several times for them [a server command to find specific text], and then he left. Those two keys matched the two keys we saw in the log this morning which accessed the Bitcoin server just prior to the hack.”

He just deleted his keys from the server?? Well fuck. Guns don’t get any smokier than that.

We all immediately move to the assumption that Bob stole the funds. He is out of the building, and so we start locking everything down. All keys are changed in haste (well, almost all).

We work for a few more hours, no word from Bob. No calls, no texts, nothing. By the end of the day, it had been 3-4 hours since he left to “take his mother to the hospital.” We decide to call him, without letting on our suspicions just yet.

> “Hey Bob, where are you?.”
>
> “Oh hey, I just decided to go home.”
>
> “You’re at home?”
>
> “Yeah, just here, working on some stuff.”

WTF?

That call is innocuous, but we recorded it. We also recorded the next one 30 mins later, in which we confront him with some of the evidence.

“So Bob, it looks like you deleted your SSH keys, and gave us a new key that had never accessed any servers.”

“Yeah, well I deleted them because I didn’t think they were important.”

Yes, he actually said that. Our server admin, in the midst of an investigation into a $130,000 theft, deletes his two keys, and only these two keys, without telling anyone, and then admits on our call that he did it because “they weren’t important.”

It just so happens those two keys were the exact ones logged into the Bitcoin server that morning, and which logged off two minutes after the theft transaction. Not important indeed!

He gives no explanation of his behavior or actions that day, but dances around questions and implies, subtly at first, and then more explicitly, that we’re being racist.

“Umm Bob, we’re targeting you because your keys were on the server, and you deleted them and left, during an active investigation.”

It goes on like that for 45 mins. He says other ridiculous stuff, all recorded.

We uncover further evidence details, and there is a sense of relief after knowing exactly what happened and who was responsible. We spend the rest of the evening documenting everything, and preparing to file civil and criminal charges against Bob.

I give him a final chance that evening for redemption. In a message to all employees, so as not to force him to implicate himself by responding,

> This is your chance to walk away, learn a lesson, and let this be closed. We will not pursue legal action if 315 Bitcoin are found in this address by 10am. No further questions will be asked, and we can part ways amicably. Send 315 BTC here: 35JBgzjyCUPswjRP9iqrUTkkX76QwrKkB9 -Erik

I get a response message from Bob at 4:36am, “I didn’t delete any keys and I regularly log into servers to check them out.”

Right, except that we have him already on record saying he did delete the keys and hadn’t logged on that morning. His ineptitude at lying appears outmatched only by his incompetence in server administration.

He goes on, with charming adolescent flare

> “Of course blaming me is the racist thing to do… you were basically looking for an excuse to satisfy your racism. I have no criminal history unlike you with the SEC.”

The next morning, our general counsel writes a formal letter (via email and post) to Bob, outlining some of the evidence that we knew, and demanding the stolen property be returned. It also notified Bob that his employment was terminated (I think that was fair, considering). In response, Bob emails back to the lawyer, addressing none of the evidence whatsoever, “Your clients are racist so make sure you know who you’re dealing with.”

It’s like he was wearing his internet troll hat in real life. Did he not even understand the seriousness of the situation? Well… the absurdity was just getting started.

Over the next days, we file the formal civil complaint. The address Bob had given us was a PO box, though we had his legal name, his bank info, and his social serfdom number. We hired a private investigator. We found his apartment within a couple days. Several attempts at service failed, though the investigator heard a dog barking behind the door. One of his cars was found; he drives two unmarked retired police cruisers.

I have investors to whom I owe a level of protocol diligence, so, we also made arrangements for a criminal case, and herein the theft constitutes a Class 3 Felony, with 4-12 years in prison. Honestly, I don’t care whether he is punished. I care whether we are made whole, and whether he realizes his error and changes his life to become a better person. No sign yet, of that.

We learn some more things. Bob has prior police records in Florida, where he’s from. Incidentally, the records indicate he’s white, after all.

With civil and criminal cases proceeding against him, and with further discovery that Bob fled to Florida (leaving his dog to be temporarily cared for by his neighbor… who is now wondering where he is and hasn’t heard from him in weeks), we thought the case was basically closed. We’d get him somewhere, sooner or later. And, hopefully, we’d get our stolen property returned, or the fiat equivalent.

## Who is Rovion

We’d worked to build a new server infrastructure in Bob’s wake, assuming his work in our system to be largely compromised. We set up a new cloud architecture with a company we’ll call CloudCo.

It’s now the week of April 4th, and we were about ready to go live with this new cloud infrastructure. Then all hell breaks loose. Again.

On Thursday April 7th, around midday, we notice a bunch of Ethereum had left the hot wallet on the new infrastructure at CloudCo. The NEW infrastructure. The infrastructure that was not even public yet. At first, we believed our code had done something weird, perhaps sweeping funds to a development server address or similar. Then we noticed a bunch of Bitcoin was also missing. And then Litecoin also.

Thief’s Bitcoin address: 14Kt9i5MdQCKvjX6HS2hEevVgbPhK13SKD

Thief’s Ethereum address: 0xC26B321d50910f2f990EF92A8Effd8EC38aDE8f5

Thief’s Litecoin address: LL9jqgXVqxUbWbWVaJocBcF9Vm8uS3NaTd

And very quickly reality hits you, and that’s what flashback feels like. The horrible sinking feeling sets in immediately, once again. What the fuck happened?

Keys that were not even on publicly known servers had been compromised, somehow. We shut the system down, including our live production site, while we investigated. We didn’t lose as much as the hack a month prior, because we’d be keeping wallets somewhat conservative, but it was still quite a bit. We couldn’t believe it. How could brand new keys, generated with brand new infrastructure, be compromised?

After several hours of fruitless investigation, we decide that one of the most likely explanations is that the cloud company itself was compromised. This has happened before in Bitcoinland. We thought CloudCo was reputable, but who knows? Clouds are very convenient and scalable, but on some level you’re trusting that company with your infrastructure. We decided we had to keep the site down for at least 24 hours, and bust our asses to prepare, yet again, an entirely new infrastructure on an entirely new set of servers.

What was nearly as bad as the money lost was not knowing how it happened. Logs were not done as well as they should have been, so they proved fruitless. Indeed, they had been wiped.

Despite that, we watched the blockchains for the hacked funds. We tracked some to an exchange account. We got profile information of the depositor.

Name: Rovion Vavilov
Email: rovion.vavilov@riseup.net
Address: Chayanova St. 15, Moscow
DOB: Feb 2, 1980
Phone: +7 9625148445

That profile information was probably fake, but I emailed him that night.

From: Erik Voorhees erik@shapeshift.io
To: rovion.vavilov@riseup.net
Subject: ShapeShift Hack…

*“Nice job on the hack. How did you do it? -Erik”*

Pro Tip: Black hats like to be recognized for their skill, regardless of how immoral their deeds may be. Talk to them calmly, as adults. They may reveal information, or help in some way. It’s weird, but it happens. In any case, I didn’t expect anything to come of my email.

The rest of that night, and into the next day (Friday, the 8th), the team worked feverishly to rebuild everything on new infrastructure, once again, in a wholly clean environment on a wholly separate host.

Now to many, ShapeShift appears to be a simple web service. It’s taken a lot of work by our engineers to keep up that appearance. Behind the scenes, the platform is complex. Over 1,400 direct asset trading pairs, integrations with half a dozen exchange API’s requiring real-time price information on all offered cryptocurrencies, low-latency service API’s to several dozen partners, the monitoring and calculation of constantly changing exchange rates and order book depth in some of the most volatile markets on Earth, and incorporation of what can only be described as alpha-level software in various states of disarray (coin daemons…bleh).

And in Bitcoinland, indeed, and there is no guide book.

Admittedly, as a non-engineer myself, I can only occasionally glimpse the magnificence of what we’re building. I wish I could take credit. To our team reading this, you have engineered an amazing machine and should be very proud of it.

And now here is where the story deepens

Around mid-day on Friday, the hacker responds to my email (remember I had asked him how he did it…)

From: rovion.vavilov@fastmail.com (noted new domain)
To: Erik Voorhees erik@shapeshift.io
Subject: ShapeShift Hack…

*“One word: Bob”*

That was the entirety of that first email, but we were stunned. For a moment, we thought, “Is Bob the hacker?” Quickly, that notion gave way to the more likely answer: that Bob sold or gave away our information to a hacker, who then exploited it.

Bob betrayed us. He betrayed his privileged position, profiting directly from the destruction of those who trusted him. He stole, lied, ran away, and then after being afforded a period of time long enough to reflect upon his actions, decided to betray us again for a few more scraps in his pathetic bowl. Hackers gonna hack, but it takes a certain variety of bastard to ascend to a trusted position, work face to face with a team, receive a salary and confidence from that team, and then screw them all for barely enough money to buy a Tesla. Oh yeah, and then abandon a dog to starve alone, likely soon to be put down by animal services.

Watch out for these people in your lives. If you suspect them, sever ties quickly.

Anyway, after herculean efforts, we had everything ready by Friday night, 24 hrs later. We launched the site on yet a new provider, who we’ll call HostCo. Despite a couple glitchy bugs, the system was running. We had told the public about the hack and decided to release more details once we studied the compromised environment in more detail later.

Exchange orders started up immediately. We breathed a sigh of relief. I fell asleep around 1am and slept peacefully, exhausted from the ordeal and very proud of the team.

Then it was Saturday 9am, and I start emerging from slumber. My phone rings. It was Greg.

“We were hacked again. Bitcoin and Ethereum taken from the HostCo hot wallets.”

I’m silent on the phone. I’m thinking only, “Is this the fucking apocalypse?!?”

It didn’t seem possible. The hack two days prior didn’t seem possible, and this now was just immensely confusing and depressing. I tell Greg to take the site down again and I’ll call him back in 30 minutes. How the hell are we going to explain this to the community, to our customers… to our investors? How do we even explain it to ourselves?

I get out of bed, not panicked, but just feeling utterly defeated. I take the worst shower of my life. Anger surrounds me… we knew Bob was involved from the hacker’s email, and we knew Bob committed a Class 3 felony against us, which the authorities knew about three weeks ago, and our private investigator had provided all the information needed for an immediate conviction. And now this happens.

As I gather my thoughts, I decide it’s time to call in some professional resources.

Michael Perklin, Head of Security and Investigative Services at Ledger Labs, and chairman of the Steering Committee for the Board of CCSS, is first on my list. He’s in Toronto, and agrees to fly out to meet us that evening. He was on his way to the hospital; he had a toe broken in an event he’d prefer not to discuss. He changes course and heads to the airport. What a champion.

I also chat further with heads of several leading exchanges. None of them like thieves, and are eager to help. Despite its hectic pace and diversity of opinions and interests, this industry comes together when it needs to.

1500 ETH recovered, and exchanges are hunting for more. The thief is probably upset by this… it sucks to be stolen from, after all.

## Fireside Chats with the Thief

In parallel to all that, I hear again from the thief via email. I had responded to his “One word: Bob” message by asking if he would provide more info. He mentions that for a price, he may.

“hi” he says.

I arrange to pay him 2 BTC for information.

“I need to know what your relation to bob is” I ask. I tried to avoid pre-empting details.

He replies, “I got information that Bob “hacked” you while I was trying to hack you too. I had some access before Bob hacked you but not enough to get the coins myself.”

“What do you know about Bob hacking us?” I ask

“Inside job. 315 BTC.” he replies. “I talked to Bob after he took the coins, asked him about how I could hack it too. He gave me more information about the infrastructure and some keys.”

I ask, “Why would he give you information and what did he give you?”

Rovion responds, “Because I offered BTC. IP addresses, server roles, users, a working SSH key. Does not work anymore.”

We chat further, and he reveals Bob’s email that he communicated with: m0money@gmail.com.

While I had not seen that email before, it seemed familiar. I thought for a while, and then realized that Bob often substituted 0’s for o’s, including on one of the two keys which he had deleted from the server (the specific key was named something which, if displayed, would give away Bob’s real name). That, and the fact that one of Bob’s common password variations was “m0m0ney.” Our security guy used l33tspeak for his passwords. Real secure.

As clear as it had been that Bob had stolen our funds a few weeks prior, it was now clear that this hacker, Rovion, was giving us information related to Bob that only Bob or those with whom he had actually interacted would know.

Another thought, could this hacker have actually framed Bob from the beginning? Sure, perhaps, but every action of Bob’s back on March 14th points away from that explanation, specifically Bob deleting his own keys right under our nose and then leaving the office, never to return. Other evidence not listed here further counters that theory.

Back to the chat with Rovion… I ask which “working SSH key” he had obtained. “None of your business,” he responds, “but he told me he got it from a coworker’s open laptop.”

Wow. If true, that means Bob, while working at ShapeShift, accessed a coworkers computer and copied a key (or more?), at some point before he stole the funds. Did he premeditate the whole thing, I wonder?

I try to get more information, but Rovion is unforthcoming. His last message…

> “Your millions will save you, Erik Voorhees. Goodbye, I will be on email.”

By the early evening, our forensic investigator, Michael Perklin, had arrived. I picked him up from the airport. We had decided to hold off on poking around in our servers until he was there. While the hacker gave a vague sense of how he came upon secret information, we didn’t really know the specifics of the breach. Keys had been changed after Bob’s departure, and while we found one key we hadn’t remembered to change, it only had access to a server that could not have stolen the funds on the preceding Thursday. And again, it wouldn’t at all explain how the Saturday morning theft occurred. Both CloudCo and HostCo had funds stolen off them, despite them being built as entirely new environments with wholly new keys.

Michael asked me to convey to him the whole story of the past month. He proceeded through his investigative protocol, which included the assumption that nobody at the company was trustworthy. It was hard to argue that the team was trustworthy, given the fact that this all started with a rogue employee. It was a depressing feeling.

Many interesting details could be added here about how such forensic work is done, but space is limited and it’s probably unwise to reveal every such method. After a while, we dove into the logs themselves, attacking the Saturday logs first. They were deleted, most of them. How were they deleted? We weren’t sure.

We know now how to prevent that… indeed, the experience we’ve received throughout this incident has been immensely valuable. Though it sounds cliché, if your startup is involved in securing information or servers whatsoever, do yourself a favor and bring in 3rd party professional help very early. We hadn’t needed it at first, because we were small. But growth creeps up on you, and before you know it you are securing significant assets with sub-standard methods.

While much of the logs were gone, we in fact recovered a great portion of them off the “empty” disk space itself using forensic techniques. This was just lucky. Perhaps the Ghost of Satoshi was looking out for us (could have used his help a week ago, of course!)

From the recovered data, we discovered the malware, if that’s the right term. There was a program, written in Go, installed on a crucial server which communicated with coins. This program had its dates changed to appear consistent with the setup of the server, and its filename made to look innocuous. But it was the direct tool by which funds were stolen.

udevd-bridge it was called

We were glad to find it (and yes, the same thing appeared in both server environments, CloudCo and HostCo). However, it still didn’t explain how it was put there. We had a lot of information, but not the whole story.

And we wouldn’t have the whole story for a couple more days. But then the stars aligned.

Out of the blue, the hacker, Rovion, emails me again on Wednesday, April 13th.

From: Rovion Vavilov rovion.vavilov@fastmail.com
To: Erik Voorhees erik@shapeshift.io
Subject: Re: ShapeShift

*“Would you be interested in buying the ETH that I currently hold back at a highly discounted rate in exchange for BTC? I’d be willing to trade in small quantities since you have no reason to trust me.”*

Yes, it appears the hacker has gotten annoyed that his Ethereum kept getting frozen at exchanges. So he comes back to the store he robbed from, and asks us if we’ll trade for a more liquid asset. We’d be essentially buying back our own Ethereum, and paying him Bitcoin.

Obviously worth it, if we can obtain more information. Since neither of us trust the other, we establish a protocol:

1) We pay 2 BTC to get the conversation started
2) Rovion gives us half the relevant information
3) We exchange, in increments of 250, 2000 ETH for BTC at 0.02 BTC/ETH rate
4) Rovion gives us second half of the relevant information
5) We exchange, in the same increments, the remaining 2500 ETH for BTC at same rate
6) We cease communication (this last one was Rovion’s suggestion)

He asks us to send the BTC to his already known BTC address: 14Kt9i5MdQCKvjX6HS2hEevVgbPhK13SKD

After the initial 2 BTC payment, Rovion begins with description of April 7th hack:

> “We contacted Bob. He gave us the ShapeShift core source code, core server IP address, an SSH key, and [redacted]. I logged in to the core server with the SSH key provided, installed a backdoor and took the coins since the core server had SSH access to the coins server.”

“What’s the fingerprint of the SSH key mentioned above?” I ask

``“9c:3f:4b:ad:d6:43:ec:9a:55:de:b9:0b:d8:f5:0a:cb”``

We see that it’s Greg’s key, newly created for the CloudCo environment. It was not even in existence until more than a week after Bob had stolen the funds in March and disappeared. How on Earth did this hacker get a new key, post Bob?

I also ask about the “[redacted]” mentioned but Rovion says that is part of the second batch of information. We proceed with the incremental exchange of the second batch of funds.

Then Rovion says,

>“[redacted] was access to an RDP installed on a coworker’s machine by Bob. That’s how I hacked you the second time.”

Wow, now it’s starting to come together, each revelation peeling back a layer of Bob’s treachery. Bob had installed an RDP (remote desktop protocol – basically a screen viewer or controller) on Greg’s computer. And perhaps on others, we must assume.

Then Rovion shares via pastebin an email from Bob (the info he purchased):

>
Looting of the Fox: The Story of Sabotage at ShapeShift
ShapeShift Erik Voorhees
Bitcoin, as any system of man, exhibits together both the highest ideals of utopia, and the lowest residual trash of society.

[Note: some names & sensitive details have been changed]

Erik VoorheesThis is the story of how ShapeShift, a leading blockchain asset exchange platform, was betrayed. Not once, not twice, but three times in less than a month.

In total, nearly two-hundred thousand dollars in cryptocurrency was stolen by thieves within and without, not to mention the significant resources expended in its wake. Nevertheless, no customer funds were ever lost or at risk, a milestone for an industry pocked with past tragedy, and ShapeShift itself has adapted and rebuilt, humbled by the experience learned, and ever more resolute in its mission of safe, frictionless asset exchange.

In the spirit of Bitcoin’s openness, we wanted to share this story with the community; may you be informed, entertained, reflective, and ever-diligent in your own affairs.

The Backstory
Since its inception in the Spring of 2014, ShapeShift has been an evolving creature. What began as a quick experimental way to swap between Bitcoin and Litecoin grew into an advanced engine for the effortless exchange of all major blockchain assets, each one into the other, with no user friction. No user accounts. No signup process. It is the Google Translate of cryptocurrency.

And we’ve always been playing catch-up. Trying to build at the speed of this industry, not only along the vertical of Bitcoin proper, but along the breadth of all crypto, is a challenge.

Last Fall, we realized the “minimum viable product” server architecture established originally for ShapeShift was insufficient. We needed a professional to join the small team, and craft a scalable, and secure, server apparatus upon which our technology could grow.

We hired such a person, and patted ourselves on the back for our proactive decision. On paper, he looked great; the reference we called confirmed his prior role and responsibility. He’d even been into Bitcoin since 2011/2012 and had built miners in his room. Awesome. We’ll call this new employee Bob… indeed his real name starts with a B.

Over the next months, Bob built and managed ShapeShift’s infrastructure. He did okay, nothing special, but we were content to have a professional taking care of devops at least well enough to enable our engineers to build upon the architecture.

In the first quarter of this year, as the market discovered what we already knew – that our world will be one of many blockchain assets each needing liquidity with the other – exchange volumes surged at ShapeShift. Ethereum was on the rise, specifically. Our infrastructure was not ready for the pace of growth. It was like riding a bicycle upon which jet engines suddenly appear full-thrust

Unfortunately, Bob did little to be helpful. He puttered around aimlessly while the team worked long hours to keep the ship together.

Scratch that, actually, Bob was not aimless.

He was preparing to steal from us.

The Genesis Betrayal
On the morning of March 14th, in the midst of one of our heaviest volume weeks ever, I get a call from our Head of Operations, Greg. “Erik, our hot wallet is missing 315 Bitcoin.” Why did we have so much in a hot wallet, you ask? Well, with volumes surging, our hot wallet would be drained through normal business in an hour at that level, which then required constant manual rebalancing. Are there ways to automate and reduce that risk? Absolutely… but hindsight of one’s development priorities is always 20/20.

So 315 Bitcoin was gone.

To those who have experienced such incidents, the feeling of sickness is profound. It’s a deep, dismal state, that doesn’t stop at the edge of financial loss, but permeates down to one’s core. When systems are breached, systems that one has engineered and cared for deeply, obsessively, that violation of what one considers safe and secure is very, very uncomfortable. And then there’s the loss itself. 315 Bitcoin… roughly $130,000. That’s college tuition, part of a house, food for ten years… a couple months of payroll. It’s a lot of money for a pre-profit startup.

I rushed to the office, hoping there was some mistake. The only comforting thought was that the loss was only our own money. With no customer accounts, neither customer funds nor personal information were at risk from the hack. That was by design from the beginning of ShapeShift; one of our tenets. But even if nobody nearby is harmed, a punch in the face still hurts like hell.

Myself, Greg, and our two lead engineers poured through logs and servers, trying frantically to figure out what had happened. The 315 BTC went to an unfamiliar Bitcoin address, and was sitting there.

Indeed, it sits there still: https://blockchain.info/address/1LchKFYxkugq3EPMoJJp5cvUyTyPMu1qBR

Despite our note to all employees to come into the office urgently, Bob, our head IT guy, the one responsible for security and infrastructure, arrives at 11:30am.

We ask Bob to join our discussion. We reveal the hack to him. We ask him if he had logged in at all that morning, to which he responded no (on several occasions). On the new of the theft, he seems neither particularly shocked nor outraged, yet it was his security that failed us. Immediately, he starts pointing to red herring explanations, “It must be one of the exchanges that got hacked, that happens all the time.” Umm, our exchange accounts are fine, Bob.

“Well, look at the IP address, it happened somewhere off west Africa.” Umm, IP addresses on block explorers indicate only the first node that noticed a transaction, and are generally meaningless in the context of Bitcoin, Bob. (What kind of Bitcoiner doesn’t know that?)

Very quickly, we realize he is pretty much useless. Here we have our “server guy” and he has zero intelligent comments about a hack against his own infrastructure.

While pouring over logs we noticed, however, a couple SSH keys (belonging to Bob) that had logged into the breached server that morning an hour before the rogue transaction, and then logged off two minutes after. Not nefarious, necessarily, for indeed Bob’s keys would be expected to log in periodically, though the timing was strange (6am-ish in the morning). We also discovered the breach occurred over the VPN, meaning someone in the office, or someone with access to our VPN, committed the theft.

We ask everyone with server access to provide the fingerprints of their SSH keys so we can start comparing them to logs. Everyone does so, but another strange thing: the fingerprint of the key handed in by Bob doesn’t appear in any logs. It appears brand new. Strange that the key of the server admin would never have been seen on any server…

Soon after, Bob decides it’s time for his lunch break, and we don’t see him for an hour, during the worst incident in ShapeShift’s history. We frankly didn’t care that much, he wasn’t helpful and suspicions were starting to creep in. He tells all of us that he’s leaving his laptop open to download some logs, and makes sure we see that the laptop is left open. He’s being a little weird.

Upon his return an hour later, he is sitting down with other engineers still investigating what occurred. I’m in the other room on a call. When I finish my call, I come check on the progress. Bob appears to receive a call “from his mother who needs to go to the hospital.” He packs up his stuff, grabs his dog who was at the office, and heads out. We’re all half relieved for his departure and half in awe… did our server admin really just leave for the second time during our investigation, which he should be leading?

He says, “I’ll be back within an hour.” This was at about 3pm, March 14.

We never saw him again

Shortly after he leaves, one of our engineers pulls myself and Greg aside, and says, “While you were on your call, we were all sitting around the table, and we saw in the logs that Bob deleted two SSH keys while he was sitting there with us, then he grep’d several times for them [a server command to find specific text], and then he left. Those two keys matched the two keys we saw in the log this morning which accessed the Bitcoin server just prior to the hack.”

He just deleted his keys from the server?? Well fuck. Guns don’t get any smokier than that.

We all immediately move to the assumption that Bob stole the funds. He is out of the building, and so we start locking everything down. All keys are changed in haste (well, almost all).

We work for a few more hours, no word from Bob. No calls, no texts, nothing. By the end of the day, it had been 3-4 hours since he left to “take his mother to the hospital.” We decide to call him, without letting on our suspicions just yet.

“Hey Bob, where are you?.”

“Oh hey, I just decided to go home.”

“You’re at home?”

“Yeah, just here, working on some stuff.”

WTF?

That call is innocuous, but we recorded it. We also recorded the next one 30 mins later, in which we confront him with some of the evidence.

“So Bob, it looks like you deleted your SSH keys, and gave us a new key that had never accessed any servers.”

“Yeah, well I deleted them because I didn’t think they were important.”

Yes, he actually said that. Our server admin, in the midst of an investigation into a $130,000 theft, deletes his two keys, and only these two keys, without telling anyone, and then admits on our call that he did it because “they weren’t important.”

It just so happens those two keys were the exact ones logged into the Bitcoin server that morning, and which logged off two minutes after the theft transaction. Not important indeed!

He gives no explanation of his behavior or actions that day, but dances around questions and implies, subtly at first, and then more explicitly, that we’re being racist.

“Umm Bob, we’re targeting you because your keys were on the server, and you deleted them and left, during an active investigation.”

It goes on like that for 45 mins. He says other ridiculous stuff, all recorded.

We uncover further evidence details, and there is a sense of relief after knowing exactly what happened and who was responsible. We spend the rest of the evening documenting everything, and preparing to file civil and criminal charges against Bob.

I give him a final chance that evening for redemption. In a message to all employees, so as not to force him to implicate himself by responding,

This is your chance to walk away, learn a lesson, and let this be closed. We will not pursue legal action if 315 Bitcoin are found in this address by 10am. No further questions will be asked, and we can part ways amicably. Send 315 BTC here: 35JBgzjyCUPswjRP9iqrUTkkX76QwrKkB9 -Erik

I get a response message from Bob at 4:36am, “I didn’t delete any keys and I regularly log into servers to check them out.”

Right, except that we have him already on record saying he did delete the keys and hadn’t logged on that morning. His ineptitude at lying appears outmatched only by his incompetence in server administration.

He goes on, with charming adolescent flare…

“Of course blaming me is the racist thing to do… you were basically looking for an excuse to satisfy your racism. I have no criminal history unlike you with the SEC.”

The next morning, our general counsel writes a formal letter (via email and post) to Bob, outlining some of the evidence that we knew, and demanding the stolen property be returned. It also notified Bob that his employment was terminated (I think that was fair, considering). In response, Bob emails back to the lawyer, addressing none of the evidence whatsoever, “Your clients are racist so make sure you know who you’re dealing with.”

It’s like he was wearing his internet troll hat in real life. Did he not even understand the seriousness of the situation? Well… the absurdity was just getting started.

Over the next days, we file the formal civil complaint. The address Bob had given us was a PO box, though we had his legal name, his bank info, and his social serfdom number. We hired a private investigator. We found his apartment within a couple days. Several attempts at service failed, though the investigator heard a dog barking behind the door. One of his cars was found; he drives two unmarked retired police cruisers.

I have investors to whom I owe a level of protocol diligence, so, we also made arrangements for a criminal case, and herein the theft constitutes a Class 3 Felony, with 4-12 years in prison. Honestly, I don’t care whether he is punished. I care whether we are made whole, and whether he realizes his error and changes his life to become a better person. No sign yet, of that.

We learn some more things. Bob has prior police records in Florida, where he’s from. Incidentally, the records indicate he’s white, after all.

With civil and criminal cases proceeding against him, and with further discovery that Bob fled to Florida (leaving his dog to be temporarily cared for by his neighbor… who is now wondering where he is and hasn’t heard from him in weeks), we thought the case was basically closed. We’d get him somewhere, sooner or later. And, hopefully, we’d get our stolen property returned, or the fiat equivalent.

Rovion
We’d worked to build a new server infrastructure in Bob’s wake, assuming his work in our system to be largely compromised. We set up a new cloud architecture with a company we’ll call CloudCo.

It’s now the week of April 4th, and we were about ready to go live with this new cloud infrastructure. Then all hell breaks loose. Again.

On Thursday April 7th, around midday, we notice a bunch of Ethereum had left the hot wallet on the new infrastructure at CloudCo. The NEW infrastructure. The infrastructure that was not even public yet. At first, we believed our code had done something weird, perhaps sweeping funds to a development server address or similar. Then we noticed a bunch of Bitcoin was also missing. And then Litecoin also.

Thief’s Bitcoin address: 14Kt9i5MdQCKvjX6HS2hEevVgbPhK13SKD

Thief’s Ethereum address: 0xC26B321d50910f2f990EF92A8Effd8EC38aDE8f5

Thief’s Litecoin address: LL9jqgXVqxUbWbWVaJocBcF9Vm8uS3NaTd

And very quickly reality hits you, and that’s what flashback feels like. The horrible sinking feeling sets in immediately, once again. What the fuck happened?

Keys that were not even on publicly known servers had been compromised, somehow. We shut the system down, including our live production site, while we investigated. We didn’t lose as much as the hack a month prior, because we’d be keeping wallets somewhat conservative, but it was still quite a bit. We couldn’t believe it. How could brand new keys, generated with brand new infrastructure, be compromised?

After several hours of fruitless investigation, we decide that one of the most likely explanations is that the cloud company itself was compromised. This has happened before in Bitcoinland. We thought CloudCo was reputable, but who knows? Clouds are very convenient and scalable, but on some level you’re trusting that company with your infrastructure. We decided we had to keep the site down for at least 24 hours, and bust our asses to prepare, yet again, an entirely new infrastructure on an entirely new set of servers.

What was nearly as bad as the money lost was not knowing how it happened. Logs were not done as well as they should have been, so they proved fruitless. Indeed, they had been wiped.

Despite that, we watched the blockchains for the hacked funds. We tracked some to an exchange account. We got profile information of the depositor.

Name: Rovion Vavilov

Email: rovion.vavilov@riseup.net

Address: Chayanova St. 15, Moscow

DOB: Feb 2, 1980

Phone: +7 9625148445

That profile information was probably fake, but I emailed him that night.

From: Erik Voorhees erik@shapeshift.io

To: rovion.vavilov@riseup.net

Subject: ShapeShift Hack…

“Nice job on the hack. How did you do it? -Erik”

Pro Tip: Black hats like to be recognized for their skill, regardless of how immoral their deeds may be. Talk to them calmly, as adults. They may reveal information, or help in some way. It’s weird, but it happens. In any case, I didn’t expect anything to come of my email.

The rest of that night, and into the next day (Friday, the 8th), the team worked feverishly to rebuild everything on new infrastructure, once again, in a wholly clean environment on a wholly separate host.

Now to many, ShapeShift appears to be a simple web service. It’s taken a lot of work by our engineers to keep up that appearance. Behind the scenes, the platform is complex. Over 1,400 direct asset trading pairs, integrations with half a dozen exchange API’s requiring real-time price information on all offered cryptocurrencies, low-latency service API’s to several dozen partners, the monitoring and calculation of constantly changing exchange rates and order book depth in some of the most volatile markets on Earth, and incorporation of what can only be described as alpha-level software in various states of disarray (coin daemons…bleh).

And in Bitcoinland, indeed, and there is no guide book.

Admittedly, as a non-engineer myself, I can only occasionally glimpse the magnificence of what we’re building. I wish I could take credit. To our team reading this, you have engineered an amazing machine and should be very proud of it.

And now here is where the story deepens

Around mid-day on Friday, the hacker responds to my email (remember I had asked him how he did it…)

From: rovion.vavilov@fastmail.com (noted new domain)

To: Erik Voorhees erik@shapeshift.io

Subject: ShapeShift Hack…

“One word: Bob”

That was the entirety of that first email, but we were stunned. For a moment, we thought, “Is Bob the hacker?” Quickly, that notion gave way to the more likely answer: that Bob sold or gave away our information to a hacker, who then exploited it.

Bob betrayed us. He betrayed his privileged position, profiting directly from the destruction of those who trusted him. He stole, lied, ran away, and then after being afforded a period of time long enough to reflect upon his actions, decided to betray us again for a few more scraps in his pathetic bowl. Hackers gonna hack, but it takes a certain variety of bastard to ascend to a trusted position, work face to face with a team, receive a salary and confidence from that team, and then screw them all for barely enough money to buy a Tesla. Oh yeah, and then abandon a dog to starve alone, likely soon to be put down by animal services.

Watch out for these people in your lives. If you suspect them, sever ties quickly.

Anyway, after herculean efforts, we had everything ready by Friday night, 24 hrs later. We launched the site on yet a new provider, who we’ll call HostCo. Despite a couple glitchy bugs, the system was running. We had told the public about the hack and decided to release more details once we studied the compromised environment in more detail later.

Exchange orders started up immediately. We breathed a sigh of relief. I fell asleep around 1am and slept peacefully, exhausted from the ordeal and very proud of the team.

Then it was Saturday 9am, and I start emerging from slumber. My phone rings. It was Greg.

“We were hacked again. Bitcoin and Ethereum taken from the HostCo hot wallets.”

I’m silent on the phone. I’m thinking only, “Is this the fucking apocalypse?!?”

It didn’t seem possible. The hack two days prior didn’t seem possible, and this now was just immensely confusing and depressing. I tell Greg to take the site down again and I’ll call him back in 30 minutes. How the hell are we going to explain this to the community, to our customers… to our investors? How do we even explain it to ourselves?

I get out of bed, not panicked, but just feeling utterly defeated. I take the worst shower of my life. Anger surrounds me… we knew Bob was involved from the hacker’s email, and we knew Bob committed a Class 3 felony against us, which the authorities knew about three weeks ago, and our private investigator had provided all the information needed for an immediate conviction. And now this happens.

As I gather my thoughts, I decide it’s time to call in some professional resources.

Michael Perklin, Head of Security and Investigative Services at Ledger Labs, and chairman of the Steering Committee for the Board of CCSS, is first on my list. He’s in Toronto, and agrees to fly out to meet us that evening. He was on his way to the hospital; he had a toe broken in an event he’d prefer not to discuss. He changes course and heads to the airport. What a champion.

I also chat further with heads of several leading exchanges. None of them like thieves, and are eager to help. Despite its hectic pace and diversity of opinions and interests, this industry comes together when it needs to.

1500 ETH recovered, and exchanges are hunting for more. The thief is probably upset by this… it sucks to be stolen from, after all.

Fireside Chats with the Thief
In parallel to all that, I hear again from the thief via email. I had responded to his “One word: Bob” message by asking if he would provide more info. He mentions that for a price, he may.

“hi” he says.

I arrange to pay him 2 BTC for information.

“I need to know what your relation to bob is” I ask. I tried to avoid pre-empting details.

He replies, “I got information that Bob “hacked” you while I was trying to hack you too. I had some access before Bob hacked you but not enough to get the coins myself.”

“What do you know about Bob hacking us?” I ask

“Inside job. 315 BTC.” he replies. “I talked to Bob after he took the coins, asked him about how I could hack it too. He gave me more information about the infrastructure and some keys.”

I ask, “Why would he give you information and what did he give you?”

Rovion responds, “Because I offered BTC. IP addresses, server roles, users, a working SSH key. Does not work anymore.”

We chat further, and he reveals Bob’s email that he communicated with: m0money@gmail.com.

While I had not seen that email before, it seemed familiar. I thought for a while, and then realized that Bob often substituted 0’s for o’s, including on one of the two keys which he had deleted from the server (the specific key was named something which, if displayed, would give away Bob’s real name). That, and the fact that one of Bob’s common password variations was “m0m0ney.” Our security guy used l33tspeak for his passwords. Real secure.

As clear as it had been that Bob had stolen our funds a few weeks prior, it was now clear that this hacker, Rovion, was giving us information related to Bob that only Bob or those with whom he had actually interacted would know.

Another thought, could this hacker have actually framed Bob from the beginning? Sure, perhaps, but every action of Bob’s back on March 14th points away from that explanation, specifically Bob deleting his own keys right under our nose and then leaving the office, never to return. Other evidence not listed here further counters that theory.

Back to the chat with Rovion… I ask which “working SSH key” he had obtained. “None of your business,” he responds, “but he told me he got it from a coworker’s open laptop.”

Wow. If true, that means Bob, while working at ShapeShift, accessed a coworkers computer and copied a key (or more?), at some point before he stole the funds. Did he premeditate the whole thing, I wonder?

I try to get more information, but Rovion is unforthcoming. His last message…

“Your millions will save you, Erik Voorhees. Goodbye, I will be on email.”

By the early evening, our forensic investigator, Michael Perklin, had arrived. I picked him up from the airport. We had decided to hold off on poking around in our servers until he was there. While the hacker gave a vague sense of how he came upon secret information, we didn’t really know the specifics of the breach. Keys had been changed after Bob’s departure, and while we found one key we hadn’t remembered to change, it only had access to a server that could not have stolen the funds on the preceding Thursday. And again, it wouldn’t at all explain how the Saturday morning theft occurred. Both CloudCo and HostCo had funds stolen off them, despite them being built as entirely new environments with wholly new keys.

Michael asked me to convey to him the whole story of the past month. He proceeded through his investigative protocol, which included the assumption that nobody at the company was trustworthy. It was hard to argue that the team was trustworthy, given the fact that this all started with a rogue employee. It was a depressing feeling.

Many interesting details could be added here about how such forensic work is done, but space is limited and it’s probably unwise to reveal every such method. After a while, we dove into the logs themselves, attacking the Saturday logs first. They were deleted, most of them. How were they deleted? We weren’t sure.

We know now how to prevent that… indeed, the experience we’ve received throughout this incident has been immensely valuable. Though it sounds cliché, if your startup is involved in securing information or servers whatsoever, do yourself a favor and bring in 3rd party professional help very early. We hadn’t needed it at first, because we were small. But growth creeps up on you, and before you know it you are securing significant assets with sub-standard methods.

While much of the logs were gone, we in fact recovered a great portion of them off the “empty” disk space itself using forensic techniques. This was just lucky. Perhaps the Ghost of Satoshi was looking out for us (could have used his help a week ago, of course!)

From the recovered data, we discovered the malware, if that’s the right term. There was a program, written in Go, installed on a crucial server which communicated with coins. This program had its dates changed to appear consistent with the setup of the server, and its filename made to look innocuous. But it was the direct tool by which funds were stolen.

udevd-bridge it was called

We were glad to find it (and yes, the same thing appeared in both server environments, CloudCo and HostCo). However, it still didn’t explain how it was put there. We had a lot of information, but not the whole story.

And we wouldn’t have the whole story for a couple more days. But then the stars aligned.

Out of the blue, the hacker, Rovion, emails me again on Wednesday, April 13th.

From: Rovion Vavilov rovion.vavilov@fastmail.com

To: Erik Voorhees erik@shapeshift.io Subject:

Re: ShapeShift

“Would you be interested in buying the ETH that I currently hold back at a highly discounted rate in exchange for BTC? I’d be willing to trade in small quantities since you have no reason to trust me.”

Yes, it appears the hacker has gotten annoyed that his Ethereum kept getting frozen at exchanges. So he comes back to the store he robbed from, and asks us if we’ll trade for a more liquid asset. We’d be essentially buying back our own Ethereum, and paying him Bitcoin.

Obviously worth it, if we can obtain more information. Since neither of us trust the other, we establish a protocol:

1) We pay 2 BTC to get the conversation started

2) Rovion gives us half the relevant information

3) We exchange, in increments of 250, 2000 ETH for BTC at 0.02 BTC/ETH rate

4) Rovion gives us second half of the relevant information

5) We exchange, in the same increments, the remaining 2500 ETH for BTC at same rate

6) We cease communication (this last one was Rovion’s suggestion)

He asks us to send the BTC to his already known BTC address: 14Kt9i5MdQCKvjX6HS2hEevVgbPhK13SKD

After the initial 2 BTC payment, Rovion begins with description of April 7th hack:

“We contacted Bob. He gave us the ShapeShift core source code, core server IP address, an SSH key, and [redacted]. I logged in to the core server with the SSH key provided, installed a backdoor and took the coins since the core server had SSH access to the coins server.”

“What’s the fingerprint of the SSH key mentioned above?” I ask

“9c:3f:4b:ad:d6:43:ec:9a:55:de:b9:0b:d8:f5:0a:cb”

We see that it’s Greg’s key, newly created for the CloudCo environment. It was not even in existence until more than a week after Bob had stolen the funds in March and disappeared. How on Earth did this hacker get a new key, post Bob?

I also ask about the “[redacted]” mentioned but Rovion says that is part of the second batch of information. We proceed with the incremental exchange of the second batch of funds.

Then Rovion says,

“[redacted] was access to an RDP installed on a coworker’s machine by Bob. That’s how I hacked you the second time.”

Wow, now it’s starting to come together, each revelation peeling back a layer of Bob’s treachery. Bob had installed an RDP (remote desktop protocol – basically a screen viewer or controller) on Greg’s computer. And perhaps on others, we must assume.

Then Rovion shares via pastebin an email from Bob (the info he purchased):

> “hi,
>
> i received your 50 bitcoin. gh source and ssh priv key as attachments”
>
> core ip: XX.XX.XX.XX
>
> router for forwarding: XX.XX.XX.XX:XXXX
>
> admin:[redacted password]
>
> rdp internal ip: XX.XX.XX.XX
>
> acadmin:pass
>
> thanks for your business.
>
> [2 attachments listed]

(specific IP’s redacted by us)

And there it is. Bob sold information on the production servers, access to ShapeShift’s internal network, part of ShapeShift’s source code, and access to an RDP client he had installed on a co-worker’s computer, to Rovion, for 50 Bitcoin. The IP and internal router info checked out.

This explained almost everything. With access to Greg’s computer (and perhaps others), via RDP, the new server environments could be witnessed and the new SSH keys could be used. It wasn’t the cloud service provider’s fault, it was our own.

We had changed almost everything, but hadn’t scrapped our personal computers used while Bob had been part of the team. Would that have been the paranoid thing to do? Yes. Would it have been the right thing to do?

Clearly.

And one of the last things Rovion said before we ended the discussion,

> “Even though I said cease communication, can you still send me an email when Bob gets sued/whatever it is you’re going to do? I feel it’s really shitty to steal from your own employer.”

# Cleaning Up a Mess

We imagine this information will assist in demonstrating criminal intent on the part of Bob. This was not a spur-of-the-moment taking, but an orchestrated treachery. I’ve lost count of the number of felonies involved at this point.

We also know that while the story from Rovion checks out, it may well not be the full story. We have to assume other details are relevant to the case, and to our infrastructure. This is why ShapeShift has been offline for longer than any of us would have liked. We are being very careful, and very paranoid.

Nonetheless, I have been immensely proud of my team. Working in a startup, in the Bitcoin industry, is stressful enough, and then to deal with a series of layered betrayals like this and all the damage (financially, technically, psychologically) it causes… that is hard. You guys have done an amazing job and I am immensely encouraged seeing the team’s cohesion and fortitude.

It didn’t help that we had just brought on four new employees in the very week of the two incidents (nearly doubling our development staff). They were thrown into the fray without mercy, and they’ve been incredible.

# ShapeShift Users Not Affected

To survive in Bitcoin, one has to be an optimist. While the betrayal and loss and clean up effort has been horribly taxing, there are some silver linings.

First, no person or organization is perfect. We learned some of our own vulnerabilities, and our own mistakes. We are correcting them, and improving upon them wherever possible. Such improvement doesn’t come cheap, but the ShapeShift of today is made better than the ShapeShift of yesterday. The steel is tempered, the machine refined. Though no single organization can ultimately achieve it, we try to approach anti-fragility, and exemplify it as an ideal in our work.

Second, no customers lost money throughout multiple hacks orchestrated even by an insider. Through decentralization, through code, through innovation, through structure… consumer protection by design is one of this industry’s most important contributions to society – something that a century of legacy banking has failed to achieve, as noted by Satoshi’s infamous line in the Genesis Block.

ShapeShift will always work to develop upon this platform of consumer protection. Many others in this community are doing the same along different avenues. Thank you for the tools you are building, and the work you have done. And indeed, there is still much to do.

To our customers, I would like to personally apologize for our downtime. While we can ensure your funds are not at risk, I know many rely on our service, and it has been unavailable. Redundancy, even in the face of disaster, will be one of our primary development goals going forward.

Further, thank you sincerely to those in the community who reached out and offered all manner of support, and to our investors who were immensely kind and understanding.

And finally, as with all intense episodes one endures, we must appreciate the room and opportunity for growth, for experience, and for one of life’s most precious luxuries, reflection.

Never a dull day in Bitcoinland

---

Erik Voorhees
CEO ShapeShift.io
Apr 19, 2016

---

- bounty: true
- amt: 30
- signedBy: 0xef4fd55584434903aa6fc9baa61eacdde5355da0
- hash: 0x0000
{.is-hidden}
