---
title: Pilhagem infiel - Uma história sobre sabotagem na ShapeShift
description: Esta é a história de como a ShapeShift foi traída. Não uma, não duas, mas três vezes em menos de um mês.
published: true
date: 2022-01-11T13:10:18.681Z
tags: hack na shapeshift, história da shapeshift, protocolo de segurança, security, segurança
editor: markdown
dateCreated: 2021-12-15T06:19:42.419Z
---

# Pilhagem infiel - Uma história sobre sabotagem na ShapeShift

Esta é a história de como a ShapeShift foi traída. Não uma, não duas, mas três vezes em menos de um mês.

No total, quase duzentos mil dólares em criptomoedas foram roubados por ladrões internos e externos, sem mencionar os recursos significativos gastos em seu rastro.
No entanto, nenhum cliente foi lesado ou exposto em situação de risco, um marco para uma indústria repleta de tragédias do passado, e a próprio ShapeShift se adaptou e reconstruiu, humilhada pela experiência aprendida e cada vez mais decidida em sua missão de promover um sistema de trocas de ativos digitais sem intermediários e atritos.

No espírito dos primórdios do Bitcoin, desejamos compartilhar essa história com a comunidade; que você se informe, se entretenha, reflita e mantenha a diligencia de suas opiniões.

> Este artigo / documento / postagem / conteúdo foi publicado originalmente em 19 de abril de 2016 por Erik Voorhees e pode  ser ligeiramente adaptado para tradução com o objetivo de garantir uma boa leitura para todos os idiomas.
{.is-success}

> Nota: alguns nomes e detalhes confidenciais foram alterados
{.is-info}


## A raíz do mal

A ShapeShift é uma criatura em evolução desde o seu início na primavera de 2014. O que começou como uma forma experimental de trocas rápidas entre Bitcoin e Litecoin tornou-se um mecanismo avançado para a troca sem esforço de todos os principais ativos do blockchain, sem ônus para o usuário. Sim, sem contas de usuário ou  processo de inscrição. Imagine o Google Translate da Criptomoeda, essa ferramenta é a ShapeShift.

É um grande desafio para a ShapeShift acompanhar a velocidade da indústria do Bitcoin ou Blockchain, apesar dos pesares, sempre buscamos recuperar o tempo perdido.

No outono passado, percebemos que a arquitetura de servidor de “produto mínimo viável” (MVP), estabelecida era insuficiente. Precisávamos de um profissional em nossa pequena equipe para otimizar o servidor de maneira escalonável e segura, de modo que nossa tecnologia pudesse crescer.

Contratamos essa pessoa e recebemos um 'tapinha nas costas' por nossa decisão proativa. No papel, ele parecia ótimo; a referência que chamamos confirmou seu papel e responsabilidade anteriores. Usuário do Bitcoin desde 2011/2012 e construiu uma rede de mineração em seu quarto. Impressionante. Vamos chamar esse novo funcionário de Bob ... na verdade, seu nome verdadeiro começa com B.

Nos meses seguintes, Bob construiu e gerenciou a infraestrutura da ShapeShift. Ele se saiu bem, nada de especial, mas ficamos contentes em ter um profissional cuidando dos devops pelo menos bem o suficiente para permitir que nossos engenheiros desenvolvessem a arquitetura.

No primeiro trimestre deste ano, quando o mercado descobriu o que já sabíamos - que a liquidez dentro da Blockchain precisa ser sustentada uns pelos outros - os volumes de câmbio aumentaram na ShapeShift. Foi o período em que Ethereum estava em ascencão, especificamente. Nossa infraestrutura não estava preparada para o ritmo de crescimento. Era como andar em uma bicicleta equipada com motores a jato em força total.

Infelizmente, Bob pouco fez para ser útil. Ele vagava sem rumo enquanto a equipe trabalhava longas horas para manter o barco, em plena tempestade, em seu curso.

Aliás, na verdade, Bob não estava sem rumo.

Ele estava se preparando para nos roubar.

## Paraíso maculado

Na manhã de 14 de março, em meio a uma semana de volume histórico, recebo um telefonema do chefe de operações, Greg. “Erik, sumiram 315 Bitcoins de nossa carteira.” Você deve se perguntar porque tanto volume em uma única carteira. Bem, com o aumento dos volumes, nossa carteira conveiconal (conta corrente) seria drenada pelos negócios normais a qualquer momento, o que exigia um reequilíbrio manual constante. Existem maneiras de automatizar e reduzir esse risco? Com certeza ... mas a retrospectiva de nossas prioridades de desenvolvimento é sempre 20/20.

E foi assim que 315 Bitcoins sumiram.

