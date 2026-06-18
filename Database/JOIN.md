# JOIN

JOIN é uma operação utilizada para combinar dados de duas ou mais tabelas relacionadas.

Seu objetivo é permitir consultas que utilizem informações armazenadas em tabelas diferentes.

Em outras palavras:

> JOIN conecta tabelas através de relacionamentos.

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

Cada tabela possui apenas parte das informações.

Para visualizar os pedidos junto com os clientes precisamos utilizar JOIN.

## Exemplo básico

Consulta:

```sql
SELECT
    customers.name,
    orders.id
FROM customers
JOIN orders
    ON customers.id = orders.customer_id;
```

Resultado:

| Nome  | Pedido |
| ----- | ------ |
| João  | 1      |
| Maria | 2      |

O banco combinou os dados das duas tabelas.

## Como funciona?

Fluxo:

```txt id="h9x2vw"
Primary Key
↓
Foreign Key
↓
JOIN
↓
Resultado combinado
```

O JOIN normalmente utiliza relacionamentos definidos por chaves.

## INNER JOIN

Retorna apenas registros que possuem correspondência nas duas tabelas.

### Exemplo

Clientes:

| ID | Nome  |
| -- | ----- |
| 1  | João  |
| 2  | Maria |
| 3  | Pedro |

Pedidos:

| ID | Cliente_ID |
| -- | ---------- |
| 1  | 1          |
| 2  | 2          |

Consulta:

```sql
SELECT *
FROM customers
INNER JOIN orders
    ON customers.id = orders.customer_id;
```

Resultado:

| Cliente | Pedido |
| ------- | ------ |
| João    | 1      |
| Maria   | 2      |

Pedro não aparece porque não possui pedidos.

## LEFT JOIN

Retorna todos os registros da tabela da esquerda.

Mesmo que não exista correspondência na tabela da direita.

Consulta:

```sql
SELECT *
FROM customers
LEFT JOIN orders
    ON customers.id = orders.customer_id;
```

Resultado:

| Cliente | Pedido |
| ------- | ------ |
| João    | 1      |
| Maria   | 2      |
| Pedro   | NULL   |

Pedro aparece mesmo sem pedidos.

## RIGHT JOIN

Funciona de forma inversa ao LEFT JOIN.

Retorna todos os registros da tabela da direita.

Consulta:

```sql
SELECT *
FROM customers
RIGHT JOIN orders
    ON customers.id = orders.customer_id;
```

É menos utilizado na prática.

## FULL JOIN

Retorna todos os registros das duas tabelas.

Mesmo quando não existe correspondência.

Consulta:

```sql
SELECT *
FROM customers
FULL JOIN orders
    ON customers.id = orders.customer_id;
```

Resultado:

```txt id="s7v4nk"
Todos os clientes
+
Todos os pedidos
```

## Visualizando os JOINs

### INNER JOIN

```txt id="d4m8qp"
Clientes ∩ Pedidos
```

Somente a interseção.

### LEFT JOIN

```txt id="y6k2rw"
Clientes
+
Correspondências em Pedidos
```

### RIGHT JOIN

```txt id="e3v7zn"
Pedidos
+
Correspondências em Clientes
```

### FULL JOIN

```txt id="w9p4tb"
Clientes
+
Pedidos
```

Todos os registros.

## Exemplo prático

Sistema de e-commerce.

Tabelas:

```txt id="u8m5qx"
Customers

Orders

Products
```

Consulta:

```sql
SELECT
    customers.name,
    orders.id
FROM customers
JOIN orders
    ON customers.id = orders.customer_id;
```

Permite visualizar quem realizou cada pedido.

## JOIN em múltiplas tabelas

Também é possível combinar diversas tabelas.

Exemplo:

```sql
SELECT
    c.name,
    o.id,
    p.name
FROM customers c
JOIN orders o
    ON c.id = o.customer_id
JOIN products p
    ON p.id = o.product_id;
```

Fluxo:

```txt id="g5w2tm"
Customers
↓
Orders
↓
Products
```

## Benefícios

### Consultas mais completas

Permite combinar informações de diferentes entidades.

### Aproveitamento da normalização

Evita duplicação de dados.

### Relacionamentos claros

Explora Primary Keys e Foreign Keys.

## Desafios

### Consultas complexas

Muitos JOINs podem dificultar leitura.

### Performance

Consultas envolvendo tabelas grandes podem ser custosas.

Por isso índices costumam ser importantes.

Fluxo:

```txt id="t2v8kr"
JOIN
↓
Index
↓
Melhor performance
```

## JOIN e Normalização

Quanto mais normalizado um banco estiver:

```txt id="q4m7zn"
Mais tabelas
↓
Mais relacionamentos
↓
Mais JOINs
```

Por isso JOIN é um dos conceitos mais importantes de bancos relacionais.

## Relação com outros conceitos

Fluxo comum:

```txt id="z8w3xp"
Modelagem
↓
Normalização
↓
Primary Key
↓
Foreign Key
↓
JOIN
```

Esses conceitos trabalham juntos para organizar e consultar dados de forma eficiente.

## Resumo

JOIN é uma operação utilizada para combinar dados de tabelas relacionadas.

Ele utiliza relacionamentos definidos por Primary Keys e Foreign Keys para reunir informações distribuídas em diferentes tabelas, sendo um dos recursos mais importantes dos bancos de dados relacionais.
