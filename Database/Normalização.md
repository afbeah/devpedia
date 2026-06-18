# Normalização

Normalização é o processo de organizar dados em um banco de dados para reduzir redundâncias e evitar inconsistências.

Seu principal objetivo é garantir que cada informação seja armazenada no local correto.

Em outras palavras:

> Normalizar é evitar duplicação desnecessária de dados.

## O problema

Imagine uma tabela de pedidos:

| Pedido | Cliente | Email                                   |
| ------ | ------- | --------------------------------------- |
| 1      | João    | [joao@email.com](mailto:joao@email.com) |
| 2      | João    | [joao@email.com](mailto:joao@email.com) |
| 3      | João    | [joao@email.com](mailto:joao@email.com) |

Perceba que os dados do cliente estão sendo repetidos.

Problemas:

* desperdício de espaço;
* maior risco de inconsistência;
* dificuldade de manutenção.

## Solução

Separar as informações em tabelas relacionadas.

### Clientes

| ID | Nome | Email                                   |
| -- | ---- | --------------------------------------- |
| 1  | João | [joao@email.com](mailto:joao@email.com) |

### Pedidos

| ID | Cliente_ID |
| -- | ---------- |
| 1  | 1          |
| 2  | 1          |
| 3  | 1          |

Agora a informação do cliente existe apenas uma vez.

## Benefícios

### Menos duplicação

Dados armazenados uma única vez.

### Maior consistência

Menor risco de informações divergentes.

### Facilidade de manutenção

Atualizações acontecem em apenas um local.

### Melhor organização

Estrutura mais clara e previsível.

## Formas Normais

A normalização é dividida em níveis chamados Formas Normais.

Na prática, as três primeiras são as mais importantes.

## Primeira Forma Normal (1FN)

Regra:

> Cada coluna deve possuir apenas um valor.

### Ruim

| Cliente | Telefones  |
| ------- | ---------- |
| João    | 1111, 2222 |

Uma coluna contém múltiplos valores.

### Melhor

| Cliente | Telefone |
| ------- | -------- |
| João    | 1111     |
| João    | 2222     |

Agora cada campo possui apenas um valor.

## Segunda Forma Normal (2FN)

Regra:

> Todos os atributos devem depender da chave inteira.

Imagine:

| Pedido_ID | Produto_ID | Nome_Produto |
| --------- | ---------- | ------------ |
| 1         | 10         | Notebook     |

O nome do produto depende apenas do produto.

Não depende do pedido.

O ideal seria:

### Produtos

| Produto_ID | Nome     |
| ---------- | -------- |
| 10         | Notebook |

### Pedidos

| Pedido_ID | Produto_ID |
| --------- | ---------- |
| 1         | 10         |

## Terceira Forma Normal (3FN)

Regra:

> Um atributo não deve depender de outro atributo que não seja a chave.

Exemplo:

| Cliente_ID | Cidade         | Estado |
| ---------- | -------------- | ------ |
| 1          | Rio de Janeiro | RJ     |

Se a cidade determina o estado, existe dependência transitiva.

Uma possível solução:

### Cidades

| Cidade_ID | Cidade | Estado |
| --------- | ------ | ------ |

### Clientes

| Cliente_ID | Cidade_ID |
| ---------- | --------- |

## Exemplo prático

Sistema de vendas.

Sem normalização:

```txt id="q2w9hf"
Pedido
↓
Nome Cliente
↓
Email Cliente
↓
Endereço Cliente
```

Os dados são repetidos em cada pedido.

Com normalização:

```txt id="j7x5pn"
Cliente
↓
Pedido
```

Cada informação é armazenada apenas uma vez.

## Chaves Primárias

A normalização normalmente utiliza chaves primárias.

Exemplo:

```sql id="k4r8nm"
id
```

Responsável por identificar registros únicos.

## Chaves Estrangeiras

Permitem relacionar tabelas.

Exemplo:

```sql id="x5v9pc"
customer_id
```

Ligando pedidos a clientes.

## Normalização x Performance

Nem sempre um banco extremamente normalizado é a melhor solução.

Em alguns cenários analíticos pode ocorrer:

```txt id="w8y4rs"
Desnormalização
```

para melhorar desempenho.

Isso é comum em:

* Data Warehouse;
* OLAP;
* BigQuery.

## Desnormalização

Consiste em duplicar algumas informações de forma controlada para acelerar consultas.

Exemplo:

```txt id="m3q7tx"
Mais espaço
↓
Menos joins
↓
Mais velocidade
```

## Quando utilizar?

A normalização é amplamente utilizada em:

* PostgreSQL;
* MySQL;
* SQL Server;
* Oracle.

Principalmente em ambientes OLTP.

## Relação com outros conceitos

Fluxo comum:

```txt id="b2w7fp"
Modelagem
↓
Normalização
↓
Banco Relacional
↓
Query
↓
Index
```

## Resumo

Normalização é o processo de organizar dados para reduzir redundâncias e evitar inconsistências.

Ela utiliza regras conhecidas como Formas Normais para garantir que informações sejam armazenadas de maneira eficiente, consistente e fácil de manter, sendo um dos fundamentos dos bancos de dados relacionais.