Para aqueles que passaram por tais incidentes, o sentimento de revolta é latente. É um estado profundo e sombrio, que não cessa no limite da perda financeira, mas permeia até o âmago da pessoa. Quando os sistemas são violados, sistemas que alguém projetou e cuidou profundamente, obsessivamente, essa violação do que se considera seguro e protegido é muito, muito desconfortável. E então há perda generalizada, sim. 315 Bitcoin… cerca de $ 130.000. Isso é mensalidade da faculdade, parte de uma casa, comida por dez anos ... alguns meses de folha de pagamento. É muito dinheiro para uma startup em estágio inicial.

Corri para o escritório, esperando que houvesse algum engano. O único pensamento reconfortante era que a perda era apenas de nosso próprio dinheiro. Sem contas de clientes, nem os fundos dos clientes nem as informações pessoais corriam risco com o hack. Isso foi planejado desde o início da ShapeShift; um dos nossos princípios. Mesmo que ninguém tenha se ferido, um soco na cara sempre machuca, e muito.

Eu, Greg e nossos dois engenheiros líderes vasculhamos os logs e servidores, tentando desesperadamente descobrir o que havia acontecido. 315 BTC foram parar em um endereço desconhecido, e lá estavam.

Na verdade, tudo começou aqui: `https://blockchain.info/address/1LchKFYxkugq3EPMoJJp5cvUyTyPMu1qBR`

Apesar de nossa mensagem enviadas para todos os colaboradores para que cheguem no escritório com urgência, Bob, nosso chefe de TI, o responsável pela segurança e infraestrutura, chega às 11h30.

Pedimos a Bob para participar de nossa discussão. Nós revelamos o hack para ele. Perguntamos se ele havia feito o login naquela manhã, ele que respondeu não (em várias ocasiões). Sobre a notícia do roubo, ele não parecia nem particularmente chocado nem indignado, mas seu protocolo de segurança que falhou. Imediatamente, ele começa a apontar explicações falsas: “Deve ser uma das trocas que foram hackeadas, isso acontece o tempo todo”. Claro, nossas contas de câmbio estão bem, Bob.

“Olhe para o endereço IP, aconteceu em algum lugar na África Ocidental.” Bem, os endereços IP em exploradores de bloco indicam apenas o primeiro nó que percebeu uma transação e geralmente não fazem sentido no contexto do Bitcoin, Bob. (Que tipo de especialista em Bitcoin não sabe disso?)

Rapidamente, percebemos que ele é praticamente inútil. Aqui temos nosso “cara do servidor” e ele não tem nenhum comentário inteligente sobre um hack contra sua própria infraestrutura.

Enquanto examinávamos os logs, notamos, no entanto, algumas chaves SSH (pertencentes a Bob) que se conectaram ao servidor violado naquela manhã, uma hora antes da transação invasora, e se desconectaram dois minutos depois. De fato, seria esperado que as chaves de Bob se conectassem periodicamente, embora o momento fosse estranho (6 horas da manhã). Também descobrimos que a violação ocorreu na VPN, o que significa que alguém internamente, ou alguém com acesso a nossa VPN, pode ter colaborado.

Pedimos a todos com acesso ao servidor que forneçam as fingerprints de suas chaves SSH para que possamos começar a compará-las aos logs. Todo mundo fez isso, mas outra coisa estranha: a fingerprints da chave entregue por Bob não aparece em nenhum registro. Parece nova em folha. Estranhamente a chave do administrador, técnicamente, nunca havia sido vista no servidor.

Logo depois, Bob decide que é hora de sua pausa para o almoço, e não o vemos por uma hora, durante o pior incidente da história da ShapeShift. Sinceramente, não nos importamos muito, ele não foi útil e as suspeitas começaram a surgir. Ele diz a todos nós que está deixando seu laptop aberto para fazer download de alguns registros e garante que veremos seu laptop  aberto. Ele está um pouco estranho.

Ao retornar, uma hora depois, ele está sentado com outros engenheiros ainda investigando o que ocorreu. Estou na outra sala em uma chamada. Quando termino minha ligação, vou verificar o andamento. Bob parece receber uma ligação “de sua mãe, que precisa ir ao hospital”. Ele empacota suas coisas, agarra seu cachorro que estava no escritório e sai. Estamos todos meio aliviados por sua saída e meio maravilhados ... nosso administrador de servidor realmente saiu pela segunda vez durante nossa investigação, que ele deveria estar liderando.

Ele disse: “Estarei de volta em uma hora”. Isso foi por volta das 15h do dia 14 de março.

Nós nunca mais o vimos.

Pouco depois de Bob ir embora, fui convocado por um de nossos engenhados e Greg, ele disse: “Enquanto você atendia sua ligação, estávamos todos sentados ao redor da mesa e vimos nos registros que Bob excluiu duas chaves SSH enquanto estava lá conosco. Essas duas chaves correspondem aquelas duas chaves que vimos no log esta manhã, que acessou o servidor Bitcoin pouco antes do hack. ”

