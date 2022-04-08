# Swagger: documentando suas APIs
iniciado em 07/04/2022

terminado em ANDAMENTO

[certificate]() 

- [Swagger: documentando suas APIs](#swagger-documentando-suas-apis)
  - [Swagger](#swagger)
  - [Entendendo o Swagger](#entendendo-o-swagger)
  - [OpenAPI](#openapi)
  - [Para saber mais](#para-saber-mais)
  - [Swagger Editor](#swagger-editor)
  - [o que aprendemos?](#o-que-aprendemos)
  - [informaçoes da API](#informaçoes-da-api)
  - [adicionando links](#adicionando-links)
  - [Complementando infos](#complementando-infos)
  - [Para saber mais: Info Object](#para-saber-mais-info-object)
  - [o que aprendemos?](#o-que-aprendemos-1)
  - [Recursos e verbos](#recursos-e-verbos)
  - [possiveis respostas](#possiveis-respostas)
  - [Parametros na requisicao](#parametros-na-requisicao)
  - [dados no corpo da requisiçao](#dados-no-corpo-da-requisiçao)
    - [conteudo do corpo](#conteudo-do-corpo)
  - [o que aprendemos?](#o-que-aprendemos-2)
  - [definindo tipos](#definindo-tipos)
    - [componentes](#componentes)
  - [definindo objetos](#definindo-objetos)
  - [Referenciando tipos](#referenciando-tipos)



## Swagger
O Swagger fornece um conjunto de ferramentas, dentre eles: Swagger Editor para escrevermos a documentação da API, Swagger UI para disponibilizarmos essa documentação e Swagger Codegen para gerar código a partir da documentação.
  

## Entendendo o Swagger
[00:00] Bem-vindos de volta. Antes de começarmos a fazer qualquer coisa, vamos entender o que é Swagger, o que é esse nome, o que esse nome significa e o que ele nos fornece. Vamos lá, quando entramos no site "swagger.io", temos a seguinte chamada "API Development for Everyone".

[00:21] Então, o que o Swagger faz é simplificar o desenvolvimento de APIs de alguma forma. Ele possui várias formas para fazer isso, para simplificar e para nos ajudar desenvolver e documentar APIs, só que iremos focar nessa parte de documentação. Nós já temos uma APIs desenvolvidas, iremos utilizar uma API de exemplo, mas vamos focar na documentação dessa API que já existe.

[00:48] O Swagger nos fornece algumas ferramentas, um editor de documentação, uma visualização dessa documentação, utilizando um formato específico, ele fornece um gerador de código baseado nessa documentação. Vamos dar uma olhada rápida clicando em "Explore Swagger Tools" na página inicial do site, para explorar as ferramentas do Swagger.

[01:11] Ele nos mostra as três ferramentas open source que ele tem. Ou seja, essas ferramentas são gratuitas e de código aberto. Se eu voltar para página inicial do site e rolar para baixo, podemos ver no centro da página a opção "Open Source Tools", veremos exatamente as mesmas três ferramentas, o "SwaggerEditor, Swagger UI e o Swagger Codegen", codegen de code generator.

[01:32] Então o Editor ele permite que desenvolvamos, que escrevamos a documentação da API, que façamos o design da nossa API. Ele ajuda na modelagem de uma API, se ainda tivermos pensando em como vai ser, e na documentação caso essa API já exista, iremos usar bastante ele.

[01:50] Existe o Swagger UI para você fornecer um ambiente visual do que criamos com o Swagger Editor, basicamente. Então imagina que você documentou toda a sua API, está todo modelado, e que você queira fornecer isso como documentação para o cliente que vai utilizar a sua API. Você pode fornecer através do Swagger UI, já vamos ver isso tudo, na prática, estamos apenas entendendo as ferramentas.

[02:12] Nesse treinamento trabalharemos o tempo todo com o Swagger Editor e vamos dar uma olhada nos Swagger UI. “Vinicius, e o Codegen, por que que não iremos utilizar?” Porque para utilizar ele eu ia precisar escolher alguma linguagem, porque se dermos uma olhada nele, ele pode gerar servidores ou clientes para diversas linguagens, como as "aspnet5, aspnetcore, erlang, PHP, node, phyton,".

[02:40] Então ele consegue gerar código em muitas linguagens, com muitas tecnologias e eu precisaria escolher uma, ou algumas linguagens para fazer isso, com certeza ia deixar alguma de fora. Por isso, não iremos entrar nessa parte, mas essa parte aqui depende do conhecimento que nós aprenderemos na hora de fazer o design de uma API, ou a documentação de uma API.

[03:00] Recapitulando, o que é Swagger, para finalizarmos. O Swagger é, basicamente, um conjunto de ferramentas que nos ajuda a fazer o design, ou seja, fazer a modelagem, a documentar e até gerar código para desenvolvimento de APIs. Iremos escrever a documentação? Como fazemos com essa documentação?

[03:21] Porque temos um meio Editor, então, teoricamente, vamos editar usando algum formato. E é exatamente sobre o formato que iremos utilizar que eu vou conversar com próximo vídeo, mas ainda sem colocar a mão na massa.

## OpenAPI
[00:00] Bem-vindos de volta, logo começaremos a escrever realmente um arquivo em um formato específico, mas antes de escrevermos, eu quero só pincelar que formato é esse, como que sabemos quais são os valores que pode colocar lá, ou não.

[00:15] Então o Swagger é uma ferramenta, um conjunto de ferramentas, e ele trabalha em cima de uma especificação, que a "OpenAPI Specification". Então vamos para a página inicial do Swagger, e se rolarmos para baixo temos a "OpenAPI Specification". Existe uma especificação de como você pode modelar APIs, como você pode documentar o design de uma API.

[00:40] Então essa nos diz que podemos ter informações de uma API, os caminhos ou os end pointsdessa API, e cada end point tem seus verbos. Temos informações de componentes, como os esquemas, componente de segurança, podemos ter tags para organizar, enfim, tem muita coisa nessa especificação.

[01:00] É utilizando essa especificação que escrevemos a nossa documentação, que escrevemos o documento através do Swagger Editor para o Swagger UI renderizar. Vamos só dar uma olhada na página do "OpenAPI Specification", não vou passar em toda a especificação, porque era gigante. Então seria impossível e seria muito maçante, vamos só dar uma olhada.

[01:21] Existem duas versões mantidas hoje, a versão "2.0", bastante famosa, e a mais recente, a 3.0, que utilizaremos. Então na página do "OpenAPI Specification" eu vou clicar na opção "3.0", temos uma versão simplificada que p Swagger fornece em seu próprio site. Mas se você acessar a internet e pesquisar a "OpenAPI Specification" você vai ter a especificação oficial, completa.

[01:42] Mas eu gosto bastante de como o Swagger organizou, com a interface do Swagger. Então sempre que eu precisar acessar a referência de alguma coisa, sempre que eu precisar acessar a documentação da especificação, vou acessar através do site do Swagger. Mas deixarei no "Para saber mais", o site oficial da especificação.

[01:59] Então a página faz umas introduções, explica que existe um documento que descreve uma API, logo teremos um documento, um arquivo que descreve algo que uma API faz. Seus end points, as suas rotas, os métodos de cada rota, os verbos da rota, enfim, tudo isso iremos conseguir utilizando essa especificação.

[02:22] Temos que a parte das versões do OpenAPI e conseguimos ver a especificação em si, a estrutura do documento. Então temos tipos de dados, nós temos os esquemas, o que conseguimos informar em cada uma das partes. Por exemplo, na hora de eu passar informações sobre API, eu posso vir aqui nesse Info Object e eu sei que posso ter um título, uma descrição de termos de serviço, contato, etc.

[02:50] Em cima disso que iremos trabalhar, desses campos que a especificação fornece. Se eu estou falando muito e essas coisas não estão ficando muito claras, então vamos parar um pouco com a teoria e no próximo vídeo vamos ver na prática. Como é esse visual do Swagger Editor, o que é Swagger UI, um pouco mais na prática. Então, vamos ver como essas ferramentas funcionam no próximo vídeo.

## Para saber mais
OpenAPI é a especificação utilizada pelo Swagger. No próprio site do Swagger há uma versão da especificação para consulta, mas caso você queira a versão "oficial" da especificação, pode consultar: https://www.openapis.org/

No momento da escrita desta atividade a última versão é a 3.1.0 e pode ser conferida aqui: https://spec.openapis.org/oas/v3.1.0

## Swagger Editor
[00:00] Bem-vindos de volta, vamos entender o que é o Swagger Editor e como ele se relaciona com Swagger UI. Na página inicial do "swagger.io > Explore Swagger Tools > Swagger Editor ", exploraremos as ferramentas do Swagger. No editor do Swagger, temos algumas opções, podemos tentar no ambiente nuvem com o "SwaggerHub". Então existe um suporte um pouco mais enterprise, vamos dizer assim, tem uma versão paga.

[00:30] Podemos baixar o Swagger para nossa máquina, seja utilizando um container do docker, ou baixar o código-fonte e subir um servidor. Ou podemos utilizar uma versão que o próprio Swagger deixa disponível. Então para não precisarmos instalar nada agora, para já começarmos direto, vamos utilizar o "Live Demo".

[00:46] O interessante desse Live Demo é que quando eu clico nele, ele já tem uma especificação pronta, já tá com muita coisa pronta para entendermos como funciona. Vamos só passar o olho para entender o que ele está nos mostrando. No canto esquerdo temos a interface do Swagger Editor, que é a parte em que nós realmente iremos escrever, iremos editar alguma coisa.

[01:09] Então, por exemplo, se eu for até a linha "description" e modificar, colocar o texto "isso é uma descrição", no canto direito da página, sem fazer nada, ele já vai atualizar. No lado direito é exatamente o que o Swagger UI tem.

[01:25] Então se eu voltar na página inicial do Swagger e entrar na página Swagger UI e acessar o Live Demo. Veremos que é exatamente o Swagger Editor, mas sem a parte da esquerda, então será apenas a parte da UI.

[01:41] O cliente, a pessoa que está olhando sua API, está vendo documentação dela, pode ver todos os end points, ver todos os componentes, ou seja, cada um dos modelos da sua API. Pode fazer alguns testes reais, então ele pode clicar no botão "Try it out" e testar essa API, para isso, ele pode precisar autorizar, ou não.

[01:58] É bastante interessante, e no Editor temos essa parte já embutida. Nesse caso, o que faremos durante esse treinamento? Nós vamos documentar uma API, utilizando o Swagger Editor online, e veremos tudo sendo refletido do lado direito da página. Então, de forma bem simples, iremos documentar uma API já existente e ver como a documentação seria vista no Swagger UI em tempo real.

[02:23] Antes de começarmos, eu quero mostrar um detalhe bem interessante, principalmente para quem já tem alguma documentação no Swagger, ou algo assim. No meu caso, na primeira linha, podemos perceber que ele está utilizando a versão 2.0, que é a versão 2.0 do OpenAPI também. Então, eu posso facilmente vir aqui na aba " Edit > Convert to OpenAPI 3". Assim, eu vou converter esse documento que está no formato do Swagger 2.0 para especificação o OpenAPI na versão três.

[02:53] Ele modificou um pouco o documento, mas o resultado é praticamente o mesmo, ele só recebe um selo a mais, informando que ele está utilizando a OpenAPI Specification. Ou seja, especificação real, sem nenhuma modificação do Swagger e na versão3. Agora que já entendemos o que é o Swagger Editor, já estamos prontos para documentar uma API. Podemos brincar um pouco com o Editor.

[03:18] A nossa descrição já foi modificada, posso mudar o contato, mudar a licença, entre outros. Mas, o que faremos realmente é apagar tudo, então vamos à barra de ferramentas," File > Clear Editor". Com a página limpa, no próximo capítulo vamos começar a documentar uma API nossa, uma API já existe.

[03:35] É uma API de testes, então não vamos precisar desenvolver nenhum código, ela já está online. Através desse ambiente completamente online, sem precisar instalar nada na máquina, começaremos a documentar uma API, mas de novo, no próximo capítulo. [00:00] Bem-vindos de volta, vamos entender o que é esse tal de Swagger Editor e como ele se relaciona com Swagger UI. Então vamos para a página inicial do "swagger.io > Explore Swagger Tools > Swagger Editor ", iremos explorar as ferramentas do Swagger. No editor do Swagger, temos algumas opções, podemos tentar no ambiente nuvem com o "SwaggerHub". Então existe um suporte um pouco mais enterprise, vamos dizer assim, tem uma versão paga.

[00:30] Podemos baixar o Swagger para nossa máquina, seja utilizando um container do docker, ou baixar o código-fonte e subir um servidor. Ou podemos utilizar uma versão que o próprio Swagger deixa disponível. Então para não precisarmos instalar nada agora, para já começarmos direto, vamos utilizar o "Live Demo".

[00:46] O interessante do Live Demo é que quando eu clico nele, ele já tem uma especificação pronta, já tá com muita coisa pronta para entendermos como funciona. Vamos só passar o olho para entender o que ele está nos mostrando. No canto esquerdo temos a interface do Swagger Editor, que é a parte em que nós realmente iremos escrever, iremos editar algo.

[01:09] Por exemplo, se eu for até a linha "description" e modificar, colocar o texto "isso é uma descrição", no canto direito da página, sem eu fazer nada, ele já vai atualizar. No lado direito é exatamente o que o Swagger UI tem.

[01:25] Então se eu voltar na página inicial do Swagger e entrar na página Swagger UI e acessar o Live Demo. Veremos que é exatamente o Swagger Editor, mas sem a parte da esquerda, então será apenas a parte da UI.

[01:41] O cliente, a pessoa que está olhando sua API, está vendo documentação dela, pode ver todos os end points, ver todos os componentes, ou seja, cada um dos modelos da sua API. Pode fazer alguns testes reais, então ele pode clicar no botão "Try it out" e testar essa API, para isso ele pode precisar autorizar, ou não.

[01:58] Então é bastante interessante, e no Editor temos essa parte já embutida. Nesse caso, o que faremos durante esse treinamento? Nós vamos documentar uma API, utilizando o Swagger Editor online, e veremos tudo sendo refletido do lado direito da página. Então, de forma bem simples, iremos documentar uma API já existente e ver como a documentação seria vista no Swagger UI em tempo real.

[02:23] Antes de começarmos, eu quero mostrar um detalhe bem interessante, principalmente para quem já tem alguma documentação no Swagger, ou algo assim. No meu caso, na primeira linha podemos ver que ele está utilizando a versão 2.0, que é a versão 2.0 do OpenAPI também. Então, eu posso facilmente vir aqui na aba " Edit > Convert to OpenAPI 3". Assim, eu vou converter esse documento que está no formato do Swagger 2.0 para especificação o OpenAPI na versão três.

[02:53] Ele modificou um pouco o documento, mas o resultado é praticamente o mesmo, ele só recebe um selo a mais, informando que ele está utilizando a OpenAPI Specification. Ou seja, especificação real, sem nenhuma modificação do Swagger e na versão3. Agora que já entendemos o que é o Swagger Editor, já estamos prontos para documentar uma API. Podemos brincar um pouco com o Editor.

[03:18] A nossa descrição já foi modificada, posso mudar o contato, mudar a licença e etc. Mas o que faremos realmente é apagar tudo, então vamos à barra de ferramentas "File > Clear Editor". Com a página limpa, no próximo capítulo vamos começar a documentar uma API nossa, uma API já existe.

[03:35] É uma API de testes, então não vamos precisar desenvolver nenhum código, ela já está online. Através desse ambiente completamente online, sem precisar instalar nada na máquina, começaremos a documentar uma API, mas de novo, no próximo capítulo.

## o que aprendemos?
* aprendemos o que é o swagger
* vimos como o swagger pode nos ajudar no desenvolvimento de APIs
* aprendemos como funcionao swagger editor

## informaçoes da API
[00:00] Boas-vindas a mais um capítulo do treinamento de Swagger. Vamos começar documentar uma API, mas qual API se eu não desenvolvi nada, nem tenho nenhuma API. O que eu vou fazer para, de novo, não precisarmos escolher uma linguagem e te obrigar a instalar o Node, o Java, o PHP ou qualquer coisa do tipo. O que eu fiz foi criar uma mock API, uma API de mentira, através do site "mockapi.io"

[00:24] E eu tenho os campos "médicos" e "especialidades". Eu tenho já cadastrada uma especialidade teste e tenho um médico chamado médico 1 com o CRM 12345, que está na especialidade 1 (especialidade dele é a com o ID 1). Logo, eu tenho um dado para cada uma dessas informações.

[00:44] Ou seja, há uma API existente que eu consigo acessando o editar, ao lado do campo editável. Consigo acessar todos os end points, ou seja, eu consigo buscar todas as especialidades, buscar uma especialidade, cadastrar uma nova especialidade, editar uma especialidade remover uma especialidade. Mesma coisa com médicos, ou seja, tem dois CRUDs.

[01:06] Poderia relacionar eles de alguma forma um pouco mais robusta, etc., mas eu não quero focar nessa parte. Então o que eu quero fazer começar a documentar essa API e antes de falarmos sobre especialidades, médicos, inserir médico, atualizar especialidade, precisamos escrever a API em si. Vamos chamar essa API de uma API de consultório.

[01:27] Então vamos começar com isso, dando um título para nossa API, descrevendo-a de alguma forma, só que no nosso Swagger Editor, precisamos informar qual formato estou utilizando. Como vimos no início do Swagger 2.0 ou OpenAPI 3.0. Então vamos fazer isso, eu vou utilizar o OpenAPI e eu posso começar a escrever e clicar em "Ctrl + Espaço", ele mostra as opções que posso colocar.

[01:53] Ele não consegue entender, ele não consegue renderizar essa definição, porque ele precisa ser um desses valores que aparecem na tela, o swagger: 2.0, openapi: 3.0.0. Então vamos utilizar o openapi: 3.0.0, que é aquela versão que já estava como padrão. Ele nos mostrando alguns erros, o primeiro é que existe uma propriedade obrigatória chamada info.

[02:16] Então vamos adicionar essa info na nossa chave, e quando colocamos o info, outros erros vão aparecer. Primeiro tem um erro estrutural na minha propriedade info, porque ela precisa ser um objeto, ou seja, preciso ter mais propriedades em info.

[02:30] E o formato que estamos utilizando, acredito que é interessante citar que, com o Swagger Editor, nós podemos editar um arquivo em Json ou em Yaml. Eu acho Yaml um pouco mais interessante para escrever, para ler e visualizar, então eu vou continuar com ele, se você quiser pode converter para Json. Mas eu vou manter o Yaml.

[02:52] Então vamos lá, em info eu uso identação para informar que o que eu vou escrever agora está dentro de info. Vou dar dois "Espaços" e informar o título da nossa API, a chave title:. Que eu posso colocar, por exemplo, uma API de consultório, eu poderia criar um nome criativo para essa API, mas não vou. Repara que já começa a aparecer no lado direito a nossa documentação, eu posso esconder os erros se eu quiser clicando em "Hide" no canto direito, mas eu vou deixá-los aqui.

[03:17] O que mais além do título eu posso ter? Posso ter descrição, eu começo a escrever a palavra, "Ctrl + Espaço > description" e escrevo API para controlar médicos e suas especialidades dentro do consultório, tenho a nossa descrição da API. Conforme eu vou digitando, ele já vai atualizando do lado direito.

[03:40] Para finalizarmos esse vídeo, que eu já falei bastante, vamos adicionar mais uma informação. A nossa API pode ter versões, eu posso versionar a minha API. Então olha essa é a documentação da versão 0.0.1 da minha API, que é uma versão Alpha. Posso adicionar a chave "version: 0.0.1".

[03:57] Então já tenho, praticamente, toda a definição obrigatória da API em si. Ou seja, eu tenho um título para ela, eu tenho uma descrição e o informei a versão. Então agora ela já começou a ser renderizada de forma correta, só que tem um detalhe ainda, eu não tenho caminhos, não tenho end points para essa API.

[04:17] Mas antes de descrevermos os end points, por exemplo, especialidades e médicos, vamos ver o que mais podemos informar sobre a API em si. Já temos todos os dados obrigatórios, mas podemos informar mais coisas como, por exemplo, links externos, um endereço de contato, licença dessa API e muito mais. Vamos conversar sobre esses detalhes no próximo vídeo.

## adicionando links
[00:00] Bem-vindos de volta. Conforme comentei, antes de definirmos end points, chamado aqui de paths, vamos definir algumas informações a mais sobre nossa própria API, então podemos adicionar algumas coisas que vão ser apresentados com links. Por exemplo, eu posso colocar uma documentação externa, eu posso colocar os termos de serviço.

[00:23] Vamos adicionar exatamente isso. Eu não tenho termos de serviço reais para essa API, até porque ela nem existe. Mas vamos colocar um link mentira, um link falso. Então posso adicionar a chave terms “Ctrl + Espaço" que o Swagger Editor completa a chave automaticamente.

[00:40] Nessa chave "termsOfService" eu vou adicionar um link, que vai redirecionar a pessoa a uma página quando ela clicar em TermsofService. Então vou colocar https://mockapi.io, quando ele salvar já aparece o TermsofService no lado direito da página.

[00:55] Seu eu abrir o link TermsofService no lado direito em uma nova guia, ele vai abrir a página "mockapi.io". Então como eu estou logado, ele já abre na área de projetos, vou fechar essa guia e voltar par ao Editor.

[01:09] Eu posso adicionar documentação externa, imagina que eu tenho essa documentação viva, onde a pessoa tem acesso a todos os end points, ela pode testar em tempo real e que eu tenho outra documentação, um pouco mais formal. Com um texto super extenso, explicando o propósito de cada coisa, um motivo para algo existir, ou ainda como você pode conseguir a chave de acesso, etc.

[01:34] Então se eu tenho uma documentação externa, além Swagger eu posso adicionar. Só não na parte de info, vou adicionar outra chave, outro valor na raiz desse documento. O que eu quero dizer com raiz, na raiz, até o momento, eu tenho o openapi, info e agora vou ter externalDocs. Ou seja, uma documentação externa.

[01:55] Essa documentação externa, quando eu adiciono apenas a chave, aparece um erro no lado direito da tela, que nos diz que ela precisa ser um objeto, então ela tem outras propriedades. Que propriedades são essas? Quando dou um "Ctrl + Espaço" ele vai mostrar as opções description ou URL.

[02:08] Ou seja, a descrição dessa documentação externa, que o que vai ficar escrito, e a URL que exatamente o link. Eu posso escrever nessa chave "Documentação burocrática", então algo que faça sentido para a sua API. Já na URL, que é obrigatório eu posso colocar também aquele mesmo link, https://mockapi.io, e vai aparecer para nós no lado direito da tela "Documentação burocrática".

[02:30] De novo, seu eu abro o link "Documentação burocrática" em uma nova guia, ele vai abrir o link do MockAPI. Dessa forma conseguimos adicionar links, eu consigo adicionar termos de serviço, eu consigo adicionar documentação externa, eu poderia colocar qualquer coisa aqui, mesmo que não fosse uma documentação externa.

[02:46] Como, por exemplo, o site para os nossos planos, "saiba mais sobre nossos planos" como um link acessível. Você pode colocar qualquer coisa, então temos acesso a uma descrição e a uma URL. Vou deixar escrito “Documentação burocrática” mesmo, porque podemos fingir que é só uma documentação externa.

[03:03] Já vamos avançando na definição da nossa API, assim existe uma infinidade do que podemos fazer aqui, então não quero me estender muito. Mas no próximo vídeo eu vou adicionar só um pouco mais detalhes. Por exemplo, informações de contato, para quem a pessoa vai enviar um e-mail se tiver algum problema?

[03:20] E a licença, esta API pode ser utilizado por qualquer pessoa? É uma API pública ou é uma exclusiva? Qual a licença dessa API, como a pessoa vai saber como ela pode utilizar. Então que adicionar essas duas informações no próximo vídeo.

## Complementando infos
[00:00] Bem vindos de volta. Como eu disse, quero adicionar algumas informações a mais para essa API. Primeiro, a licença, ou seja, como a pessoa pode utilizar a API, e algum dado de contato. Vamos começar pelo contato, se eu começar a escrever contato e apertar em "Ctrl + Espaço" para completar, eu posso adicionar um contato diretamente, e eu vejo que contato também é um objeto.

[00:20] O contrato ele pode ter um nome, um e-mail e uma URL. Vamos começar com o nome, vou colocar nome: Suporte a Devs. E esse suporte a devs vai ter comente um e-mail, que vai ser email: contato@example.com. Então vai aparecer no lado direito da tela a opção "Contact Suporte a Devs" e se eu clicar, ele vai abrir algo de e-mail para enviar um e-mail para lá.

[00:49] Se eu quiser ter uma URL, eu posso ter uma, url: https://mockapi.io. No lado direito já aparece o website, ou seja, o link para este Suporte a Devs ou enviar um e-mail para o Suporte a Devs. Então conseguimos ter essas duas informações quando estamos falando sobre contatos. Ou um Website, ou um e-mail ou ambos.

[01:15] Então já temos as informações de contato, eu quero adicionar uma licença, eu quero informar que essa API tem como licença a GPL 3 que é General Public License, alguma coisa assim. Eu posso adicionar uma license:, e a licença também é um objeto, ela tem o nome da licença e a URL da licença. Vamos começar com o nome, que vai ser nome: GPLv3 e a URL desta licença é esse link, url: https://www.gnu.org/licenses/gpl-3.0.html.

[01:46] Se eu clicar nesse link ele abre o site da GNU, em específico da "General Public License". No lado direito é possível perceber que licença é essa. Já aparece o link para a pessoa acessar, ler e saber tudo que ele precisa em relação à licença da nossa API. Eu posso escrever o que eu quiser no license, não é obrigatório estar escrito o nome da licença específico, mas obviamente faz sentido que o utilize.

[02:19] Posso ainda colocar como name: "Licença: GPLv3", entre aspas para aparecer os dois pontos, informando que a licença é a GPLv3. Dessa forma conseguimos ter vários links de apoio na nossa API, além da descrição, título, versão e claro, temos informações extras.

[02:37] Já coloquei um monte de links nessa documentação, mas tem um erro continua aparecendo. Eu quero definir o que essa API faz realmente, eu quero definir os paths, ou os end pints, as URLs disponíveis nesta API. É exatamente nisso que iremos focar no próximo capítulo.

## Para saber mais: Info Object
Neste capítulo nós utilizamos as chaves externalDocs e info. Todas as chaves que usamos possuem alguns campos obrigatórios e outros opcionais.

Nesse link você pode conferir os campos de info: https://swagger.io/specification/#info-object

Aqui você pode conferir as informações da chave externalDocs: https://swagger.io/specification/#external-documentation-object

## o que aprendemos?
* definimos informaçoes sobre a API no Swagger editor
* Aprendemos a adicionar links sobre API
* adicionamos detalhes de contat e licença da API

## Recursos e verbos
[00:00] Boas-vindas a mais um capítulo desse treinamento, onde estamos brincando um pouco com a documentação de uma API usando o Swagger. Agora eu quero tornar o que já fizemos um pouco mais funcional, tentar, pelo menos, fazer uma requisição, para buscar todas as especialidades. Para isso eu preciso definir os paths.

[00:20] Então vamos definir o paths, adicionando a chave "paths:" e se eu dou um "Enter" aparece o erro no lado direito da tela me avisando que isso é um objeto. Precisamos definir chaves e valores, as chaves desse objeto vão ser as URLs, por exemplo, a chave /especialidades:. E o valor de cada uma dessas chaves é outro objeto também.

[00:42] Podemos ter, nesse caso, os verbos, por exemplo, eu quero o verbo get: e esse verbo pode ter algumas informações como o sumary:, a descrição, o que isso realmente é. Então eu posso colocar sumary: Recupera todas as especialidades. Já começamos e na parte direita da tela já apareceu um detalhe, que é de um end point, de um path na nossa API.

[01:12] Inclusive se clicar nesse path ele me mostra parâmetros, que eu não tenho ainda, e ele me mostraria as possíveis respostas, que também não tenho. Mas eu quero atentar para outro detalhe, o "Default". Nós temos essa informação, essa API e quando eu tento fazer um execute, não acontece nada, ele não nos devolve nada.

[01:38] Porque ele está tentando acessar editor.swagger.io/especialidades. Eu não tenho nenhum servidor informado, antes do default não tem nada informando qual é o servidor que eu estou acessando. Então antes de termos paths, eu preciso ter servidores. Teremos que adicionar um servidor, reparem que servers é um array, podemos inclusive ter mais de um servidor.

[02:05] Então eu vou adicionar um array, onde eu posso informar a URL, - url:, description:. Clicar em “API de Teste” e eu vou pegar a URL da nossa API, que é "-url: http//mockapi.io/projects/6096015d116f300174b29bb". Ou seja, quando eu fizer um teste agora o que o Swagger vai tentar acessar é essa URL que acabei de adicionar, incluindo o "/especialidades”, usando o verbo get, sem passar parâmetro nenhum.

[02:35] Então eu poderia ter mais de uma URL, imagina que eu quero ter uma documentação que possa acessar o nosso servidor de teste e o servidor de produção. Bastaria eu inserir uma outra URL, por exemplo, - url: google.com, e descrição seria description: API de Prod. Então eu posso hora fazer uma requisição para saber de nossa API de produção, hora para API de teste.

[02:58] Vou retirar a "API de Prod", para não acabar fazendo requisição para o local errado. O Editor me mostra que eu ainda tenho erros, eu não tenho todas as informações necessárias, mas, teoricamente, eu já tenho suficiente para realizar uma requisição. Então vamos ver o que acontece quando eu aperto "F12" ou eu venho, em qualquer lugar da página, e clico "Botão direito > Inspecionar” e seleciono a aba "Networks".

[03:26] Quando eu clico no botão "Execute", ele faz uma requisição para a nossa API de especialidades, eu abrir a requisição em uma nova aba, espera um pouco que ele está autorizando. Vamos ver, eu suponho que eu coloquei o link errado, deixa eu dar uma olhada na nossa API de especialidades. Vou colocar a URL correta "-url: http//6096015d116f300174b29bb". Agora sim, eu copiei o link do projeto, era isso que estava errado, eu copiei o servidor errado.

[04:04] Agora sim, vamos executar, ele está fazendo uma requisição que está carregando, e vamos ver porque que não funcionou de novo. Vou executar e ver o que está acontecendo, ele está fazendo a requisição. Ótimo, ele devolveu algo, perfeito, a requisição foi feita, e por que ele não colocou nada para nós?

[04:21] Vamos fechar a aba "Inspecionar" e recapitular tudo. O que acontece com essa interface, o que ele está fazendo? Quando eu tenho um path e tenho todas as informações dele, o próprio Swagger consegue realizar uma requisição de teste, e ele realmente está fazendo essa requisição. Tanto é que quando eu abri a aba de redes, a requisição foi feita para o local correto, devolveu as respostas corretas.

[04:47] Eu ainda tenho erros aparecendo na minha tela, então isso, muito provavelmente, está impedindo o Swagger de exibir a resposta para nós. Porque ele não sabe o que exibir, ele não sabe se ele pode exibir tudo, se está tudo correto. Ou seja, ele não sabe que ele precisa parsear aquele Json e exibir na tela, por exemplo.

[05:05] Então o que precisamos fazer agora, que exatamente o erro que está aparecendo no Editor. Eu preciso informar quais são as possíveis respostas desse end point. Se, por exemplo, tiver um erro no meu banco de dados eu respondo com o status 500, em caso de sucesso eu respondo com status 200, posso colocar até exemplos de resposta. Então vamos ver exatamente como conseguimos definir uma resposta.

## possiveis respostas
[00:00] Bem vindos de volta. Vamos definir as possíveis respostas desse path* ou end point. Eu vou adicionar o responses:, um objeto, onde a chave é o status possível. Então, imagine que em caso de sucesso, eu tenho 200. Dentro dessa chave eu posso ter a descrição desse status, então, por exemplo, description: Sucesso, ou algo do tipo.

[00:30] Ainda, eu posso ter o conteúdo content:. Então vamos descrever esse conteúdo, o conteúdo pode ser em vários formatos. Logo, a chave do conteúdo é o formato, por exemplo, escrevo application/json:. E o valor é o conteúdo em si, posso ter então em Json, XMIL, texto puro, HTML e outros. Como eu posso descrever essa resposta?

[00:54] Eu posso dar um exemplo, adicionar um texto puro mesmo, colocar mais de um exemplo. Mas o que eu vou fazer é definir um esquema adicionando a chave schema:, ou seja, vou informar qual é o tipo de retorno. Por exemplo, aqui o tipo vai ser objeto, type: object.

[01:12] Esse objeto ele tem propriedade, escrevo properties:. Então posso definir para ele uma série de propriedade. Reparem que quando definir o responses a minha resposta já apareceu no lado direito da tela. Voltando as propriedades, eu vou ter uma propriedade chamada id:, essa ID tem como tipo type: integer, ela é do tipo inteiro.

[01:34] Também vou ter uma propriedade descrição:, onde o tipo é um string, type: string. Teoricamente eu tenho um esquema bem formatado, então vamos recapitular o que eu escrevi antes de vermos como ele vai aparecer. Eu tenho um path de especialidades, onde se eu fizer uma requisição get para especialidades, ele vai recuperar todas as especialidades e respostas possíveis no status 200.

[02:03] Repare que só essa resposta possível, onde a description é no caso de sucesso, eu posso colocar ou não essa descrição, normalmente colocamos. E eu posso informar qual é o conteúdo, ou não, talvez eu não precise informar, mas dessa vez eu quero informar. O conteúdo devolvido é em Json, ou seja, isso é o formato, é um mine type. Eu poderia ter Text, HTML, ou alguma outra coisa, Text Plain se fosse um texto puro, mas eu vou querer Jason.

[02:32] Eu posso definir ou exemplos de como isso vai retornar, ou um scheme, um esquema de como isso vai ser e através desse esquema o próprio Swagger pode montar exemplos para mim. Então como esse esquema? Ele poderia ser um a única string, poderia ser uma inteira, mas nesse caso vai ser um objeto.

[02:50] E quais são as propriedades desse objeto? ID, que é do tipo inteiro, e descrição que é do tipo string. Com isso definido, vamos ver como fica, repara que eu poderia ter várias respostas para os parâmetros, mas eu tenho uma só. Onde o código é 200 e descrição é sucesso. Posso ainda ter vários media types, vários tipos dessa resposta.

[03:10] No meu caso eu tenho apenas o application/json como media type. Com o scheme que adicionamos o Editor ele já monta um valor de exemplo, e eu cometi um errinho, defini como se o retorno fosse um objeto, quando na verdade é um array. Então vamos modificar, na verdade, o type: array, onde items: type: object e as outras propriedades são essas.

[03:42] Agora que está tudo certo, agora é um array, onde cada item desse array tem ID, que um inteiro, e descrição que é uma string. Agora, com essa resposta mapeada, o que eu vou fazer é tentar executar essa requisição de exemplo. Depois que eu o executo, nos mostra o comando que eu poderia executar usando o “curl” para fazer essa reposição, qual é a URL efetiva que ele fez requisição, e a resposta real.

[04:15] Então eu tenho o ID 1 e a descrição desse ID, dessa especialidade é teste, ele mostra também os cabeçalhos dessa resposta, tudo funcionou. Conseguimos diretamente do nosso Swagger UI, que está dentro do Swagger Editor, fazer uma requisição real para nossa API. Não só conseguimos documentar, mas podemos fornecer um ambiente de teste para a nossa API.

[04:41] Já definimos as respostas, definimos como esse dado volta do Servidor, mas conseguimos definir como enviar informações para o servidor. Através de parâmetros, ou até no corpo dar requisição. Então vamos conversar um pouco mais sobre isso nos próximos vídeos.


## Parametros na requisicao
[00:00] Bem vindos de volta. Então já sabemos como definir um path, ou endpoint, já sabemos como definir o que ele traz de volta para nós. Agora vamos definir o que podemos mandar para eles. Se dermos uma olhada na nossa MockAPI, quando eu clico em "Edit" a especialidade, eu tenho a opção de enviar um ID para especialidades.

[00:25] Para essa URL eu posso colocar "/especialidade/1", e ele vai trazer somente a especialidade com o ID 1. Então vamos definir exatamente isso, para podermos enviar esse parâmetro. Lá no final da página do Editor eu vou inserir um novo path, usando as especialidades/, e eu preciso informar que nessa parte da URL vai ser um parâmetro. E para informar que é um parâmetro eu coloco entre chaves {id}, chamando de ID.

[00:53] Posso chamar do que eu quiser, por exemplo, especialidadeID, alguma coisa assim, mas eu vou chamar só de ID. Vamos lá, eu quero mapear uma requisição adicionando o verbo get. Dentro dessa requisição get aquela mesma história eu posso ter um sumary: Recupera uma entidade pelo ID.

[01:13] E eu posso ter as responses, mas antes de ter as respostas eu quero mapear esse parâmetro ID, que o primeiro erro que está aparecendo para mim. Esse parâmetro ID que foi declarado, ele precisa ser definido de alguma forma, ou dentro da aplicação toda, ou dentro desse path.

[01:30] Então vamos lá, eu vou informar que eu tenho parameters:. Essa chave parâmetro ela é um array, no quadro a direita “precisa ser uma array”. Para definir um array o que eu posso definir no parâmetro o nome dele e tem que ser exatamente o que tá aqui no URL, então no caso é ID, eu preciso informar onde esse parâmetro ID vai ser enviado.

[01:57] Esse parâmetro ID eu sei que ele vai ser enviado direto na URL no path, porque ele está já está definido. Então vou colocar abaixo no nome, in: path. Só que existem outras possibilidades, por exemplo, se ao invés especialidades/id, fosse /especialidades/id/1, com uma query string eu colocasse que o ID é 1, ao invés de fazer especialidade/1, se fosse naquele outro formato eu poderia colocar aqui uma query e remover esse parâmetro iddaqui, mas não é o nosso caso, realmente vai ser no path.

[02:32] Eu posso adicionar algumas outras informações como, por exemplo, colocando o schema, então aqui eu vou definir o type: integer, e esse tipo é um inteiro, ou seja, o ID precisa ser um número. Eu preciso informar se este parâmetro é ou não obrigatório, no nosso caso como ele tá na URL, eu preciso passar ele.

[02:51] Então required: true, ou seja, verdadeiro, eu preciso informar esse parâmetro. Tendo definido como eu envio esse parâmetro, se eu dou uma olhada no nosso Swagger UI, quando eu for enviar essa requisição eu posso adicionar a informação de ID nela. Mas antes vamos colocar as respostas possíveis.

[03:16] Volto ao Editor, dou um "Enter", e adiciono "responses:", com aquele esquema. Eu posso ter uma resposta de sucesso que vai ser assim desciption: Sucesso, com nesse caso foi sucesso. Ainda temos o contente que é um application/json:, então sempre respostas dessa API vão vir em Json.

[03:36] Da mesma forma como fizemos anteriormente, eu posso adicionar um schema:. Então vou pegar isso daqui do nosso path. Porque não vou retornar o array, somente o objeto direto. Repara que eu já tenho uma resposta em Json, no caso de sucesso, trazendo um ID e uma descrição.

[03:59] Então eu posso testar essa requisição, eu vou buscar a especialidade com ID 1, quando eu executo no Swagger UI, se eu não fiz nenhuma besteira. A requisição feita corretamente e tá devolvendo a requisição com o ID 1, e tem a descrição teste. Mas repare que nas respostas possíveis, eu só tenho um caso de sucesso, e se eu passar o ID errado? Se eu passar o ID errado eu já sei o que vai acontecer.

[04:24] Então primeiro eu vou descrever, caso eu passe o errado eu vou ter um cenário de 404. E a descrição para isso eu vou dizer que é description: Especialidade não encontrada. O conteúdo dessa resposta um pouco diferente também, vai vir com o cabeçalho informando um application/Json, mas, na verdade, eu nem preciso de um schema.

[04:51] Eu posso ter se eu quiser, mas, na verdade, eu já vou colocar um example, porque ele vai retornar a mensagem example: “Not found”. Como isso vai ser exibido, deixa eu fazer um clear, para limpar aquela resposta que já veio. Então, de novo, eu tenho aqui um possível ID para eu passar e as possíveis respostas são 200 em caso de sucesso, e 404 no caso de especialidade não encontrada.

[05:13] O valor retornado vai ser um string Not found. Então eu posso na barra de busca do UI e tentar buscar “especialidade dois”, por exemplo, que eu sei que não existe. Quando eu executar a resposta exatamente o que eu disse, Not found, esse é o corpo da resposta. O código é 404 e tem o content - type: json, então mapeamos corretamente.

[05:36] Então reparem que nós fizemos duas coisas nessa aula, nós mapeamos um parâmetro, ou seja, nós podemos enviar um parâmetro para nesse específico get de /especialidades/{id}/, podemos passar esse parâmetro. E esse parâmetro tem que ser um inteiro e é obrigatório.

[05:53] “Ah Vinícius, eu poderia colocar esses parâmetros fora da minha operação *get, poderia colocar aqui direto aqui fora, se eu copiar aqui para fora, isso aqui daria um erro?”

[06:10] Vamos ver o que acontece, isso não veio. O que vai acontecer agora é se eu tiver alguma requisição além do verbo get. Se eu tiver, por exemplo, algum put ou post it, eu já vou ter as definições desse parâmetro ID definidas corretamente.

[06:24] Então deixa eu limpar a execução e eu continuo conseguindo passar o parâmetro corretamente, ele busca corretamente. Só para você entender um pouco melhor o que isso quer dizer. Se eu tiver além de uma requisição do tipo get, alguma outra requisição para especialidades/id, eu não preciso de novo repetir essa definição do parâmetro.

[06:45] Eu posso simplesmente definir esse parâmetro para todos os verbos que forem feitos nesse path, nessa URL. Então essa é a diferença entre colocar direto na “especialidades”, no mesmo nível que todos os verbos. Ou colocar dentro de algum verbo, se eu colocar como estava antes, dentro do get. Significa que se eu tivesse um put, por exemplo, eu teria que definir esse parâmetro de novo.

[07:12] Agora nesse caso como eu fiz agora pouco, para todos os verbos que eu definir esse parâmetro já vai estar definido. Então recapitulando, nós aprendemos três coisas, na verdade, como definir um parâmetro, seja para um end point específico ou para um verbo específico. Aprendemos também a como definir mais de uma resposta, inclusive, não só com um schema, mas também com o example.

[07:40] Ou seja, além de definir o esquema, o que vem, um objeto, eu posso direto dar um exemplo de como ele virá. Então dessa forma conseguimos definir essa resposta. Agora não só parâmetros podemos enviar para lá, imagina que eu queria cadastrar uma nova especialidade.

[07:59] Então quero fazer uma requisição post para a barra especialidades. Eu preciso enviar algo no corpo da requisição, então essa parte um pouco mais complicada, vamos ver como definimos o corpo de uma requisição do próximo vídeo.

## dados no corpo da requisiçao
[00:00] Bem vindos de volta. Vamos definir um cenário onde consigamos cadastrar uma nova especialidade. Nós temos duas URLs por enquanto, barra especialidades e especialidades, barra alguma coisa. Então a URL para eu cadastrar algo também é barra especialidades, não uma URL nova, como barra especialidades, barra nova, ou algo do tipo.

[00:28] Então o que eu vou fazer é definir um novo verbo dentro desse mesmo path. Então vamos definir um post:, através do verbo post eu consigo criar uma nova especialidade. Eu posso adicionar as mesmas informações, como, por exemplo, sumary: Criar nova especialidade. Posso utilizar o sumary para informar o que esse end point faz.

[01:01] Mas eu também tenho o description: “Através desse endpoint você pode criar novas especialidades". Então isso não aparece de cara aqui, mas aparece na descrição. Então se algo precisar de uma informação a mais, você pode adicionar a descrição. Vou tirar a 'description', que no nosso caso não é necessário.

[01:24] Temos o sumary, e o que mais temos no nosso caso do get. Nós temos as respostas, então vamos criar também as responses. Porém, eu ainda não sei como é a resposta nesse post, eu vou supor que ele me retorna um 201, que é o created, ou seja, funcionou, deu tudo certo. Eu vou adicionar um description: “Sucesso”, então eu suponho que seja isso, eu nem vou colocar o scheme, porque eu não sei o que ele me devolve.

[01:57] Só que além da resposta eu preciso informar como que essa especialidade que eu estou criando vai ser enviada. Então preciso enviar uma especialidade, no meu caso eu preciso enviar somente a descrição. Vamos definir o nosso requestBody: Então temos uma nova chave dos nossos verbos HTTP que é o requestbody. E podemos colocar uma descrição, informando se no corpo você precisa enviar o objeto do tipo especialidade.

[02:29] Ou posso ir direto para o contente onde podemos colocar application/json e aqui dentro o nosso schema que já conhecemos, então vai ser um type: objecte properties: descricao: onde type: string.

[02:49] Se não escrevi nada errado, ele já mostra um valor de exemplo, então descrição e alguma string, e me mostra também o schema. Então, se eu não fiz nenhuma besteira, já consigo realizar essa requisição.

[02:59] Então vamos testar, no corpo ele já preenche para mim esse Json, com um valor de exemplo, eu vou colocar no corpo uma "nova especialidade". Vamos realizar essa requisição e ver como vem resposta, se a resposta vai chegar, mesmo sem ter definido o schema, vamos ver o que acontece. Quando eu executo ele mostra de novo seu URL completo, aparentemente tudo bem, e realmente ele devolveu um 201 e o corpo é um objeto do tipo especialidade.

[03:33] Ou seja, ele traz para nós o ID e a descrição. Então podemos colocar aqui, vamos aproveitar a informação que temos agora para colocar o nosso contente com o application/json:sendo esse schema: aqui. Eu posso copiar o type: object com as propriedades lá do nosso path. O tipo é um objeto e as propriedades são essas. Então agora deixa eu limpar essa busca que eu fiz e tenho a resposta correta.

[04:10] Então dessa forma conseguimos descrever como é o corpo de uma requisição, como o corpo de uma requisição precisa ser e, inclusive, acabamos de fazer um post. Ou seja, nós criamos uma nova especialidade, se eu vier e buscar todas as especialidades, eu espero que venham duas agora. Apareceu a descrição teste e a descrição nova especialidade.

[04:34] Então com isso, já conseguimos definir como enviar informações para o servidor, seja com parâmetros, como nós vimos, que pode ser do path, na query, no header ou em cookie. Vimos como enviar um requestbody, ou seja, mandar dados no corpo da requisição. Agora eu vou deixar um desafio para você, já tenho o get, tenho post, faltam só dois verbos para completarmos o crude da especialidade.

[05:07] Então com o que temos, você já consegue fazer o put e o delete, como que isso vai ser? Deixa-me te explicar o que você vai fazer. Em especialidades já conseguimos criar uma especialidade e buscar todas. Já em especialidades/id conseguimos buscar uma, atualizar a especialidade em questão e remover uma especialidade.

[05:30] Então, além do get, você vai adicionar o post e o delete, vai fazer alguns testes, verificar o que é necessário para você realizar suas requisições. Sempre crie uma especialidade e depois tente remover, ver o que é necessário. Crie uma nova especialidade, tente atualizá-la, ver o que é necessário enviar. Dessa forma você vai chegar na documentação.

[05:54] Caso, por algum motivo, você não consiga, o fórum está aberto e eu vou tentar te ajudar, mas com o conhecimento que já temos, é possível documentar essas duas novas operações. Agora que já estudamos muitos conteúdos, vamos sair um pouco desse comum e ver como melhorar o que já temos.

[06:12] Por exemplo, reutilizar essa definição de uma especialidade, porque temos o type object sendo repetido em muitos lugares. Enfim, podemos fazer bastante coisa ainda, vamos ver o que mais podemos definir com o Swagger a partir do próximo Capítulo.

### conteudo do corpo
nós definimos o que deve ser enviado no corpo de uma requisição de nossa API através da chave requestBody. O requestBody possui uma propriedade content que é um mapa (ou dicionário).

O que significa cada chave do mapa content?

R: o formato da requisiçao

Cada chave do mapa é um tipo de mídia que será enviado como o cabeçalho Content-Type. Em nosso exemplo, como a API só suporta JSON, informamos apenas application/json.

## o que aprendemos?
* aprendemos a definir um path, ou endpoint
* vimos como definir as possiveis respostas de um path
* aprendemos a definir parametros para uma requisiçao
* vimos como definir o corpo da requisiçao

## definindo tipos
[00:00] Boas-vindas a mais um capítulo do nosso treinamento. Nós estamos documentando uma API utilizando Swagger. Então já fizemos bastante coisa e a documentação está bastante funcional, eu diria até que ela está bem completa. Só que agora eu posso facilitar um pouco nossa vida, porque, por exemplo, o pedaço de código abaixo está sendo repetido em muitos lugares.

[00:20] Então podemos melhorar isso criando esquemas em um lugar separado, chamado componentes, ou components. Vou fechar a chave de paths e tudo mais que temos, clicando na flechinha ao lado da chave. Agora o que eu quero adicionar é "components:", que é um objeto. Dentro dele eu posso adicionar schemas, respostas, parâmetros, exemplos, corpos, cabeçalho, enfim, muitas coisas.

[00:56] Mas o que eu quero adicionar é um schema. Esse schema tem como chave um nome e depois todas aquelas informações do tipo, se é um objeto ou não. Então, antes de qualquer coisa, vamos definir um tipo bem simples. Imagine que ao invés de ter o ID como um inteiro, eu queria criar um tipo ID.

[01:17] Posso fazer da seguinte forma, eu vou chamar de Id:, e esse ID pode ter várias coisas como um type: integer, por exemplo. E está aparecendo um erro no meu documento porque esse ID não está sendo usado em nenhum lugar, mas se olho aqui em baixo eu já tenho essa definição, repara um ID como inteiro.

[01:36] Posso ter um título, por exemplo, title: "Id", e eu posso ter uma descrição description: "Identificador único de alguma coisa", de alguma especialidade ou algo assim. Então podemos ir adicionando informações nessa chave e eu posso colocar, por exemplo, quantos caracteres esse ID pode ter, se fosse uma string, mas no caso é um inteiro, posso definir o valor máximo ou mínimo. O valor mínimo é um, não posso ter um inteiro menor que um.

[02:07] Eu posso ir adicionando informações a esses componentes, a esses schemas. Então se eu consigo criar vários tipos, eu consigo criar um tipo chamado especialidade. Vamos fazer exatamente isso no próximo vídeo, vamos criar o nosso tipo especialidade, para que não precisemos ficar fazendo todo esse trabalho.

[02:28] Nas propriedades do schema eu tenho o esquema object e todas as propriedades. Aqui em cima eu também tenho o type object com as propriedades, e depois na resposta tem o type object com as propriedades. Então vamos fazer exatamente isso, vamos pegar o schema, vamos criar esse schema para não precisar ficar repetindo esse código em outros lugares.

### componentes
Conhecemos neste vídeo o conceito de componentes e nele nós pudemos definir um tipo ou schema.

Qual das definições a seguir é a mais correta para a chave components?

R: um conjunto de objetos para serem reutilizados

Em componentes nós podemos definir schemas, responses, requestBodys e muito mais.

## definindo objetos
[00:00] Bem vindos de volta. Já sabemos como definir um tipo, se você ainda não fez isso, pausa o vídeo agora e define o tipo de especialidade, depois volta e ver se fizemos igual. Para você poder praticar, porque com os conhecimentos que temos, teoricamente, já conseguimos fazer. Então pausou, voltou e eu vou fazer com você.

[00:22] Eu não vou ter mais o tipo ID, porque ele não está trazendo valor nenhum para nós. Vou ter um tipo chamado Especialidade, esse tipo especialidade não é um inteiro, ele é objeto ele não tem esse título, ele não precisa dessa descrição. Se eu quiser posso colocar, mas ele não tem. E ele, obviamente, não tem valor máximo ou mínimo.

[00:40] O que ele tem é propriedades. Então vou definir as propriedades do meu tipo especialidade, ele tem um ID que tem como tipo um inteiro, id que tem type: integer. Também tem uma descrição que tem como tipo uma string, descricao: que tem como tipo type: string.

[01:00] Inclusive em uma string, poderíamos colocar um formato, por exemplo, se é uma data format: date-time. Mas no nosso caso não é nada disso, é realmente só uma string. Então não preciso de formato, mas acho válido citar.

[00:01:16] Tenho meu schema definido então, teoricamente, isso já nos mostra um ID que é um inteiro, e uma descrição que é uma string. Agora o que nós temos é um componente definido, nós temos um esquema definido, fora de qualquer operação, fora de qualquer path, fora de qualquer coisa.

[01:35] O que eu quero fazer agora pegar o esquema, essa especialidade e utilizar em algum lugar. Mas, por enquanto, ainda não sei como fazer isso. Então vamos para recapitular o que fizemos na parte de definição, temos fora de qualquer objeto, nós temos a possibilidade de definir componentes.

[01:56] Um dos componentes possíveis é o esquema, se eu tiver alguma resposta que é sempre devolvida igual. Por exemplo, se sempre que eu cadastrar uma especialidade, aparece uma especialidade sem o ID, e sempre que eu atualizo também vem sem o ID, eu posso definir um novo esquema.

[02:16] Ou melhor, eu posso definir direto a resposta, então se sempre que eu insiro uma especialidade, ele devolve uma especialidade inteira. Quando eu busco especialidade, ele também traz de volta especialidade inteira. Eu posso definir essa resposta responses:. Inclusive posso dar um nome para essa resposta como, por exemplo, Especialidade também.

[02:37] Dentro dessa chave você vai definir as informações dessa especialidade, da mesma forma como definiríamos uma resposta. Então um componente é algo que a gente pode reutilizar em vários lugares. Eu não vou definir essa resposta, eu vou deixar como desafio para que você defina. Porque o que eu quero fazer agora é, de alguma forma, agora entendemos o que é um componente que é "qualquer coisa que eu possa reutilizar em vários lugares".

[03:02] Quero saber como efetivamente reutilizar, eu quero pegar essa especialidade e utilizar. Reutilizar ela em todas as chaves que contém ID no meu documento, ou seja, pegar aquele componente fazer o uso dele em vários lugares, e é exatamente isso que vamos fazer no próximo vídeo.

## Referenciando tipos 
[00:00] Bem vindos de volta. Agora o que eu quero fazer é pegar algo que eu definir nos componentes e referenciar em outro lugar. Por exemplo, nas minhas respostas ou até no corpo, se fosse o caso, em um request body. Vamos começar onde eu tenho um array e dentro de items eu posso ter esse objeto, que a especialidade.

[00:23] Em algum momento eu quero referenciar um componente, posso utilizar uma propriedade chamada $ref:". Essa propriedade chamada ref é uma string, então posso colocar entre aspas. Qual o formato dela? Eu começo com hashtag para indicar a raiz desse documento, como estou na raiz desse documento, eu posso acessar os componentes.

[00:50] Dentro dos componentes eu posso acessar os schemas, e dentro de schemas especialidade, então "$ref: "#/components/schemas/Especialidades"". Então, teoricamente, agora na minha resposta de Especialidades tenho aqui como resposta possível aquele mesmo array. Logo, o meu esquema é um array de especialidade, aparece os colchetes indicando um array e dentro deles a Especialidades.

[01:15] Vamos fazer exatamente isso para os nossos outros cenários onde utilizamos esse mesmo tipo. Reparem que aqui não temos uma especialidade, porque não é um ID e uma descrição, temos apenas a descrição, então não conta.

[01:33] Já na resposta podemos utilizar, podemos trazer esse ref aqui. Então vamos ver se eu coloquei no local correto, isso aqui é a resposta do meu post, então a resposta do meu post está certo, está lá como Especialidade.

[01:46] Vamos ver onde mais eu posso colocar, aqui, nessa resposta do meu especialidades/{id}. Também posso colar esse ref, então no especialidades/{id} a resposta está certa, aparecendo como um array, temos um esquema trazendo uma especialidade. Então repare que dessa forma conseguimos reutilizar código na nossa documentação.

[02:09] Se em algum momento, por exemplo, essa resposta existe em muitos lugares, então aqui em responses eu tenho sempre um 200 quando o script no sucesso, e o conteúdo é sempre um applicationjson que o schema é essa referência?

[02:22] Você pode colocar nos componentes a mesma response. Então, de novo, eu vou deixar como desafio, eu não vou implementar isso. Porque eu quero chamar atenção para um detalhe fizemos, contudo, eu não expliquei muito. No próximo vídeo eu volto para falar sobre arrays.