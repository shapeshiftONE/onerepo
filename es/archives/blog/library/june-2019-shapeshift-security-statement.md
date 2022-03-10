---
title: Declaración de seguridad de ShapeShift
description: Nuestra respuesta para aclarar las afirmaciones recientes de Ledger
published: true
date: 2022-03-10T14:57:57.951Z
tags: archivo, biblioteca
editor: markdown
dateCreated: 2022-03-10T14:57:57.951Z
---

# Declaración de Seguridad ShapeShift

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9fdf3cce036369ec8de731_1_R53l5-JzGtTc0ZTNCs9HfQ.png)

El fin de semana pasado, durante la [Conferencia Breaking Bitcoin](https://twitter.com/breakingbitcoin), el director de seguridad de Ledger, Charles Guillemet, presentó *Extracción de semillas de carteras (de hardware).* La presentación expuso vulnerabilidades en carteras de hardware abiertas, incluidas [ KeepKey.](https://www.keepkey.com/) Esta vulnerabilidad resultó en la extracción de la clave privada.

**Consideramos esta clase de vulnerabilidad, una que puede revelar claves privadas, el tipo de error más crítico.**

Así que profundizamos más para entender el problema.

Aunque Guillemet no pudo especificar cómo Ledger recuperó la clave privada, ShapeShift sabe de un ataque que genera la clave privada *desde* antes de que adquiriéramos KeepKey en 2017.<br/>

## Cómo funciona este ataque

Un atacante **roba** su dispositivo KeepKey, lo abre y usa dispositivos electrónicos especializados para leer datos cifrados del almacenamiento flash. A continuación, usa un software para adivinar su código PIN probando todas las combinaciones posibles. Para lograr esto, un ataque necesitaría:

* Conocimientos, habilidades y experiencia especializados en ingeniería de hardware
* Conocimientos, habilidades y experiencia especializados en ingeniería de software
* Software especializado diseñado para adivinar todos los códigos PIN posibles; y
* Posesión física de su KeepKey

Las billeteras de hardware (como KeepKey) están diseñadas para protegerlo de los vectores de ataque más comunes: incluidos malware, virus y piratas informáticos remotos que buscan robar claves privadas. Pero, la vulnerabilidad a la que hacen referencia Guillemet y Ledger no ataca las claves de esta manera.

** Más bien, esta vulnerabilidad es una en la que un atacante necesitaría tener posesión física de su KeepKey. ** El trabajo de KeepKey es proteger sus claves contra ataques remotos.

Si alguien más tiene acceso físico a su dispositivo, así como el tiempo, la habilidad y las herramientas necesarias, **siempre** podrá ordenarle al dispositivo que haga lo que quiera, sin pasar por ningún bloqueo digital que exista.

**Nuevamente, esto es cierto para cualquier billetera de hardware.**

Por supuesto, esto no es nada nuevo. Las empresas han estado luchando contra este problema en la informática durante décadas sin éxito, ya que surge en una variedad de industrias.

Por ejemplo, los sistemas operativos, las aplicaciones y los medios digitales utilizan bloqueos digitales para garantizar que los usuarios finales hayan pagado las licencias. Los piratas informáticos modifican el código en sus máquinas locales para que el sistema crea que está pagado.

Los juegos usan una variedad de bloqueos digitales para evitar las trampas, pero los tramposos modifican los juegos para jugar como ellos quieren.

Y cada vez que un ingeniero brillante piensa en un nuevo tipo de cerradura digital, un hacker igualmente brillante analiza la cerradura en su propia máquina para comprender cómo funciona, y luego usa ese conocimiento para sortearla.

**Es como un laberinto donde puedes ver cada giro y giro, todo desde una vista de pájaro.**

El hecho es que no hay forma de evitar que un atacante altamente sofisticado con la posesión física del dispositivo y mucho tiempo, tecnología y recursos, "arruine" completamente ese dispositivo, eventualmente.

ShapeShift recomienda que asegure su dispositivo con la misma precaución que tendría con otras inversiones u objetos de valor. Proteja su KeepKey como si se lo pudieran robar mañana.

**Es como un laberinto donde puedes ver cada giro y giro, todo desde una vista de pájaro.**

Si bien los códigos PIN agregan de 4 a 9 dígitos simples para crear una barrera entre los piratas informáticos y su(s) clave(s) privada(s), 9 dígitos no son suficientes. En su presentación, Guillemet demostró que se puede adivinar un PIN de 9 dígitos en aproximadamente un minuto.

Con KeepKey, puede establecer una frase de contraseña que proporciona una capa adicional de protección.

Guillemet recomienda utilizar frases de contraseña compuestas por al menos 32 dígitos formadas por una combinación única de números, símbolos y letras mayúsculas y minúsculas.

Con una suficientemente larga [frase de contraseña](https://keepkey.zendesk.com/hc/en-us/articles/360000616300-How-Do-I-Access-My-ShapeShift-Membership-Account-with-a-Passphrase-), si un atacante extrae los datos de su dispositivo, nunca podrá desbloquearlo. Su PIN y su frase de contraseña **k**mantienen sus fondos a salvo.<br/> 

## Habilite su frase de contraseña BIP39 con [Cliente KeepKey](https://chrome.google.com/webstore/detail/keepkey-client/idgiipeogajjpkgheijapngmlbohdhjg)

1. Conecte y desbloquee su KeepKey
2. Haga clic en el ícono de ajustes **⚙️** ubicado en la parte superior izquierda del cliente KeepKey
3. Haga clic en "Habilitar frase de contraseña BIP39"
4. Ingrese una frase de contraseña larga (se le pedirá que vuelva a ingresar/confirmar esto).
5. Copie/Escriba su nuevo bitcoin/litecoin/etc. direcciones de su cuenta protegida con frase de contraseña
6. Desenchufe su KeepKey y vuelva a enchufarlo.
7. No ingrese una frase de contraseña. Haga clic en "Aceptar" con una frase de contraseña vacía para acceder a sus cuentas originales desprotegidas.
8. Envíe su bitcoin/litecoin/etc. a las direcciones que copió en el #5 (arriba). Vuelva a verificar las direcciones que no han sido alteradas por el malware de secuestro del portapapeles.
9. Desenchufe su KeepKey y vuelva a enchufarlo.
10. Ingrese su frase de contraseña y haga clic en "Aceptar".
11. Ahora puede ver todas sus monedas en sus direcciones cifradas con frase de contraseña.<br/>

## Pensamientos finales

Si está interesado en seguridad adicional para protegerse contra este caso extremo extremadamente improbable, asegúrese de consultar [*¿Cómo accedo a mi cuenta de membresía de ShapeShift con una frase de contraseña?*](https://keepkey.zendesk.com/hc/en-us/articles/360000616300-How-Do-I-Access-My-ShapeShift-Membership-Account-with-a-Passphrase-)

Si es un investigador de seguridad que ha identificado lo que cree que es un error o una vulnerabilidad en cualquiera de los productos o servicios de ShapeShift, nos encantaría saber de usted.

Y, siempre estamos aquí para ayudar. [Comuníquese con nuestro equipo de soporte](https://shapeshift.zendesk.com/hc/en-us/requests/new), en cualquier momento.
---

> Este documento fue publicado originalmente el 13 de junio de 2019 por el equipo ShapeShift y es posible que el flujo de trabajo de Información y globalización haya modificado ligeramente su traducción para un proyecto de archivo en curso.
>
> El artículo original se puede encontrar [aquí](https://shapeshift.com/library/shapeshift-security-statement).
{.is-success}

---

- bounty: true
- amt: 40
- signedBy: 0xFAc9dD5194098461B627554347f83D5431Fb30e2
- hash: 
{.is-hidden}