Imediatamente Bob tornou-se o principal suspeito. Ele já estava fora do prédio, então começamos a trancar tudo. Todas as chaves são alteradas às pressas (bem, quase todas).

Trabalhamos por mais algumas horas, sem notícias de Bob. Sem chamadas, sem mensagens de texto, nada. No final do dia, haviam se passado 3-4 horas desde que ele saiu para "levar sua mãe ao hospital". Decidimos ligar para ele, sem deixar que ele suspeitasse.

> “Ei Bob, onde você está?”
>
> “Alô, eu decidi vir para casa.”
>
> “Você está em casa?”
>
> “Sim, estou trabalhando em algumas coisas...”

WTF? Fiquei sem entender.

Essa ligação é inócua, mas nós a gravamos. Também gravamos o próximo 30 minutos depois, no qual o confrontamos com algumas das evidências.

“Bob, parece que você excluiu suas chaves SSH e nos deu uma nova chave que nunca acessou nenhum servidor.”

“Sim, bem... Eu deletei porque não achei que fossem importantes.”

Sim, ele realmente disse isso. Nosso administrador de servidor, no meio de uma investigação sobre um roubo de $ 130.000, exclui suas duas chaves sem contar a ninguém, e então admite em ligação que fez isso porque "elas não eram importantes".

Acontece que essas duas chaves foram exatamente as mesmas conectadas ao servidor Bitcoin naquela manhã, e que foram desconectadas dois minutos após a transação de roubo. Como se não fosse algo realmente importante.

Ele não deu nenhuma explicação sobre seu comportamento ou ações naquele dia, mas gira em torno de perguntas e sugere, sutilmente no início, e depois de forma mais explícita, que estamos sendo racistas.

“Bob, estamos suspeitando de você porque suas chaves estavam no servidor e você as excluiu e saiu, durante uma investigação ativa.”

Continua assim por 45 minutos. Ele diz outras coisas ridículas, todas gravadas.

Descobrimos mais detalhes de evidências e uma sensação de alívio ocorreu de saber exatamente o que aconteceu e quem foi o responsável. Passamos o resto da noite documentando tudo e nos preparando para abrir ações civis e criminais contra Bob.

Eu dou a ele uma chance final de redenção naquela noite. Em uma mensagem a todos os colaboradores, de modo a não forçá-lo a se envolver respondendo,

> Esta é sua chance de ir embora, aprender uma lição e deixar que isso seja encerrado. Não entraremos em ação legal se 315 Bitcoins forem depositados neste endereço até 10h da manhã. Nenhuma outra pergunta será feita e podemos nos separar amigavelmente. Envie 315 BTC para este endereço: 35JBgzjyCUPswjRP9iqrUTkkX76QwrKkB9 -Erik

Recebo uma mensagem de resposta de Bob às 4h36: “Não excluí nenhuma chave e faço login regularmente nos servidores para verificá-las”.

Sua incapacidade em mentir parece superada apenas por sua incompetência na administração de servidores, naquele dia ele mesmo havia admitido que não havia realizado o login.

Ele continua, desta vez parte para com um discurso infantil:

> “Me culpar é a coisa mais racista a fazer ... você estava basicamente procurando uma desculpa para satisfazer o seu racismo. Não tenho antecedentes criminais, ao contrário de você com a SEC.”

Na manhã seguinte, nosso consultor jurídico escreve uma carta formal (via e-mail e correio) para Bob, descrevendo algumas das evidências que conhecíamos e exigindo que a propriedade roubada seja devolvida. Também notificou Bob que seu emprego foi rescindido (acho que foi justo, considerando). Em resposta, Bob responde o e-mail de volta para o advogado, sem abordar nenhuma das evidências, "Seus clientes são racistas, então certifique-se de saber com quem está lidando."

É como se ele estivesse usando sua máscara da internet na vida real. Ele nem mesmo entendeu a gravidade da situação? Bem ... o absurdo estava apenas começando.

Nos próximos dias, protocolamos a ação civil formal. O endereço que Bob nos deu era uma caixa postal, embora tivéssemos seu nome legal, suas informações bancárias e seu CPF. Contratamos um investigador particular. Encontramos seu apartamento em poucos dias. Várias tentativas de contato falharam, embora o investigador tenha ouvido um cachorro latindo atrás da porta. Um de seus carros foi encontrado; ele dirige duas viaturas policiais aposentadas sem identificação.

Existem investidores a quem devo protocolar diligências, portanto, também tomamos providências para um processo criminal e, neste caso, o roubo constitui um crime de classe 3 nos Estados Unidos e prevê 4 a 12 anos de prisão. Honestamente, não me importo se ele será punido. Eu me preocupo se ele perceberá seu erro e mudará sua vida para se tornar uma pessoa melhor. A esta altura do campeonato, ele não me parece uma pessoa legal. 

