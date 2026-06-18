# Chave Primária (Primary Key)

Uma Chave Primária (Primary Key) é uma coluna ou conjunto de colunas utilizada para identificar unicamente cada registro de uma tabela.

Seu principal objetivo é garantir que não existam registros duplicados.

Em outras palavras:

> A chave primária funciona como a identidade de um registro.

## Por que utilizar?

Imagine uma tabela de usuários.

| Nome | Email                                   |
| ---- | --------------------------------------- |
| João | [joao@email.com](mailto:joao@email.com) |
| João | [joao@email.com](mailto:joao@email.com) |

Como identificar qual registro é qual?

Para resolver esse problema utilizamos uma chave primária.

## Exemplo

Tabela:

| ID | Nome  |
| -- | ----- |
| 1  | João  |
| 2  | Maria |
| 3  | Pedro |

Nesse caso:

```txt id="v8k2tw"
ID
```

é a chave primária.

Cada registro possui um identificador único.

## Características

Uma chave primária deve possuir:

### Unicidade

Não pode existir repetição.

Exemplo:

```txt id="j4r8pn"
1
2
3
```

Válido.

```txt id="r7x2mc"
1
1
2
```

Inválido.

### Não pode ser nula

Todo registro precisa possuir um identificador.

Exemplo:

```txt id="c3v7zp"
NULL
```

não é permitido.

### Estabilidade

Idealmente não deve mudar com frequência.

## Exemplo SQL

Criação de tabela:

```sql
CREATE TABLE users (

    id SERIAL PRIMARY KEY,

    name VARCHAR(100),

    email VARCHAR(100)

);
```

Nesse exemplo:

```txt id="h2m5rw"
id
```

é a chave primária.

## Chave Natural

É uma informação que já existe no domínio do negócio.

Exemplos:

```txt id="y8q4tv"
CPF

RG

Número de Passaporte
```

Embora possível, nem sempre é a melhor escolha.

## Chave Artificial (Surrogate Key)

É criada apenas para identificação.

Exemplo:

```txt id="w4n7ks"
id
```

ou

```txt id="f7m2px"
UUID
```

Esse modelo é muito utilizado em sistemas modernos.

## UUID

Uma alternativa ao identificador numérico.

Exemplo:

```txt id="t5j8zb"
550e8400-e29b-41d4-a716-446655440000
```

Vantagem:

```txt id="p8r3wn"
Alta unicidade
```

Muito utilizado em microsserviços.

## Chave Composta

Uma chave primária também pode ser formada por múltiplas colunas.

Exemplo:

```sql
PRIMARY KEY (
    order_id,
    product_id
)
```

Nesse caso a combinação dos dois valores forma a chave.

## Exemplo prático

Tabela de pedidos:

| ID | Cliente |
| -- | ------- |
| 1  | João    |
| 2  | Maria   |

Tabela de itens:

| Pedido_ID | Produto_ID |
| --------- | ---------- |
| 1         | 10         |
| 1         | 20         |

Os registros podem ser identificados pela combinação das colunas.

## Chave Primária e Relacionamentos

A chave primária normalmente é utilizada por outras tabelas.

Exemplo:

```txt id="x4t7rm"
Cliente
↓
Pedido
```

A tabela Pedido utiliza a chave do Cliente para criar a relação.

## Benefícios

* Identificação única;
* Integridade dos dados;
* Facilita relacionamentos;
* Melhora organização do banco.

## Relação com Normalização

A normalização utiliza chaves primárias para eliminar redundâncias e organizar relacionamentos.

Fluxo:

```txt id="m6w2pk"
Modelagem
↓
Normalização
↓
Primary Key
↓
Relacionamentos
```

## Resumo

Uma Chave Primária (Primary Key) é um identificador único utilizado para distinguir registros dentro de uma tabela.

Ela garante integridade, evita duplicidades e serve como base para relacionamentos entre tabelas em bancos de dados relacionais.
