# Swagger: documentando suas APIs
iniciado em 07/04/2022

terminado em ANDAMENTO

[certificate]() 

- [Swagger: documentando suas APIs](#swagger-documentando-suas-apis)
  - [Swagger](#swagger)
  - [Entendendo o Swagger](#entendendo-o-swagger)
  - [OpenAPI](#openapi)
    - [OpenAPI Specification](#openapi-specification)
  - [Para saber mais](#para-saber-mais)
  - [Swagger Editor](#swagger-editor)
  - [o que aprendemos?](#o-que-aprendemos)
  - [informaçoes da API](#informaçoes-da-api)
    - [propriedade obrigatorio da API: info](#propriedade-obrigatorio-da-api-info)
    - [title](#title)
    - [description](#description)
    - [versao da API](#versao-da-api)
    - [documento completo atual](#documento-completo-atual)
  - [adicionando links](#adicionando-links)
    - [termsOfService](#termsofservice)
    - [ExternalDocs](#externaldocs)
    - [documento completo atual](#documento-completo-atual-1)
  - [Complementando infos](#complementando-infos)
    - [contact](#contact)
    - [licença](#licença)
    - [documento completo atual](#documento-completo-atual-2)
  - [Para saber mais: Info Object](#para-saber-mais-info-object)
  - [o que aprendemos?](#o-que-aprendemos-1)
  - [Recursos e verbos](#recursos-e-verbos)
    - [Paths](#paths)
    - [servers](#servers)
    - [documento completo atual](#documento-completo-atual-3)
  - [possiveis respostas](#possiveis-respostas)
    - [responses](#responses)
    - [documento completo atual](#documento-completo-atual-4)
  - [Parametros na requisicao](#parametros-na-requisicao)
    - [parametros na URL](#parametros-na-url)
    - [documentando um 404](#documentando-um-404)
      - [response message example: "not found"](#response-message-example-not-found)
    - [Parametros globais](#parametros-globais)
    - [documento completo atual](#documento-completo-atual-5)
  - [dados no corpo da requisiçao](#dados-no-corpo-da-requisiçao)
    - [requestBody](#requestbody)
    - [documento completo atual](#documento-completo-atual-6)
    - [conteudo do corpo](#conteudo-do-corpo)
  - [o que aprendemos?](#o-que-aprendemos-2)
  - [definindo tipos](#definindo-tipos)
    - [components](#components)
    - [componentes](#componentes)
  - [definindo objetos](#definindo-objetos)
    - [documento completo atual](#documento-completo-atual-7)
  - [Referenciando tipos](#referenciando-tipos)
    - [$ref](#ref)
    - [documento completo atual](#documento-completo-atual-8)
  - [Definindo arrays](#definindo-arrays)
    - [items](#items)
    - [documento completo atual](#documento-completo-atual-9)
  - [para saber mais: OpenAPI](#para-saber-mais-openapi)
  - [o que aprendemos?](#o-que-aprendemos-3)
  - [Security schemas](#security-schemas)
    - [SecuritySchemes](#securityschemes)
      - [bearer](#bearer)
    - [documento completo atual](#documento-completo-atual-10)
  - [para saber mais: Tokens](#para-saber-mais-tokens)
  - [Parametro security](#parametro-security)
    - [proteger com security todos os endpoinds](#proteger-com-security-todos-os-endpoinds)
    - [documento completo atual](#documento-completo-atual-11)
    - [onde usar?](#onde-usar)
  - [Bearer format](#bearer-format)
    - [bearerFormat](#bearerformat)
    - [documento completo atual](#documento-completo-atual-12)
  - [o que aprendemos?](#o-que-aprendemos-4)
  - [baixando o editor](#baixando-o-editor)
  - [Baixando o UI](#baixando-o-ui)
  - [o que aprendemos?](#o-que-aprendemos-5)
    - [documento completo atual](#documento-completo-atual-13)



## Swagger
O Swagger fornece um conjunto de ferramentas, dentre eles: Swagger Editor para escrevermos a documentação da API, Swagger UI para disponibilizarmos essa documentação e Swagger Codegen para gerar código a partir da documentação.
  

## Entendendo o Swagger
Antes de começarmos a fazer qualquer coisa, vamos entender o que é Swagger, o que é esse nome, o que esse nome significa e o que ele nos fornece. 

Vamos lá, quando entramos no site "swagger.io", temos a seguinte chamada "API Development for Everyone".

Então, o que o Swagger faz é simplificar o desenvolvimento de APIs de alguma forma. 

Ele possui várias formas para fazer isso, para simplificar e para nos ajudar desenvolver e documentar APIs, só que iremos focar nessa parte de documentação. 

Nós já temos uma APIs desenvolvidas, iremos utilizar uma API de exemplo, mas vamos focar na documentação dessa API que já existe.

O Swagger nos fornece algumas ferramentas, um editor de documentação, uma visualização dessa documentação, utilizando um formato específico, ele fornece um gerador de código baseado nessa documentação. 

Vamos dar uma olhada rápida clicando em "Explore Swagger Tools" na página inicial do site, para explorar as ferramentas do Swagger.

Ele nos mostra as três ferramentas open source que ele tem. 

Ou seja, essas ferramentas são gratuitas e de código aberto. 

Se eu voltar para página inicial do site e "Open Source Tools", veremos exatamente as mesmas três ferramentas, o "SwaggerEditor, Swagger UI e o Swagger Codegen", codegen de code generator.

Então o Editor ele permite que desenvolvamos, que escrevamos a documentação da API, que façamos o design da nossa API. 

Ele ajuda na modelagem de uma API, se ainda tivermos pensando em como vai ser, e na documentação caso essa API já exista, iremos usar bastante ele.

Existe o Swagger UI para você fornecer um ambiente visual do que criamos com o Swagger Editor, basicamente. 

Então imagina que você documentou toda a sua API, está todo modelado, e que você queira fornecer isso como documentação para o cliente que vai utilizar a sua API. 

Você pode fornecer através do Swagger UI, já vamos ver isso tudo, na prática, estamos apenas entendendo as ferramentas.

Nesse treinamento trabalharemos o tempo todo com o Swagger Editor e vamos dar uma olhada nos Swagger UI. 

E o Codegen, por que que não iremos utilizar?” 

Porque para utilizar ele eu ia precisar escolher alguma linguagem, porque se dermos uma olhada nele, ele pode gerar servidores ou clientes para diversas linguagens, como as "aspnet5, aspnetcore, erlang, PHP, node, phyton,".

Então ele consegue gerar código em muitas linguagens, com muitas tecnologias e eu precisaria escolher uma, ou algumas linguagens para fazer isso, com certeza ia deixar alguma de fora. 

Por isso, não iremos entrar nessa parte, mas essa parte aqui depende do conhecimento que nós aprenderemos na hora de fazer o design de uma API, ou a documentação de uma API.

Recapitulando, o que é Swagger, para finalizarmos. 

```diff
+ O Swagger é, basicamente, um conjunto de ferramentas que nos ajuda a fazer o design, ou seja, fazer a modelagem, a documentar e até gerar código para desenvolvimento de APIs. 
```
Iremos escrever a documentação? Como fazemos com essa documentação?

Porque temos um meio Editor, então, teoricamente, vamos editar usando algum formato. 

## OpenAPI
Logo começaremos a escrever realmente um arquivo em um formato específico, mas antes de escrevermos, eu quero só pincelar que formato é esse, como que sabemos quais são os valores que pode colocar lá, ou não.

### OpenAPI Specification
Então o Swagger é uma ferramenta, um conjunto de ferramentas, e ele trabalha em cima de uma especificação, que a "OpenAPI Specification". 

Então vamos para a página inicial do Swagger, e se rolarmos para baixo temos a "OpenAPI Specification". 

Existe uma especificação de como você pode modelar APIs, como você pode documentar o design de uma API.

Então essa nos diz que podemos ter informações de uma API, os caminhos ou os end points dessa API, e cada end point tem seus verbos. 

Temos informações de componentes, como os esquemas, componente de segurança, podemos ter tags para organizar, enfim, tem muita coisa nessa especificação.

É utilizando essa especificação que escrevemos a nossa documentação, que escrevemos o documento através do Swagger Editor para o Swagger UI renderizar. 

Vamos só dar uma olhada na página do "OpenAPI Specification", não vou passar em toda a especificação, porque é gigante. 

Então seria impossível e seria muito maçante, vamos só dar uma olhada.

Existem duas versões mantidas hoje, a versão "2.0", bastante famosa, e a mais recente, a 3.0, que utilizaremos. 

Então na página do "OpenAPI Specification" eu vou clicar na opção "3.0", temos uma versão simplificada que o Swagger fornece em seu próprio site. 

Mas se você acessar a internet e pesquisar a "OpenAPI Specification" você vai ter a especificação oficial, completa.

Mas eu gosto bastante de como o Swagger organizou, com a interface do Swagger.

Então sempre que eu precisar acessar a referência de alguma coisa, sempre que eu precisar acessar a documentação da especificação, vou acessar através do site do Swagger. 

Mas deixarei no "Para saber mais", o site oficial da especificação.

Então a página faz umas introduções, explica que existe um documento que descreve uma API, logo teremos um documento, um arquivo que descreve algo que uma API faz. 

Seus end points, as suas rotas, os métodos de cada rota, os verbos da rota, enfim, tudo isso iremos conseguir utilizando essa especificação.

Temos que a parte das versões do OpenAPI e conseguimos ver a especificação em si, a estrutura do documento. 

Então temos tipos de dados, nós temos os esquemas, o que conseguimos informar em cada uma das partes. 

Por exemplo, na hora de eu passar informações sobre API, eu posso vir aqui nesse Info Object e eu sei que posso ter um título, uma descrição de termos de serviço, contato, etc.

Em cima disso que iremos trabalhar, desses campos que a especificação fornece. 

## Para saber mais
OpenAPI é a especificação utilizada pelo Swagger. No próprio site do Swagger há uma versão da especificação para consulta, mas caso você queira a versão "oficial" da especificação, pode consultar: https://www.openapis.org/

No momento da escrita desta atividade a última versão é a 3.1.0 e pode ser conferida aqui: https://spec.openapis.org/oas/v3.1.0

## Swagger Editor
Vamos entender o que é o Swagger Editor e como ele se relaciona com Swagger UI. 

Na página inicial do "swagger.io > Explore Swagger Tools > Swagger Editor ", exploraremos as ferramentas do Swagger. 

No editor do Swagger, temos algumas opções, podemos tentar no ambiente nuvem com o "SwaggerHub". 

Então existe um suporte um pouco mais enterprise, vamos dizer assim, tem uma versão paga.

Podemos baixar o Swagger para nossa máquina, seja utilizando um container do docker, ou baixar o código-fonte e subir um servidor. 

Ou podemos utilizar uma versão que o próprio Swagger deixa disponível. 

Então para não precisarmos instalar nada agora, para já começarmos direto, vamos utilizar o "Live Demo".

O interessante desse Live Demo é que quando eu clico nele, ele já tem uma especificação pronta, já tá com muita coisa pronta para entendermos como funciona. 

Vamos só passar o olho para entender o que ele está nos mostrando. 

No canto esquerdo temos a interface do Swagger Editor, que é a parte em que nós realmente iremos escrever, iremos editar alguma coisa.

Então, por exemplo, se eu for até a linha "description" e modificar, colocar o texto "isso é uma descrição", no canto direito da página, sem fazer nada, ele já vai atualizar. 

No lado direito é exatamente o que o Swagger UI tem.

Então se eu voltar na página inicial do Swagger e entrar na página Swagger UI e acessar o Live Demo. 

Veremos que é exatamente o Swagger Editor, mas sem a parte da esquerda, então será apenas a parte da UI.

O cliente, a pessoa que está olhando sua API, está vendo documentação dela, pode ver todos os end points, ver todos os componentes, ou seja, cada um dos modelos da sua API. 

Pode fazer alguns testes reais, então ele pode clicar no botão "Try it out" e testar essa API, para isso, ele pode precisar autorizar, ou não.

É bastante interessante, e no Editor temos essa parte já embutida. 

Nesse caso, o que faremos durante esse treinamento? 

Nós vamos documentar uma API, utilizando o Swagger Editor online, e veremos tudo sendo refletido do lado direito da página. 

Então, de forma bem simples, iremos documentar uma API já existente e ver como a documentação seria vista no Swagger UI em tempo real.

Antes de começarmos, eu quero mostrar um detalhe bem interessante, principalmente para quem já tem alguma documentação no Swagger, ou algo assim. 

No meu caso, na primeira linha, podemos perceber que ele está utilizando a versão 2.0, que é a versão 2.0 do OpenAPI também. 

Então, eu posso facilmente vir aqui na aba " Edit > Convert to OpenAPI 3". 

Assim, eu vou converter esse documento que está no formato do Swagger 2.0 para especificação o OpenAPI na versão três.

Ele modificou um pouco o documento, mas o resultado é praticamente o mesmo, ele só recebe um selo a mais, informando que ele está utilizando a OpenAPI Specification. 

Ou seja, especificação real, sem nenhuma modificação do Swagger e na versão3. 

Agora que já entendemos o que é o Swagger Editor, já estamos prontos para documentar uma API. 

Podemos brincar um pouco com o Editor.

A nossa descrição já foi modificada, posso mudar o contato, mudar a licença, entre outros. 

Mas, o que faremos realmente é apagar tudo, então vamos à barra de ferramentas," File > Clear Editor". 

Com a página limpa, no próximo capítulo vamos começar a documentar uma API nossa, uma API já existe.

É uma API de testes, então não vamos precisar desenvolver nenhum código, ela já está online. 

Através desse ambiente completamente online, sem precisar instalar nada na máquina, começaremos a documentar uma API, mas de novo, no próximo capítulo.

## o que aprendemos?
* aprendemos o que é o swagger
* vimos como o swagger pode nos ajudar no desenvolvimento de APIs
* aprendemos como funcionao swagger editor

## informaçoes da API
Vamos começar documentar uma API, mas qual API se eu não desenvolvi nada, nem tenho nenhuma API. 

O que eu vou fazer para, de novo, não precisarmos escolher uma linguagem e te obrigar a instalar o Node, o Java, o PHP ou qualquer coisa do tipo. 

O que eu fiz foi criar uma mock API, uma API de mentira, através do site "mockapi.io"

E eu tenho os campos "médicos" e "especialidades". 

Eu tenho já cadastrada uma especialidade teste e tenho um médico chamado médico 1 com o CRM 12345, que está na especialidade 1 (especialidade dele é a com o ID 1). 

Logo, eu tenho um dado para cada uma dessas informações.

Ou seja, há uma API existente que eu consigo acessando o editar, ao lado do campo editável. 

Consigo acessar todos os end points, ou seja, eu consigo buscar todas as especialidades, buscar uma especialidade, cadastrar uma nova especialidade, editar uma especialidade remover uma especialidade. 

Mesma coisa com médicos, ou seja, tem dois CRUDs.

Poderia relacionar eles de alguma forma um pouco mais robusta, etc., mas eu não quero focar nessa parte. 

Então o que eu quero fazer começar a documentar essa API e antes de falarmos sobre especialidades, médicos, inserir médico, atualizar especialidade, precisamos descrever a API em si. 

Vamos chamar essa API de uma API de consultório.

Então vamos começar com isso, dando um título para nossa API, descrevendo-a de alguma forma, só que no nosso Swagger Editor, precisamos informar qual formato estou utilizando. 

Como vimos no início do Swagger 2.0 ou OpenAPI 3.0. 

```
openapi: 3.0.1
```

Então vamos fazer isso, eu vou utilizar o OpenAPI e eu posso começar a escrever e clicar em "Ctrl + Espaço", ele mostra as opções que posso colocar.

Ele não consegue entender, ele não consegue renderizar essa definição, porque ele precisa ser um desses valores que aparecem na tela, o swagger: 2.0, openapi: 3.0.0. 

Então vamos utilizar o openapi: 3.0.0, que é aquela versão que já estava como padrão. 

### propriedade obrigatorio da API: info
Ele nos mostrando alguns erros, o primeiro é que existe uma propriedade obrigatória chamada info.

Então vamos adicionar essa info na nossa chave, e quando colocamos o info, outros erros vão aparecer. 


Primeiro tem um erro estrutural na minha propriedade info, porque ela precisa ser um objeto, ou seja, preciso ter mais propriedades em info.

E o formato que estamos utilizando, acredito que é interessante citar que, com o Swagger Editor, nós podemos editar um arquivo em Json ou em Yaml. 

Eu acho Yaml um pouco mais interessante para escrever, para ler e visualizar, então eu vou continuar com ele, se você quiser pode converter para Json. Mas eu vou manter o Yaml.

Então vamos lá, em info eu uso identação para informar que o que eu vou escrever agora está dentro de info. 

### title
Vou dar dois "Espaços" e informar o título da nossa API, a chave title:. 

Que eu posso colocar, por exemplo, uma API de consultório, eu poderia criar um nome criativo para essa API, mas não vou. 

Repara que já começa a aparecer no lado direito a nossa documentação, eu posso esconder os erros se eu quiser clicando em "Hide" no canto direito, mas eu vou deixá-los aqui.

```
openapi: 3.0.1
info:
  title: API de consultorio
```

O que mais além do título eu posso ter? 

### description
Posso ter descrição, eu começo a escrever a palavra, "Ctrl + Espaço > description" e escrevo API para controlar médicos e suas especialidades dentro do consultório, tenho a nossa descrição da API. 

Conforme eu vou digitando, ele já vai atualizando do lado direito.

```
openapi: 3.0.1
info:
  title: API de consultorio
  description: API para controlar médicos e suas especialidades dentro do consultório
```

### versao da API
Para finalizarmos, que eu já falei bastante, vamos adicionar mais uma informação. 

A nossa API pode ter versões, eu posso versionar a minha API. 

Então olha essa é a documentação da versão 0.0.1 da minha API, que é uma versão Alpha. 

Posso adicionar a chave "version: 0.0.1".

```
openapi: 3.0.1
info:
  title: API de consultorio
  description: API para controlar médicos e suas especialidades dentro do consultório
  version: 0.0.1
```

Então já tenho, praticamente, toda a definição obrigatória da API em si. 

Ou seja, eu tenho um título para ela, eu tenho uma descrição e o informei a versão.

Então agora ela já começou a ser renderizada de forma correta, só que tem um detalhe ainda, eu não tenho caminhos, não tenho end points para essa API.

Mas antes de descrevermos os end points, por exemplo, especialidades e médicos, vamos ver o que mais podemos informar sobre a API em si. 

Já temos todos os dados obrigatórios, mas podemos informar mais coisas como, por exemplo, links externos, um endereço de contato, licença dessa API e muito mais. 

### documento completo atual
```
openapi: 3.0.1
info:
  title: API de consultorio
  description: API para controlar médicos e suas especialidades dentro do consultório
  version: 0.0.1
```

## adicionando links
Antes de definirmos end points, chamado aqui de paths, vamos definir algumas informações a mais sobre nossa própria API, então podemos adicionar algumas coisas que vão ser apresentados com links. 

Por exemplo, eu posso colocar uma documentação externa, eu posso colocar os termos de serviço.

Vamos adicionar exatamente isso. 

Eu não tenho termos de serviço reais para essa API, até porque ela nem existe. 

Mas vamos colocar um link mentira, um link falso. 

### termsOfService
Então posso adicionar a chave terms “Ctrl + Espaço" que o Swagger Editor completa a chave automaticamente.

Nessa chave "termsOfService" eu vou adicionar um link, que vai redirecionar a pessoa a uma página quando ela clicar em TermsofService. 

Então vou colocar https://mockapi.io, quando ele salvar já aparece o TermsofService no lado direito da página.

Seu eu abrir o link TermsofService no lado direito em uma nova guia, ele vai abrir a página "mockapi.io". 

Então como eu estou logado, ele já abre na área de projetos, vou fechar essa guia e voltar par ao Editor.

```
openapi: 3.0.1
info:
  title: API de consultorio
  description: API para controlar médicos e suas especialidades dentro do consultório
  version: 0.0.1
  termsOfService: https://www.google.com.br/
```

Eu posso adicionar documentação externa, imagina que eu tenho essa documentação viva, onde a pessoa tem acesso a todos os endpoints, ela pode testar em tempo real e que eu tenho outra documentação, um pouco mais formal.

Com um texto super extenso, explicando o propósito de cada coisa, um motivo para algo existir, ou ainda como você pode conseguir a chave de acesso, etc.

Então se eu tenho uma documentação externa, além Swagger eu posso adicionar. 

Só não na parte de info, vou adicionar outra chave, outro valor na raiz desse documento. 

O que eu quero dizer com raiz, na raiz, até o momento, eu tenho o openapi, info e agora vou ter externalDocs. 

### ExternalDocs
Ou seja, uma documentação externa.

Essa documentação externa, quando eu adiciono apenas a chave, aparece um erro no lado direito da tela, que nos diz que ela precisa ser um objeto, então ela tem outras propriedades. 

Que propriedades são essas? 

Quando dou um "Ctrl + Espaço" ele vai mostrar as opções description ou URL.

Ou seja, a descrição dessa documentação externa, que o que vai ficar escrito, e a URL que exatamente o link. 

Eu posso escrever nessa chave "Documentação burocrática", então algo que faça sentido para a sua API. 

Já na URL, que é obrigatório eu posso colocar também aquele mesmo link, https://mockapi.io, e vai aparecer para nós no lado direito da tela "Documentação burocrática".

```
externalDocs:
  description: Documentaçao burocratica
  url: https://www.google.com.br/

```

De novo, seu eu abro o link "Documentação burocrática" em uma nova guia, ele vai abrir o link do MockAPI. 

Dessa forma conseguimos adicionar links, eu consigo adicionar termos de serviço, eu consigo adicionar documentação externa, eu poderia colocar qualquer coisa aqui, mesmo que não fosse uma documentação externa.

Como, por exemplo, o site para os nossos planos, "saiba mais sobre nossos planos" como um link acessível. 

Você pode colocar qualquer coisa, então temos acesso a uma descrição e a uma URL. 

Vou deixar escrito “Documentação burocrática” mesmo, porque podemos fingir que é só uma documentação externa.

Já vamos avançando na definição da nossa API, assim existe uma infinidade do que podemos fazer aqui, então não quero me estender muito. 

Por exemplo, informações de contato, para quem a pessoa vai enviar um e-mail se tiver algum problema?

E a licença, esta API pode ser utilizado por qualquer pessoa? 

É uma API pública ou é uma exclusiva? 

Qual a licença dessa API, como a pessoa vai saber como ela pode utilizar. 

### documento completo atual
```
openapi: 3.0.1
info:
  title: API de consultorio
  description: API para controlar médicos e suas especialidades dentro do consultório
  version: 0.0.1
  termsOfService: https://www.google.com.br/
externalDocs:
  description: Documentaçao burocratica
  url: https://www.google.com.br/
```

## Complementando infos
Como eu disse, quero adicionar algumas informações a mais para essa API. 

Primeiro, a licença, ou seja, como a pessoa pode utilizar a API, e algum dado de contato. 

### contact
Vamos começar pelo contato, se eu começar a escrever contato e apertar em "Ctrl + Espaço" para completar, eu posso adicionar um contato diretamente, e eu vejo que contato também é um objeto.

O contrato ele pode ter um nome, um e-mail e uma URL. 

Vamos começar com o nome, vou colocar nome: Suporte a Devs. 

E esse suporte a devs vai ter comente um e-mail, que vai ser email: contato@example.com. 

Então vai aparecer no lado direito da tela a opção "Contact Suporte a Devs" e se eu clicar, ele vai abrir algo de e-mail para enviar um e-mail para lá.

```
info:
  title: API de consultorio
  description: API para controlar médicos e suas especialidades dentro do consultório
  version: 0.0.1
  termsOfService: https://www.google.com.br/
  contact:
    name: Suporte a Devs
    email: contato@example.com
```

Se eu quiser ter uma URL, eu posso ter uma, url: https://mockapi.io. 

No lado direito já aparece o website, ou seja, o link para este Suporte a Devs ou enviar um e-mail para o Suporte a Devs. 

```
info:
  title: API de consultorio
  description: API para controlar médicos e suas especialidades dentro do consultório
  version: 0.0.1
  termsOfService: https://www.google.com.br/
  contact:
    name: Suporte a Devs
    email: contato@example.com
    url: https://www.google.com.br/
```

Então conseguimos ter essas duas informações quando estamos falando sobre contatos. Ou um Website, ou um e-mail ou ambos.

### licença
Então já temos as informações de contato, eu quero adicionar uma licença, eu quero informar que essa API tem como licença a GPL 3 que é General Public License, alguma coisa assim. 

Eu posso adicionar uma license:, e a licença também é um objeto, ela tem o nome da licença e a URL da licença. 

Vamos começar com o nome, que vai ser nome: GPLv3 e a URL desta licença é esse link, url: https://www.gnu.org/licenses/gpl-3.0.html.

Se eu clicar nesse link ele abre o site da GNU, em específico da "General Public License". No lado direito é possível perceber que licença é essa. Já aparece o link para a pessoa acessar, ler e saber tudo que ele precisa em relação à licença da nossa API. 

Eu posso escrever o que eu quiser no license, não é obrigatório estar escrito o nome da licença específico, mas obviamente faz sentido que o utilize.

Posso ainda colocar como name: "Licença: GPLv3", entre aspas para aparecer os dois pontos, informando que a licença é a GPLv3. 

```
info:
  title: API de consultorio
  description: API para controlar médicos e suas especialidades dentro do consultório
  version: 0.0.1
  termsOfService: https://www.google.com.br/
  contact:
    name: Suporte a Devs
    email: contato@example.com
    url: https://www.google.com.br/
  license:
    name: "Licença: GPLv3"
    url: https://www.google.com.br/
```

Dessa forma conseguimos ter vários links de apoio na nossa API, além da descrição, título, versão e claro, temos informações extras.

### documento completo atual
```
openapi: 3.0.1
info:
  title: API de consultorio
  description: API para controlar médicos e suas especialidades dentro do consultório
  version: 0.0.1
  termsOfService: https://www.google.com.br/
  contact:
    name: Suporte a Devs
    email: contato@example.com
    url: https://www.google.com.br/
  license:
    name: "Licença: GPLv3"
    url: https://www.google.com.br/
externalDocs:
  description: Documentaçao burocratica
  url: https://www.google.com.br/
```  

## Para saber mais: Info Object
Neste capítulo nós utilizamos as chaves externalDocs e info. Todas as chaves que usamos possuem alguns campos obrigatórios e outros opcionais.

Nesse link você pode conferir os campos de info: https://swagger.io/specification/#info-object

Aqui você pode conferir as informações da chave externalDocs: https://swagger.io/specification/#external-documentation-object

## o que aprendemos?
* definimos informaçoes sobre a API no Swagger editor
* Aprendemos a adicionar links sobre API
* adicionamos detalhes de contat e licença da API

## Recursos e verbos
Agora eu quero tornar o que já fizemos um pouco mais funcional, tentar, pelo menos, fazer uma requisição, para buscar todas as especialidades. 

### Paths
Para isso eu preciso definir os paths.

Então vamos definir o paths, adicionando a chave "paths:" e se eu dou um "Enter" aparece o erro no lado direito da tela me avisando que isso é um objeto. 

Precisamos definir chaves e valores, as chaves desse objeto vão ser as URLs, por exemplo, a chave /especialidades:. 

E o valor de cada uma dessas chaves é outro objeto também.

Podemos ter, nesse caso, os verbos, por exemplo, eu quero o verbo get: e esse verbo pode ter algumas informações como o sumary:, a descrição, o que isso realmente é. 

Então eu posso colocar sumary: Recupera todas as especialidades. 

Já começamos e na parte direita da tela já apareceu um detalhe, que é de um endpoint, de um path na nossa API.

```
paths:
  /especialidades:
    get:
      summary: Recupera todas as especialidades
```

Inclusive se clicar nesse path ele me mostra parâmetros, que eu não tenho ainda, e ele me mostraria as possíveis respostas, que também não tenho. 

### servers
Mas eu quero atentar para outro detalhe, o "Default". 

Nós temos essa informação, essa API e quando eu tento fazer um execute, não acontece nada, ele não nos devolve nada.

Porque ele está tentando acessar editor.swagger.io/especialidades. 

Eu não tenho nenhum servidor informado, antes do default não tem nada informando qual é o servidor que eu estou acessando. 

Então antes de termos paths, eu preciso ter servidores. 

Teremos que adicionar um servidor, reparem que servers é um array, podemos inclusive ter mais de um servidor.

Então eu vou adicionar um array, onde eu posso informar a URL, - url:, description:. 

Clicar em “API de Teste” e eu vou pegar a URL da nossa API, que é "-url: http//mockapi.io/projects/6096015d116f300174b29bb". 

Ou seja, quando eu fizer um teste agora o que o Swagger vai tentar acessar é essa URL que acabei de adicionar, incluindo o "/especialidades”, usando o verbo get, sem passar parâmetro nenhum.

Então eu poderia ter mais de uma URL, imagina que eu quero ter uma documentação que possa acessar o nosso servidor de teste e o servidor de produção. 

Bastaria eu inserir uma outra URL, por exemplo, - url: google.com, e descrição seria description: API de Prod. 

Então eu posso hora fazer uma requisição para saber de nossa API de produção, hora para API de teste.

```
servers: 
- url: http//mockapi.io/projects/6096015d116f300174b29bb
  description: API de testes
- url: https://www.google.com.br/
  description: API de produçao
```

Vou retirar a "API de Prod", para não acabar fazendo requisição para o local errado. 

O Editor me mostra que eu ainda tenho erros, eu não tenho todas as informações necessárias, mas, teoricamente, eu já tenho suficiente para realizar uma requisição. 

Então vamos ver o que acontece quando eu aperto "F12" ou eu venho, em qualquer lugar da página, e clico "Botão direito > Inspecionar” e seleciono a aba "Networks".

Quando eu clico no botão "Execute", ele faz uma requisição para a nossa API de especialidades, eu abrir a requisição em uma nova aba, espera um pouco que ele está autorizando. 

Vamos ver, eu suponho que eu coloquei o link errado, deixa eu dar uma olhada na nossa API de especialidades. 

Vou colocar a URL correta "-url: http//6096015d116f00174b29ba.mockapi.io". 

Agora sim, eu copiei o link do projeto, era isso que estava errado, eu copiei o servidor errado.

```
servers: 
- url: http//6096015d116f00174b29ba.mockapi.io
  description: API de testes
- url: https://www.google.com.br/
  description: API de produçao
```

Agora sim, vamos executar, ele está fazendo uma requisição que está carregando, e vamos ver porque que não funcionou de novo. 

Vou executar e ver o que está acontecendo, ele está fazendo a requisição. 

Ótimo, ele devolveu algo, perfeito, a requisição foi feita, e por que ele não colocou nada para nós?

Vamos fechar a aba "Inspecionar" e recapitular tudo. 

O que acontece com essa interface, o que ele está fazendo? 

Quando eu tenho um path e tenho todas as informações dele, o próprio Swagger consegue realizar uma requisição de teste, e ele realmente está fazendo essa requisição. 

Tanto é que quando eu abri a aba de redes, a requisição foi feita para o local correto, devolveu as respostas corretas.

Eu ainda tenho erros aparecendo na minha tela, então isso, muito provavelmente, está impedindo o Swagger de exibir a resposta para nós. 

Porque ele não sabe o que exibir, ele não sabe se ele pode exibir tudo, se está tudo correto. 

Ou seja, ele não sabe que ele precisa parsear aquele Json e exibir na tela, por exemplo.

Então o que precisamos fazer agora, que exatamente o erro que está aparecendo no Editor. 

Eu preciso informar quais são as possíveis respostas desse endpoint. 

Se, por exemplo, tiver um erro no meu banco de dados eu respondo com o status 500, em caso de sucesso eu respondo com status 200, posso colocar até exemplos de resposta. 

Então vamos ver exatamente como conseguimos definir uma resposta.

### documento completo atual
```
openapi: 3.0.1
info:
  title: API de consultorio
  description: API para controlar médicos e suas especialidades dentro do consultório
  version: 0.0.1
  termsOfService: https://www.google.com.br/
  contact:
    name: Suporte a Devs
    email: contato@example.com
    url: https://www.google.com.br/
  license:
    name: "Licença: GPLv3"
    url: https://www.google.com.br/
externalDocs:
  description: Documentaçao burocratica

  url: https://www.google.com.br/

# servidores
servers: 
- url: http//6096015d116f00174b29ba.mockapi.io
  description: API de testes
- url: https://www.google.com.br/
  description: API de produçao


# endpoints
paths:
  /especialidades:
    get:
      summary: Recupera todas as especialidades
```  
    
## possiveis respostas
Vamos definir as possíveis respostas desse path ou endpoint. 

### responses
Eu vou adicionar o responses:, um objeto, onde a chave é o status possível. 

Então, imagine que em caso de sucesso, eu tenho 200. 

Dentro dessa chave eu posso ter a descrição desse status, então, por exemplo, description: Sucesso, ou algo do tipo.

Ainda, eu posso ter o conteúdo content:. 

Então vamos descrever esse conteúdo, o conteúdo pode ser em vários formatos. 

Logo, a chave do conteúdo é o formato, por exemplo, escrevo application/json:. 

E o valor é o conteúdo em si, posso ter então em Json, XML, texto puro, HTML e outros. 

Como eu posso descrever essa resposta?

Eu posso dar um exemplo, adicionar um texto puro mesmo, colocar mais de um exemplo. 

Mas o que eu vou fazer é definir um esquema adicionando a chave schema:, ou seja, vou informar qual é o tipo de retorno. 

Por exemplo, aqui o tipo vai ser objeto, type: object.

Esse objeto ele tem propriedade, escrevo properties:. 

Então posso definir para ele uma série de propriedade. 

Reparem que quando definir o responses a minha resposta já apareceu no lado direito da tela. 

Voltando as propriedades, eu vou ter uma propriedade chamada id:, essa ID tem como tipo type: integer, ela é do tipo inteiro.

Também vou ter uma propriedade descrição:, onde o tipo é um string, type: string.

Teoricamente eu tenho um esquema bem formatado, então vamos recapitular o que eu escrevi antes de vermos como ele vai aparecer. 

Eu tenho um path de especialidades, onde se eu fizer uma requisição get para especialidades, ele vai recuperar todas as especialidades e respostas possíveis no status 200.

Repare que só essa resposta possível, onde a description é no caso de sucesso, eu posso colocar ou não essa descrição, normalmente colocamos. 

E eu posso informar qual é o conteúdo, ou não, talvez eu não precise informar, mas dessa vez eu quero informar. 

O conteúdo devolvido é em Json, ou seja, isso é o formato, é um mimetype. 

Eu poderia ter Text, HTML, ou alguma outra coisa, Text Plain se fosse um texto puro, mas eu vou querer Jason.

Eu posso definir ou exemplos de como isso vai retornar, ou um scheme, um esquema de como isso vai ser e através desse esquema o próprio Swagger pode montar exemplos para mim. 

Então como esse esquema? 

Ele poderia ser um a única string, poderia ser uma inteira, mas nesse caso vai ser um objeto.

E quais são as propriedades desse objeto? 

ID, que é do tipo inteiro, e descrição que é do tipo string. 

```
paths:
  /especialidades:
    get:
      summary: Recupera todas as especialidades
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              schema:
                type: object
                properties:
                  id:
                    type: integer
                  descricao:
                    type: string
```

Com isso definido, vamos ver como fica, repara que eu poderia ter várias respostas para os parâmetros, mas eu tenho uma só. 

Onde o código é 200 e descrição é sucesso. 

Posso ainda ter vários media types, vários tipos dessa resposta.

No meu caso eu tenho apenas o application/json como media type. 

Com o scheme que adicionamos o Editor ele já monta um valor de exemplo, e eu cometi um errinho, defini como se o retorno fosse um objeto, quando na verdade é um array. 

Então vamos modificar, na verdade, o type: array, onde items: type: object e as outras propriedades são essas.

```
paths:
  /especialidades:
    get:
      summary: Recupera todas as especialidades
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              schema:
                type: array
                items:
                  type: object
                  properties:
                    id:
                      type: integer
                    descricao:
                      type: string
```

Agora que está tudo certo, agora é um array, onde cada item desse array tem ID, que um inteiro, e descrição que é uma string. 

Agora, com essa resposta mapeada, o que eu vou fazer é tentar executar essa requisição de exemplo. 

Depois que eu o executo, nos mostra o comando que eu poderia executar usando o “curl” para fazer essa reposição, qual é a URL efetiva que ele fez requisição, e a resposta real.

Então eu tenho o ID 1 e a descrição desse ID, dessa especialidade é teste, ele mostra também os cabeçalhos dessa resposta, tudo funcionou. 

Conseguimos diretamente do nosso Swagger UI, que está dentro do Swagger Editor, fazer uma requisição real para nossa API. 

Não só conseguimos documentar, mas podemos fornecer um ambiente de teste para a nossa API.

Já definimos as respostas, definimos como esse dado volta do Servidor, mas conseguimos definir como enviar informações para o servidor. 

Através de parâmetros, ou até no corpo dar requisição. 
### documento completo atual
```
openapi: 3.0.1
info:
  title: API de consultorio
  description: API para controlar médicos e suas especialidades dentro do consultório
  version: 0.0.1
  termsOfService: https://www.google.com.br/
  contact:
    name: Suporte a Devs
    email: contato@example.com
    url: https://www.google.com.br/
  license:
    name: "Licença: GPLv3"
    url: https://www.google.com.br/
externalDocs:
  description: Documentaçao burocratica

  url: https://www.google.com.br/

# servidores
servers: 
- url: http//6096015d116f00174b29ba.mockapi.io
  description: API de testes
- url: https://www.google.com.br/
  description: API de produçao


# endpoints
paths:
  /especialidades:
    get:
      summary: Recupera todas as especialidades
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              schema:
                type: array
                items:
                  type: object
                  properties:
                    id:
                      type: integer
                    descricao:
                      type: string
```

## Parametros na requisicao
Então já sabemos como definir um path, ou endpoint, já sabemos como definir o que ele traz de volta para nós. 

Agora vamos definir o que podemos mandar para eles. 

Se dermos uma olhada na nossa MockAPI, quando eu clico em "Edit" a especialidade, eu tenho a opção de enviar um ID para especialidades.

### parametros na URL
Para essa URL eu posso colocar "/especialidade/1", e ele vai trazer somente a especialidade com o ID 1. 

Então vamos definir exatamente isso, para podermos enviar esse parâmetro. 

Lá no final da página do Editor eu vou inserir um novo path, usando as especialidades/, e eu preciso informar que nessa parte da URL vai ser um parâmetro. 

```diff
+ E para informar que é um parâmetro eu coloco entre chaves {id}, chamando de ID.
```

Posso chamar do que eu quiser, por exemplo, especialidadeID, alguma coisa assim, mas eu vou chamar só de ID. 

Vamos lá, eu quero mapear uma requisição adicionando o verbo get. 

Dentro dessa requisição get aquela mesma história eu posso ter um sumary: Recupera uma entidade pelo ID.

E eu posso ter as responses, mas antes de ter as respostas eu quero mapear esse parâmetro ID, que o primeiro erro que está aparecendo para mim. 

Esse parâmetro ID que foi declarado, ele precisa ser definido de alguma forma, ou dentro da aplicação toda, ou dentro desse path.

Então vamos lá, eu vou informar que eu tenho parameters:. 

Essa chave parâmetro ela é um array, no quadro a direita “precisa ser uma array”. 

Para definir um array o que eu posso definir no parâmetro o nome dele e tem que ser exatamente o que tá aqui no URL, então no caso é ID, eu preciso informar onde esse parâmetro ID vai ser enviado.

Esse parâmetro ID eu sei que ele vai ser enviado direto na URL no path, porque ele está já está definido. 

Então vou colocar abaixo no nome, in: path. 

Só que existem outras possibilidades, por exemplo, se ao invés especialidades/id, fosse /especialidades/id/1, com uma query string eu colocasse que o ID é 1, ao invés de fazer especialidade/1, se fosse naquele outro formato eu poderia colocar aqui uma query e remover esse parâmetro id daqui, mas não é o nosso caso, realmente vai ser no path.

Eu posso adicionar algumas outras informações como, por exemplo, colocando o schema, então aqui eu vou definir o type: integer, e esse tipo é um inteiro, ou seja, o ID precisa ser um número. 

Eu preciso informar se este parâmetro é ou não obrigatório, no nosso caso como ele tá na URL, eu preciso passar ele.

Então required: true, ou seja, verdadeiro, eu preciso informar esse parâmetro.

Tendo definido como eu envio esse parâmetro, se eu dou uma olhada no nosso Swagger UI, quando eu for enviar essa requisição eu posso adicionar a informação de ID nela. 

```
  /especialidades/{id}
    get:
      summary: Recupera uma entidade pelo ID
      parameters:
      - name: id #deve ser igual ao definido no caminho do path {id}
        in: path
        schema: 
          type: integer
        required: true
```

Mas antes vamos colocar as respostas possíveis.

Volto ao Editor, dou um "Enter", e adiciono "responses:", com aquele esquema. 

Eu posso ter uma resposta de sucesso que vai ser assim desciption: Sucesso, com nesse caso foi sucesso. 

Ainda temos o content que é um application/json:, então sempre respostas dessa API vão vir em Json.

Da mesma forma como fizemos anteriormente, eu posso adicionar um schema:. 

Então vou pegar isso daqui do nosso path. 

Porque não vou retornar o array, somente o objeto direto. 

Repara que eu já tenho uma resposta em Json, no caso de sucesso, trazendo um ID e uma descrição.

Então eu posso testar essa requisição, eu vou buscar a especialidade com ID 1, quando eu executo no Swagger UI. 

```
/especialidades/{id}:
    get:
      summary: Recupera uma entidade pelo ID
      parameters:
      - name: id #deve ser igual ao definido no caminho do path {id}
        in: path
        schema: 
          type: integer
        required: true
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              schema:
                type: array
                items:
                  type: object
                  properties:
                    id:
                      type: integer
                    descricao:
                      type: string
```

A requisição feita corretamente e tá devolvendo a requisição com o ID 1, e tem a descrição teste. 

Mas repare que nas respostas possíveis, eu só tenho um caso de sucesso, e se eu passar o ID errado? 

Se eu passar o ID errado eu já sei o que vai acontecer.

### documentando um 404
Então primeiro eu vou descrever, caso eu passe o errado eu vou ter um cenário de 404. 

E a descrição para isso eu vou dizer que é description: Especialidade não encontrada. 

O conteúdo dessa resposta um pouco diferente também, vai vir com o cabeçalho informando um application/Json, mas, na verdade, eu nem preciso de um schema.

#### response message example: "not found"
Eu posso ter se eu quiser, mas, na verdade, eu já vou colocar um example, porque ele vai retornar a mensagem example: “Not found”. 

Como isso vai ser exibido, deixa eu fazer um clear, para limpar aquela resposta que já veio. 

Então, de novo, eu tenho aqui um possível ID para eu passar e as possíveis respostas são 200 em caso de sucesso, e 404 no caso de especialidade não encontrada.

O valor retornado vai ser um string 'Not found'. 

```
  /especialidades/{id}:
    get:
      summary: Recupera uma entidade pelo ID
      parameters:
      - name: id #deve ser igual ao definido no caminho do path {id}
        in: path
        schema: 
          type: integer
        required: true
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              schema:
                type: array
                items:
                  type: object
                  properties:
                    id:
                      type: integer
                    descricao:
                      type: string
        400:
          description: Especialidade nao encontrada
          content:
            application/json:
              example: "Not Found"
```

Então eu posso na barra de busca do UI e tentar buscar “especialidade dois”, por exemplo, que eu sei que não existe. 

Quando eu executar a resposta exatamente o que eu disse, Not found, esse é o corpo da resposta. 

O código é 404 e tem o content - type: json, então mapeamos corretamente.

Então reparem que nós fizemos duas coisas nessa aula, nós mapeamos um parâmetro, ou seja, nós podemos enviar um parâmetro para nesse específico get de /especialidades/{id}/, podemos passar esse parâmetro. 

E esse parâmetro tem que ser um inteiro e é obrigatório.

### Parametros globais
“Ah Vinícius, eu poderia colocar esses parâmetros fora da minha operação get, poderia colocar aqui direto aqui fora, se eu copiar aqui para fora, isso aqui daria um erro?”

Vamos ver o que acontece, isso não veio. O que vai acontecer agora é se eu tiver alguma requisição além do verbo get. 

Se eu tiver, por exemplo, algum put ou post it, eu já vou ter as definições desse parâmetro ID definidas corretamente.

Então deixa eu limpar a execução e eu continuo conseguindo passar o parâmetro corretamente, ele busca corretamente. 

Só para você entender um pouco melhor o que isso quer dizer. 

Se eu tiver além de uma requisição do tipo get, alguma outra requisição para especialidades/id, eu não preciso de novo repetir essa definição do parâmetro.

```
/especialidades/{id}:
    parameters:
      - name: id #deve ser igual ao definido no caminho do path {id}
        in: path
        schema: 
          type: integer
        required: true
    get:
      summary: Recupera uma entidade pelo ID
      responses:
      ...
```
Eu posso simplesmente definir esse parâmetro para todos os verbos que forem feitos nesse path, nessa URL. Então essa é a diferença entre colocar direto na “especialidades”, no mesmo nível que todos os verbos. Ou colocar dentro de algum verbo, se eu colocar como estava antes, dentro do get. 

Significa que se eu tivesse um put, por exemplo, eu teria que definir esse parâmetro de novo.

Agora nesse caso como eu fiz agora pouco, para todos os verbos que eu definir esse parâmetro já vai estar definido. 

Então recapitulando, nós aprendemos três coisas, na verdade, como definir um parâmetro, seja para um end point específico ou para um verbo específico. 

Aprendemos também a como definir mais de uma resposta, inclusive, não só com um schema, mas também com o example.

Ou seja, além de definir o esquema, o que vem, um objeto, eu posso direto dar um exemplo de como ele virá. 

Então dessa forma conseguimos definir essa resposta. 

Agora não só parâmetros podemos enviar para lá, imagina que eu queria cadastrar uma nova especialidade.

Então quero fazer uma requisição post para a barra especialidades. 
### documento completo atual
```
openapi: 3.0.1
info:
  title: API de consultorio
  description: API para controlar médicos e suas especialidades dentro do consultório
  version: 0.0.1
  termsOfService: https://www.google.com.br/
  contact:
    name: Suporte a Devs
    email: contato@example.com
    url: https://www.google.com.br/
  license:
    name: "Licença: GPLv3"
    url: https://www.google.com.br/
externalDocs:
  description: Documentaçao burocratica

  url: https://www.google.com.br/

# servidores
servers: 
- url: http//6096015d116f00174b29ba.mockapi.io
  description: API de testes
- url: https://www.google.com.br/
  description: API de produçao


# endpoints
paths:
  /especialidades:
    get:
      summary: Recupera todas as especialidades
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              schema:
                type: array
                items:
                  type: object
                  properties:
                    id:
                      type: integer
                    descricao:
                      type: string
                      
  /especialidades/{id}:
    get:
      summary: Recupera uma entidade pelo ID
      parameters:
      - name: id #deve ser igual ao definido no caminho do path {id}
        in: path
        schema: 
          type: integer
        required: true
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              schema:
                type: array
                items:
                  type: object
                  properties:
                    id:
                      type: integer
                    descricao:
                      type: string
        400:
          description: Especialidade nao encontrada
          content:
            application/json:
              example: "Not Found"
```

## dados no corpo da requisiçao
Vamos definir um cenário onde consigamos cadastrar uma nova especialidade.

Nós temos duas URLs por enquanto, /especialidades e  /especialidades/id. 

Então a URL para eu cadastrar algo também é /especialidades, não uma URL nova, como /especialidades/nova, ou algo do tipo.

Então o que eu vou fazer é definir um novo verbo dentro desse mesmo path. 

Então vamos definir um post:, através do verbo post eu consigo criar uma nova especialidade. 

Eu posso adicionar as mesmas informações, como, por exemplo, sumary: Criar nova especialidade. 

Posso utilizar o sumary para informar o que esse end point faz.

Mas eu também tenho o description: “Através desse endpoint você pode criar novas especialidades". 

Então isso não aparece de cara aqui, mas aparece na descrição. 

Então se algo precisar de uma informação a mais, você pode adicionar a descrição.

Vou tirar a 'description', que no nosso caso não é necessário.

Temos o sumary, e o que mais temos no nosso caso do get. 

Nós temos as respostas, então vamos criar também as responses. 

Porém, eu ainda não sei como é a resposta nesse post, eu vou supor que ele me retorna um 201, que é o created, ou seja, funcionou, deu tudo certo. 

Eu vou adicionar um description: “Sucesso”, então eu suponho que seja isso, eu nem vou colocar o scheme, porque eu não sei o que ele me devolve.

Só que além da resposta eu preciso informar como que essa especialidade que eu estou criando vai ser enviada. 

Então preciso enviar uma especialidade, no meu caso eu preciso enviar somente a descrição. 

### requestBody
Vamos definir o nosso requestBody: Então temos uma nova chave dos nossos verbos HTTP que é o requestbody. 

E podemos colocar uma descrição, informando se no corpo você precisa enviar o objeto do tipo especialidade.

Ou posso ir direto para o content onde podemos colocar application/json e aqui dentro o nosso schema que já conhecemos, então vai ser um type: object
properties: descricao: onde type: string.

```
    post:
      summary: Cria nova especialidade
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                descricao:
                  type: string
      responses:
        201:
          description: "Sucesso"
```

Se não escrevi nada errado, ele já mostra um valor de exemplo, então descrição e alguma string, e me mostra também o schema. 

Então vamos testar, no corpo ele já preenche para mim esse Json, com um valor de exemplo, eu vou colocar no corpo uma "nova especialidade".

Vamos realizar essa requisição e ver como vem resposta, se a resposta vai chegar, mesmo sem ter definido o schema, vamos ver o que acontece. 

Quando eu executo ele mostra de novo seu URL completo, aparentemente tudo bem, e realmente ele devolveu um 201 e o corpo é um objeto do tipo especialidade.

Ou seja, ele traz para nós o ID e a descrição. 

Então podemos colocar aqui, vamos aproveitar a informação que temos agora para colocar o nosso content com o application/json:sendo esse schema: aqui. 

```
    post:
      summary: Cria nova especialidade
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                descricao:
                  type: string
      responses:
        201:
          description: "Sucesso"
          content:
            application/json:
              schema:
                type: object
                  properties:
                    id:
                      type: integer
                    descricao:
                      type: string
```

Eu posso copiar o type: object com as propriedades lá do nosso path. 

O tipo é um objeto e as propriedades são essas. 

Então dessa forma conseguimos descrever como é o corpo de uma requisição, como o corpo de uma requisição precisa ser e, inclusive, acabamos de fazer um post. 

Ou seja, nós criamos uma nova especialidade, se eu vier e buscar todas as especialidades, eu espero que venham duas agora. 

Apareceu a descrição teste e a descrição nova especialidade.

Então com isso, já conseguimos definir como enviar informações para o servidor, seja com parâmetros, como nós vimos, que pode ser do path, na query, no header ou em cookie. 

Vimos como enviar um requestbody, ou seja, mandar dados no corpo da requisição.

Agora eu vou deixar um desafio para você, já tenho o get, tenho post, faltam só dois verbos para completarmos o crud da especialidade.

Então com o que temos, você já consegue fazer o put e o delete, como que isso vai ser? 

Deixa-me te explicar o que você vai fazer. 

Em especialidades já conseguimos criar uma especialidade e buscar todas. 

Já em especialidades/id conseguimos buscar uma, atualizar a especialidade em questão e remover uma especialidade.

Então, além do get, você vai adicionar o put e o delete, vai fazer alguns testes, verificar o que é necessário para você realizar suas requisições. 

Sempre crie uma especialidade e depois tente remover, ver o que é necessário. 

Crie uma nova especialidade, tente atualizá-la, ver o que é necessário enviar. 

Dessa forma você vai chegar na documentação.

Caso, por algum motivo, você não consiga, o fórum está aberto e eu vou tentar te ajudar, mas com o conhecimento que já temos, é possível documentar essas duas novas operações. 
### documento completo atual
```
openapi: 3.0.1
info:
  title: API de consultorio
  description: API para controlar médicos e suas especialidades dentro do consultório
  version: 0.0.1
  termsOfService: https://www.google.com.br/
  contact:
    name: Suporte a Devs
    email: contato@example.com
    url: https://www.google.com.br/
  license:
    name: "Licença: GPLv3"
    url: https://www.google.com.br/
externalDocs:
  description: Documentaçao burocratica

  url: https://www.google.com.br/

# servidores
servers: 
- url: http//6096015d116f00174b29ba.mockapi.io
  description: API de testes
- url: https://www.google.com.br/
  description: API de produçao


# endpoints
paths:
  /especialidades:
    get:
      summary: Recupera todas as especialidades
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              schema:
                type: array
                items:
                  type: object
                  properties:
                    id:
                      type: integer
                    descricao:
                      type: string
                      
    post:
      summary: Cria nova especialidade
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                descricao:
                  type: string
      responses:
        201:
          description: "Sucesso"
          content:
            application/json:
              schema:
                type: object
                properties:
                  id:
                    type: integer
                  descricao:
                    type: string
                      
  /especialidades/{id}:
    parameters:
      - name: id #deve ser igual ao definido no caminho do path {id}
        in: path
        schema: 
          type: integer
        required: true
    get:
      summary: Recupera uma entidade pelo ID
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              schema:
                type: object
                properties:
                  id:
                    type: integer
                  descricao:
                    type: string
        400:
          description: Especialidade nao encontrada
          content:
            application/json:
              example: "Not Found"
              
    put:
      summary: Atualiza uma entidade pelo ID
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                descricao:
                  type: string        
      responses:
        200:
          description: "Sucesso"
          content:
            application/json:
              schema:
                type: object
                properties:
                  id:
                    type: integer
                  descricao:
                    type: string
        404:
          description: Especialidade nao encontrada
          content:
            application/json:
              example: "Not Found"
              
    delete:
      summary: Deleta uma entidade pelo ID
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              example: "OK"
        404:
          description: Especialidade nao encontrada
          content:
            application/json:
              example: "Not Found"
  
```

### conteudo do corpo
nós definimos o que deve ser enviado no corpo de uma requisição de nossa API através da chave requestBody. 

O requestBody possui uma propriedade content que é um mapa (ou dicionário).

O que significa cada chave do mapa content?

R: o formato da requisiçao

```diff
+ Cada chave do mapa é um tipo de mídia que será enviado como o cabeçalho Content-Type. 

+ Em nosso exemplo, como a API só suporta JSON, informamos apenas application/json.
```

## o que aprendemos?
* aprendemos a definir um path, ou endpoint
* vimos como definir as possiveis respostas de um path
* aprendemos a definir parametros para uma requisiçao
* vimos como definir o corpo da requisiçao

## definindo tipos
Então já fizemos bastante coisa e a documentação está bastante funcional, eu diria até que ela está bem completa. 

Só que agora eu posso facilitar um pouco nossa vida, porque, por exemplo, o pedaço de código abaixo está sendo repetido em muitos lugares.

```
type: object
  properties:
    id:
      type: integer
    descricao:
      type: string
```

Então podemos melhorar isso criando esquemas em um lugar separado, chamado componentes, ou components. 

### components
Agora o que eu quero adicionar é "components:", que é um objeto. 

Dentro dele eu posso adicionar schemas, respostas, parâmetros, exemplos, corpos, cabeçalho, enfim, muitas coisas.

Mas o que eu quero adicionar é um schema. 

Esse schema tem como chave um nome e depois todas aquelas informações do tipo, se é um objeto ou não. 

Então, antes de qualquer coisa, vamos definir um tipo bem simples. 

Imagine que ao invés de ter o ID como um inteiro, eu queria criar um tipo ID.

Posso fazer da seguinte forma, eu vou chamar de Id:, e esse ID pode ter várias coisas como um type: integer, por exemplo. 

E está aparecendo um erro no meu documento porque esse ID não está sendo usado em nenhum lugar, mas se olho aqui em baixo eu já tenho essa definição, repara um ID como inteiro.

Posso ter um título, por exemplo, title: "Id", e eu posso ter uma descrição description: "Identificador único de alguma coisa", de alguma especialidade ou algo assim. 

Então podemos ir adicionando informações nessa chave e eu posso colocar, por exemplo, quantos caracteres esse ID pode ter, se fosse uma string, mas no caso é um inteiro, posso definir o valor máximo ou mínimo. 

O valor mínimo é um, não posso ter um inteiro menor que um.

Eu posso ir adicionando informações a esses componentes, a esses schemas. Então se eu consigo criar vários tipos, eu consigo criar um tipo chamado especialidade.

```
components:
  schemas:
    Id:
      type: integer
      title: "Id"
      description: "Identificador unico de alguma coisa"
      minimum: 1
```

### componentes
Conhecemos neste vídeo o conceito de componentes e nele nós pudemos definir um tipo ou schema.

Qual das definições a seguir é a mais correta para a chave components?

R: um conjunto de objetos para serem reutilizados

Em componentes nós podemos definir schemas, responses, requestBodys e muito mais.


## definindo objetos
Já sabemos como definir um tipo, se você ainda não fez isso, pausa o vídeo agora e define o tipo de especialidade, depois volta e ver se fizemos igual. 

Para você poder praticar, porque com os conhecimentos que temos, teoricamente, já conseguimos fazer. Então pausou, voltou e eu vou fazer com você.

Eu não vou ter mais o tipo ID, porque ele não está trazendo valor nenhum para nós.

Vou ter um tipo chamado Especialidade, esse tipo especialidade não é um inteiro, ele é objeto ele não tem esse título, ele não precisa dessa descrição. 

Se eu quiser posso colocar, mas ele não tem. 

E ele, obviamente, não tem valor máximo ou mínimo.

O que ele tem é propriedades. 

Então vou definir as propriedades do meu tipo especialidade, ele tem um ID que tem como tipo um inteiro, id que tem type: integer. 

Também tem uma descrição que tem como tipo uma string, descricao: que tem como tipo type: string.

Inclusive em uma string, poderíamos colocar um formato, por exemplo, se é uma data format: date-time. 

Mas no nosso caso não é nada disso, é realmente só uma string. 

Então não preciso de formato, mas acho válido citar.

Tenho meu schema definido então, teoricamente, isso já nos mostra um ID que é um inteiro, e uma descrição que é uma string. 

```
components:
  schemas:
    Especialidade: 
      type: object
      properties:
        id:
          type: integer
        descricao:
          type: string
```

Agora o que nós temos é um componente definido, nós temos um esquema definido, fora de qualquer operação, fora de qualquer path, fora de qualquer coisa.

O que eu quero fazer agora pegar o esquema, essa especialidade e utilizar em algum lugar. 

Mas, por enquanto, ainda não sei como fazer isso. Então vamos para recapitular o que fizemos na parte de definição, temos fora de qualquer objeto, nós temos a possibilidade de definir componentes.

Um dos componentes possíveis é o esquema, se eu tiver alguma resposta que é sempre devolvida igual. Por exemplo, se sempre que eu cadastrar uma especialidade, aparece uma especialidade sem o ID, e sempre que eu atualizo também vem sem o ID, eu posso definir um novo esquema.

Ou melhor, eu posso definir direto a resposta, então se sempre que eu insiro uma especialidade, ele devolve uma especialidade inteira. 

Quando eu busco especialidade, ele também traz de volta especialidade inteira. 

Eu posso definir essa resposta responses:. Inclusive posso dar um nome para essa resposta como, por exemplo, Especialidade também.

Dentro dessa chave você vai definir as informações dessa especialidade, da mesma forma como definiríamos uma resposta. 

Então um componente é algo que a gente pode reutilizar em vários lugares. 

Eu não vou definir essa resposta, eu vou deixar como desafio para que você defina.

Porque o que eu quero fazer agora é, de alguma forma, agora entendemos o que é um componente que é "qualquer coisa que eu possa reutilizar em vários lugares".

Quero saber como efetivamente reutilizar, eu quero pegar essa especialidade e utilizar. 

Reutilizar ela em todas as chaves que contém ID no meu documento, ou seja, pegar aquele componente fazer o uso dele em vários lugares.
### documento completo atual

```
openapi: 3.0.1
info:
  title: API de consultorio
  description: API para controlar médicos e suas especialidades dentro do consultório
  version: 0.0.1
  termsOfService: https://www.google.com.br/
  contact:
    name: Suporte a Devs
    email: contato@example.com
    url: https://www.google.com.br/
  license:
    name: "Licença: GPLv3"
    url: https://www.google.com.br/
externalDocs:
  description: Documentaçao burocratica

  url: https://www.google.com.br/

# servidores
servers: 
- url: http//6096015d116f00174b29ba.mockapi.io
  description: API de testes
- url: https://www.google.com.br/
  description: API de produçao


# endpoints
paths:
  /especialidades:
    get:
      summary: Recupera todas as especialidades
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              schema:
                type: array
                items:
                  type: object
                  properties:
                    id:
                      type: integer
                    descricao:
                      type: string
                      
    post:
      summary: Cria nova especialidade
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                descricao:
                  type: string
      responses:
        201:
          description: "Sucesso"
          content:
            application/json:
              schema:
                type: object
                properties:
                  id:
                    type: integer
                  descricao:
                    type: string
                      
  /especialidades/{id}:
    parameters:
      - name: id #deve ser igual ao definido no caminho do path {id}
        in: path
        schema: 
          type: integer
        required: true
    get:
      summary: Recupera uma entidade pelo ID
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              schema:
                type: object
                properties:
                  id:
                    type: integer
                  descricao:
                    type: string
        400:
          description: Especialidade nao encontrada
          content:
            application/json:
              example: "Not Found"
              
    put:
      summary: Atualiza uma entidade pelo ID
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                descricao:
                  type: string        
      responses:
        200:
          description: "Sucesso"
          content:
            application/json:
              schema:
                type: object
                properties:
                  id:
                    type: integer
                  descricao:
                    type: string
        404:
          description: Especialidade nao encontrada
          content:
            application/json:
              example: "Not Found"
              
    delete:
      summary: Deleta uma entidade pelo ID
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              example: "OK"
        404:
          description: Especialidade nao encontrada
          content:
            application/json:
              example: "Not Found"
components:
  schemas:
    Especialidade: 
      type: object
      properties:
        id:
          type: integer
        descricao:
          type: string
```

## Referenciando tipos 
Agora o que eu quero fazer é pegar algo que eu definir nos componentes e referenciar em outro lugar. 

Por exemplo, nas minhas respostas ou até no corpo, se fosse o caso, em um request body. 

Vamos começar onde eu tenho um array e dentro de items eu posso ter esse objeto, que a especialidade.

```
          content:
            application/json:
              schema:
                type: array
                items:
                  type: object
                  properties:
                    id:
                      type: integer
                    descricao:
                      type: string
```
### $ref
Em algum momento eu quero referenciar um componente, posso utilizar uma propriedade chamada $ref:". 

Essa propriedade chamada ref é uma string, então posso colocar entre aspas. 

Qual o formato dela? 

Eu começo com hashtag para indicar a raiz desse documento, como estou na raiz desse documento, eu posso acessar os componentes.

Dentro dos componentes eu posso acessar os schemas, e dentro de schemas especialidade, então "$ref: "#/components/schemas/Especialidades"". Então, teoricamente, agora na minha resposta de Especialidades tenho aqui como resposta possível aquele mesmo array. 

Logo, o meu esquema é um array de especialidade, aparece os colchetes indicando um array e dentro deles a Especialidades.

```
          content:
            application/json:
              schema:
                type: array
                items:
                  $ref: "#/components/schemas/Especialidade"
```

Vamos fazer exatamente isso para os nossos outros cenários onde utilizamos esse mesmo tipo. 

Reparem que no verbo 'post' não temos uma especialidade, porque não é um ID e uma descrição, temos apenas a descrição, então não conta.

Já na resposta podemos utilizar, podemos trazer esse ref aqui. 

```
      responses:
        201:
          description: "Sucesso"
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Especialidade"
```

Então vamos ver se eu coloquei no local correto, isso aqui é a resposta do meu post, então a resposta do meu post está certo, está lá como Especialidade.

Vamos ver onde mais eu posso colocar, aqui, nessa resposta do meu especialidades/{id}. 

```
    get:
      summary: Recupera uma entidade pelo ID
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Especialidade"
```

Também posso colar esse ref, então no especialidades/{id} a resposta está certa, aparecendo como um array, temos um esquema trazendo uma especialidade. 

Então repare que dessa forma conseguimos reutilizar código na nossa documentação.

Se em algum momento, por exemplo, essa resposta existe em muitos lugares, então aqui em responses eu tenho sempre um 200 quando o script no sucesso, e o conteúdo é sempre um applicationjson que o schema é essa referência?

Você pode colocar nos componentes a mesma response. 

Então, de novo, eu vou deixar como desafio, eu não vou implementar isso. Porque eu quero chamar atenção para um detalhe fizemos, contudo, eu não expliquei muito. 

### documento completo atual
```
openapi: 3.0.1
info:
  title: API de consultorio
  description: API para controlar médicos e suas especialidades dentro do consultório
  version: 0.0.1
  termsOfService: https://www.google.com.br/
  contact:
    name: Suporte a Devs
    email: contato@example.com
    url: https://www.google.com.br/
  license:
    name: "Licença: GPLv3"
    url: https://www.google.com.br/
externalDocs:
  description: Documentaçao burocratica

  url: https://www.google.com.br/

# servidores
servers: 
- url: http//6096015d116f00174b29ba.mockapi.io
  description: API de testes
- url: https://www.google.com.br/
  description: API de produçao


# endpoints
paths:
  /especialidades:
    get:
      summary: Recupera todas as especialidades
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              schema:
                type: array
                items:
                  $ref: "#/components/schemas/Especialidade"
                      
    post:
      summary: Cria nova especialidade
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                descricao:
                  type: string
      responses:
        201:
           $ref: "#/components/responses/Sucesso"
                      
  /especialidades/{id}:
    parameters:
      - name: id #deve ser igual ao definido no caminho do path {id}
        in: path
        schema: 
          type: integer
        required: true
    get:
      summary: Recupera uma entidade pelo ID
      responses:
        200:
        
          description: Sucesso
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Especialidade"
        400:
          description: Especialidade nao encontrada
          content:
            application/json:
              example: "Not Found"
              
    put:
      summary: Atualiza uma entidade pelo ID
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                descricao:
                  type: string        
      responses:
        200:
          $ref: "#/components/responses/Sucesso"
          
        404:
          description: Especialidade nao encontrada
          content:
            application/json:
              example: "Not Found"
              
    delete:
      summary: Deleta uma entidade pelo ID
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              example: "OK"
        404:
          description: Especialidade nao encontrada
          content:
            application/json:
              example: "Not Found"
components:
  schemas:
    Especialidade: 
      type: object
      properties:
        id:
          type: integer
        descricao:
          type: string
          
  responses:
    Sucesso:
      description: Sucesso
      content:
        application/json:
          schema:
            $ref: "#/components/schemas/Especialidade"

```

## Definindo arrays
Só para explicar um detalhe, algo que eu fiz, mas acabei não explicando muito bem. 

Nós podemos ter diversos tipos de dados, podemos ter integer que é um inteiro, number que é algum número diferente de inteiro, string que pode ser um texto qualquer, uma data, data e hora.

Podemos ter object, que são várias propriedades, ou seja, uma chave mapeada para um valor, uma chave uma mapeada para um valor. 

E podemos ter array, que é um conjunto de algum desses outros dados. 

Temos também o booleano, verdadeiro ou falso.

Então definimos um array no nosso documento e não falou muito sobre ele. 

Vamos definir alguns componentes teste, por exemplo, uma String: que é do tipo type: string ela pode ter como format: date-time. 

Esses tipos representam uma data ou uma data e hora.

Nós temos números Number: que é do type: number onde o formato pode ser float ou decimal. 

Float é um tipo de é número flutuante, ou decimal que é um pouco maior vamos dizer assim, algo que tem mais precisão.

Agora quando falamos de array, deixa eu remover o que acabei de fazer, temos um detalhe de interessante que já fizemos e é bastante simples. 

### items
Então vou chamar de especialidades no plural, o tipo array ele não possui propriedades, não possui formato, o que ele possui é items, ele tem aqui os itens.

A partir desse detalhe de itens, eu posso informar o tipo dele, por exemplo, eu posso informar título, todas as restrições que eu poderia em qualquer outro esquema.

Então posso indicar que ele é type: object e tem as properties: de uma especialidade. 

Ou eu posso vir aqui e fazer um $ref: “#/componentes/schemas/Especialidade”. 

Então se eu tenho especialidades, significa que é um array de especialidade. 

Ele é um array de ID e de descrição. 

Lá naquele momento que usamos array eu posso agora fazer um diretamente esse ref aqui. 

Porém, ao invés de ser especialidade, vai ser de especialidades, no plural.

```
components:
  schemas:
    Especialidade: 
      type: object
      properties:
        id:
          type: integer
        descricao:
          type: string
    Especialidades:
      type: array
      items:
        $ref: "#/components/schemas/Especialidade"
```      


Então deixa eu voltar na minha primeira definição de especialidade e o nosso example continua igual. 

```
  /especialidades:
    get:
      summary: Recupera todas as especialidades
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Especialidades"
```

Então essa aula foi só para entendermos um pouco melhor sobre os tipos, e vou deixar um "para saber mais" com todas essas definições de cada um dos tipos, mas era principalmente para entendermos o que fizemos na parte de arrays.

Porque quando eu tenho um tipo array eu preciso definir quais são os itens que vão estar dentro desse array. 

Que pode ser desde qualquer coisa, até outro esquema nosso mesmo. 

Conseguimos filtrar bem o que pode ter dentro de um array.

Falamos bastante sobre esses componentes, definimos esquemas, já sabemos até como reutilizar respostas e fica aí o desafio. 

Agora vamos ver o que mais podemos colocar nesses componentes que não trabalhamos ainda. 

Que inclusive, já dando spoiler, é algo que nem iremos utilizar em nossa API, mas é de extrema importância sabermos como fazer para APIs do mundo real. 

Então vamos falar um pouco sobre segurança.

### documento completo atual

```
openapi: 3.0.1
info:
  title: API de consultorio
  description: API para controlar médicos e suas especialidades dentro do consultório
  version: 0.0.1
  termsOfService: https://www.google.com.br/
  contact:
    name: Suporte a Devs
    email: contato@example.com
    url: https://www.google.com.br/
  license:
    name: "Licença: GPLv3"
    url: https://www.google.com.br/
externalDocs:
  description: Documentaçao burocratica

  url: https://www.google.com.br/

# servidores
servers: 
- url: http//6096015d116f00174b29ba.mockapi.io
  description: API de testes
- url: https://www.google.com.br/
  description: API de produçao


# endpoints
paths:
  /especialidades:
    get:
      summary: Recupera todas as especialidades
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Especialidades"
                      
    post:
      summary: Cria nova especialidade
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                descricao:
                  type: string
      responses:
        201:
           $ref: "#/components/responses/Sucesso"
                      
  /especialidades/{id}:
    parameters:
      - name: id #deve ser igual ao definido no caminho do path {id}
        in: path
        schema: 
          type: integer
        required: true
    get:
      summary: Recupera uma entidade pelo ID
      responses:
        200:
        
          description: Sucesso
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Especialidade"
        400:
          description: Especialidade nao encontrada
          content:
            application/json:
              example: "Not Found"
              
    put:
      summary: Atualiza uma entidade pelo ID
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                descricao:
                  type: string        
      responses:
        200:
          $ref: "#/components/responses/Sucesso"
          
        404:
          description: Especialidade nao encontrada
          content:
            application/json:
              example: "Not Found"
              
    delete:
      summary: Deleta uma entidade pelo ID
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              example: "OK"
        404:
          description: Especialidade nao encontrada
          content:
            application/json:
              example: "Not Found"
components:
  schemas:
    Especialidade: 
      type: object
      properties:
        id:
          type: integer
        descricao:
          type: string
    Especialidades:
      type: array
      items:
        $ref: "#/components/schemas/Especialidade"
        
          
  responses:
    Sucesso:
      description: Sucesso
      content:
        application/json:
          schema:
            $ref: "#/components/schemas/Especialidade"
```

## para saber mais: OpenAPI
Neste capítulo além de utilizar components nós discutimos um pouco sobre os possíveis tipos de dados da especificação OpenAPI.

Nesse link você pode conferir todos os possíveis tipos de dados e seus respectivos formatos:

https://swagger.io/specification/#data-types

Data Types
Primitive data types in the OAS are based on the types supported by the JSON Schema Specification Wright Draft 00. Note that integer as a type is also supported and is defined as a JSON number without a fraction or exponent part. null is not supported as a type (see nullable for an alternative solution). Models are defined using the Schema Object, which is an extended subset of JSON Schema Specification Wright Draft 00.

Primitives have an optional modifier property: format. OAS uses several known formats to define in fine detail the data type being used. However, to support documentation needs, the format property is an open string-valued property, and can have any value. Formats such as "email", "uuid", and so on, MAY be used even though undefined by this specification. Types that are not accompanied by a format property follow the type definition in the JSON Schema. Tools that do not recognize a specific format MAY default back to the type alone, as if the format is not specified.

The formats defined by the OAS are:

| type    	| format    	| Comments                          	|
|---------	|-----------	|-----------------------------------	|
| integer 	| int32     	| signed 32 bits                    	|
| integer 	| int64     	| signed 64 bits (a.k.a long)       	|
| number  	| float     	|                                   	|
| number  	| double    	|                                   	|
| string  	|           	|                                   	|
| string  	| byte      	| base64 encoded characters         	|
| string  	| binary    	| any sequence of octets            	|
| boolean 	|           	|                                   	|
| string  	| date      	| As defined by full-date - RFC3339 	|
| string  	| date-time 	| As defined by date-time - RFC3339 	|
| string  	| password  	| A hint to UIs to obscure input.   	|

## o que aprendemos?
* aprendemos a definir tipos para reutilizar schemas
* vimos como definir um objeto para ser reutilizado
* aprendemos a referenciar tipos com $ref
* entendemos mais sobre os tipos e sobre arrays

## Security schemas
Agora descreveremos algo que nem vamos utilizar nessa API. 

E não vamos utilizar porque, por ser uma API de teste, que eu criei com o "mockapi.io", ela não exige autenticação. 

Mas a maioria, senão todas as APIs que desenvolvemos, precisam de algum processo de autenticação, às vezes até de autorização.

É muito comum precisarmos, por exemplo, gerar um token, e a partir desse token, fazer as próximas requisições. 

Então, descreveremos isso agora, vamos descrever como essa autenticação é feita, ou seja, se é utilizando um token, se é uma API key, ou algo do tipo.

Depois, como que protegemos algum endpoint para que ele só seja utilizado, para ele só seja acessado, depois termos a autorização. 

### SecuritySchemes
Vamos começar definindo esse esquema de segurança, além de termos esquemas, além de termos respostas, podermos ter securitySchemes, ou seja, os nossos esquemas de segurança.

Eu posso dar qualquer nome para os meus esquemas, então vou chamar esse esquema de auth, mas pode chamar de qualquer coisa. 

Esse meu esquema ele precisa ter algumas informações como, por exemplo, ele vai ser uma API Key, ou seja, é só uma chave de API que eu forneço para meu cliente, ele vai ser através de um token gerado pelo servidor, então ele será enviado por HTTP de alguma forma.

É através de Oauth, a forma como vamos fazer. 

Então eu vou definir como se a nossa API estivesse utilizando um token, ou seja, JWT ou alguma outra coisa é semelhante. 

Porque, pela minha experiência, é o mais comum, é o que iremos mais utilizar, é o que eu sempre utilizei. 

Para definirmos um tipo de autorização usando o token, iremos colocar type: http. Ou seja, essa informação de segurança enviada através de HTTP.

Além disso, eu preciso definir o esquema, mas não esquema como estamos definindo até hoje, e sim o esquema HTTP dessa informação. 

Eu não vou entrar em detalhes sobre o que é um esquema HTTP de autorização, mas existem basicamente alguns tipos de token, o tipo mais comum, é o tipo de token em que enviamos informando que nós somos os portadores aquele token.

Ou seja, eu envio meu token dizendo," Olha só esse token é meu, então eu estou em autorizando. 

Como se eu estivesse fazendo login, eu estou te dando minhas informações para você garantir que eu sou eu."

#### bearer
Então esse tipo de token é o que chamamos de bearer, adicionamos scheme:bearer, ou seja, esse token é um portador. 

De novo, é como se fizéssemos login, e um processo real, eu vou até deixar um "para saber mais", sobre como foi processo de autorização por token e depois de um exemplo com JWT. 

Mas basicamente como funciona, temos uma URL /login, /auth e mais alguma coisa.

Onde enviamos os nossos dados, do nosso usuário e senha, por exemplo, e esse endpoint devolve um token, usando JWT, por exemplo. 

E agora para todas as outras requisições, para requisiçoes que precisam que eu esteja logado, eu não vou mais mandar o meu usuário e senha, eu não preciso.

Eu vou mandar esse token, e lá no servidor quando eu receber essa requisição, verifica se esse token está correto, se ele é válido, se é realmente de quem ele diz ser e, a partir disso, autoriza a requisição.

```
  securitySchemes:
    auth:
      type: http
      scheme: bearer
```

Então dessa forma conseguimos autorizar requisições, e reparem que, após definir esse esquema de segurança, aparece no SwaggerUI um botão “Authorize”, ou seja, posso liberar o uso dessa API. 

Poderia clicar nesse botão “Authorize” e definir o valor para esse token. 

“que valor é esse?” 

É o valor que a API, depois que eu fizesse login, me devolveria.

Nesse caso, eu vou botar um nome de "teste", porque, de novo, na nossa API não estamos utilizando isso, não precisamos de autenticação. 

Em uma API real, você enviaria seu usuário e senha para algum endpoint /login, por exemplo, e ele devolveria com um token e esse token você colocaria nesse campo.

Então quando eu clico em “Authorize”, ele simplesmente vai armazenar esse token.

Agora o que ele vai fazer? 

Se em alguma requisição, se em algum path desses eu informar que esse path precisa de autorização, então ele vai enviar esse token que salvamos. 

“e como informamos que determinado path precisa dessa autorização ou não?” 
### documento completo atual
```
openapi: 3.0.1
info:
  title: API de consultorio
  description: API para controlar médicos e suas especialidades dentro do consultório
  version: 0.0.1
  termsOfService: https://www.google.com.br/
  contact:
    name: Suporte a Devs
    email: contato@example.com
    url: https://www.google.com.br/
  license:
    name: "Licença: GPLv3"
    url: https://www.google.com.br/
externalDocs:
  description: Documentaçao burocratica

  url: https://www.google.com.br/

# servidores
servers: 
- url: http//6096015d116f00174b29ba.mockapi.io
  description: API de testes
- url: https://www.google.com.br/
  description: API de produçao


# endpoints
paths:
  /especialidades:
    get:
      summary: Recupera todas as especialidades
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Especialidades"
                      
    post:
      summary: Cria nova especialidade
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                descricao:
                  type: string
      responses:
        201:
           $ref: "#/components/responses/Sucesso"
                      
  /especialidades/{id}:
    parameters:
      - name: id #deve ser igual ao definido no caminho do path {id}
        in: path
        schema: 
          type: integer
        required: true
    get:
      summary: Recupera uma entidade pelo ID
      responses:
        200:
        
          description: Sucesso
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Especialidade"
        400:
          description: Especialidade nao encontrada
          content:
            application/json:
              example: "Not Found"
              
    put:
      summary: Atualiza uma entidade pelo ID
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                descricao:
                  type: string        
      responses:
        200:
          $ref: "#/components/responses/Sucesso"
          
        404:
          description: Especialidade nao encontrada
          content:
            application/json:
              example: "Not Found"
              
    delete:
      summary: Deleta uma entidade pelo ID
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              example: "OK"
        404:
          description: Especialidade nao encontrada
          content:
            application/json:
              example: "Not Found"
components:
  schemas:
    Especialidade: 
      type: object
      properties:
        id:
          type: integer
        descricao:
          type: string
    Especialidades:
      type: array
      items:
        $ref: "#/components/schemas/Especialidade"
        
          
  responses:
    Sucesso:
      description: Sucesso
      content:
        application/json:
          schema:
            $ref: "#/components/schemas/Especialidade"
  
  securitySchemes:
    auth:
      type: http
      scheme: bearer
```

## para saber mais: Tokens
Autenticação por token é um conhecimento mais do que necessário quando se trata de desenvolvimento de APIs. Vou deixar aqui 2 vídeos para explicar melhor o funcionamento desse tipo de autenticação:

(Autenticação por token)[https://www.youtube.com/watch?v=MZetkcs2xIo]
(Autenticação com JWT)[https://www.youtube.com/watch?v=B-7e-ZpIWAs]

## Parametro security
Vamos entender como podemos informar ao Swagger que sempre, por exemplo, que eu tentar acessar todas as especialidades, ele precisa mandar aquele token. 

Podemos fazer isso através de uma chave na nossa definição. 

Logo após responses, eu vou adicionar security:.

E em security eu posso definir diversas formas de autenticação, que ele aceita. 

Uma delas, que vai ser com o nome que já definimos anteriormente que é auth:. 

Então se eu tivesse colocado ali calopsita, em security eu colocaria calopsita também, mas no nosso caso é auth. 

E isso é um objeto, então a chave é o nome que já definirmos e o valor é um array.

```diff
+ Esse array só é utilizado se eu tivesse a minha forma de autenticação for por Oauth, método de autenticação normalmente usados quando integramos com serviços externos, mas pode ser utilizado só pela API também.
```
Porém, ele é um pouco mais complexo, então não vou entrar em detalhes agora.

Mas como estamos utilizando outro tipo de autenticação, através de tokens, que é uma autenticação HTTP, eu vou simplesmente deixar o array vazio. 

Com isso, o que vai acontecer? 

Vou vou abrir o meu inspecionador de elementos, vou inspecionar elementos, vou vir aqui em “Network”, está tudo vazio. 

Agora repara que aparece um cadeado ao lado das minhas especialidades, isso significa que quando eu fizesse a requisição eu preciso estar logado. 

Ou seja, meu authorize precisa ter algum token.

Quando eu fiz essa requisição o que o Swagger vai fazer, ele vai enviar um cabeçalho authorization com o valor bearer e o valor do meu token. 

Então quando eu fizer o teste, quando eu executar, na opção request header do meu inspecionar, eu tenho um cabeçalho authorization com o valor bearer, que aquele scheme do token. 

Ou seja, o scheme dessa forma de autenticação.

Que pode ser basic, que não é através de token, é através de usuários e senha mesmo. 

Bearer que é através de token, outros schemes HTTP. 

Mas enfim, eu tenho o meu tipo de token e o valor do meu token, então dessa forma se a minha API, ele realmente precisasse dessa autenticação, ela estaria recebendo essa informação.

Repare que eu não preciso especificar diretamente, porque minha API já está autorizada, eu já tenho os meus securityschemes definidos. 

```
paths:
  /especialidades:
    get:
      summary: Recupera todas as especialidades
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Especialidades"
      security: 
      - auth: []
```

Se eu tenho um scheme, eu poderia ter essa security não só para um path, mas para várias coisas. 

### proteger com security todos os endpoinds
Então será que eu poderia colocar direto na chave path um security?

Eu posso, então olha só o que eu vou fazer eu vou adicionar a chave path e apagar esse security que eu coloquei nas outras chaves. 

```
paths:
  /especialidades:
    get:
      summary: Recupera todas as especialidades
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Especialidades"
                      
    post:
      summary: Cria nova especialidade
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                descricao:
                  type: string
      responses:
        201:
           $ref: "#/components/responses/Sucesso"
                      
  /especialidades/{id}:
    parameters:
      - name: id #deve ser igual ao definido no caminho do path {id}
        in: path
        schema: 
          type: integer
        required: true
    get:
      summary: Recupera uma entidade pelo ID
      responses:
        200:
        
          description: Sucesso
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Especialidade"
        400:
          description: Especialidade nao encontrada
          content:
            application/json:
              example: "Not Found"
              
    put:
      summary: Atualiza uma entidade pelo ID
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                descricao:
                  type: string        
      responses:
        200:
          $ref: "#/components/responses/Sucesso"
          
        404:
          description: Especialidade nao encontrada
          content:
            application/json:
              example: "Not Found"
              
    delete:
      summary: Deleta uma entidade pelo ID
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              example: "OK"
        404:
          description: Especialidade nao encontrada
          content:
            application/json:
              example: "Not Found"
security: 
- auth: []
```

A partir de agora todos os meus end points tem um cadeado. 

Então sempre que eu fizer todas essas requisições, o meu token vai ser enviado. 

E se eu vier em “Authorize” e fizer log out e fechar, os cadeados agora ficam cinza, ele tá um pouco mais opaco.

Então se eu tentar fazer essa requisição agora, abrindo o meu inspecionar. 

Se eu tentar fazer requisição ele não vai enviar esse dado, ele agora só ele não envia o cabeçalho authorization. 

Se fosse uma API real que precisa da autorização, iriamos receber como resposta um erro.

Dessa forma conseguimos definir autorização, definimos o schema para conseguir realizar autorizações direto pelo nosso Swagger. 

E conseguimos definir endpoint, a endpoint, verbo a verbo, ou geral para toda a nossa aplicação, que ela vai utilizar determinado esquema de segurança.

### documento completo atual
```
openapi: 3.0.1
info:
  title: API de consultorio
  description: API para controlar médicos e suas especialidades dentro do consultório
  version: 0.0.1
  termsOfService: https://www.google.com.br/
  contact:
    name: Suporte a Devs
    email: contato@example.com
    url: https://www.google.com.br/
  license:
    name: "Licença: GPLv3"
    url: https://www.google.com.br/
externalDocs:
  description: Documentaçao burocratica

  url: https://www.google.com.br/

# servidores
servers: 
- url: http//6096015d116f00174b29ba.mockapi.io
  description: API de testes
- url: https://www.google.com.br/
  description: API de produçao


# endpoints
paths:
  /especialidades:
    get:
      summary: Recupera todas as especialidades
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Especialidades"
      security: 
      - auth: []
                      
    post:
      summary: Cria nova especialidade
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                descricao:
                  type: string
      responses:
        201:
           $ref: "#/components/responses/Sucesso"
                      
  /especialidades/{id}:
    parameters:
      - name: id #deve ser igual ao definido no caminho do path {id}
        in: path
        schema: 
          type: integer
        required: true
    get:
      summary: Recupera uma entidade pelo ID
      responses:
        200:
        
          description: Sucesso
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Especialidade"
        400:
          description: Especialidade nao encontrada
          content:
            application/json:
              example: "Not Found"
              
    put:
      summary: Atualiza uma entidade pelo ID
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                descricao:
                  type: string        
      responses:
        200:
          $ref: "#/components/responses/Sucesso"
          
        404:
          description: Especialidade nao encontrada
          content:
            application/json:
              example: "Not Found"
              
    delete:
      summary: Deleta uma entidade pelo ID
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              example: "OK"
        404:
          description: Especialidade nao encontrada
          content:
            application/json:
              example: "Not Found"
              
components:
  schemas:
    Especialidade: 
      type: object
      properties:
        id:
          type: integer
        descricao:
          type: string
    Especialidades:
      type: array
      items:
        $ref: "#/components/schemas/Especialidade"
        
          
  responses:
    Sucesso:
      description: Sucesso
      content:
        application/json:
          schema:
            $ref: "#/components/schemas/Especialidade"
  
  securitySchemes:
    auth:
      type: http
      scheme: bearer
```

### onde usar?
Vimos 2 locais onde a propriedade security pode ser utilizada.

Onde nós podemos informar a propriedade security?

R: Na raiz do documento
Nós podemos definir a chave security fora de qualquer outra chave, o que significa que aquela autenticação vai ser utilizada por todas as operações.

## Bearer format
Eu só quero trazer um detalhe bem pequeno que nem interfere na usabilidade de quem estiver olhando o Swagger UI, mas pode ajudar um pouco em alguns casos, quando estivermos olhando pelo Swagger Editor. 

Podemos ter essa autorização HTTP, com esse scheme, ou seja, utilizando tokens.

Com qualquer formato de token, você pode criar o seu formato de token, inclusive naquele vídeo que eu deixei no "para saber mais" falando sobre autorização por tokens, Comentamos exatamente sobre isso, sobre a possibilidade de eu criar meu token e utilizá-lo na hora de autorizar algo.

Mas, no nosso caso, nós estamos utilizando um formato específico token, que é o JWT. 

### bearerFormat
Então nós conseguimos deixar claro através do bearerFormat:, esse bearerformat podemos escrever qualquer coisa nele. E essa qualquer coisa serve somente para sabermos o formato desse token, como a nossa API vai tratar esse token.

O cliente nem precisa saber disso, porque tudo que ele vai fazer mandar o usuário e senha, vai receber um token de volta, independente do formato. 

E esse token ele tem que mandar nas outras requisições. 

Então para sabermos que isso é um JWT, é comum que tenhamos esse bearerformat com o JWT.

```
  securitySchemes:
    auth:
      type: http
      scheme: bearer
      bearerFormat: JWT
```

Isso é um detalhe a mais para quem está consumindo essa documentação, para quem está trabalhando com o Swagger Editor. 

Então repare que essa chave bearerformat não é algo que eu inventei, é uma chave existente. 

Justamente para dar esse auxílio para, sabermos com qual formato estamos trabalhando.

Então dessa forma definimos que a nossa autorização é utilizando HTTP, que por padrão, é enviando aquele cabeçalho authorization. 

Que o schema dessa autorização é através de tokens, ou seja, um bearer que informa quem é o portador daquele token.

E estamos informando o formato desse token, o formato que o portador do token está utilizado é o JWT. 

Então dessa forma a gente completa essa parte de autorização e, talvez, você esteja se perguntando um detalhe. 

Eu estou utilizando o Swagger Editor online, na plataforma do Swagger.

O Swagger UI está integrado com o Swagger Editor, como que eu realmente posso fornecer isso, ou para a minha equipe escrever no Swagger Editor sem ter que utilizar essa plataforma, não sei se o Swagger está olhando o meu código.

E como podemos fornecer Swagger UI para os clientes, sem que eles precisem ver todo esse nosso código. 

### documento completo atual
```
openapi: 3.0.1
info:
  title: API de consultorio
  description: API para controlar médicos e suas especialidades dentro do consultório
  version: 0.0.1
  termsOfService: https://www.google.com.br/
  contact:
    name: Suporte a Devs
    email: contato@example.com
    url: https://www.google.com.br/
  license:
    name: "Licença: GPLv3"
    url: https://www.google.com.br/
externalDocs:
  description: Documentaçao burocratica

  url: https://www.google.com.br/

# servidores
servers: 
- url: http//6096015d116f00174b29ba.mockapi.io
  description: API de testes
- url: https://www.google.com.br/
  description: API de produçao


# endpoints
paths:
  /especialidades:
    get:
      summary: Recupera todas as especialidades
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Especialidades"
      security: 
      - auth: []
                      
    post:
      summary: Cria nova especialidade
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                descricao:
                  type: string
      responses:
        201:
           $ref: "#/components/responses/Sucesso"
                      
  /especialidades/{id}:
    parameters:
      - name: id #deve ser igual ao definido no caminho do path {id}
        in: path
        schema: 
          type: integer
        required: true
    get:
      summary: Recupera uma entidade pelo ID
      responses:
        200:
        
          description: Sucesso
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Especialidade"
        400:
          description: Especialidade nao encontrada
          content:
            application/json:
              example: "Not Found"
              
    put:
      summary: Atualiza uma entidade pelo ID
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                descricao:
                  type: string        
      responses:
        200:
          $ref: "#/components/responses/Sucesso"
          
        404:
          description: Especialidade nao encontrada
          content:
            application/json:
              example: "Not Found"
              
    delete:
      summary: Deleta uma entidade pelo ID
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              example: "OK"
        404:
          description: Especialidade nao encontrada
          content:
            application/json:
              example: "Not Found"
              
components:
  schemas:
    Especialidade: 
      type: object
      properties:
        id:
          type: integer
        descricao:
          type: string
    Especialidades:
      type: array
      items:
        $ref: "#/components/schemas/Especialidade"
        
          
  responses:
    Sucesso:
      description: Sucesso
      content:
        application/json:
          schema:
            $ref: "#/components/schemas/Especialidade"
  
  securitySchemes:
    auth:
      type: http
      scheme: bearer
      bearerFormat: JWT
```

## o que aprendemos?
* entendemos sobre schemas de segurança
* adicionamos authenticacao a todos os endpoints
* vimos como adicionar uma informaçao adicional com bearerFormat

## baixando o editor
O questionamento levantado no último capítulo foi de que eu estou utilizando esse online do Swagger, mas se ele sair do ar, ou se eu estiver sem internet, como que eu posso ter esse editor, ou na minha máquina um servidor da minha empresa. Outro detalhe é como eu disponibilizo o Swagger UI para os meus clientes, para que eles possam ver essa minha documentação interativa.

Então vamos acessar o site do Swagger, "swagger.io" e vamos começar pelos Swagger Editor. Vamos acessar as ferramentas, ir em “Swagger Editor”, e ao invés de clicar em Live demo, que estamos utilizando, vamos baixar esse editor, clicando em "Download Swagger Editor". Aqui podemos fazer o login e utilizar o “SwaggerHub”, ferramenta um pouco mais enterprise que, inicialmente, é gratuita para pessoas físicas.

Vou utilizar diretamente, baixando o Swagger Editor de alguma forma, então, quando eu clico na opção "Download", sou redirecionado para o GitHub. Aqui sabemos - teoricamente as pessoas que já desenvolvem sabem - como funciona o GitHub.

Eu poderia baixar esse código, ter esse código na minha máquina e subir um servidor web, porque isso é um projeto web. Como sabemos, é um sistema que está rodando de forma online, então poderia subir um servidor web.

Só se repararmos no arquivo “Dockerfile”, significa que de alguma forma eles usam Docker, então quando vamos descendo a página, podemos ver como rodar isso localmente, e podemos fazer através do Docker. Então podemos baixar essa imagem "docker pull swaggerapi/swagger-editor", ele vai fazer o download, no meu caso essa imagem já está no meu computador, já está atualizado.

E podemos rodar esse comando "docker run-d -p 80:8080 swaggerapi/swagger-editor", ou seja, rodar esse container e executá-lo, para termos um Swagger Editor na nossa máquina. Não falei, mas acredito que seja óbvio: para isso tudo você precisa ter o Docker na sua máquina. Caso você não queira instalar o Docker, de novo, você pode baixar o projeto como um todo e subir em algum servidor web, sem problema nenhum.

Se eu não me engano é um projeto em JavaScript pelo pack de ponto Json e pela configuração do JavaScript, eu suponho que seja um projeto em JavaScript. Mas continuando, o que eu posso fazer além de simplesmente inicializar o servidor, eu posso passar algumas informações. Como, por exemplo, fazer com que ele leia o meu arquivo em Yaml, ou um arquivo Json, para a partir dele já carregar a definição, e depois eu ir editando.

Então o que eu vou fazer, no Swagger Editor, do que eu fiz até agora, eu vou à barra de ferramentas "File > Save as YAML". Eu já tenho uma pasta, eu já tenho ele salvo inclusive, mas vou sobrescrever e substituir. Em breve precisaremos dele em Json também então já converter e salvar como Json, "File > Convert and save as JSON". Eu também já tinha ele, mas eu vou salvar e substituir.

Tenho dois arquivos, “openapi.json” e “openapi.yml”. Eu posso executar o segundo comando da página do GitHub, ""docker run-d -p 80:8080 -v $(pwd):/tmp -e ...", vou copiar, colar e editar um pouco ele no Docker. Primeiro eu não vou rodar nesse modo de "-d -p", vou apagar isso, ou seja, não vou liberar o meu terminal. Porque eu não preciso disso, vou deixar o terminal travado com ele.

Ele vai rodar na porta 80, ou seja, no porta padrão HTTP, só que lá dentro ele vai usar porta 8080, internamente. Ele tá mapeando a minha pasta atual, eu acho que isso é importante. Vou abrir uma nova guia do Docker, a minha pasta atual possui os dois arquivos que eu acabei de baixar, eu os salvei dentro de uma pasta Swagger.

Ele está mapeando um volume da minha pasta atual, para uma pasta “tmp”, uma pasta temporária lá no container. E lá no container ele vai tentar carregar o arquivo de Swagger na pasta “tmp”, com o nome que está no comando. Então vou modificar para esse nome para "opneapi.yml". Vai rodar um container a parte dessa imagem do Swagger Editor. Dei "Enter", se nada deu errado, eu posso ir para o meu navegador e digitar "localhost".

```
docker run -d -p 80:8080 -v $(pwd):/tmp -e SWAGGER_FILE=/tmp/openapi.yml swaggerapi/swagger-editor
```

Ele abriu meu Swagger Editor, caso não abra de cara, tente atualizar a página. 

Ele abriu com aquele arquivo já pronto, para podermos editar e fazer o que quiser. Um detalhe chato como, isso aqui é um projeto web, o que precisamos fazer. Precisamos ir editar, fazer tudo o que precisa fazer e depois salvar de novo, salvar como Yaml. Mas isso é um trabalho pequeno, não é nada muito complexo.

Se você não precisar dessa plataforma do Swagger Editor, se você só precisa, por exemplo, modificar um ID, que antes era um inteiro e agora é um flout, ou sei lá, a descrição que antes era um string agora é um booleano. Se eu quiser fazer pequenas modificações, você pode abrir esse arquivo com seu editor de texto mesmo, não precisa dos Swagger Editor. Porque ele é um arquivo de texto.

Vou interromper meu Swagger Editor. Eu posso ir no Docker, e abrir o arquivo "openapi.yml", ele é um arquivo de texto, eu posso editar ele tranquilamente por aqui, se eu não precisar daquela plataforma. E algum editor de código como VS Code, ou PHPStorm, ou Visual Studio, ou IntelliJ. Algum editor de código, ou IDE vai saber identificar isso como Yaml, talvez alguns tenham até algum plug in e já até renderizem de alguma forma.

Vale a pena dar uma olhada em como você pode digitar isso de forma um pouco mais simples. Mas, voltando ao assunto, conseguimos facilmente ter um Swagger Editor na nossa máquina, eu não preciso de internet para isso mais. Porque esse Swagger Editor está rodando na minha máquina. Então tudo o que eu preciso está aqui, eu posso editar livremente, ver de forma automática, de forma instantânea isso sendo atualizado, como ficaria no Swagger UI.

Com aquele pequeno problema, de ser um projeto web, então sempre que realizar alguma edição, eu preciso vir aqui e baixar o arquivo de novo.

Agora que fizemos tudo isso, agora que já temos o Swagger Editor na nossa máquina, precisamos falar da parte que é mais importante. Porque editar eu posso tranquilamente acessar um próprio Swagger Editor online, colar o meu arquivo, fazer as modificações que eu quiser e baixar o arquivo de novo, nada me impede de fazer isso.

Eu posso editar esse arquivo direto pelo meu editor de texto também, nada me impede de fazer isso. Agora e o meu cliente, a pessoa que vai acessar essa documentação através dos Swagger UI, ou seja, como que eu tenho o Swagger UI em alguma máquina, para poder disponibilizar através do meu servidor web, por exemplo. Então vamos agora, assim como baixamos o Swagger Editor, vamos baixar também o Swagger UI, de novo, usando o Docker, mas no próximo vídeo.

## Baixando o UI
Agora que já temos o Swagger Editor possivelmente rodando na nossa máquina, vamos baixar o Swagger UI, para disponibilizarmos, através de algum servidor web nosso, ou como preferirmos. De novo, vou usar o Docker para facilitar as coisas, vou em "Swagger IU”. Mesmo esquema, ao invés de ir ao Live demo, eu posso vir em "Download Swagger UI".

De novo, aquele mesmo esquema, eu poderia fazer poderia me cadastrar para acessar o "SwaggerHub", onde temos alguns recursos a mais, mas eu não preciso disso então eu clico em "Download" e vou direto para o projeto do Swagger UI no GitHub. Aqui como um projeto, teoricamente, um pouco mais complexo, a documentação um pouco mais extensa. Mas se eu descer a página até a parte de instalação, eu tenho também a opção de utilizar o Docker.

Então iremos baixar imagem, só que dessa vez, ao invés de Swagger Editor iremos baixar a imagem do Swagger UI. Como eu já tenho foi rápido, no seu cenário pode demorar um pouco da primeira vez. Eu poderia subir um container utilizando essa imagem "docker run-d -p 80:8080 swaggerapi/swagger-ui", só que de novo eu já tenho um arquivo, então eu vou utilizar ele. Então eu posso copiar esse comando "docker run-d -p 80:8080 -e SWAGGER_JSON=/foo ...", e colar no Docker.

Agora vamos entender ele e fazer algumas modificações. Repare que eu preciso informar o Json, eu preciso informar o arquivo no formato de Json. Eu vou adicionar isso de novo no, “tmp”, aquele diretório temporário e adicionar openaapi.json.

```
docker run -p 80:8080 -e SWAGGER_FILE=/tmp/openapi.json -v $(pwd):/tmp swaggerapi/swagger-ui
```

Eu vou criar um volume, do meu diretório atual, (pwd). Ou seja, a parta que estou agora vai ser mapeada para a pasta temporária, lá naquele container do Docker que vai ser criado a partir dessa imagem.

Então que eu estou fazendo, em “tmp” eu vou ter tudo que eu tenho na minha pasta atual. E eu tenho o arquivo “openapi.json” na minha pasta atual, então o Docker vai conseguir encontrar o /tmp/openapi.json, para acessar ele, o Swagger UI vai acessar ele e carregar a documentação a partir disso.

Teoricamente, agora no meu localhost ao invés de ter o Swagger Editor, eu vou ter o Swagger UI. Então quando eu atualizo a página do localhosto no navegador, eu tenho apenas o Swagger UI. Ou seja, ao invés de ter um editor, eu tenho só parte que um possível cliente utilizaria. Então tem toda aquela nossa descrição, tipo e etc., todos os links que adicionamos. E aquela API que eu posso realmente utilizar, que fazer aqueles testes interativos.

Posso fazer o meu login, imagino que o cliente precisa realmente fazer o login, posso colocar aqui qualquer coisa, porque imagina que isso é um token real. Depois ele pode me mandar requisições, pode conferir a resposta, copiar o seu URL e analisar tudo com calma, de forma realmente interativa. Um detalhe que eu não falei, eu vou deixar de desafio para você.

Na verdade, eu vou deixar um "para saber mais”, mas eu vou deixar um desafio para você fazer antes de ler o "para saber mais". Você vai abrir numa janela, um Swagger Editor com a versão três já, você vai converter para a versão três. E vai dar uma olhada que não tem esse default naquele padrão deles, ao invés de ser o default ele é separado por categorias.

Ou tags. Fica aí o spoiler. Eu vou deixar um "para saber mais" só para você entender como essas tags são organizadas. Porque é bastante simples, então cobrimos nesse treinamento para não estender ele demais, mas só um exercício no final para você não dizer que nesse último capítulo não passei nenhum exercício. Então recapitulando o que vimos nesse capítulo.

Podemos ter tanto o Swagger Editor quanto o Swagger UI, na nossa própria infraestrutura. Seja na nossa máquina local, ou disponibilizado através de um servidor, para que nossos clientes, para que nossos possíveis clientes, possam acessar essa documentação.

Isso pode ser bastante útil, não só para nós desenvolvedores termos acesso a possíveis endpoints. Mas para a equipe de negócios disponibilizar isso, para um possível cliente, utilizar isso como ponto de venda, mostrar sobre organização, entre outros. Não quero me alongar, mas vimos como é tranquilo termos tudo isso na nossa própria infraestrutura.

## o que aprendemos?
* vimo que é possivel disponibilizar o swagger em nossa infra
* aprendemos a usar o swagger editor a partid do docker
* vimos como disponibilizar o swagger UI atravez do docker

### documento completo atual
```
openapi: 3.0.1
info:
  title: API de consultorio
  description: API para controlar médicos e suas especialidades dentro do consultório
  version: 0.0.1
  termsOfService: https://www.google.com.br/
  contact:
    name: Suporte a Devs
    email: contato@example.com
    url: https://www.google.com.br/
  license:
    name: "Licença: GPLv3"
    url: https://www.google.com.br/
externalDocs:
  description: Documentaçao burocratica

  url: https://www.google.com.br/

# servidores
servers: 
- url: http//6096015d116f00174b29ba.mockapi.io
  description: API de testes
- url: https://www.google.com.br/
  description: API de produçao


# endpoints
paths:
  /especialidades:
    get:
      summary: Recupera todas as especialidades
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Especialidades"
      security: 
      - auth: []
                      
    post:
      summary: Cria nova especialidade
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                descricao:
                  type: string
      responses:
        201:
           $ref: "#/components/responses/Sucesso"
                      
  /especialidades/{id}:
    parameters:
      - name: id #deve ser igual ao definido no caminho do path {id}
        in: path
        schema: 
          type: integer
        required: true
    get:
      summary: Recupera uma entidade pelo ID
      responses:
        200:
        
          description: Sucesso
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/Especialidade"
        400:
          description: Especialidade nao encontrada
          content:
            application/json:
              example: "Not Found"
              
    put:
      summary: Atualiza uma entidade pelo ID
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                descricao:
                  type: string        
      responses:
        200:
          $ref: "#/components/responses/Sucesso"
          
        404:
          description: Especialidade nao encontrada
          content:
            application/json:
              example: "Not Found"
              
    delete:
      summary: Deleta uma entidade pelo ID
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              example: "OK"
        404:
          description: Especialidade nao encontrada
          content:
            application/json:
              example: "Not Found"
              
components:
  schemas:
    Especialidade: 
      type: object
      properties:
        id:
          type: integer
        descricao:
          type: string
    Especialidades:
      type: array
      items:
        $ref: "#/components/schemas/Especialidade"
        
          
  responses:
    Sucesso:
      description: Sucesso
      content:
        application/json:
          schema:
            $ref: "#/components/schemas/Especialidade"
  
  securitySchemes:
    auth:
      type: http
      scheme: bearer
      bearerFormat: JWT
```