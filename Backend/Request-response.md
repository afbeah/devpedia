# Request

HTTP request é a requisição enviada pelo cliente para o servidor.

Ela contém informações que descrevem:

- o que o cliente deseja;
- qual recurso acessar;
- qual ação executar.

## O que uma request pode conter?

- Método HTTP (GET, POST, PUT, etc);
- URL;
- Headers;
- Query params;
- Body;
- Cookies;
- Tokens de autenticação.

## Exemplo de request

```http
GET /usuarios/1 HTTP/1.1
Host: api.exemplo.com
```

## Quando uma request acontece?

Uma request pode acontecer quando:

- abrimos uma página;
- clicamos em um botão;
- enviamos um formulário;
- consumimos uma API;
- fazemos login em um sistema.


# Response

HTTP response é a resposta enviada pelo servidor após processar uma request.

Ela informa:

- se a operação funcionou;
- quais dados foram retornados;
- ou se ocorreu algum erro.

## O que uma response pode conter?

- Status HTTP;
- Headers;
- Body;
- JSON;
- HTML;
- Mensagens de erro.

## Exemplo de response

```http
HTTP/1.1 200 OK
Content-Type: application/json
{
  "id": 1,
  "nome": "João"
}
```

## Fluxo básico

```txt
Cliente
   ↓
Request
   ↓
Servidor
   ↓
Response
   ↓
Cliente
```

## Status HTTP comuns

|    Código    |       Significado     |
|      200     |        Sucesso        |
|      201     |         Criado        |
|      400     |  Requisição inválida  |
|      401     |     Não autorizado    |
|      404     |     Não encontrado    |
|      500     |      Erro interno     |
