---
title: Desbloqueando los Misterios de las Claves Privadas
description: Las claves privadas son de vital importancia en la industria de la criptografía. Aprende más.
published: true
date: 2022-03-11T14:55:52.657Z
tags: 
editor: markdown
dateCreated: 2022-03-11T14:55:52.657Z
---

# Desbloqueando los Misterios de las Claves Privadas

## ***Primera parte de una serie de tres partes***

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/60410f04b90eef50bdcef5fb_Paper.Port_is_-_Private_Keys.4.png)

## Claves privadas: una descripción general

En muchos sentidos, poseer una criptomoneda se reduce simplemente a tener una clave privada. A diferencia del mundo "real", donde poseer una propiedad física generalmente implica poseer una escritura a su nombre o tener un recibo de venta, **poseer** **es equivalente a saber en el mundo criptográfico.** En términos más simples , conocer una clave privada es equivalente a poseer activos criptográficos, ya que las claves privadas son las que le permiten autorizar transacciones con ellas.

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/604110379bf86942b436399f_Owning.png)

*La afirmación "el conocimiento es poder" nunca ha sido tan cierta como en criptografía.*<br/><br/>

En el mundo real, las transacciones generalmente se autorizan con su firma. Sin embargo, en el mundo de las criptomonedas, solo las **claves privadas** pueden autorizarlas, criptográficamente, otorgando acceso a los fondos**.** Aunque cualquiera puede generar una transacción que involucre sus activos criptográficos, solo la persona en posesión de la clave privada puede hacerlo. firmar, y así validar, la transacción.<br/>

> *Aunque las firmas falsas son un problema en el mundo real, el mundo criptográfico está protegido por su naturaleza criptográfica subyacente. A día de hoy, ningún truco conocido permite que alguien firme transacciones en sus activos sin su clave.*

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/604110c6415c80a0e6b91c39_Access.png)

*La poderosa frase, “no sus llaves, no sus monedas” proviene del hecho de que al tener una clave privada, cualquier persona puede firmar cualquier transacción sobre estos activos y así transferirlos o moverlos a su antojo (lo que hace que la posesión exclusiva de ellos sea importante) .*<br/>

## ¿Qué son las claves privadas y cómo se generan?

Las claves privadas son números dentro de un rango específico, generalmente muy grande. Desde una perspectiva matemática, una clave privada es solo un **número entero positivo aleatorio**. Sin embargo, una descripción más técnica y precisa sería: *Una clave privada es un número aleatorio criptográficamente fuerte que se ha obtenido usando un generador de números aleatorios* *dado un rango positivo definido.*

La mayoría de las veces, las computadoras usan **generadores de números pseudoaleatorios (PRNG)** para generar estos números enteros positivos aleatorios. (Los verdaderos generadores de números aleatorios son difíciles de conseguir; estos generadores a menudo requieren hardware especializado y utilizan fuentes físicas como el ruido térmico en los circuitos eléctricos o la sincronización precisa de los clics del contador Geiger). Los PRNG son funciones criptográficamente fuertes sembradas con un valor que tiene suficiente **entropía**. La entropía es un concepto complejo, pero su objetivo es simple: proporcionar imprevisibilidad a las funciones. Mediante el uso de fuentes de entropía seguras, los PRNG pueden crear números que es muy poco probable que no sean aleatorios (dentro de un rango aceptable dado).
<br/>

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/604111422a65fc3b152c1bbf_Entropy.png)

*“/dev/urandom” en Linux o “rand\_s” en Microsoft Windows son fuentes de entropía comúnmente utilizadas para PRNG para la generación segura de números aleatorios. En este diagrama, el término "rango" se usa vagamente para referirse tanto al concepto matemático de rango como al tamaño de bytes que se le da a una computadora para generar un número aleatorio.*<br/><br/>

El rango dado a un PRNG para crear de forma segura una clave privada válida de Ethereum o Bitcoin es **2^256–1** (imagine un candado de combinación de los números 0–9, que tiene 78 dígitos). Debido al tamaño de este rango, la probabilidad de generar dos claves privadas con el mismo número es despreciable. El conjunto de enteros del que se selecciona su clave es un [número masivo](https://www.wolframalpha.com/input/?i=2%5E256): es ** aproximadamente el mismo que el número total de átomos visibles En el universo**.

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/604113247ce66b0a06d760cc_Range.png)

