---
title: Claves privadas: creación de direcciones de Ethereum
description: Aprenda cómo obtener una billetera Ethereum desde una dirección criptográfica.
published: true
date: 2022-03-04T00:07:40.588Z
tags: archivo, biblioteca
editor: markdown
dateCreated: 2022-03-04T00:07:40.588Z
---

# Claves privadas: Creación de Direcciones de Ethereum

## ***Segunda parte de una serie de tres partes***

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/6050d4a7d055404d1ebb9cf4_PK2%20header%20image.png)

*Descargo de responsabilidad: tenga en cuenta que todas las claves privadas generadas y utilizadas en este blog tienen únicamente fines educativos. No utilice ninguno de los códigos, claves o direcciones compartidas en esta publicación para almacenar ningún tipo o cantidad de criptoactivos.*

## Las claves privadas son bloques de construcción

Como revisamos en la [Parte 1](https://shapeshift.com/library/unlocking-the-mysteries-of-private-keys) de nuestra miniserie, "Desbloqueando los misterios de las claves privadas", el procedimiento para generar Las claves privadas se basan en generadores de números pseudoaleatorios (PRNG) con suficiente entropía. Lo más importante que debe recordar acerca de una clave privada es que debe seleccionarse **aleatoriamente** del espacio entero 2^256-1. Cualquier número puede ser una clave privada siempre que esté dentro del valor de 1 y 2^256 - 1.

Ahora que entendemos un poco las matemáticas detrás de las claves privadas, podemos continuar y generar nuestra propia clave privada válida. Una buena forma de visualizar este proceso de generación es pensar en un candado de combinación de dígitos horizontal de 78 dígitos (la cantidad total de dígitos en 2^256-1) y luego dividirlo en tres filas de 26 dígitos cada una. Puede pensar en una función PRNG como algo que "barajaría" todos los dígitos en ese candado de combinación al azar: comenzando todos en 0 y, posteriormente, generando un número sin ningún patrón distinguible. Supongamos que ejecutamos una función PRNG en nuestro candado y obtenemos los siguientes números en cada fila: 

(1)04406941321102621719184878,(2)43014596507006094171646853, (3)06780198554267270848908554.

<br/>

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/6050d54295b0e5f2121d4126_PK2%20Browsers.png)