Também descobrimos que Bob tem antecedentes policias na Flórida, sua terra natal. 

Com processos civis e criminais contra ele e com a descoberta de que Bob fugiu para a Flórida (deixando seu cachorro para ser temporariamente com seu vizinho ... e que agora está se perguntando onde Bob está, já que tem notícias dele há semanas), pensei que o caso estava basicamente encerrado. Nós o pegaríamos em algum lugar, mais cedo ou mais tarde. E, com sorte, teríamos nossa propriedade roubada devolvida, ou o equivalente por decreto.

## Rovion

Trabalhamos para construir uma nova infraestrutura de servidor em torno do que Bob havia tocado, supondo que seu trabalho em nosso sistema estivesse amplamente comprometido. Montamos uma nova arquitetura de nuvem com uma empresa que chamaremos de CloudCo.

Estamos em 4 de abril e estávamos quase prontos para entrar em operação com essa nova infraestrutura de nuvem. Então, as portas do inferno se abriram. Novamente.

Na quinta-feira, 7 de abril, por volta do meio-dia, notamos que houve um saque em Ethereum através da infraestrutura da CloudCo. A NOVA infraestrutura. A infraestrutura que ainda nem era pública. No início, acreditamos que nosso código tinha feito algo estranho, talvez levando fundos para um endereço de servidor de desenvolvimento ou similar. Então notamos que um monte de Bitcoins também estavam faltando, pior, uma quantidade considerável de Litecoin também.

Endereço Bitcoin do criminoso: `14Kt9i5MdQCKvjX6HS2hEevVgbPhK13SKD`

Endereço Ethereum do criminoso: `0xC26B321d50910f2f990EF92A8Effd8EC38aDE8f5`

Endereço Litecoin do criminoso: `LL9jqgXVqxUbWbWVaJocBcF9Vm8uS3NaTd`

E de repente realidade te atinge, e é assim quue ocorre o mesmo flashback. A sensação horrível de afogar em desespero se instala imediatamente, mais uma vez. O que diabos aconteceu?

Chaves que nem mesmo estavam em servidores conhecidos publicamente foram comprometidas de alguma forma. Desligamos o sistema, incluindo nosso site de produção ao vivo, enquanto investigávamos. Não perdemos tanto quanto o roubo de um mês antes, até porque havia reforçados certos protocolos,  ainda assim foi considerável. Não podíamos acreditar. Como novas chaves geradas com uma infraestrutura totalmente nova, podem ser comprometidas?

Após várias horas de investigação infrutífera, decidimos que uma das explicações mais prováveis é que a própria empresa de nuvem foi comprometida. Isso já aconteceu antes em Bitcoinland. Achávamos que a CloudCo era bem conceituada, mas quem sabe? Tecnologia em Cloud são muito convenientes e escaláveis, mas em algum nível você está confiando nessa empresa com sua infraestrutura. Decidimos que tínhamos que manter o site inativo por pelo menos 24 horas e nos arrasar para preparar, mais uma vez, uma infraestrutura inteiramente nova em um conjunto inteiramente novo de servidores.

O problema maior não era apenas o dinheiro perdido, mas sim não saber como isso aconteceu. Os logs não estavam como deveriam estar, logo, se provaram inúteis. Na verdade, eles foram apagados.

Apesar disso, observamos os blockchains dos fundos hackeados. Rastreamos alguns para uma conta de câmbio. Recebemos informações do perfil do depositante.

Nome: Rovion Vavilov
E-mail: rovion.vavilov@riseup.net
Endereço: Chayanova St. 15, Moscow
Nascimento: Feb 2, 1980
Telefone: +7 9625148445

As informações do perfil provavelmente eram falsas, mas enviei um e-mail para ele naquela noite.

De: Erik Voorhees erik@shapeshift.io
Para: rovion.vavilov@riseup.net
Assunto: ShapeShift Hack…

*“Belo hack. Como você fez isso? -Erik”*

Dica dos prós: Black hats gostam de ser reconhecidos por suas habilidades, independentemente de quão imorais suas ações possam ser. Fale com eles com calma, como adultos. Eles podem revelar informações ou ajudar de alguma forma. É estranho, mas acontece. Em qualquer caso, eu não esperava que nada viesse do meu e-mail.

Durante o resto daquela noite e no dia seguinte (sexta-feira, dia 8), a equipe trabalhou febrilmente para reconstruir tudo na nova infraestrutura, mais uma vez, em um ambiente totalmente limpo em um host totalmente separado.

Para muitos a ShapeShift parece executar um serviço simples. É necessário muito trabalho dos nossos engenheiros para manter essa aparência. Nos bastidores, a plataforma é complexa. Mais de 1.400 pares de negociação de ativos diretos, integrações com meia dúzia de APIs de câmbio exigindo informações de preços em tempo real em todas as criptomoedas oferecidas, APIs de serviço de baixa latência para várias dezenas de parceiros, monitoramento e cálculo de taxas de câmbio em constante mudança e profundidade da carteira de pedidos em alguns dos mercados mais voláteis da Terra, e incorporação do que só pode ser descrito como software de nível alfa em vários estágios 

