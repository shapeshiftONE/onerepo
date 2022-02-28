---
title: Cómo ShapeShift protege sus datos
description: ShapeShift se compromete a hacer todo lo posible para mantener seguros los datos de los clientes
published: true
date: 2022-02-28T14:27:03.269Z
tags: archivo, biblioteca
editor: markdown
dateCreated: 2022-02-28T14:27:03.269Z
---

# Cómo ShapeShift protege sus datos

ShapeShift ofrece a los usuarios una variedad de beneficios emocionantes y únicos, como tarifas más bajas, límites de negociación más altos, recompensas por volumen de negociación, acceso sin problemas a intercambios descentralizados y más. Si bien algunos servicios no requieren que recopilemos y almacenemos datos de clientes (o prácticas de "Conozca a su cliente"), otros, como la compra de Bitcoin, aún lo requieren para cumplir con los requisitos reglamentarios.

En ShapeShift, nos comprometemos a hacer todo lo posible para mantener seguros los datos de los clientes. Hicimos la pregunta, "¿qué pueden hacer los piratas informáticos si ingresan a nuestros sistemas?" para informar nuestras decisiones de diseño.

Para nuestros servicios que requieren KYC, la plataforma ShapeShift recopila su información y la cifra inmediatamente con una clave RSA de 4096 bits utilizando el software GPG de código abierto ampliamente utilizado. Estos datos cifrados se almacenan en nuestra base de datos y, en la mayoría de los casos, nunca se vuelven a utilizar. Una vez recopilada, no necesitamos hacer referencia a ella por ningún motivo comercial.

Si tiene un problema y se pone en contacto con el servicio de atención al cliente (por ejemplo, para obtener ayuda), no ven su nombre ni sus detalles de forma predeterminada, lo que les permite centrarse en su problema en lugar de en su identidad.

Solo hay unos pocos casos en los que nuestro personal necesita usar su información de identidad. Por ejemplo, si pierde su contraseña y la autenticación de dos factores y está tratando de volver a ingresar a su cuenta, nuestro personal necesitará saber su nombre y otra información para compararla con lo que les ha proporcionado. En este caso, nuestros agentes de atención al cliente descargarán sus datos cifrados en su máquina y utilizarán un dispositivo de almacenamiento en frío que contiene la clave privada para descifrar su información. Esto se gestiona caso por caso, impidiendo el acceso mayorista a la información de los clientes por parte de cualquier empleado de la empresa. Otro ejemplo sería si estuviéramos legalmente obligados a hacerlo mediante una citación válida o un documento similar. Para obtener más información sobre este ejemplo, consulte nuestra Política de privacidad [aqui](https://shapeshift.com/privacy).

Dado que los servidores de ShapeShift nunca tienen la clave de descifrado de ninguna información personal (se almacena en frío), incluso si un atacante viola los servidores y copia toda la base de datos, no podrá ver ni acceder a su información. Si uno de nuestros dispositivos de almacenamiento en frío se pierde o es robado, está configurado para borrarse solo en determinadas circunstancias.

ShapeShift entiende el valor de sus datos y privacidad. Estamos comprometidos a garantizar la seguridad de su información al mismo tiempo que brindamos las mejores soluciones financieras descentralizadas sin custodia en la industria.<br/>

---

> Este documento fue publicado originalmente el 4 de septiembre de 2018 por Michael Perklin, CISO en ShapeShift y puede haber sido ligeramente modificado para su traducción por parte del flujo de trabajo de Información y globalización para un proyecto de archivo en curso.
>
> El artículo original se puede encontrar [aqui](https://shapeshift.com/library/how-shapeshift-protects-your-data).
{.is-success}

---

- bounty: true
- amt: 21
- signedBy: 0xFAc9dD5194098461B627554347f83D5431Fb30e2
- hash: 
{.is-hidden}