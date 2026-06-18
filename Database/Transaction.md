# Transaction

Uma Transaction (Transação) é um conjunto de operações executadas como uma única unidade de trabalho.

Seu objetivo é garantir que os dados permaneçam consistentes mesmo em caso de falhas.

Em outras palavras:

> Ou todas as operações acontecem, ou nenhuma acontece.

## Por que utilizar?

Imagine uma transferência bancária.

Conta A:

```txt id="k2m5zp"
Saldo = 1000
```

Conta B:

```txt id="q7v4tw"
Saldo = 500
```

Transferência:

```txt id="x8m3rh"
Retirar 100 da Conta A

Adicionar 100 na Conta B
```

E se o sistema falhar no meio do processo?

Resultado:

```txt id="e5w2pk"
Conta A = 900

Conta B = 500
```

Os dados ficam inconsistentes.

A Transaction existe para evitar esse problema.

## Como funciona?

Fluxo:

```txt id="c9x7tn"
BEGIN
↓
Operações
↓
COMMIT
```

Se tudo funcionar:

```txt id="m4r8zw"
COMMIT
```

As alterações são confirmadas.

Se ocorrer erro:

```txt id="v2k5px"
ROLLBACK
```

As alterações são desfeitas.

## Exemplo SQL

```sql id="h8m4tz"
BEGIN;

UPDATE accounts
SET balance = balance - 100
WHERE id = 1;

UPDATE accounts
SET balance = balance + 100
WHERE id = 2;

COMMIT;
```

Se houver falha:

```sql id="g3x7wp"
ROLLBACK;
```

## ACID

As transações seguem os princípios ACID.

### Atomicidade

Tudo ou nada.

```txt id="n6v3kt"
Sucesso total

ou

Falha total
```

### Consistência

Os dados permanecem válidos.

### Isolamento

Uma transação não interfere na outra.

### Durabilidade

Após o COMMIT os dados são preservados.

## Exemplo prático

Sistema de e-commerce.

Fluxo:

```txt id="w7m2rh"
Criar pedido
↓
Atualizar estoque
↓
Registrar pagamento
```

Essas operações podem fazer parte de uma única transação.

## Benefícios

* Integridade dos dados;
* Consistência;
* Segurança;
* Confiabilidade.

## Desafios

* Consumo de recursos;
* Possíveis bloqueios;
* Impacto na performance.

## Transaction e OLTP

Transações são fundamentais em sistemas OLTP.

Exemplos:

* pagamentos;
* transferências;
* pedidos;
* estoque.

## Resumo

Transaction é um mecanismo que permite executar múltiplas operações como uma única unidade de trabalho.

Seu objetivo é garantir consistência e integridade dos dados, utilizando conceitos como COMMIT, ROLLBACK e os princípios ACID.
