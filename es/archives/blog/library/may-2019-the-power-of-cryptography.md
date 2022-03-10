---
title: El Poder de la Criptografía
description: Una guía para principiantes sobre claves públicas y privadas.
published: true
date: 2022-03-10T17:02:45.948Z
tags: archivo, biblioteca
editor: markdown
dateCreated: 2022-03-10T17:02:45.948Z
---

# El Poder de la Criptografía

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9fe664f01b87e59121323b_1_3VBrEt6tEGGLUrte9icrbQ.jpeg)

<br/>Ya sea que sea nuevo en criptografía o un veterano de mucho tiempo, hay ciertas ideas que todos los involucrados en este espacio deben comprender. Hoy vamos a cubrir uno de ellos: claves públicas y privadas.

En nuestra publicación anterior sobre [Almacenamiento Criptográfico](https://bit.ly/2UtogzI), usamos estos dos términos ampliamente para ayudar a transmitir los beneficios de las billeteras de hardware. Ahora los desglosaremos para mostrar cómo encajan en el ecosistema más grande que nos rodea.

Para hacer esto, debemos comenzar con los conceptos básicos de la criptografía, la idea fundamental sobre la que se construyen las claves públicas y privadas.<br/>

## **¿Qué es la criptografía?**

La palabra criptografía, como muchas otras palabras en el idioma inglés, tiene sus raíces en el griego. Desglosada, la palabra se traduce aproximadamente como "escritura oculta". En un entorno como Internet, donde la privacidad puede parecer escasa, las claves públicas y privadas permiten que las personas se comuniquen a través de la criptografía.

Entonces, ¿cómo es esto relevante para usted? Imaginemos que está enviando un documento importante a un amigo a través de Internet. Tal vez sea una nota secreta que solo quieres que vean; tal vez sea su contrato de arrendamiento. Quiere enviar este documento a su amigo y quiere asegurarse de que nadie más que él pueda leerlo. Ahí es donde entran en juego las claves públicas y privadas en forma de criptografía asimétrica.<br/>

## **Criptografía asimétrica frente a simétrica**

La criptografía asimétrica es un método que utiliza una clave para cifrar datos (la clave pública) y una clave para descifrar datos (la clave privada). Por el contrario, la criptografía simétrica utiliza la misma clave para cifrar y descifrar el mismo dato.

Como resultado, la criptografía asimétrica es más segura que la simétrica, pero el proceso puede demorar *un poco* más ya que se trata de dos claves en lugar de una.

Ahora, como la criptografía asimétrica es lo que se usa en el protocolo Bitcoin, en eso nos enfocaremos.

Ok, sigamos con el ejemplo de enviarle a un amigo su contrato de arrendamiento. Si quieres asegurarte mediante criptografía que solo ellos pueden leer el acuerdo, estos son los pasos que seguirías:

1. Obtén la clave pública de tus amigos
2. Cifrar el acuerdo con esa clave pública
3. Envía el acuerdo encriptado a tu amigo
4. Tu amigo recibe el acuerdo cifrado y lo descifra con su clave privada

De esta manera, cualquier persona puede enviarle datos cifrados a su amigo cuando usa la clave pública de ese amigo, mientras que su amigo es el único que puede descifrarlos y leer los mensajes cifrados. Esto funciona de la misma manera que cualquier persona puede enviarle un correo electrónico, pero solo usted puede abrir su buzón y leer los mensajes.<br/>

## **Cómo se relaciona con las criptomonedas**

Entonces, ¿cómo se relaciona esto con la tecnología blockchain y las criptomonedas? En un nivel básico, las claves públicas y privadas son uno de los componentes fundamentales que hacen posibles las transacciones en la cadena de bloques.

Cuando se crean sus claves, su clave pública se somete a [una función hash](https://www.investopedia.com/terms/h/hash.asp), y la cadena aleatoria resultante de letras y números se usa como su dirección de la billetera. Las transacciones funcionarán como nuestro ejemplo de contrato de arrendamiento anterior.

Usemos Bitcoin como ejemplo. Primero, alguien enviará bitcoins a la dirección de tu billetera. Al hacerlo, le otorgan el derecho a gastar ese bitcoin, *siempre y cuando pueda demostrar que es el propietario de la dirección*. Al firmar la transacción con la clave privada correspondiente, se le otorga la propiedad de ese derecho a gastar ([Lea más sobre las UTXO aquí](https://www.investopedia.com/terms/u/utxo.asp)).

Conocer los conceptos básicos de las claves públicas y privadas es fundamental para comprender el protocolo de Bitcoin e impresionar a tus amigos.

---

> Este documento fue publicado originalmente el 2019-05-12 por Ari Chernoff y puede haber sido ligeramente modificado para su traducción por parte del flujo de trabajo de Información y globalización para un proyecto de archivo en curso.
>
> El artículo original se puede encontrar [aquí](https://shapeshift.com/library/the-power-of-cryptography).
{.is-success}

---

- bounty: true
- amt: 29
- signedBy: 0xFAc9dD5194098461B627554347f83D5431Fb30e2
- hash: 
{.is-hidden}