*El rango de 2^256–1 ha sido definido tanto por Bitcoin como por Ethereum, y funciona debido a las estrategias matemáticas que utilizan ambas cadenas de bloques para crear claves públicas. Por ejemplo, Ethereum utiliza curvas elípticas (particularmente SECP-256k1) para generar su clave pública. En su original* [*papel amarillo*](http://gavwood.com/paper.pdf)*, el Dr. Davin Wood definió una clave privada como un número entero positivo seleccionado al azar (representado como una matriz de bytes de longitud 32 en un forma big-endian) en el rango [1, secp256k1n–1]. Para todas las definiciones formales, consulte el documento amarillo actual.*<br/>

## Claves públicas, direcciones y su relación con las claves privadas

Dado que las claves privadas están destinadas a ser guardadas. . . bien . . . privado, necesitamos un mecanismo diferente para permitir que otras personas encuentren nuestros activos y que nosotros encontremos los suyos. Como resultado, todas las cadenas de bloques utilizan el concepto de **direcciones**: números únicos derivados de su clave privada. Estas direcciones son la ubicación de sus activos criptográficos y se pueden compartir con quien necesite conocer el saldo de sus activos criptográficos (si así lo desea).

Se crea una dirección de cadena de bloques utilizando su **clave pública** para asegurarse de que usted es el propietario de la dirección en cuestión. A su vez, esta clave pública se genera a partir de su clave privada. Este proceso es **unidireccional**, lo que significa que puede usar una clave privada para crear una cuenta, pero no una cuenta para adivinar una clave privada.

> *Las claves privadas pueden derivar claves públicas, y las claves públicas pueden derivar direcciones de blockchain. Sin embargo, las direcciones de blockchain no se pueden usar para derivar sus claves públicas, y las claves públicas no se pueden usar para derivar sus claves privadas.*

Este proceso unidireccional se realiza a través de **funciones de trampilla criptográfica**. Una función trampilla es una función unidireccional que solo puede generar su valor en función de una entrada específica y no se puede usar para derivar la entrada original de ella. Es como saber cómo hornear un pastel y tener una idea aproximada de lo que hay en un pastel; sin embargo, es imposible saber los ingredientes exactos de un pastel específico solo con probarlo.

Dependiendo del ecosistema de la cadena de bloques, estas funciones unidireccionales varían. Por ejemplo, los sistemas de cadena de bloques más populares utilizan construcciones algebraicas basadas en curvas elípticas para generar sus claves públicas. Independientemente de estas características, el resultado es siempre **determinista**: una clave pública es única para su correspondiente clave privada, y la clave privada siempre genera la misma clave pública.<br/><br/>

<br/>

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/604113a0b5a6cc67e23d3750_Public%20keys.png)

*Aunque las cadenas de bloques populares como Bitcoin o Ethereum usan un punto generador fijo de la curva elíptica secp256k1 sobre ECDSA para multiplicar la clave privada para obtener su clave pública, otros proyectos de cadenas de bloques usan estrategias diferentes. Por ejemplo, Monero usa Curve25519 sobre EdDSA, mientras que las cadenas Polkadot y Substrate usan Ed25519 sobre sr25519. Todos ellos generan una clave pública basada en una clave privada dada con un rango de 2^256-1.

Las direcciones de cadena de bloques también usan funciones unidireccionales, llamadas [funciones hash](https://en.wikipedia.org/wiki/Hash_function). Las direcciones de Bitcoin y Ethereum se crean a partir de una o más **funciones de hashing criptográficamente sólidas** sobre su clave pública, además de matemáticas específicas que dependen de la cadena de bloques en particular. grado en que su dirección de cadena de bloques es única para su clave pública y, por lo tanto, para su clave privada.

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/604113ed9bbe7adeb9daed5b_Accounts.png)

*Una cuenta de Ethereum es el hash Keccak-256 de una clave pública además de tomar los 20 bytes más a la derecha de dicho cálculo. Las claves de Bitcoin usan SHA-256 y RIPEMD-160, mientras que Polkadot y ZCash usan Blake2b. Todos estos hashes son resistentes a colisiones, lo que reduce la posibilidad de generar una sola cuenta a partir de dos claves públicas y garantiza que la única forma en que se puede regenerar una cuenta a partir de una entrada es a través de una fuerza bruta económicamente ineficiente. No hay garantías de que estas funciones hash no se rompan, pero a partir de hoy, ninguna función hash conocida utilizada en ninguna cadena de bloques ha sido rota.*<br/> <br/>

## El lenguaje universal de las matemáticas guarda nuestros secretos

La criptografía y las matemáticas detrás de las claves privadas son la razón por la que nuestros activos criptográficos están seguros, siempre y cuando mantengamos nuestras claves seguras. A partir de hoy, es imposible encontrar y aplicar fuerza bruta a cualquier dirección de cadena de bloques conectada a sus claves privadas debido al hecho de que costaría [más energía de la que almacena el sol](https://support.mycrypto.com/staying-safe/ethereum-dos-personas-misma-clave-privada). <br/>

En nuestro próximo blog, veremos los ecosistemas populares de blockchain y algunas de las matemáticas detrás de la generación de claves públicas. Le proporcionaremos algunos ejemplos de código para que intente calcular las claves del proceso que describe cada cadena de bloques y use las bibliotecas existentes que facilitan el proceso de generación. ¡Estén atentos!<br/>

---

> Este documento fue publicado originalmente el 2021-03-05 por Jose Aguinaga y puede haber sido ligeramente modificado para su traducción por parte del flujo de trabajo de Información y Globalización para un proyecto de archivo en curso.
>
> El artículo original se puede encontrar [aquí](https://shapeshift.com/library/unlocking-the-mysteries-of-private-keys).
{.is-success}

---

- bounty: true
- amt: 63
- signedBy: 0xFAc9dD5194098461B627554347f83D5431Fb30e2
- hash: 
{.is-hidden}