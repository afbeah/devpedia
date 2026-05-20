# Request Flow

## Handler

Um handler é uma função, método ou componente responsável por processar uma requisição ou evento específico.

Em aplicações web, handlers normalmente:

- recebem requisições HTTP;
- executam regras de negócio;
- acessam banco de dados;
- retornam respostas ao cliente.

A principal ideia de um handler é separar responsabilidades, tornando o código:

- modular;
- reutilizável;
- organizado;
- mais fácil de manter.

## Middleware

Middleware é um componente que intercepta requisições e respostas durante o fluxo da aplicação.

Ele funciona como uma camada intermediária entre:

- a requisição do cliente;
- e o handler da aplicação.

Middlewares são usados para:

- autenticação;
- logs;
- validação;
- tratamento de erros;
- CORS;
- rate limiting;
- monitoramento.
- Como funciona?

### Fluxo comum:

```txt
Cliente
   ↓
Middleware
   ↓
Handler
   ↓
Resposta
```

### Benefícios

- Reutilização de lógica;
- Separação de responsabilidades;
- Código mais organizado;
- Facilidade de manutenção;
- Padronização do fluxo.
  
### Exemplos comuns de middleware

- Autenticação JWT;
- Logger;
- Recovery;
- CORS;
- Compressão;
- Timeout;
- Rate limiting.
