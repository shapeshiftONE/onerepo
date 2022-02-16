---
title: Como a ShapeShift protege seus dados
description: A ShapeShift está empenhada em manter os dados dos clientes seguros.
published: true
date: 2021-12-20T23:02:39.376Z
tags: shapeshift, segurança, privacidade
editor: markdown
dateCreated: 2021-12-20T23:02:39.376Z
---

# Como a ShapeShift protege seus dados

O ShapeShift oferece aos usuários uma variedade de benefícios interessantes e exclusivos como taxas mais baixas, limites de negociação mais altos, recompensas pelo volume de negociação, acesso contínuo a exchanges descentralizadas e muito mais. Embora alguns serviços não exijam coleta e armazenamento de dados dos clientes (ou práticas de “Conheça seu cliente”), outros – como comprar Bitcoin – ainda exigem para atender aos requisitos regulatórios.

Na ShapeShift, estamos comprometidos em fazer todo o possível para manter os dados dos clientes seguros. Para aprimorar nossas decisões de design, nos fizemos a seguinte pergunta: “o que os hackers podem fazer se invadirem nossos sistemas?”

Para nossos serviços que exigem KYC, a plataforma ShapeShift coleta suas informações e as criptografa imediatamente com uma chave RSA de 4096 bits usando o software GPG de código aberto amplamente utilizado. Esses dados criptografados são armazenados em nosso banco de dados e, na maioria dos casos, nunca são usados ​​novamente. Depois de coletados, não precisamos fazer referência a eles por nenhum motivo comercial.

Se você tiver um problema e entrar em contato com o suporte ao cliente (por exemplo, para obter ajuda), eles não verão seu nome ou detalhes por padrão, permitindo que se concentrem no seu problema e não na sua identidade.

Existem apenas alguns casos em que nossa equipe precisa usar suas informações de identidade. Por exemplo, se você perder sua senha e autenticação de dois fatores e estiver tentando acessar sua conta novamente, nossa equipe precisará saber seu nome e outras informações para comparar os dados que procura com os que você forneceu. Nesse caso, nossos agentes de suporte ao cliente baixarão os seus dados criptografados para as nossas máquinas e usarão um dispositivo de “armazenamento frio” contendo a chave privada para descriptografar suas informações. Isso é gerenciado caso a caso, impedindo o acesso indiscriminado e livre às informações do cliente por qualquer funcionário da empresa. Outro exemplo seria se fôssemos legalmente obrigados a fazê-lo por uma intimação válida ou documento semelhante. Para obter mais informações sobre este exemplo, consulte nossa Política de Privacidade [aqui](https://shapeshift.com/privacy).

Como os servidores da ShapeShift nunca têm a chave de descriptografia para nenhuma informação pessoal (ela é mantida em “armazenamento frio”), mesmo que um invasor invada os servidores e copie todo o banco de dados, ele não poderá ver ou acessar suas informações. Se um de nossos dispositivos de armazenamento frio for perdido ou roubado, ele está configurado para se auto apagar em circunstâncias determinadas.

A ShapeShift entende o valor dos seus dados e da sua privacidade. Estamos comprometidos em garantir a segurança das suas informações, ao mesmo tempo em que fornecemos as melhores soluções financeiras não custodiais e descentralizadas do setor.<br/>

---

> Este documento foi publicado originalmente em 04/09/2018 por Michael Perklin, CISO da ShapeShift e pode ter sido ligeiramente modificado para tradução pelo fluxo de trabalho de Informação e Globalização para um projeto de arquivamento em andamento.
>
> O artigo original pode ser encontrado [aqui](https://shapeshift.com/library/how-shapeshift-protects-your-data).

{.is-success}

---

- bounty: true
- amt: 21
- signedBy: 0xFAc9dD5194098461B627554347f83D5431Fb30e2
- hash: 
{.is-hidden}
