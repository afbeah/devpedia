# Chave Estrangeira (Foreign Key)

Uma Chave Estrangeira (Foreign Key) é uma coluna utilizada para criar relacionamentos entre tabelas.

Seu principal objetivo é garantir a integridade dos dados e permitir que diferentes entidades do sistema se conectem.

Em outras palavras:

> A Foreign Key é a ponte entre tabelas.

## Por que utilizar?

Imagine um sistema de vendas.

Tabela de clientes:

| ID | Nome  |
| -- | ----- |
| 1  | João  |
| 2  | Maria |

Tabela de pedidos:

| ID | Cliente_ID |
| -- | ---------- |
| 1  | 1          |
| 2  | 2          |

Como o banco sabe a quem pertence cada pedido?

Através da Foreign Key.

## Como funciona?

A Foreign Key referencia uma Primary Key existente em outra tabela.

Exemplo:

```txt id="p4x7tv"
Clientes
↓
ID (Primary Key)
```

```txt id="z7m2rw"
Pedidos
↓
Cliente_ID (Foreign Key)
```

Nesse caso:

```txt id="u8k5pm"
Cliente_ID
```

aponta para:

```txt id="a4r9wx"
Clientes.ID
```

## Exemplo SQL

Tabela de clientes:

```sql id="g8t4vy"
CREATE TABLE customers (

    id SERIAL PRIMARY KEY,

    name VARCHAR(100)

);
```

Tabela de pedidos:

```sql id="m5p7zx"
CREATE TABLE orders (

    id SERIAL PRIMARY KEY,

    customer_id INT,

    FOREIGN KEY (customer_id)
        REFERENCES customers(id)

);
```

Agora cada pedido deve estar associado a um cliente válido.

## Integridade Referencial

Uma das principais funções da Foreign Key.

Imagine:

```txt id="y3n7kv"
Pedido
↓
Cliente_ID = 99
```

Mas o cliente 99 não existe.

Sem Foreign Key:

```txt id="v2r8pm"
Dado inconsistente
```

Com Foreign Key:

```txt id="x6m4zh"
Operação bloqueada
```

O banco protege a integridade dos dados.

## Exemplo Visual

```txt id="q7k3vx"
Clientes
┌────┬───────┐
│ ID │ Nome  │
├────┼───────┤
│ 1  │ João  │
│ 2  │ Maria │
└────┴───────┘
```

```txt id="n8w5tj"
Pedidos
┌────┬─────────────┐
│ ID │ Cliente_ID  │
├────┼─────────────┤
│ 1  │ 1           │
│ 2  │ 2           │
└────┴─────────────┘
```

Relacionamento:

```txt id="r4y9hp"
Pedidos.Cliente_ID
↓
Clientes.ID
```

## Tipos de Relacionamento

### Um para Um (1:1)

Exemplo:

```txt id="e6v2kw"
Usuário
↓
Perfil
```

Cada usuário possui apenas um perfil.

---

### Um para Muitos (1:N)

Exemplo:

```txt id="j9x4pm"
Cliente
↓
Pedidos
```

Um cliente pode possuir vários pedidos.

Esse é o relacionamento mais comum.

---

### Muitos para Muitos (N:N)

Exemplo:

```txt id="t7w5rb"
Pedido
↓
Produto
```

Um pedido possui vários produtos.

Um produto pode estar em vários pedidos.

Normalmente utiliza-se uma tabela intermediária.

Exemplo:

```txt id="c5m8vx"
orders_products
```

## ON DELETE

Define o comportamento quando um registro é removido.

### RESTRICT

Impede a exclusão.

```txt id="w3r7nh"
Cliente possui pedidos
↓
Não pode ser removido
```

### CASCADE

Remove os registros relacionados automaticamente.

```txt id="q9k2zp"
Cliente removido
↓
Pedidos removidos
```

### SET NULL

Define o valor da Foreign Key como nulo.

```txt id="k4x8tv"
Cliente removido
↓
Cliente_ID = NULL
```

## Benefícios

### Integridade dos dados

Evita referências inválidas.

### Relacionamentos consistentes

Mantém tabelas conectadas corretamente.

### Facilidade de consulta

Permite realizar joins.

Exemplo:

```sql id="s6t4wx"
SELECT *
FROM customers c
JOIN orders o
ON c.id = o.customer_id;
```

## Foreign Key e Normalização

A normalização utiliza Foreign Keys para evitar duplicação de dados.

Exemplo:

Sem normalização:

```txt id="n5r2vw"
Pedido
↓
Nome Cliente
↓
Email Cliente
```

Com normalização:

```txt id="m8p7kh"
Cliente
↓
Pedido
```

A ligação ocorre através da Foreign Key.

## Primary Key x Foreign Key

| Primary Key              | Foreign Key             |
| ------------------------ | ----------------------- |
| Identifica registros     | Cria relacionamentos    |
| Única                    | Pode repetir            |
| Não pode ser nula        | Pode depender da regra  |
| Existe na própria tabela | Referencia outra tabela |

## Relação com outros conceitos

Fluxo comum:

```txt id="v4k7mz"
Modelagem
↓
Normalização
↓
Primary Key
↓
Foreign Key
↓
Relacionamentos
```

Esses são os fundamentos dos bancos relacionais.

## Resumo

Uma Chave Estrangeira (Foreign Key) é uma coluna utilizada para criar relacionamentos entre tabelas.

Ela referencia uma Primary Key existente, garantindo integridade referencial e permitindo que diferentes entidades do sistema se conectem de forma consistente.