É claro que em terra de Bitcoin não existe guia ou mapa. 

Reconheço que, como não sou engenheiro, só ocasionalmente posso vislumbrar a magnificência do que estamos construindo. Eu gostaria de poder levar o crédito. Para nossa equipe que está lendo isso, você projetou uma máquina incrível e deve estar muito orgulhoso dela.

É agora em que a história se aprofunda...

Por volta do meio-dia de sexta-feira, o hacker responde ao meu e-mail (lembre-se de que perguntei a ele como ele fez isso ...)

De: rovion.vavilov@fastmail.com (novo domínio)
Para: Erik Voorhees erik@shapeshift.io
Assunto: ShapeShift Hack…

*“Uma palavra: Bob”*

Esse foi todo o primeiro e-mail, mas ficamos chocados. Por um momento, pensamos: “Bob é o hacker?” Rapidamente, pensamos em uma resposta mais provável: que Bob vendeu ou deu nossas informações a um hacker, que então as explorou.

Bob nos traiu. Ele utilizou de sua posição privilegiada, lucrando diretamente com a destruição daqueles que confiavam nele. Ele roubou, mentiu, fugiu e, depois de um período longo o suficiente para refletir sobre suas ações, decidiu nos trair novamente por mais algumas migalhas. 'Hackers gonna hack', mas é preciso uma certa dose de maldade para ascender a uma posição de confiança, trabalhar cara a cara com uma equipe, receber um salário e a confiança dessa equipe e, em seguida, ferrar com todos eles por dinheiro que mal dá para comprar um Tesla. Ah, sim, e então abandone um cachorro para morrer de fome sozinho, provavelmente logo será sacrificado pelos serviços de defesa animal.

Cuidado com essas pessoas em suas vidas. Se você suspeitar deles, corte os laços rapidamente.

De qualquer forma, após esforços colossais, tudo estava pronto na noite de sexta-feira, 24 horas depois. Lançamos o site em um novo provedor, que chamaremos de HostCo. Apesar de alguns bugs o sistema estava funcionando. Havíamos falado ao público sobre o hack e decidido liberar mais detalhes assim que estudássemos o ambiente comprometido com mais detalhes posteriormente.

As trocas começaram a ocorrer. Soltamos um suspiro de alívio. Adormeci por volta da 1h da manhã e dormi pacificamente, exausto mentalmente e muito orgulhoso da equipe.

Era sábado, 9h, e comecei a acordar. Meu telefone toca. Era Greg.

“Fomos hackeados novamente. Mais Bitcoin e Ethereum retirados das carteiras na HostCo. ”

Eu estava em silêncio na ligação, somente conseguia pensar: "Isso é a porcaria do apocalipse?!?"

Não parecia possível. O hack de dois dias antes não parecia possível, e isso agora era imensamente confuso e deprimente. Disse ao Greg para tirar o site do ar novamente e que entretia em contato em 30 minutos. Como vamos explicar isso para a comunidade, para nossos clientes ... para nossos investidores? Como podemos explicar isso para nós mesmos?

Eu levanto da cama, não em pânico,  apenas me sentindo totalmente derrotado. Eu tomo o pior banho da minha vida. A raiva me cerca ... sabíamos que Bob estava envolvido com o e-mail do hacker e sabíamos que Bob cometeu um crime grave contra nós, que as autoridades sabiam há cerca de três semanas, e nosso investigador particular forneceu todas as informações necessárias para uma condenação imediata. E agora isso acontece, novamente.

Enquanto organizava meus pensamentos, decido que é hora de recorrer a recursos profissionais.

Michael Perklin, chefe de segurança e serviços investigativos do Ledger Labs, e presidente do comitê diretor do conselho do CCSS, é o primeiro da minha lista. Ele está em Toronto e concorda em voar para nos encontrar naquela noite. Ele estava a caminho do hospital; ele quebrou um dedo do pé em um evento que prefere não discutir. Ele muda de curso e segue para o aeroporto. Ele é um campeão.

Também converso mais com os chefes de várias bolsas importantes. Nenhum deles gosta de ladrões e está ansioso para ajudar. Apesar de seu ritmo frenético e da diversidade de opiniões e interesses, esse setor se reúne quando é necessário.

1500 ETH foram recuperados, e as corretoras estão procurando por mais. O ladrão provavelmente está chateado com isso ... é uma pena ser roubado, afinal.

## Fogo cruzado

