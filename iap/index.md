# Plataforma de Integração


A Plataforma de Integração é a solução da Plataforma de Interoperabilidade que proporciona um método fácil e integrado de disponibilização de serviços electrónicos transversais, tornando-se uma peça fundamental no processo de modernização administrativa.

Centrada no cidadão, os seus princípios são:

- Criar mecanismos de autenticação forte e gestão de identidade para, de uma forma segura, facilitarem a identificação do Cidadão perante os Entidades que se encontram
- integradas na Plataforma de Interoperabilidade. Este objectivo é atingido recorrendo ao Fornecedor de Autenticação;
- Permitir de forma fácil e integrada a disponibilização de serviços electrónicos transversais centrados no Cidadão;
-Garantir ao Cidadão e à Administração Pública a privacidade, confidencialidade e segurança dos dados;
-Assegurar os mecanismos necessários de forma a controlar as transacções, qualidade da informação e transparência nos processos de negócio suportados na Plataforma de Integração. Para saber mais consulte [IAPl](https://iap.gov.pt)

##	Ligação à Plataforma de Integração
Este capítulo pretende introduzir os conceitos necessários para a integração com a Plataforma de Integração (PI) da Administração pública. A Plataforma de Interoperabilidade é uma iniciativa lançada pela AMA que pretende implementar uma arquitetura tecnológica comum que facilite a interoperabilidade uniforme de diferentes sistemas de informação, tendo por base princípios de interoperabilidade e segurança, permitindo sinergias e redução das necessidades de desenvolvimento, levando a diminuição de custos. A PI pretende dotar a Administração Pública de uma componente que serve de intermediária / facilitadora para os atuais sistemas de informação, na qual serão registados e disponibilizados serviços eletrónicos. A orientação para a disponibilização eletrónica de serviços exige requisitos que são necessário cumprir de forma a garantir o correto funcionamento de uma forma controlada e segura. Nos pontos abaixo seguem-se os requisitos que devem ser seguidos para a ligação com a Plataforma de Interoperabilidade.

##	Infraestrutura
O estabelecimento de comunicação segura entre os sistemas de informação da Entidade e os sistemas da Plataforma de Interoperabilidade; o Regras de redes que permitam a comunicação entre os sistemas de informação na Entidade e os sistemas da Plataforma de Interoperabilidade, para comunicação no protocolo http; o Utilização (opcional) de certificado digital para suporte a comunicação segura (https); o Contactos de elementos responsáveis a nível de infraestrutura, para operações de configuração e manutenção da infraestrutura de comunicação.

##	Desenvolvimento do Servidor
Deverá ser desenvolvido do lado da entidade o serviço messageRequest recorrendo ao WSDL. Este poderá ser desenvolvido em qualquer linguagem ou sistema que suporte a receção de mensagens XML SOAP.

-	Representado via WSDL 1.1 (http://www.w3.org/TR/wsdl)
-	 Binding Soap 1.1 ou 1.2;
-	XML document-style;
-	 Implementação assíncrona (one-way) ;
-	 Canal de transporte HTTP:
-	Utilização opcional de HTTPS
-	Utilização opcional de autenticação http basic auth;
-	 WS-Addressing v1.0 (http://www.w3.org/TR/ws-addr-core/), como forma de correlacionamento de mensagens em modelo de comunicação assíncrona; o Deve respeitar as recomendações WS-Interoperability Basic-Profile 1.1 (Interoperability Testing Tools 1.1 - http://www.ws-i.org/deliverables/testingtools.html


##	Desenvolvimento do Servidor
  No âmbito de configuração de serviços e processos a serem integrados com a Plataforma de Integração, e de acordo com as necessidades, será necessário que:
  -	Deve implementar o serviço de acordo com o WSDL para que seja configurado na Plataforma de Integração.

  No que diz respeito à integração orientada aos serviços são aqui incluídas as normas respeitantes aos Web Sevices que devem ser suportadas pelas Entidades visadas. A norma XML é utilizada na especificação do Web Service que é invocado para executar uma determinada tarefa ou um conjunto de tarefas e assim obter um resultado específico.

  O XML é usado como linguagem de base para a especificação dos principais padrões que estruturam os Web Services:  
  - WSDL – Web Service Description Language  
  - SOAP – Simple Object Aplication Protocol

  Nesse âmbito, a descrição de um Web Service é efectuada através de uma estrutura WSDL que contém os detalhes de interação que é possível estabelecer com o respectivo. Esta descrição contém o formato das men-sagens trocadas e os respectivos protocolos de transporte. A comunicação entre os vários Web Services e as entidades que os invocam é regrada pelo protocolo SOAP que descreve os seu modo de interação.

  A utilização do protocolo SOAP na Plataforma de Integração é suportada sobre transporte em HTTP (ou HTTPS de forma opcional), que é um protocolo independente e compatível com qualquer web browser ou servidor aplicacional.

  A utilização de SOAP sobre HTTP possui ainda como vantagens o estabelecimento simplificado a nível de regras de infraestrutura em proxy e firewall, para além de ser atualmente considerado um protocolo que é independente do tipo de plataforma ou de linguagem usado nos diferentes sistemas.
  Um pedido SOAP sobre HTTP identifica o tipo de pedido que é efetuado sobre este protocolo. Uma mensagem SOAP contém informação estruturada em XML e contém os seguintes elementos:  

   HTTP Headers – com informação específica do protocolo HTTP   SOAP Envelope – com informação específica do protocolo SOAP o Header ou cabeçalho com informação; o Body ou corpo com informação de Request e Response; o Fault ou erro com informação descritiva de erros de processamento.
  Embora o SOAP forneça os fundamentos da transmissão de mensagens, é necessária mais informação para fornecer diretrizes de mensagem em ambientes de transmissão assíncrona.

   O WS-Adressing define os cabeçalhos das mensagens que são aplicados às mensagens SOAP para determinar onde as mensagens devem ser enviadas e fornecer a correlação entre mensagens.
  De seguida são apresentados os atributos/elementos associados ao WS-Addressing:

  __<MessageID>__- Identificador Único da mensagem – URI. Se uma mensagem é retransmitida, mantém o mesmo MessageID. Este elemento deve ser gerado pelo consumidor do serviço, a partir do qual será possível efetuar e identificar a localização da mensagem em todo o seu caminho. Este valor mantém-se inalterado até ao final do ciclo de vida da mensagem.  

  **<RelatesTo>**- Identifica a mensagem de origem através do MessageID aquando do envio da mensagem de resposta. Permite efetuar a correlação assíncrona de mensa-gens de resposta, com as respetivas mensagens de pedido.  

  **<ReplyTo>** -Especifica o endpoint reference para onde deve ser enviada a resposta para a mensagem. É de utilização obrigatória sempre que se consuma um serviço electrónico, ao qual é expectável a existência de uma resposta assíncrona correlacionada.

  **<To>** - Especifica o endpoint reference destino desta mensagem.  I

**<Action>** - dentifica a semântica da mensagem, ou seja, associa à mensagem o portType do WSDL para identificar se a mensagem é um **<input>**, **<output>** ou **<fault>**.
