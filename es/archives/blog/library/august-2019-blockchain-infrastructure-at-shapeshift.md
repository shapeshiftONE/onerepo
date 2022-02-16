---
title: Infraestructura Blockchain en ShapeShift
description: Aprenda cómo el equipo de ingeniería de ShapeShift estructura los nodos de blockchain.
published: true
date: 2022-02-16T15:33:46.795Z
tags: biblioteca
editor: markdown
dateCreated: 2022-02-16T15:33:46.795Z
---

# Infraestructura de Blockchain en ShapeShift

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9fbae5efc62b1120b46150_1_F0R4y3MkSpLjbo0bRB10Yw%20(1).png)

Los nodos de blockchains (demonios de monedas) son programas que validan completamente transacciones y bloques. Son las puertas de entrada a las criptomonedas que admitimos. [**ShapeShift**](http://shapeshift.com/) depende de los nodos de blockchain para recibir y transmitir datos de transacciones, lo que los hace críticos para nuestras operaciones comerciales.

Arrear cientos de nodos es un punto doloroso con el que muchos en la industria tienen que lidiar. Para escalar las operaciones para admitir más de un par de cientos de transacciones, estos nodos de monedas deben ejecutarse en paralelo para reducir el estrés que se les impone. Algunos nodos de blockchain no son confiables, tienen severas limitaciones de rendimiento y, a menudo, carecen de la documentación adecuada.

Además de todo, la mayoría de los nodos de blockchain requieren grandes cantidades de capacidad de almacenamiento para almacenar el historial de transacciones. Algunos de estos volúmenes de datos pueden llegar a tener varios Terabytes de tamaño.

Buscamos crear un marco que administrara la construcción, implementación y monitoreo de nodos de blockchain. Este marco tendría que cumplir varios requisitos:

* Construcciones automatizadas
* 100% contenerización
* Múltiples versiones implementadas simultáneamente
* Altamente disponible/resistente (multicentro de datos)
* Escalable (establecer nuevos nodos rápidamente)

Después de repetir la frase "Coin Daemon Container" demasiadas veces, decidimos llamar al framework Cointainers.

## Herramientas de plataforma

Para construir la plataforma Cointainers, necesitábamos herramientas que nos permitieran iterar rápidamente en construcciones e implementaciones. Docker fue una elección fácil en este sentido, ya que nos permitió crear compilaciones reproducibles en todas las plataformas con muy poca configuración.

Para ejecutar las compilaciones de Docker dentro de los sistemas de producción, elegimos Kubernetes, que tiene soporte para [aplicaciones stateful](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/) y [complementos de almacenamiento para todas las nubes principales.<br/> ](https://kubernetes.io/docs/concepts/storage/)

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9fbb02efc62b44b7b47b60_1*FHxwJvmHucRhWCvEIUXfKw.png)

También necesitábamos que todas las compilaciones y la infraestructura fueran reproducibles, por lo que esto significaba incorporar algún tipo de infraestructura como código (IaC) en la mezcla. [Terraform](https://www.terraform.io/) suele ser la solución general para esto, es el marco IaC más grande y más utilizado. Hashicorp (la compañía detrás de Terraform) también anunció recientemente [soporte de primera clase para Kubernetes dentro de Terraform](https://www.hashicorp.com/blog/first-class-kubernetes-support-for-hashicorp-products).

Sin embargo, Terraform requiere aprender un nuevo lenguaje, el [HCL DSL](https://github.com/hashicorp/hcl). Usarlo aumentaría la barrera de entrada para que nuestros ingenieros aprendan y trabajen en Cointainers. Ahí es donde entra Pulumi.

Pulumi es un marco de infraestructura como código muy similar a Terraform, mejor descrito por la empresa en su [página de comparación](https://www.pulumi.com/docs/reference/vs/terraform/):

*Pulumi es como Terraform, en el sentido de que crea, implementa y administra la infraestructura como código en cualquier nube. Sin embargo, a diferencia de Terraform, utilizará herramientas y lenguajes familiares de propósito general para hacerlo. Al igual que Terraform, Pulumi es* [*código abierto en GitHub*](https://github.com/pulumi/pulumi) *y es* [*de uso gratuito*](https://www.pulumi.com/docs/quickstart/)*.*

Al usar Pulumi, podemos aprovechar los lenguajes de alto nivel con los que la mayoría de nuestros ingenieros ya se sienten cómodos. También nos permite ser más expresivos con nuestro IaC al evitar las limitaciones del lenguaje de configuración Hashicorp (HCL). Esto también se describe en la comparación.

*Debido al uso de lenguajes reales, obtiene construcciones familiares como bucles for, funciones y clases. Esto mejora significativamente la capacidad de reducir la repetición y hacer cumplir las mejores prácticas. En lugar de crear un nuevo ecosistema de módulos y compartir, Pulumi le permite aprovechar las herramientas y técnicas de administración de paquetes existentes.*

## Construir

Un cointainer comienza con una imagen de Docker. En el interior, colocamos el binario del demonio de monedas (software de nodo de cadena de bloques). También construimos un segundo contenedor (sidecar), que se ejecuta junto con el software del nodo para monitorearlo.<br/> 

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9fbb03533c77038410f85b_1*z9XydSqnB12ApvEF3Gt8fw.png)

Dado que necesitamos admitir varias versiones, nuestro proceso de compilación se parece a esto:

1. Lea la lista de nodos de monedas que necesitamos construir (por ejemplo, Bitcoin, Dogecoin, Ethereum, etc.)
2. Descargue las últimas N* versiones de coin daemon (por ejemplo, bitcoin-0.18.0, bitcoin-1.17.1, bitcoin-0.17.0.1, etc.)
3. Cree contenedores Docker para contener software de daemon de monedas
4. Cree un contenedor Docker para nodos de monitoreo
5. Prueba de integración de todos los contenedores
6. Empuje los contenedores al repositorio de imágenes

** Personalizable por moneda*

Utilizando el [@pulumi/docker](https://github.com/pulumi/pulumi-docker) podemos crear repositorios de contenedores de Docker, crear nuestras imágenes de Docker y enviarlas a los repositorios, todo en un solo flujo de trabajo.<br/> 

$ make deploy<br/><br/>Previewing deploy<br/><br/>    |   Type                         | Name           | Plan<br/>--------------------------------------------------------------<br/> +   ├─ cointainer:Deploys             ethereum         create<br/> +   │  ├─ container:Deploy            ethereum:2.4.5   create<br/> +   │  |  ├─ container:StatefulSet    ethereum:2.4.5   create<br/> +   │  |  ├─ container:AutoScaler     ethereum:2.4.5   create<br/> +   │  |  ├─ container:IngressRule    ethereum:2.4.5   create<br/> +   │  |  ├─ container:MonitorAlert   ethereum:2.4.5   create<br/> +   │  └─ container:Deploy            ethereum:2.6.5   create<br/> +   │     ├─ container:StatefulSet    ethereum:2.6.5   create<br/> +   │     ├─ container:AutoScaler     ethereum:2.6.5   create<br/> +   │     ├─ container:IngressRule    ethereum:2.6.5   create<br/> +   │     ├─ container:MonitorAlert   ethereum:2.6.5   createResources:<br/>    + 8 resources to create<br/><br/>Do you want to apply to changes?<br/>  yes<br/>> no<br/>  details<br/> 

## Desplegar

También usamos Pulumi dentro de nuestro proceso de implementación para crear los recursos necesarios dentro de nuestros clústeres de Kubernetes. El [@pulumi/kubernetes](https://github.com/pulumi/pulumi-kubernetes) El módulo nos permite crear IngressRules, StatefulSets y HorizontalPodAutoscalers.

Para que nuestros desarrolladores siempre tengan las versiones más recientes de los nodos disponibles para trabajar, hemos configurado una automatización que busca nuevas versiones y las implementa de forma recurrente.

Nuestro flujo de trabajo de implementación crea nuestros recursos y monitoreo, todo a la vez:

1. Encuentra todas las versiones de los nodos que construimos anteriormente
2. Implemente las versiones que no están en el entorno
3. Cree monitoreo y alertas para cada versión implementada<br/> 

$ make deploy

Previewing deploy   

 |   Type                         | Name           | Plan<br/>--------------------------------------------------------------<br/> +   ├─ cointainer:Deploys             ethereum         create<br/> +   │  ├─ container:Deploy            ethereum:2.4.5   create<br/> +   │  |  ├─ container:StatefulSet    ethereum:2.4.5   create<br/> +   │  |  ├─ container:AutoScaler     ethereum:2.4.5   create<br/> +   │  |  ├─ container:IngressRule    ethereum:2.4.5   create<br/> +   │  |  ├─ container:MonitorAlert   ethereum:2.4.5   create<br/> +   │  └─ container:Deploy            ethereum:2.6.5   create<br/> +   │     ├─ container:StatefulSet    ethereum:2.6.5   create<br/> +   │     ├─ container:AutoScaler     ethereum:2.6.5   create<br/> +   │     ├─ container:IngressRule    ethereum:2.6.5   create<br/> +   │     ├─ container:MonitorAlert   ethereum:2.6.5   createResources:<br/>    + 8 resources to create<br/><br/>Do you want to apply to changes?<br/>  yes<br/>> no<br/>  details<br/> 

Más información sobre el uso de Pulumi con Kubernetes [aqui](https://www.pulumi.com/blog/pulumi-a-better-way-to-kubernetes/)

## Arquitectura

Durante la puesta en marcha de cada nodo, comprobamos si el volumen de datos tiene una copia de la cadena de bloques. Si se trata de una réplica de un nodo nuevo y no tiene bloques, o si la cadena está demasiado atrasada, descargamos una copia de seguridad para evitar tener que esperar a que el nodo se sincronice manualmente (lo que puede tardar semanas en completarse).<br/> 

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9fbb0354b6e3785920e526_1*zbFYJNWGRzpdYp8GSPu8Qg.png)

<br/>Después de que se descarga la copia de seguridad y se inicia el software del nodo, nuestros sistemas esperan hasta que esté 100 % sincronizado antes de que esté disponible.

Nuestro contenedor de monitoreo verifica la altura del bloque del nodo con exploradores de bloques externos, y también si el nodo informa que todavía está sincronizando bloques. Una vez que el nodo está completamente sincronizado y la altura de su bloque es superior o igual al explorador de bloques, lo colocamos detrás del equilibrador de carga.

Si el nodo se atrasa, lo sacamos del balanceador de carga y esperamos a que se recupere antes de volver a ponerlo en servicio para los clientes.

<br/> 

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9fbb03efc62b63e2b47b93_1*00OwEzzfIBPJliOyj3wMjA.png)

El tráfico solo se dirige a nodos en buen estado/sincronizados<br/>Mantenemos un mínimo de 3 nodos para cada versión de moneda en varios centros de datos: uno reservado para copias de seguridad y dos para mantener la confiabilidad. A medida que aumenta la carga en los nodos de monedas, nuestros sistemas lanzan automáticamente más para satisfacer la demanda.

En un nivel superior, servimos múltiples versiones de los nodos para nuestras aplicaciones. Esto permite que nuestros equipos de desarrollo cambien de versión en cualquier momento, lo que les da la capacidad de retroceder inmediatamente si es necesario.<br/> 

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9fbb03df8913769e880eb2_1*3tI4eIfns6iJEmvzUO6q9Q.png)

Múltiples versiones de Bitcoin<br/>Después de que todas nuestras aplicaciones migran de la versión anterior a la nueva, la retiramos y conservamos las restantes de las que aún dependen nuestras aplicaciones.<br/> 

## Supervisión

Con los monitores creados en la implementación, nuestros sistemas verifican el estado de los Cointainers cada 15 segundos para asegurarse de que estén accesibles y respondan con datos válidos. También monitoreamos la cantidad de réplicas de nodos que ejecutamos para cada versión de moneda. Si alguna versión de moneda tiene menos de 2 nodos activos, nuestros sistemas de monitoreo hacen sonar alarmas que notifican a nuestros ingenieros y equipos de servicios para miembros.

Si estás interesado en trabajar en proyectos como Cointainers, consulta nuestra página  [**Carreras**](http://shapeshift.com/careers) . Estamos buscando: ingenieros de software, vicepresidente de marketing y unicornios 🦄!<br/> 

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9fbb037e6909591b3c32e2_1*0CtbPVcRkofblk3ZXkUuXw.png)

 

---

> Este documento fue publicado originalmente el 13 de agosto de 2019 por Azamat Mukhiddinov y puede haber sido ligeramente modificado para su traducción por parte del flujo de trabajo de Información y globalización para un proyecto de archivo en curso.
>
> El artículo original se puede encontrar [aqui](https://shapeshift.com/library/blockchain-infrastructure-at-shapeshift).
{.is-success}

---

- bounty: true
- amt: 61
- signedBy: 0xFAc9dD5194098461B627554347f83D5431Fb30e2
- hash: 
{.is-hidden}