Paralelamente a tudo isso, volto-me ao e-mail do ladrão. Eu respondi aquela mensagem “Uma palavra: Bob” perguntando se ele poderia fornecer mais informações. Ele menciona que, por um preço, ele pode.

“Olá” diz o hacker.

Eu proponho pagá-lo 2 BTC para obter informações.

“Preciso saber qual é a sua relação com Bob”, pergunto. Tentei evitar detalhes antecipados.

Ele responde: “Recebi a informação de que Bob estava “hackeando” você enquanto eu tentava hackear você também. Eu obtive acesso antes de Bob, mas não o suficiente para pegar as moedas sozinho. ”

“O que você sabe sobre o roubo do Bob?”, perguntei.

“Trabalho interno. 315 BTC. ” ele responde. “Conversei com Bob depois que ele roubou aos fundos  e perguntei como eu poderia hackear também. Ele me deu informações sobre a infraestrutura e algumas chaves. ”

Eu pergunto: “Por que ele lhe daria informações e o que ele deu a você?”

Rovion responde: “Porque eu ofereci BTC. Endereços IP, funções de servidor, usuários, uma chave SSH funcional. Não funciona mais.”

Conversamos um pouco mais e ele revelou o e-mail de Bob, com o qual se comunicou: m0money@gmail.com.

Embora eu não tivesse visto aquele e-mail antes, parecia familiar. Pensei um pouco e então percebi que Bob costumava substituir os 0's por os, inclusive em uma das duas chaves que ele havia excluído do servidor (a chave específica tinha um nome que, se exibido, revelaria o nome real de Bob) . Isso e o fato de que uma das variações de senha comuns de Bob era "m0m0ney". Um DevOps usou l33tspeak em suas senhas. Realmente "seguro".

Por mais claro que estivesse que Bob roubou nossos fundos algumas semanas antes, agora estava claro que esse hacker, Rovion, estava nos dando informações relacionadas a Bob que apenas Bob ou aqueles com quem ele realmente interagiu saberiam.

Uma outra linha de pensamento que possuo é que este hacker poderia realmente ter incriminado Bob desde o início. Mas as ações de Bob em 14 de março tornam essa explicação mais distante, especificamente Bob porque excluiu suas próprias chaves bem debaixo de nosso nariz e depois deixou o escritório, para nunca mais voltar. Outras evidências não listadas aqui vão contra essa teoria.

De volta ao bate-papo com Rovion… Eu pergunto qual “chave SSH funcional” ele obteve. “Não é da sua conta”, ele responde, “mas ele me disse que comprou de um laptop aberto de um colega de trabalho”.

Uau. Se for verdade, isso significa que Bob, enquanto trabalhava no ShapeShift, acessou o computador de um colega de trabalho e copiou uma chave (ou mais?) em algum momento antes de roubar os fundos. Eu me pergunto se ele premeditou a coisa toda. 

Tento obter mais informações, mas Rovion não colabora mais. Sua última mensagem ...

> “Seus milhões irão salvar sua pele, Erik Voorhees. Adeus, estarei no e-mail.”

No início da noite, nosso investigador forense, Michael Perklin, havia chegado. Eu o busquei no aeroporto. Havíamos decidido adiar as pesquisas em nossos servidores até que ele estivesse lá. Embora o hacker tenha dado uma vaga noção de como ele obteve informações secretas, não sabíamos realmente os detalhes da violação. As chaves foram alteradas após a partida de Bob e, embora tenhamos encontrado uma chave que não nos lembramos de alterar, ela só tinha acesso a um servidor que não poderia ter roubado os fundos na quinta-feira anterior. E, novamente, não explicaria como ocorreu o roubo na manhã de sábado. Tanto a CloudCo quanto a HostCo tiveram fundos roubados, apesar de terem sido construídos como ambientes inteiramente novos com chaves totalmente novas.

Michael me solicitou todo o histórico do mês passado. Ele prosseguiu com seu protocolo de investigação, que incluía a suposição de que ninguém na empresa era confiável. Era difícil argumentar que a equipe era confiável, visto que tudo começou com um funcionário desonesto. Foi uma sensação deprimente.

Muitos detalhes interessantes podem ser adicionados aqui sobre como esse trabalho forense é feito, mas o espaço é limitado e provavelmente não é aconselhável revelar cada um desses métodos. Depois de um tempo, mergulhamos nos logs, analisando primeiro os logs de sábado. Eles foram excluídos, a maioria deles. Como eles foram excluídos? Não tínhamos certeza.

Agora sabemos como evitar isso ... na verdade, a experiência que recebemos ao longo deste incidente foi imensamente valiosa. Embora pareça clichê, se a sua startup está envolvida na proteção de informações ou servidores de qualquer natureza, faça um favor a si mesmo e traga ajuda profissional terceirizada o mais breve possível. Não precisávamos disso tudo no início porque éramos pequenos. Mas o crescimento se aconteceu e, antes que percebessemos, estávamos garantido ativos significativos utilizando métodos abaixo dos padrões.

