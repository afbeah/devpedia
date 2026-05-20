# Context

Em Go, context é utilizado para transportar informações relacionadas ao ciclo de vida de uma operação.

Ele permite compartilhar:

- deadlines;
- cancelamentos;
- timeouts;
- valores de requisição

entre funções, APIs e goroutines de forma segura e padronizada.

## Para que serve?

O context é muito utilizado para:

- cancelar operações longas;
- controlar timeouts;
- propagar informações entre chamadas;
- coordenar goroutines;
- controlar requisições HTTP;
- evitar vazamento de recursos.


## Principais funcionalidades

- Cancelamento de operações;
- Controle de timeout;
- Definição de deadlines;
- Compartilhamento de valores;
- Coordenação de concorrência.

## Exemplo simples

```go
ctx, cancel := context.WithCancel(context.Background())

defer cancel()
```
- Timeout com context

```go
ctx, cancel := context.WithTimeout(
    context.Background(),
    5*time.Second,
)

defer cancel()
```

## Quando usar context?

- APIs HTTP;
- Banco de dados;
- Goroutines;
- Microsserviços;
- Requisições externas;
- Operações concorrentes.

## Benefícios

- Melhor controle de execução;
- Cancelamento seguro;
- Evita goroutines órfãs;
- Facilita gerenciamento de recursos;
- Padroniza fluxo de execução.