*Los navegadores usan* [*Web Cryptography API*](https://developer.mozilla.org/en-US/docs/Web/API/Web_Crypto_API)*, una API moderna que nos proporciona primitivas criptográficas como Crypto. getRandomValues(32)(o el equivalente de crear un búfer de 32 bytes) como un PRNG, que se siembra con la fuente de entropía de su computadora para generar números aleatorios. Siempre debe usar una fuente digital para la generación de números aleatorios, ya que los humanos son terribles para elegir números aleatorios, como algunos* [*estudios*](https://www.thebalanceeveryday.com/random-number-generators-more-complicated-than-you-think-4177342) *indicar.* Acabas de generar la clave privada 44069413211026217191848784301459650700609417164685306780198554267270848908554. Ahora podemos usarla para generar una dirección de Bitcoin o Ethereum que admita 2 claves privadas en casi cualquier^2 -1 rango.

Para generar una dirección de Ethereum a partir de esta clave privada, debemos hacer [multiplicación de puntos de curva elíptica](https://en.wikipedia.org/wiki/Elliptic_curve_point_multiplication). Esto puede ser complicado, así que para simplificar, usaremos una computadora para que lo haga por nosotros. Primero, debemos entender que las computadoras no procesan información en formato decimal. Las computadoras solo entienden **código binario** y, hasta ahora, solo tenemos nuestra clave privada en formato numérico decimal. Por lo tanto, para usar nuestra clave privada, primero debemos convertirla en bits y bytes.<br/>

## Un poco sobre bits y bytes

¿Qué son los "bits y bytes"? Los dispositivos digitales solo pueden comprender información utilizando los números 0 y 1, comúnmente conocidos como **bits** (o "dígito binario"). Aunque nuestros teléfonos inteligentes y computadoras pueden mostrar caracteres, imágenes, canciones, etc., las computadoras finalmente representan y procesan todo como bits. Los grupos de bits representan cosas más grandes, pero desde el marco de referencia de una computadora, siempre son solo un montón de 0 y 1. La representación más común de bits son **bytes**, que se componen de 8 bits. Otra representación popular pero menos utilizada son los **nibbles**, que se componen de 4 bits.

Según el contexto, varios bits pueden representar caracteres (p. ej., la letra a se puede definir como 01100001 mediante la codificación [ASCII](https://en.wikipedia.org/wiki/ASCII) utilizando 1 byte) o números (es decir, , 01100001 representa el número 97 en formato decimal). En **formato binario**, tanto los bits como los bytes pueden representar **enteros** sumando las potencias de todos los bits utilizados, donde la **base** es 2 y cada dígito secuencial aumenta el **exponente** utilizado . Por ejemplo, normalmente contamos en **formato decimal**, donde los números se expresan como la suma de las potencias de todos los dígitos utilizados, usando el número 10 como base. Sin embargo, usando una forma binaria, podemos expresar números como 2 elevado a la **n-ésima potencia**, donde “n” es la cantidad de bits necesarios para representar y almacenar esta información en una computadora.

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/6050d5b5f4af7c4f57dc9798_PK2%208bit%20video.png)

*Los videojuegos de 8 bits solo podían expresar valores de hasta 255 porque las unidades de procesamiento de computadora (CPU) utilizadas en ellos solo podían realizar operaciones de hasta 8 bits.*<br/>

Aunque podemos representar cualquier número en formato binario, este formato es bastante "torpe". Para expresar simplemente 97, necesitábamos ocho dígitos binarios. Los números binarios son fáciles de procesar para las computadoras pero increíblemente engorrosos de leer para los humanos. Entonces, en lugar de representar datos en formato binario, las computadoras generalmente usan el **formato hexadecimal:** un sistema de numeración posicional que representa números usando una base de 16. A diferencia del formato binario, podemos representar 4 bits en una sola letra en formato hexadecimal . Podemos representar 01100001, el número 97, usando 61, reduciendo seis dígitos de nuestro ejemplo anterior. Los números hexadecimales usan ABCDEF para representar de 10 a 15 y se usan comúnmente para expresar datos en pequeños fragmentos.

## Contando bits en una clave

Volviendo a nuestra clave privada, sabemos que es un número entre 1 y 2^256-1. ¿Cómo podemos representarlo en bits y cuántos bits necesitamos? Discutimos que en formato binario, los números representan números enteros sumando las potencias de todos los bits usados, donde la base es 2; así, usando 8 bits, podemos representar 2^7 + 2^6 + 2^5 + 2^4 + 2^3 + 2^2 + 2^1 + 2^0, que es 255. Entonces podemos ver que en 2^n, n es igual a la cantidad total de bits necesarios para representar cualquier número en bits. Si correlacionamos este razonamiento, podemos decir que se necesitan 256 bits, o mejor aún, 32 bytes (256/8), para representar nuestra clave privada.

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/6050d614c80f3db79eb93f23_PK2%20Hexadecimal.png)

*La representación hexadecimal de datos pretende reducir la cantidad de dígitos necesarios para representar números. Sin embargo, las computadoras aún procesan datos usando 0 y 1. *Si podemos aceptar que necesitamos 32 bytes para representar nuestra clave privada [1,2^256-1], entonces usando el formato hexadecimal, podemos aceptar que necesitamos 64 caracteres para representar nuestra clave privada. Ahora podemos convertir nuestra clave privada original 440694132110262171917487843017171646853067717164685306780198554267780848908554 a su formato hexadecimal equivalente: 616E6769652E6A6177775696E61677775E66167682E6C696E6B0D0A. Vea las adiciones de las letras A, B, C, D, E y F en nuestro nuevo número; la presencia de estas letras es una manera fácil de identificar que un número está representado en formato hexadecimal.

## De clave privada a clave pública

Ahora podemos decirle a nuestra computadora sobre nuestra clave privada usando su formato hexadecimal. Usando lenguajes de programación como JavaScript, podemos importar fácilmente nuestra clave privada a un formato que podamos usar para una mayor multiplicación. En el siguiente código, definimos nuestra clave privada ("sk" para secret\_key, una notación estándar utilizada en criptografía) para importar el valor hexadecimal definido previamente. Proporcionamos el formato hexadecimal asegurándonos de que la raíz (base) sea 16.

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/6050d67e84b5e361c566b221_PK2%20BigNumber.png)

*Usando la biblioteca BigNumber, podemos asegurarnos de que no se pierdan decimales en la conversión. Estos números generalmente se expresan como exponenciales (por ejemplo, 4.406941321102622e+76) y, cuando se analizan directamente en hexadecimal, pierden precisión. Sin BigNumber, nuestra conversión hexadecimal devolvería 616e6769652e6c00000000000000000000000000000000000000000000000000 en lugar de nuestro número hexadecimal real.*<br/>Con nuestra clave importada, el siguiente paso es crear la clave pública. Como recordará de nuestro primer blog, necesitamos derivar la clave pública de nuestra clave privada antes de poder obtener la dirección de Ethereum. Siguiendo las instrucciones del [documento amarillo original de Ethereum](https://ethereum.github.io/yellowpaper/paper.pdf), descubrimos que el proceso de generación de claves sigue una [generación de clave pública ECDSA estándar](https://en.wikipedia.org/wiki/Elliptic_Curve_Digital_Signature_Algorithm), donde multiplicamos el punto generador y concatenamos las coordenadas en un solo valor. Nuestra clave pública (ahora definida como pk) ahora se puede usar para generar nuestra dirección Ethereum.

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/6050d6c77da9ec1ea15aca07_PK2%20ValuesXY.png)

*Los valores x e y se obtienen de la multiplicación del punto de la curva elíptica por nuestra clave privada (sk). Aunque una clave privada se puede usar en cualquier cadena de bloques como un identificador único de una dirección, Ethereum es específico sobre el uso de la curva elíptica secp256k1 para la generación de claves públicas y, por lo tanto, sus operaciones de firma equivalentes. *Ay, el paso final ha llegado. Con nuestra clave pública definida, podemos ejecutar la última instrucción del papel amarillo, definida de la siguiente manera:

<br/>

> *Para una clave privada determinada, la dirección A de Ethereum se define como los 160 bits más a la derecha del hash Keccak de la clave pública ECDSA correspondiente.*

<br/>

Teniendo en cuenta que ya tenemos nuestra clave pública ECDSA, la única tarea restante es ejecutar la función hash [Keccak](https://en.wikipedia.org/wiki/SHA-3) en nuestra clave pública y obtener los 160 bits más a la derecha. de esta operación. Como almacenamos estas operaciones en "búferes" (piense en pequeñas cajas donde almacenamos bytes de información), simplemente podemos "soltar" (cortar) los primeros 24 caracteres, dejando solo 40 caracteres, o más concretamente, 20 bytes: el tamaño de una dirección de Ethereum.

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/6050d7373d4368addc733bc1_PK2%20Ethereum%20addresses.png)

*Las direcciones de Ethereum tienen una longitud de 20 bytes por diseño. Al descartar algunos de sus bytes (12 para ser precisos), se podría argumentar que podría haber una colisión donde dos claves privadas terminan generando la misma dirección Ethereum. Sin embargo, a día de hoy, eso aún no ha sucedido.*<br/><br/>

## Ha creado su propia billetera

Como puede ver, a partir de un solo número (aunque sea largo), puede obtener una dirección de Ethereum donde puede almacenar todo tipo de activos: desde NFT que representan música, entradas, etc., hasta criptoactivos que pueden acumular valor monetario. . Su dirección de Ethereum es pública, similar a su dirección física, y lo conecta a esa clave privada única. <br/>

En caso de que no quiera seguir los pasos descritos aquí, puede registrarse para obtener una cuenta en [www.ShapeShift.com](http://www.shapeshift.com) para crear su propia clave privada, conocida solo para usted, y aproveche una serie de opciones de billetera de software y hardware.<br/>

En la siguiente y última parte de nuestra miniserie, veremos cómo ahora podemos usar nuestras claves privadas para crear y transmitir transacciones desde nuestra dirección de Ethereum y firmar mensajes, y aprenderemos las implicaciones que estas firmas pueden tener en el ecosistema de Ethereum.

---

> Este documento fue publicado originalmente el 16 de marzo de 2021 por José Aguinaga y puede haber sido ligeramente modificado para su traducción por parte del flujo de trabajo de Información y globalización para un proyecto de archivo en curso.
>
> El artículo original se puede encontrar [aquí](https://shapeshift.com/library/private-keys-creating-ethereum-addresses).
{.is-success}

---

- bounty: true
- amt: 80
- signedBy: 0xFAc9dD5194098461B627554347f83D5431Fb30e2
- hash: 
{.is-hidden}