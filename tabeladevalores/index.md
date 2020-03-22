# Integração de Serviços Comuns
A ISCAPI é uma camada de integração de sistemas com parceiros com um conjunto de operações que permitem integrar com as plataformas de serviços do [ePortugal](https://ePortugal.gov.pt)

- [Regressar ao ecrã inicial](../)

## Operações
[Consultar as operações disponíveis](../operacoes)

# Tabelas de Valores

## Meios de Pagamento

|Id| Valor |
|------------ | ------------|
|1|	Multibanco|
|2|	Cartão de Crédito|
|3|	Numerário|
|4|	Cheque|
|5|	Transferência Bancária|
|6|	Anulação Manual|




## 	Tipos de Taxa

|Id| Valor |
|------------ | ------------|
|TA|	1º Pagamento|
|T|	2º Pagamento|

## 	Entidades
Para verificar o código de (uma) entidade(s), deverá aceder ao SIOE, em http://www.sioe.dgaep.gov.pt/Default.aspx.

## 	Tipos de Utilizador

|Id| Valor |
|------------ | ------------|
|1|	Advogado|
|2|	Solicitador|
|4|	Cidadão|
|6|	Notário|


## 	Tipo de Documento
Para verificar o código associado ao tipo de documento, deverá ser acedido o serviço eletrónico do Catálogo de Entidades e Serviços - este acesso encontra-se esclarecido no documento CES-WS API

## 	Estado do processo

|Id| Valor |
|------------ | ------------|
|1|	Processo em elaboração|
|2|	Aguarda emissão de pagamento|
|3|	Aguarda pagamento|
|4|	Aguarda atribuição de taxa|
|5|	Pagamento liquidado|
|6|	Cancelado|
|7|	Processo arquivado|
|8|	Aguarda análise|
|9|	Em análise|
|10|Aguarda esclarecimentos|
|11|	Aguarda audiência dos interessados|
|12	|Aguarda pagamento da taxa de decisão|
|13	|Processo decidido|
|14	|Processo submetido à entidade competente|
|15	|Pagamento da taxa de decisão liquidado|
|16|Processo migrado|
|19	|Suspenso|
|20	|Aguarda introdução de token|
|21	|Pagamento fora do prazo|

## 	Canais

|Id| Valor |
|------------ | ------------|
|PointOfCareType.Presential|Presencial|
|PointOfCareType.Phone|	Telefone|
|PointOfCareType.Fax|	Fax|
|PointOfCareType.Email|	Correio Eletrónico|
|PointOfCareType.Mail|	Correio Postal|
|PointOfCareType.Web|	Aplicação Web|
|PointOfCareType.MobileApp|	Aplicação Móvel|
|PointOfCareType.SocialNetwork|	Rede Social|

## 	Local\Ponto de Atendimento
Código identificador do Ponto de Atendimento no Catálogo de Entidades e Serviços.


## 	Códigos de erro na receção de número externo(ReplyCode)

|Id| Valor |
|------------ | ------------|
|100 |	Aguarda Intervenção Manual ou Programada|
|200|	Sucesso|
|400|	Erro Aplicacional ou Formato Inesperado|
|401|	Registo Duplicado ou inesperado|
|500|	Erro Inesperado|

## 	Códigos de erro (ErrorCode)

|Id| Valor |
|------------ | ------------|
|100 |	Aguarda Intervenção Manual ou Programada|
|400|	Erro Aplicacional ou Formato Inesperado|
|401|	Registo Duplicado ou inesperado|
|403| Acesso não autorizado|
|404| O pedido solicitado não foi encontrado|
|500|	Erro Inesperado|

##	 Códigos de Ação

|Id| Valor |
|------------ | ------------|
|1|	Preenchimento formulário|
|2|Submissão formulário|
|3|Colocar pedido em análise|
|4|Finalizar processo|
|5|Aguardar selecção de pagamento|
|6|Emitir guia de pagamento|
|7|Efectuar pagamento do pedido|
|8|Caducar pagamento|
|9|Colocar pedido em atribuição de taxa|
|10|Reatribuir pedido|
|11|Reservar pedido|
|12|Notificar para esclarecimentos|
|13|Reapreciar|
|14|Emitir decisão|
|15|Convocar audência de interessados|
|16|Registar taxa após decisão|
|17|Arquivar pedido|
|18|Libertar pedido|
|19|Submeter pedido à entidade competente|
|20|Enviar notificação|
|29|Criar pedido|
|30|Submeter pedido à análise|
|31|Submeter pedido à análise|
|32|Notificar para esclarecimentos com paragem de prazos|
|33|Comunica|
|34|Comunica|
|35|Registo de intervenção s/ suspenção de prazo|
|36|Registo de intervenção c/ suspensão de prazo|
|37|Retoma de pedido|
|38|Registo de pagamento manual|
|39|Pagamento de taxa em atraso|
|40|Atribuição manual de número de pedido externo|
|41|Correção|

##	Tipo de Taxa

|Id| Valor |
|------------ | ------------|
|TA|Taxa Administrativa|
|T|Taxa de Serviço|

## Plataforma de Integração
[Consultar aqui a informação sobre a Plataforma de Integração](../iap)

## Transferência de Ficheiros
[Consultar aqui a informação sobre a transferência de ficheiros](../largefiles)

## Estrutura Fixa
[Consultar aqui a informação sobre a estrutura fixa](..|EstruturaFixa)
