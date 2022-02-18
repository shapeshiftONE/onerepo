---
title: Profundizando en las soluciones de blockchain de capa 2
description: Obtenga información sobre la tecnología que se esfuerza por resolver los problemas de escalado de las criptomonedas.
published: true
date: 2022-02-18T15:02:32.475Z
tags: 
editor: markdown
dateCreated: 2022-02-18T15:02:32.475Z
---

# Profundizando en las soluciones blockchain de capa 2

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9f294424536954b69806bd_1_L8GpHTyR1-JRyyo31JzZeQ.png)

Los geeks de **Blockchain** y los entusiastas de las criptomonedas a menudo usan los términos capa 2 y red relámpago indistintamente cuando se refieren a soluciones de escalabilidad de blockchain. La verdad es que estos términos ***no*** son intercambiables.<br/> 

## Más allá de Bitcoin: escalar con la capa 2

El término **capa 2** se refiere a una segunda capa de codificación que existe sobre la estructura de codificación original de una cadena de bloques. Esto permite que una cadena de bloques descentralizada evolucione y se ocupe de un puñado de problemas como:

* Escalamiento de volumen y velocidad de pago
* Escalar la creación y ejecución de contratos inteligentes
* Realización de cálculos fuera de la cadena

La actualización de Lightning Network de Bitcoin es específica para escalar pagos, pero es solo uno de los proyectos dedicados a resolver este problema. Para comprender mejor las soluciones de capa 2, debe mirar más allá de Bitcoin a las diferentes blockchain que utilizan esta tecnología.<br/>

## **¿Por qué escalar es un problema?**

La escalabilidad simplemente se refiere a la capacidad de una red para manejar una gran cantidad de transacciones por segundo. Aumentar la cantidad de transacciones que puede manejar una blockchain se considera fundamentalmente uno de los mayores obstáculos que enfrentan las criptomonedas y las plataformas de pago descentralizadas. Se considera que la escalabilidad es el mayor obstáculo entre la criptografía y la adopción masiva.

