# Swagger

Swagger é um conjunto de ferramentas utilizado para criar, documentar, testar e consumir APIs.

Ele utiliza a especificação OpenAPI para descrever a estrutura e o funcionamento de uma API de forma padronizada.

Isso permite que:

- desenvolvedores;
- aplicações;
- ferramentas;
- clientes HTTP

entendam como interagir com a API sem precisar acessar o código-fonte.

## O que o Swagger permite?

- Documentação interativa de APIs;
- Testes de endpoints diretamente pelo navegador;
- Geração automática de código;
- Padronização da documentação;
- Facilitar integração entre sistemas.

## Principais ferramentas do ecossistema Swagger

- Swagger UI → interface visual da documentação;
- Swagger Editor → editor de especificações OpenAPI;
- Swagger Codegen → geração automática de código cliente e servidor.

## Benefícios

- Melhor comunicação entre equipes;
- Facilidade de integração;
- Redução de erros;
- Documentação centralizada;
- Maior produtividade no desenvolvimento.

## Exemplo simples

```YAML
paths:
  /users:
    get:
      summary: Lista usuários
```