Embora muitos dos logs tenham desaparecido, na verdade, recuperamos uma grande parte deles do próprio espaço em disco “vazio” usando técnicas forenses. Isso foi apenas sorte. Talvez o fantasma de Satoshi estivesse cuidando de nós (Seria ótimo se pudéssemos contar com essa ajuda algumas semanas atrás!)

A partir dos dados recuperados, descobrimos o malware, se esse é o termo certo. Havia um programa, escrito em Go, instalado em um servidor crucial que se comunicava com moedas. Este programa teve suas datas alteradas para parecerem consistentes com a configuração do servidor, e seu nome de arquivo feito para parecer inócuo. Mas foi a ferramenta direta pela qual os fundos foram roubados.

udevd-bridge como é chamado.

Ficamos felizes em encontrá-lo (e sim, a mesma coisa apareceu em ambos os ambientes de servidor, CloudCo e HostCo). No entanto, ainda não sabiamos como foi colocado lá. Tínhamos muitas informações em mãos, porém, o caso ainda não estava solucionado.

Não enxergamos luz no fim do túnel durante semanas, mas como um vislumbre cósmico, as estrelas se alinharam.

Do nada, Rovion enviou um e-mail na quarta-feira, 13 de abril.

De: Rovion Vavilov rovion.vavilov@fastmail.com
Para: Erik Voorhees erik@shapeshift.io
Assunto: Re: ShapeShift

*“Você está interessado em comprar o ETH que tenho em mãos com um desconto generoso em troca de BTC? Estou disposto a negociar em pequenas quantidades, já que você não tem motivos para confiar em mim.”*

Sim, parece que o hacker ficou irritado porque seu Ethereum ficava congelado nas trocas. Então ele volta para a loja que roubou e nos pergunta se vamos trocar por um ativo mais líquido. Estaríamos essencialmente comprando de volta nosso próprio Ethereum e pagando Bitcoin a ele.

Obviamente, vale a pena, se pudermos obter mais informações. Como nenhum de nós confia no outro, estabelecemos um protocolo:

1) Pagaremos 2 BTC para iniciar a conversa
2) Rovion fornece a primeira metade de informações
3) Trocamos, em incrementos de 250, 2.000 ETH por BTC na taxa de 0,02 BTC / ETH
4) Rovion nos dá a segunda metade das informações relevantes
5) Trocamos, nos mesmos incrementos, os 2500 ETH restantes por BTC com a mesma taxa
6) Encerramos a comunicação (esta última foi sugestão de Rovion)

Ele nos pede para enviar o BTC para seu endereço BTC, já conhecido: 14Kt9i5MdQCKvjX6HS2hEevVgbPhK13SKD

Após o pagamento inicial de 2 BTC, Rovion começa com a descrição do hack de 7 de abril:

> “Entramos em contato com Bob. Ele nos deu o código-fonte principal da ShapeShift, o endereço IP do servidor principal e uma chave SSH. Efetuei login no servidor principal com a chave SSH fornecida, instalei um backdoor e peguei os fundos, pois, o servidor principal e com acesso SSH estava vinculado ao servidor das moedas.”

“Qual é a fingerprint da chave SSH mencionada acima?”, perguntei.

``“9c:3f:4b:ad:d6:43:ec:9a:55:de:b9:0b:d8:f5:0a:cb”``

Vemos que é a chave de Greg, recém-criada para o ambiente CloudCo. Ela foi criada depois que Bob roubou os fundos em março e desapareceu. Como esse hacker conseguiu uma nova chave, mesmo após o Bob partindo?

Também pergunto sobre o que foi “redigido por Bob” mas Rovion diz que faz parte do segundo lote de informações. Prosseguimos com a troca.

Então Rovion responde,

>“foi o acesso através do RDP instalado na máquina de um colega de trabalho por Bob. Foi assim que eu te hackeei pela segunda vez”

Uau, agora está começando a se encaixar, cada revelação removendo uma camada da traição de Bob. Bob instalou um RDP (protocolo de desktop remoto - basicamente um visualizador de tela ou controlador) no computador de Greg. E talvez em outros, suponoh.

Em seguida, Rovion compartilha via pastebin um e-mail de Bob:

> “Olá,
> 
> Recebi os 50 Bitcoins. Código-fonte e chaves estão no anexo deste e-mail.”
> 
> IP Principal: XX.XX.XX.XX
> 
> Roteador: XX.XX.XX.XX:XXXX
> 
> admin:[redacted password]
> 
> IP do RDP: XX.XX.XX.XX
> 
> acadmin:pass
> 
> grato por fazer negócios com você.
> 
> [2 anexos]

