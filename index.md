# Integração de Serviços Comuns

A ISCAPI é uma camada de integração de sistemas com parceiros com um conjunto de operações que permitem integrar com as plataformas de serviços do [ePortugal](https://ePortugal.gov.pt)

As operações apresentadas estarão de acordo com o levantamento e documentação efetuada.


## Operações disponíveis


### Envio de formulário
O formulário submetido na plataforma de serviços da AMA é enviado através desta operação.

|Elemento| Tipo | Cardinalidade|
|------------ | ------------|
|OperationCode|String|1....1|
|OperationVersion|String|1....1|
|Form|Formulário eForms|1....1|

```markdown
<operationDaa>
  <operationCode>ISCOP001SendForm</operationCode>
  <operationVersion></operationVersion>
  <Form></Form>
</operationData>
```


### Envio de número de processo externo
A entidade que recebe o formulário deve utilizar esta operação para comunicar o nº de processo no seu sistema.

|Elemento| Tipo | Cardinalidade|
|------------ | ------------|
|OperationCode|string|1....1|
|OperationVersion|string|1....1|
|requestNumber|string|1....1|
|compEntityReqNumber|string|1....1|
|replyType|string|1....1|
|replyCode|string|1....1|

```markdown
<operationData>
  <operationCode>ISCOP003SendProcessNumber</operationCode>
  <operationVersion>1.0</operationVersion>
  <requestNumber>694/2020</requestNumber>
  <compEntityReqNumber>PROC/487/2020</compEntityReqNumber>
  <replyType>OK</replyType>
  <replyCode>200</replyCode>
</operationData>
```

### Alteração de estado
Esta operação pode ser usada de forma bidirecional conforme os cenários , permite comunicar uma alteração de estado e
pode ser originada a partir da plataforma de serviços ou do sistema de informação da entidade parceira.

|Elemento| Tipo | Cardinalidade|
|------------ | ------------|
|OperationCode|string|1....1|
|OperationVersion|string|1....1|
|requestNumber|string|1....1|
|compEntityReqNumber|string|1....1|
|changeDate|timestamp|1....1|
|sendDate|timestamp|1....1|
|stateCode|int|1....1|
|stateDesc|string|1....1|
|action|int|1....1|
|actionDesc|string|1....1|
|comments|string|1....1|

```markdown
<operationDaa>
  <operationCode>ISCOP002SendStateUpdate</operationCode>
  <operationVersion>1.0</operationVersion>
  <requestNumber>696/2020</requestNumber>
  <compEntityReqNumber>PROC/489/2020</compEntityReqNumber>
  <changeDate>2020-03-20T17:37:58</changeDate>
  <sendDate>2020-03-20T17:37:58</sendDate>
  <stateCode>13</stateCode>
  <stateDesc>Processo decidido</stateDesc>
  <actionCode>14</actionCode>
  <actionDesc>Emitir decisão</actionDesc>
  <comments />
</operationData>
```

### Solicitar meio/forma de pagamento
Esta operação pode ser usada de forma bidirecional conforme os cenários , permite solicitar os meios de pagamento para a tramitação do processo na plataforma de serviços ou no sistema de informação da entidade parceira.

|Elemento| Tipo | Cardinalidade|
|------------ | ------------|
|OperationCode|String|1....1|
|OperationVersion|String|1....1|
|Form|Formulário eForms|1....1|

```markdown
<operationDaa>
    <operationCode>ISCOP004GetPaymentMethods</operationCode>
    <operationVersion />
    <paymentValue>120.00</paymentValue>
    <paymentTypeId>1</paymentTypeId>
    <buyerEmail />
    <requests>
      <requestNumber>1679</requestNumber>
      <serviceCode>CES:SRV:000005469</serviceCode>
      <entityCode>SIOE:ORG:070080000</entityCode>
    </requests>
</operationData>
```

**Necessita de protocolo com a Plataforma de Pagamentos da AMA para usar**

### Enviar notificações
Para enviar uma curta comunicação a um utilizador no âmbito de um processo.
Esta comunicação escrita não pode enviar dados do processo , apenas apelar à sua visualização no ePortugal.

|Elemento| Tipo | Cardinalidade|
|------------ | ------------|
|OperationCode|String|1....1|
|OperationVersion|String|1....1|
|Form|Formulário eForms|1....1|

```markdown
<operationDaa>
  <operationCode>ISCOP013SendNotifications</operationCode>
  <operationVersion>1</operationVersion>
  <receiver>email@email.com</receiver>
  <subject>Tem uma nova notificação na Área Reservada do Licenciamento Industrital no ePortugal</subject>
  <body>Recebeu uma nova notificação em 13/03/2020 às 11:59:46, relativa ao Pedido de Vistoria, Nº 16/2019-2 do estabelecimento Idioma de tons - Estamparia, Lda com o NUEI 030308000048.
Consulte a sua Área Reservada do Licenciamento Industrial, no ePortugal, para visualizar detalhes.</body>
</operationData>
```

### Solicitar envio de formulário
**BETA**
É uma forma de solicitar o envio de um formulário, é um mecanismo disponível para a plataforma de serviços,
solicitar o envio de um formulário no âmbito de uma alteração.

|Elemento| Tipo | Cardinalidade|
|------------ | ------------|
|OperationCode|String|1....1|
|OperationVersion|String|1....1|
|Form|Formulário eForms|1....1|

```markdown
<operationDaa>
  <operationCode>ISCOP001SendForm</operationCode>
  <operationVersion></operationVersion>
  <Form></Form>
</operationData>
```


### Envio de um erro
**BETA**
Esta operação pode ser usada de forma bidirecional e serve para a comunicação de erros na troca de mensagens.

|Elemento| Tipo | Cardinalidade|
|------------ | ------------|
|OperationCode|String|1....1|
|OperationVersion|String|1....1|
|Form|Formulário eForms|1....1|

```markdown
<operationDaa>
  <operationCode>ISCOP001SendForm</operationCode>
  <operationVersion></operationVersion>
  <Form></Form>
</operationData>
```


### Pedido de acesso
**BETA**
Esta operação serve para solicitar acesso a um formulário.

|Elemento| Tipo | Cardinalidade|
|------------ | ------------|
|OperationCode|String|1....1|
|OperationVersion|String|1....1|
|compEntityReqNumber|string|1..1|
|userType|string|1....1
|documentType|string|1....1
|documentId|string|1....1|
|comments|string|	0....1|

```markdown
<operationDaa>
  <operationCode>ISCOP006FormAuthRequest</operationCode>
  <operationVersion></operationVersion>
  <compEntityReqNumber>?</compEntityReqNumber>
  <userType>?</userType>
  <documentType>?</documentType>
  <documentId>?</documentId>
  <comments>?</comments>
</operationData>
```
### Resposta a pedido de acesso

**BETA**
Esta operação serve para responder a um pedido de acesso a um formulário.

|Elemento| Tipo | Cardinalidade|
|------------ | ------------|
|OperationCode|String|1....1|
|OperationVersion|String|1....1|
|Form|Formulário eForms|1....1|

```markdown
<operationDaa>
  <operationCode>ISCOP001SendForm</operationCode>
  <operationVersion></operationVersion>
  <Form></Form>
</operationData>
```


### Pedido de esclarecimentos
**BETA**
Esta operação permite o envio de um pedido de esclarecimentos ou recolha de informação adicional para um determinado pedido.

|Elemento| Tipo | Cardinalidade|
|------------ | ------------|
|OperationCode|String|1....1|
|OperationVersion|String|1....1|
|Form|Formulário eForms|1....1|

```markdown
<operationDaa>
  <operationCode>ISCOP001SendForm</operationCode>
  <operationVersion></operationVersion>
  <Form></Form>
</operationData>
```

### Resposta a pedido de esclarecimentos
**BETA**
Esta operação permite o envio de uma resposta ao pedido de esclarecimentos ou recolha de informação adicional para um determinado pedido

|Elemento| Tipo | Cardinalidade|
|------------ | ------------|
|OperationCode|String|1....1|
|OperationVersion|String|1....1|
|Form|Formulário eForms|1....1|

```markdown
<operationDaa>
  <operationCode>ISCOP001SendForm</operationCode>
  <operationVersion></operationVersion>
  <Form></Form>
</operationData>
```

### Registo de uma decisão
**BETA**
Esta operação permite o registo de uma decisão associada a um processo.

|Elemento| Tipo | Cardinalidade|
|------------ | ------------|
|OperationCode|String|1....1|
|OperationVersion|String|1....1|
|Form|Formulário eForms|1....1|

```markdown
<operationDaa>
  <operationCode>ISCOP001SendForm</operationCode>
  <operationVersion></operationVersion>
  <Form></Form>
</operationData>
```

### Pedido de dados resumo
**BETA**
Esta operação permite o envio de dados de serviço de forma resumida.

|Elemento| Tipo | Cardinalidade|
|------------ | ------------|
|OperationCode|String|1....1|
|OperationVersion|String|1....1|
|Form|Formulário eForms|1....1|

```markdown
<operationDaa>
  <operationCode>ISCOP001SendForm</operationCode>
  <operationVersion></operationVersion>
  <Form></Form>
</operationData>
```

You can use the [editor on GitHub](https://github.com/dsiama/iscapi/edit/master/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Operações

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/dsiama/iscapi/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
