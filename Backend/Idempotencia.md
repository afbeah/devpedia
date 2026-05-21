# Idempotência 

Idempotence é uma propriedade de operações que garante que executar a mesma requisição múltiplas vezes produzirá o mesmo efeito final no sistema.

Ou seja:

- repetir a operação;
- não altera o resultado além da primeira execução.

## Exemplo simples

Imagine uma API para atualizar o nome de um usuário:

```http
PUT /usuarios/1
```

```JSON
{
  "nome": "João"
}
```

Mesmo que essa requisição seja enviada várias vezes, o resultado continuará sendo:

```txt
Usuário com nome "João"
```

## Métodos HTTP e idempotência

|     Método   |    Idempotente?    |
|     :---:    |       :---:        |
|      GET     |        Sim         |
|      PUT     |        Sim         |
|    DELETE    |        Sim         |
|     POST     |        Não         |
|     PATCH    |      Depende       |

## Por que idempotência é importante?

- Evita operações duplicadas;
- Garante consistência;
- Facilita retries automáticos;
- Melhora confiabilidade de APIs;
- Reduz problemas em sistemas distribuídos.

## Casos comuns

- APIs REST;
- Pagamentos;
- Microsserviços;
- Sistemas distribuídos;
- Filas e mensageria.

### Exemplo prático

Sem idempotência:

```txt
POST /pagamento
```

Se a requisição for repetida:

- o pagamento pode ser cobrado duas vezes.

Com idempotência:

- múltiplas tentativas geram apenas uma cobrança.