E aí está, Bob vendeu informações sobre os servidores de produção, acesso à rede interna do ShapeShift, parte do código-fonte da ShapeShift e acesso a um cliente RDP que ele instalou no computador de um colega de trabalho para Rovion, por 50 Bitcoin. 

Isso explica quase tudo. Com acesso ao computador de Greg (e talvez outros), via RDP, os novos ambientes de servidor podem ser escalados e novas chaves SSH podem ser usadas. Não foi culpa do CloudHost, foi nossa.

Havíamos alterado quase tudo, mas não descartado nossos computadores pessoais enquanto Bob fazia parte da equipe. Seria paranóia?  

Gostaria de compartilhar uma das últimas coisas que Rovion disse antes de encerrarmos a discussão,

> “Mesmo que eu tenha dito para interromper a comunicação, você ainda pode me enviar um e-mail para contar se o Bob foi processado ou sejá lá o que vocÊ for fazer? Eu acho que é uma merda roubar do seu próprio empregador.”

## Reconstruindo o santuário

Imaginamos que essa informação ajudará a demonstrar a intenção criminosa de  Bob. Não foi um plano repentino, mas sim uma traição orquestrada. Eu perdi a conta do número de crimes envolvidos.

Também sabemos que, embora a história de Rovion se confirme, pode muito bem não ser a história completa. Temos que assumir que outros detalhes são relevantes para o caso e para nossa infraestrutura. É por isso que a ShapeShift está offline há mais tempo do que qualquer um de nós gostaria. Estamos sendo muito cuidadosos neste momento, beirando a paranóia.

Mesmo assim, estou imensamente orgulhoso de minha equipe. Trabalhar em uma startup, na indústria de Bitcoin, é estressante o suficiente, ter que lidar com uma série de problemas em todas as esferas, além dee todos os danos (financeiros, técnicos, psicológicos) que isso acarreta ... Não é fácil, é difícil. Vocês fizeram um trabalho incrível e estou imensamente encorajado e motivado em ver a coesão e força da nossa equipe.

Contratamos quatro novos colaboradores na mesma semana dos dois incidentes (dobrando nossa equipe de desenvolvimento). Eles estão no olho do furacão e são incríveis.

## Usuários ShapeShift não foram afetados

Para sobreviver no universo do Bitcoin, é preciso ser otimista. Embora a traição, a perda e o esforço de limpeza tenham sido terrivelmente desgastantes, existem alguns pontos positivos.

Primeiro, nenhuma pessoa ou organização é perfeita. Aprendemos algumas de nossas vulnerabilidades e nossos próprios erros. Estamos corrigindo-os e aprimorando-os. Essa melhoria não sai barata, mas a ShapeShift de hoje é melhor do que o ShapeShift de ontem. O aço é temperado e a está máquina refinada. Embora nenhuma organização possa alcançar a perfeição, tentamos abordar a anti-fragilidade e exemplificá-la como um ideal em nosso trabalho.

Em segundo lugar, nenhum cliente perdeu dinheiro mesmo a após ShapeShift sofrer vários hacks orquestrados por um agente interno. Utilizando de protocolos descentralizados e códigos avançados, além de muita estrutura, desenha-se o layout de proteção ao consumidor, uma das contribuições mais importantes desta indústria para a sociedade - algo que em um século nenhum banco tradicional  conseguiu alcançar, conforme observado pela infame linhagem de Satoshi no Bloco Genesis.

A ShapeShift sempre trabalhará para desenvolver esta plataforma de proteção ao consumidor. Muitos outros nesta comunidade estão fazendo o mesmo em caminhos diferentes. Obrigado pelas ferramentas que vocês estão construindo e pelo trabalho que está sendo desenvolvido. E, de fato, ainda há muito a fazer.

Aos nossos clientes, gostaria de pedir desculpas pessoalmente pelo nosso tempo de inatividade. Embora possamos garantir que seus fundos não corram risco, sei que muitos dependem de nosso serviço e ele não está disponível. Um plano de contingência, mesmo diante de um desastre, será uma de nossas principais metas de desenvolvimento daqui para frente.

Além disso, agradeço sinceramente todas as comunidade que estenderam a mão e ofereceram qualquer tipo de apoio, principalmente aos nossos investidores, que foram extremamente gentis e compreensivos.

E, finalmente, como acontece em todos os episódios intensos que alguém enfrenta, devemos valorizar o espaço e a oportunidade de crescimento, de experiência e de um dos luxos mais preciosos da vida: a reflexão.

Nunca é um dia entediante na universo do Bitcoin.

> *Para Bob ... Observe que seu nome real e informações de identificação não foram divulgados. Considere isso uma cortesia final.*

Erik Voorhees, CEO da ShapeShift, 19 de abril de 2016.

- bounty: true
- amt: 30
- signedBy: 0xef4fd55584434903aa6fc9baa61eacdde5355da0
- hash: 0x0000
{.is-hidden}