Las tarjetas de crédito como Visa y Mastercard pueden manejar hasta 47 000 transacciones por segundo en un momento dado. De hecho, se estima que durante el infame global de China [Evento de compras del Día del Soltero](https://techcrunch.com/2018/11/09/alibaba-singles-day-11-festival/), estas compañías de tarjetas de crédito pueden procesar cerca de 100.000 transacciones por segundo.

En comparación, Bitcoin realiza aproximadamente [4.6 transacciones](https://hackernoon.com/the-blockchain-scalability-problem-the-race-for-visa-like-transaction-speed-5cce48f9d44) por segundo. La razón de esta gran discrepancia es que Visa y MasterCard son parte del sistema bancario centralizado, que existe desde hace más de 100 años. Las tecnologías descentralizadas deben enfrentarse siempre a lo que se conoce como el 'triángulo imposible'.

**El triángulo imposible** se refiere a los tres principios que le dan a una cadena de bloques su utilidad:

1. Seguridad
2. Escalabilidad
3. Descentralización

En este momento, no hay una sola criptomoneda en una cadena de bloques completamente pública que domine las tres anteriores. Ripple maneja actualmente [1,500 transacciones por segundo](https://www.ripple.com/xrp/). La cadena de bloques EOS tiene un rendimiento de casi [4000 transacciones por segundo](https://thenextweb.com/hardfork/2018/11/01/eos-blockchain-benchmark/). Es seguro decir que hasta este punto, el triángulo sigue resultando imposible de dominar. Esta es la razón por la que los enfoques de capa 2 se conocen más comúnmente como una solución de escalado.<br/> 

## **La Red Lightning**

La [Red Lightning](https://medium.com/shapeshift-stories/ride-the-lightning-ec6b8d3a086f) permite transacciones más pequeñas a través de canales de pago. Abrir un canal de pago es excelente para transacciones más pequeñas y recurrentes, como comprar café todos los días. Un gran amante del café podría comprar tres tazas por día, lo que equivale a 21 transacciones por semana. Lightning Network permite a los usuarios crear un canal de pago que confirma estas 21 transacciones, el saldo inicial y el saldo final de todas estas transacciones en la cadena de bloques.

Lightning Network es necesaria porque la [transacción promedio de bitcoin](https://hackernoon.com/2019-blockchain-layer-2-solution-review-d00385147396#1cee) vale alrededor de $50, con una tarifa de alrededor de $20. Eso hace que mantener pequeñas transacciones "en cadena" sea poco práctico. Hacer transacciones fuera de la cadena reduce la carga en la blockchain. Lightning Network también hace que se deba usar una dirección de firma múltiple; lo que significa que ninguna de las dos partes puede manipularse entre sí para completar una transacción. La desventaja es que la red Lightning no se puede usar fuera de línea. Tampoco se puede usar para grandes cantidades y permite que los nodos se conviertan potencialmente en grandes centros de pago que contienen grandes sumas de valor.

[*>>> Lea más sobre Lightning Network de Bitcoin <<<*](https://medium.com/shapeshift-stories/ride-the-lightning-ec6b8d3a086f)
## Canales de pago

Desde el punto de vista de la codificación, un canal de pago es realmente solo una iteración de una solución de capa 2 de canal estatal. Una implementación de canal estatal:

* Permite bloquear parte del estado de la blockchain mediante direcciones de firmas múltiples o contratos inteligentes
* Permite a los participantes actualizar el estado de esa parte de la cadena
* Envía el estado actualizado a la blockchain

Este enfoque de canal estatal se entiende más fácilmente en un intercambio monetario; el intercambio puede ser cualquier cosa. Podría usarse para rastrear cualquier otro tipo de cambio en el estado de una cadena de bloques, ya sea que la transacción esté relacionada con dinero, propiedad intelectual, identificación del gobierno, etc.<br/> 

## **Soluciones de escalado de Ethereum**

Ethereum pretende ser la supercomputadora descentralizada del mundo. Su existencia brinda a los desarrolladores una plataforma para crear y lanzar aplicaciones descentralizadas que todos pueden usar. Eso es lo que lo hace diferente de Bitcoin. Lo que hace que las dos criptomonedas sean similares es que ambas usan el algoritmo de consenso [prueba de trabajo] (https://medium.com/shapeshift-stories/exploring-consensus-algorithms-8403c301b2ff).

## Casper

Casper es la actualización que llevará a Ethereum al enfoque de prueba de participación posiblemente más eficiente. Los algoritmos de prueba de participación hacen que la validación de transacciones sea más eficiente, tanto técnicamente hablando como en términos de costos de energía.

## Plasma

Cuando un algoritmo de consenso de prueba de participación valida las transacciones, la actualización de Plasma aplica la segunda capa de contratos inteligentes a la blockchain. Ayudará a reemplazar las granjas de servidores con una red de igual a igual que hace que la ejecución de aplicaciones descentralizadas sea más escalable. Como explica el [documento técnico de Plasma] (https://plasma.io/plasma-deprecated.pdf), las transacciones pueden ocurrir de forma privada entre usuarios en cadenas privadas y luego representarse en la cadena pública.
## fragmentación

Sharding complementará a Casper y Plasma para hacer que la blockchain de Ethereum sea más escalable. Permite que [se dividan los datos](https://www.trustnodes.com/2018/05/01/sharding-proof-concept-launches-casper-32-staking-eth-requirements-coming-says-vitalik- buterin) y alojado en varios servidores. Significa que el libro público se fragmenta, pero todas las transacciones aún se contabilizarán.

## Transacciones de cadena lateral y fuera de cadena

Ahora conoce dos de los enfoques más populares para escalar pagos y contratos inteligentes. Hay otras dos soluciones notables de capa 2 para explorar.

## Cadena lateral

Una cadena lateral es una blockchain separada que se une a una cadena principal mediante una vinculación bidireccional, que permite intercambiar activos entre sí a una tasa fija. Las cadenas laterales se pueden usar para todo tipo de activos digitales y necesitan sus propios mineros para permanecer seguros. Los proyectos que usan cadenas laterales de manera efectiva incluyen [OmiseGO](https://omisego.co/), [POA Network](https://poa.network/) y [Alacris](https://alacris.io/).

## **Fuera de la cadena**

Las transacciones fuera de la cadena ocurren completamente fuera de una blockchain. Esto puede suceder a través de un acuerdo de transferencia entre las dos partes, a través de un tercero garante (similar a lo que hace Paypal en el mundo fiduciario) o utilizando un mecanismo basado en cupones. Las transacciones fuera de la cadena pueden ocurrir instantáneamente sin tarifas y con más anonimato. Los proyectos que implementan un enfoque fuera de la cadena incluyen [Provable](https://provable.xyz/), [AlphaWallet](https://alphawallet.com/) y [Transmute](https://www.transmute.industries /).

## Pruebas de Cero Conocimiento

¿Sabía que los fundamentos criptográficos que permiten la privacidad en Zcash también se pueden aprovechar para aumentar la escalabilidad? Este enfoque prometedor de capa 2 se está construyendo actualmente en Ethereum, utilizando tanto STARKS como SNARKS (los dos tipos principales de pruebas de conocimiento cero).

Del lado de STARKS, [STARKWARE](https://starkware.co/) de Israel está creando una solución innovadora que puede procesar por lotes miles de transacciones fuera de la cadena sin necesidad de una configuración confiable. Además, esté atento a [Matter Labs](https://matter-labs.io/) y sus "roll-ups" basados en SNARK.

Aunque estas soluciones están lejos de ser perfectas, existe el potencial para llevar la tecnología blockchain al siguiente nivel. Con avances de escala como las soluciones de capa 2, la misión de llevar la adopción generalizada de criptografía parece estar en el horizonte.<br/> 


---

> Este documento fue publicado originalmente el 17 de octubre de 2019 por el equipo de ShapeShift y es posible que el flujo de trabajo de Información y globalización lo haya modificado ligeramente para traducirlo para un proyecto de archivo en curso.
>
> El artículo original puede encontrarse [aquí](https://shapeshift.com/library/digging-into-layer-2-blockchain-solutions).
{.is-success}

---

- bounty: true
- amt: 54
- signedBy: 0xFAc9dD5194098461B627554347f83D5431Fb30e2
- hash: 
{.is-hidden}