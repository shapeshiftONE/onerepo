---
title: Soluções Blockchain em 2 camadas
description: Aprenda sobre a tecnologia que  procura  resolver os problemas de dimensionamento.
published: true
date: 2021-12-20T23:02:33.907Z
tags: bitcoin, layer 2, camada 2, blockchain
editor: markdown
dateCreated: 2021-12-20T23:02:33.907Z
---

# Soluções Blockchain em 2 camadas

![](https://camo.githubusercontent.com/ec6aaace3247f74cb7afc0ba3567187510ea7adfebdc3ee2d283dda20a48e821/68747470733a2f2f6173736574732e776562736974652d66696c65732e636f6d2f3565396130393631306237646365373166383766376631372f3565396632393434323435333639353462363938303662645f315f4c38477048547952312d4a5279796f33314a7a5a65512e706e67)

Os geeks da **Blockchain** e entusiastas de cripto costumam usar os termos 2 camadas e *Lightning Network* de forma intercambiável ao se referir a soluções de escalabilidade de blockchain. A verdade é que esses termos **não** são intercambiáveis.

## Além do Bitcoin: Escalando com 2 camadas
O termo **2 camadas** se refere a uma segunda camada de código que existe em cima de uma estrutura de código blockchain original. Isso permite que uma blockchain descentralizada evolua e lide com um punhado de problemas tais como:

* Escalonamento de velocidade e de volume de pagamento.
* Escalonamento de criação e de execução de contratos inteligentes.
* Executar cálculos fora da cadeia.

A atualização da Lightning Network do Bitcoin é específica para escalonar pagamentos, mas é apenas um dos projetos dedicados a resolver esse problema. Para entender melhor as soluções de 2 camadas, você precisa olhar além do Bitcoin para as diferentes blockchains que estão usando essa tecnologia.

## Por que o escalonamento é um problema 
A escalabilidade refere-se simplesmente à capacidade de uma rede de lidar com um grande número de transações por segundo. Aumentar o número de transações que uma blockchain pode processar é fundamentalmente considerado um dos maiores obstáculos que as plataformas de pagamento descentralizadas e criptomoedas enfrentam. O escalonamento é considerado o maior obstáculo entre a cripto e a adoção em massa.

Cartões de crédito como Visa e Mastercard podem processar até 47.000 transações por segundo a qualquer momento. Na verdade, estima-se que durante o infame evento global de compras do [Dia do Solteiro na China](https://techcrunch.com/2018/11/09/alibaba-singles-day-11-festival/), essas empresas de cartão de crédito possam processar cerca de 100.000 transações por segundo.

Em comparação, o Bitcoin executa aproximadamente [4,6 transações](https://hackernoon.com/the-blockchain-scalability-problem-the-race-for-visa-like-transaction-speed-5cce48f9d44) por segundo. A razão para esta grande discrepância é que Visa e MasterCard fazem parte do sistema bancário centralizado, que existe há mais de 100 anos. As tecnologias descentralizadas devem sempre enfrentar o que é conhecido como o “triângulo impossível”.

**O triângulo impossível** se refere aos três princípios que dão a uma blockchain sua utilidade

Segurança
Escalabilidade
Descentralização

No momento, não há uma única criptomoeda em uma blockchain completamente pública que domine todos os três itens acima. A Ripple atualmente lida com [1.500 transações por segundo](https://www.ripple.com/xrp/). A blockchain EOS tem uma taxa de transferência de quase [4.000 transações por segundo](https://thenextweb.com/hardfork/2018/11/01/eos-blockchain-benchmark/). É seguro dizer até este ponto que o triângulo ainda está se mostrando impossível de dominar. É por isso que as abordagens de 2 camadas estão se tornando mais conhecidas como uma solução de escalonamento.

## A Lightning Network
A [Lightning Network](https://medium.com/shapeshift-stories/ride-the-lightning-ec6b8d3a086f) permite menores transações através dos canais de pagamentos. Abrir um canal de pagamento é ótimo para transações menores e recorrentes, como comprar café todos os dias. Um grande amante de café pode comprar três xícaras por dia, ou seja, 21 transações por semana. A Lightning Network permite que os usuários criem um canal de pagamento que confirme essas 21 transações, o saldo inicial e o saldo final de todas essas transações na blockchain.

A Lightning Network é necessária porque a [transação de bitcoin média](https://hackernoon.com/2019-blockchain-layer-2-solution-review-d00385147396#1cee) vale aproximadamente 50 dólares, com uma taxa de aproximadamente 20 dólares. Isso torna impraticável manter pequenas transações 'on-chain' [na-cadeia]. Fazer transações off-chain [fora da cadeia] reduz a carga na blockchain. A Lightning Network também faz com que um endereço multi-assinatura deva ser usado; significando que duas partes não podem manipular uma à outra na conclusão de uma transação. A desvantagem é que a Lightning Network não pode ser usada off-line. Ela também não pode ser usada para grandes quantias, e permite que os *nodes* se tornem potencialmente grandes centros de pagamento que detêm grandes somas de valor.

[>>> Leia mais sobre a Lightning Network do Bitcoin <<<](https://medium.com/shapeshift-stories/ride-the-lightning-ec6b8d3a086f)

## Canais de Pagamento
De um ponto de vista de código, um canal de pagamento é na verdade apenas uma iteração de uma solução de 2 camadas de canal de estado. Uma implementação de canal de estado:

* Permite que parte do estado da blockchain seja travado usando endereços de múltipla assinatura ou contratos inteligentes
* Permite que os participantes atualizem o estado daquela parte da cadeia
* Envia o estado de atualização de volta para a blockchain

Essa abordagem de canal de estado é mais facilmente compreendida em uma troca monetária; a troca pode ser qualquer coisa. Ele pode ser usado para rastrear qualquer outro tipo de alteração no estado de uma blockchain, seja a transação relacionada a dinheiro, propriedade intelectual, identificação do governo etc.

## Soluções de escalonamento Ethereum

A Ethereum pretende ser o supercomputador descentralizado do mundo. Sua existência oferece aos desenvolvedores uma plataforma para criar e lançar aplicações descentralizadas que todos podem usar. Isso é o que a torna diferente do Bitcoin. O que torna as duas criptomoedas semelhantes é que ambas usam o algoritmo de consenso de [*proof-of-work*](https://medium.com/shapeshift-stories/exploring-consensus-algorithms-8403c301b2ff) [prova-de-trabalho].

## Casper
A Casper é a atualização que levará a Ethereum para a abordagem de *proof-of-stake* [prova-de-participação] indiscutivelmente mais eficiente. Algoritmos de prova-de-participação tornam a validação de transações mais eficiente, tanto tecnicamente quanto em termos de custos de energia.

## Plasma
Onde um algoritmo de consenso de prova-de-participação valida as transações, a atualização Plasma aplica a segunda camada de contratos inteligentes à blockchain. Isso ajudará a substituir os farms de servidores por uma rede *peer-to-peer* [ponto-a-ponto] que torna a execução de aplicativos descentralizados mais escalável. Conforme o [Plasma whitepaper](https://plasma.io/plasma-deprecated.pdf) explica, transações podem ocorrer privadamente entre usuários em cadeias privadas, e então serem representadas em cadeias públicas.

## Sharding
Sharding complementará a Casper e a Plasma para fazer a blockchain Ethereum mais escalável. Permite que [os dados sejam divididos](https://www.trustnodes.com/2018/05/01/sharding-proof-concept-launches-casper-32-staking-eth-requirements-coming-says-vitalik-buterin) e hosteados em múltiplos servers. Isso significa que o livro-razão público fica fragmentado, mas todas as transações ainda serão contabilizadas.

# Transações *Sidechain* and *Off-Chain*
Agora você conhece duas das abordagens mais populares para dimensionar pagamentos e contratos inteligentes. Há duas outras soluções de 2 camadas dignas de nota a serem exploradas.

## *Sidechain*
Uma *sidechain* é uma blockchain separada que é anexada a uma cadeia pai usando um pino bidirecional, que permite a troca de ativos uns pelos outros a uma taxa fixa. As sidechains podem ser usadas para todos os tipos de ativos digitais e precisam de seus próprios mineradores para permanecerem seguras. Projetos que usam sidechains efetivamente incluem [OmiseGO](https://omisego.co/), [POA Network](https://poa.network/), e [Alacris](https://alacris.io/).

## *Off-Chain*
Transações off-chain ocorrem completamente fora de uma blockchain. Isso pode acontecer via um acordo de transferência entre as duas partes, por meio de um fiador terceirizado (semelhante ao que o Paypal faz no mundo fiduciário) ou usando um mecanismo baseado em cupom. As transações off-chain podem acontecer instantaneamente, sem taxas e com mais anonimato. Os projetos que implementam uma abordagem off-chain incluem [Provable](https://provable.xyz/), [AlphaWallet](https://alphawallet.com/), e [Transmute](https://www.transmute.industries/).

## *Zero-Knowledge Proofs* [Provas-de-Conhecimento-Zero]
Você sabia que os fundamentos criptográficos que permitem a privacidade no Zcash podem ser aproveitados para aumentar a escalabilidade também? Essa abordagem promissora das 2 camadas está sendo construída na Ethereum, usando STARKS e SNARKS (os dois principais tipos de provas-de-conhecimento-zero).

Do lado da STARKS, o [STARKWARE](https://starkware.co/) de Israel está construindo uma solução inovadora que pode agrupar milhares de transações off-chain sem a necessidade de uma configuração confiável. Além disso, fique de olho no [Matter Labs](https://starkware.co/) e seus “roll-ups” baseados em SNARK.

Mesmo que essas soluções estejam longe de serem perfeitas — o potencial de levar a tecnologia blockchain para o próximo nível está lá. Com avanços de escalonamento, como soluções de 2 camadas, a missão de trazer a adoção mainstream para a cripto parece estar no horizonte.

---

> Este documento foi originalmente publicado em 2019-10-17 pelo Time ShapeShift e pode ter sido levemente modificado para tradução pelo fluxo de trabalho de informação e globalização para um ocorrente projeto de arquivamento.
>
>O artigo original pode ser encontrado [aqui](https://shapeshift.com/library/digging-into-layer-2-blockchain-solutions).


{.is-success}

---

- bounty: true
- amt: 54
- signedBy: 0xFAc9dD5194098461B627554347f83D5431Fb30e2
- hash: 
{.is-hidden}
