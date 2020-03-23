# Integração de Serviços Comuns
A ISCAPI é uma camada de integração de sistemas com parceiros com um conjunto de operações que permitem integrar com as plataformas de serviços do [ePortugal](https://ePortugal.gov.pt)

- [Regressar ao ecrã inicial](../)

## Operações
[Consultar as operações disponíveis](..\operacoes)


## Tabelas de valores
[Consultar as tabelas de valores](..\tabeladevalores)

## Plataforma de Integração
[Consultar aqui a informação sobre a Plataforma de Integração](..\iap)

## Transferência de Ficheiros
[Consultar aqui a informação sobre a transferência de ficheiros](largefiles)

## Estrutura Fixa

## Dados da Mensagem
Estrutura para roteamento da mensagem.

|Elemento| Tipo | Cardinalidade|
|------------ | ------------|
|messageEntityId|string|1....1|
|messageRelatesToId|string|1....1|
|messageRelatesToEntityId|string|1....1|
|messageDate|string|1....1|

```markdown
<messageData>
         <messageEntityId>?</messageEntityId>
         <messageRelatesToId>?</messageRelatesToId>
         <messageRelatesToEntityId>?</messageRelatesToEntityId>
         <messageDate>?</messageDate>
</messageData>
```

## Dados do Pedido
Estrutura para identificação do pedido.

|Elemento| Tipo | Cardinalidade|
|------------ | ------------|
|processNumber|string|1....1|
|requestNumber|string|1....1|
|requestExternalNumber|string|1....1|
|requestDate|string|1....1|
|serviceCode|string|1....1|
|channel|string|1....1|
|localCode|string|1....1|
|userCode|string|1....1|
|userName|string|1....1|


```markdown
<requestData>
  <processNumber>?</processNumber>
  <requestNumber>?</requestNumber>
  <requestExternalNumber>?</requestExternalNumber>
  <requestDate>?</requestDate>
  <serviceCode>?</serviceCode>
  <channel>?</channel>
  <entityCode>?</entityCode>
  <localCode>?</localCode>
  <userCode>?</userCode>
  <userName>?</userName>
</requestData>
```


## Dados da Operação
Estrutura para identificação da operação

|Elemento| Tipo | Cardinalidade|
|------------ | ------------|
|operationCode|string|1....1|
|operationVersion|string|1....1|

```markdown
<operationData>
         <operationCode>?</operationCode>         
         <operationVersion>?</operationVersion>
</operationData>      
```


## Dados dos ficheiros
Estrutura para envio de ficheiros

|Elemento| Tipo | Cardinalidade|
|------------ | ------------|
|TTL|string|1....1|
|fileGuid|string|1....1|
|fileName|string|1....1|
|fileType|string|1....1|
|filePath|string|1....1|

```markdown
<attachContext>
  <TTL>?</TTL>
  <fileGuid>?</fileGuid>
  <fileName>?</fileName>
  <fileType>?</fileType>
  <filePath>?</filePath>
</attachContext>    
```
