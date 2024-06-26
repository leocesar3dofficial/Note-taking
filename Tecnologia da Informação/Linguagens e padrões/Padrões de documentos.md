# Padrões de Documentos

## XML (Extensible Markup Language)

- Linguagem de marcação utilizada para estruturar e armazenar dados de forma legível, tanto para humanos quanto para máquinas.
- Permite definir etiquetas (tags) personalizadas para descrever o conteúdo dos dados.
- Facilita a troca de informações entre diferentes sistemas.
- Tendo um documento:
  - Pode ler.
  - Pode verificar se o documento é bem formatado.
  - Pode validá-lo somente se tiver acesso ao esquema.

## XSLT (Extensible Stylesheet Language Transformations)

- Linguagem utilizada para transformar documentos XML em outros formatos, como HTML ou XML com estrutura diferente.
- Permite criar regras de transformação especificando como o documento XML de entrada deve ser processado e formatado para obter a saída desejada.

## WSDL (Web Services Description Language)

- Linguagem utilizada para descrever serviços web, incluindo operações, mensagens, formatos de dados e protocolos de comunicação.
- Fornece um contrato formal para os serviços web, permitindo que os consumidores entendam como interagir com eles.

## UDDI (Universal Description, Discovery, and Integration)

- Padrão para descoberta e integração de serviços web.
- Fornece um diretório centralizado onde os fornecedores de serviços publicam informações sobre seus serviços web, e os consumidores procuram e descobrem esses serviços com base em critérios específicos.
- Framework de plataforma independente desenvolvido na plataforma .NET.
- Possibilita uma exposição controlada dos serviços da empresa/fornecedor.
- Comunicação realizada através do SOAP.
- Interfaces web service descritas por WSDL.

## SOAP (Simple Object Access Protocol)

- Protocolo de comunicação para troca de informações/mensagens entre sistemas distribuídos.
  - Permite que aplicativos em diferentes plataformas e linguagens se comuniquem de maneira padronizada.
- Define uma estrutura de mensagem XML representando solicitações e respostas entre o cliente e o servidor.
  - Exige o uso de XML para fornecer a resposta.
  - Baseado em padrões XML para estruturar os dados transmitidos.
  - Estrutura de mensagem com envelope SOAP contendo cabeçalho (opcional) e corpo (obrigatório).
- Usa HTTP como protocolo de transporte padrão.
  - Protocolo extensível permitindo definição de protocolos específicos de aplicação (bindings).
- Facilita a interoperabilidade entre diferentes plataformas e tecnologias.
- Mecanismos de proteção incluem autenticação via token.
- Utilizado em aplicações e serviços web.

## JSON (JavaScript Object Notation)

- Formato de dados leve e legível por humanos.
- Usado para trocar informações estruturadas entre sistemas, sendo utilizado em aplicativos e serviços web.
- Alternativa ao XML, utilizando uma sintaxe simples baseada em pares de chave-valor para representar os dados.
- Facilmente interpretado e manipulado por várias linguagens de programação.
