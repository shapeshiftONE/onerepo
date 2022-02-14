---
title: O Poder da Criptografia
description: Guia para iniciantes sobre chaves públicas e privadas
published: false
date: 2021-12-20T23:03:17.065Z
tags: chave pública, chave privada, guia, iniciante
editor: markdown
dateCreated: 2021-12-20T23:03:17.065Z
---

# O Poder da Criptografia

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9fe664f01b87e59121323b_1_3VBrEt6tEGGLUrte9icrbQ.jpeg)

<br/>Seja você novo nas criptos ou um veterano de longa data, há certas ideias que todos envolvidos nesse espaço deveriam entender. Hoje vamos cobrir uma delas: chaves públicas e privadas.

Em nossa postagem anterior sobre [Armazenamento de Criptos](https://bit.ly/2UtogzI) usamos esses dois termos de forma extensiva para ajudar a expressar os benefícios de carteiras em hardware. Agora iremos quebrá-los para mostrar como eles se encaixam no ecossistema maior ao nosso redor.

Para fazer isso, precisamos começar com o básico sobre a criptografia, a ideia fundamental sobre a qual chaves públicas e privadas são desenvolvidas.<br/> 

## **O que é Criptografia?**

A palavra criptografia, assim como muitas outras palavras na língua inglesa, tem suas raízes no grego. Quebrada, a palavra grosseiramente diz "escrita escondida". Em um ambiente como a internet, onde a privacidade pode parecer escassa, chaves públicas e privadas fazem com que as pessoas se comuniquem através da criptografia.

Então, o quão relevante é isso pra você? Imaginemos que você está enviando um importante documento para um amigo pela internet. Talvez seja uma nota secreta que você quer que só vocês vejam ela; talvez seja seu acordo e você quer mandar esse documento para seu amigo, e você quer ter certeza que ninguém pode ler isso senão ele. É aí que as chaves pública e privadas entram em jogo na forma de criptografia assimétrica.<br/> 

## **Criptograia Assimétrica vs Simétrica**

A criptografia assimétrica é um método que usa uma chave para encriptar dados (a chave pública) e uma chave para decriptar dados (a chave privada). Conversívelmente, criptografia simétrica usa a mesma chave tanto para encriptar quanto para decriptar o mesmo pedaço de dado.

Como um resultado, a criptografia assimétrica é mais segura que a criptografia simétrica, mas o processo pode demorar *levemente* mais enquanto você está lidando com duas chaves em vez de uma.

Agora, enquanto a criptografia assimétrica é o que é usado no protocolo Bitcoin, é nisso que iremos nos focar.

Ok, então fiquemos com o exemplo de enviar a um amigo seu acordo de aluguel. Se você quer assegurar através da criptografia que apenas ele pode ler o acordo, esses são os passos que você seguiria:

1. Obtenha a chave pública de seu amigo
2. Encripte o acordo com essa chave pública
3. Envie o acordo encriptada para seu amigo
4. Seu amigo recebe o acordo encriptado e decripta ele com a chave privada dele.

Desse modo, qualquer um pode enviar a seu amigo dados encriptados quando usa a chave pública desse amigo, enquanto seu amigo é o único que pode decriptar eles e ler as mensagens encriptadas. Isso funciona do mesmo modo que qualquer um pode te mndar um email, e apenas você pode abrir sua caixa de email e ler as mensagens.<br/> 

## **Como isso se Relaciona a Cripto**

Então como isso se relaciona com a tecnologia blockchain e com as criptomoedas? A um nível base, as chaves públicas e privadas são um dos componentes fundamentais que fazem as transações na blockchain serem possíveis.

Quando suas chaves  são criadas, sua chave pública é colocada em uma [função hash](https://www.investopedia.com/terms/h/hash.asp), e o arranjo aleatório de letras e de números é usada como o endereço da sua carteira. As transações irão funcionar assim como o nosso exemplo acima do acordo de aluguel.

Usemos o Bitcoin como um exemplo. Primeiro, alguém irá enviar o bitcoin para o endereço de sua carteira. Ao fazer isso, ele está te dando o direito de gastar esse bitcoin, *na medida em que você pode provar que você mesmo é o dono do endereço*. Ao assinar a transação usando a chave privada correspondente, é dada a propriedade desse direito de gastar([Leia mais sobre UTXO's aqui](https://www.investopedia.com/terms/u/utxo.asp)).

Conhecer o básico sobre chaves públicas e privadas é fundamental no entendimento do protocolo Bitcoin, e para impressionar seus amigos.

---

> Esse documento foi originalmente publicado em 12/05/2019 por Ari Chernoff e pode ter sido levemente modificado para tradução pelo fluxo de trabalho de Informação e Globalização para um projeto de arquivamento em andamento.
>
> O artigo original pode ser achado [aqui](https://shapeshift.com/library/the-power-of-cryptography).

{.is-success}

---

- bounty: true
- amt: 29
- signedBy: 0xFAc9dD5194098461B627554347f83D5431Fb30e2
- hash: 
{.is-hidden}
