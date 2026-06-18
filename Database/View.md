# View

Uma View é uma tabela virtual criada a partir do resultado de uma consulta SQL.

Ela não armazena dados diretamente, mas apresenta informações derivadas de uma ou mais tabelas.

Em outras palavras:

> Uma View é uma consulta salva no banco de dados.

## Por que utilizar?

Imagine uma consulta utilizada frequentemente.

```sql id="g7m2tw"
SELECT
    c.name,
    o.id
FROM customers c
JOIN orders o
    ON c.id = o.customer_id;
```

Em vez de escrever essa consulta repetidamente, podemos criar uma View.

## Exemplo

```sql id="p8v4mz"
CREATE VIEW customer_orders AS

SELECT
    c.name,
    o.id
FROM customers c
JOIN orders o
    ON c.id = o.customer_id;
```

Agora basta consultar:

```sql id="k4x7rn"
SELECT *
FROM customer_orders;
```

## Como funciona?

Fluxo:

```txt id="m9w3tb"
Tabelas
↓
Query
↓
View
↓
Consulta
```

A View simplifica o acesso aos dados.

## Exemplo prático

Tabelas:

```txt id="y2k8rw"
Customers

Orders
```

View:

```txt id="r5m4tx"
CustomerOrders
```

Usuários podem consultar a View sem conhecer toda a estrutura do banco.

## Benefícios

### Reutilização

Evita repetir consultas complexas.

### Organização

Centraliza lógica de consulta.

### Segurança

Permite expor apenas determinados dados.

### Facilidade de uso

Consultas tornam-se mais simples.

## Exemplo de Segurança

Tabela original:

```txt id="w3v7kn"
ID

Nome

Email

CPF
```

View:

```txt id="f6m2rp"
Nome

Email
```

Usuários acessam apenas os dados necessários.

## View e JOIN

Views frequentemente utilizam JOINs.

Exemplo:

```txt id="z8x5tm"
Customers
↓
Orders
↓
Products
↓
View
```

Isso permite criar visões consolidadas dos dados.

## Materialized View

Alguns bancos oferecem Materialized Views.

Diferença:

### View

```txt id="v4m8tz"
Consulta executada a cada acesso
```

### Materialized View

```txt id="k9w2rp"
Resultado armazenado
```

Isso pode melhorar a performance.

## Benefícios

* Simplificação de consultas;
* Reutilização;
* Segurança;
* Organização.

## Desafios

* Dependência das tabelas originais;
* Possível impacto de performance;
* Necessidade de manutenção.

## View e Data Warehouse

Views são muito utilizadas em:

* BI;
* Relatórios;
* Dashboards;
* Data Warehouses.

Elas ajudam a organizar consultas analíticas complexas.

## Relação com outros conceitos

Fluxo comum:

```txt id="x7m4tb"
Primary Key
↓
Foreign Key
↓
JOIN
↓
Query
↓
View
```

Uma View normalmente encapsula consultas que utilizam esses conceitos.

## Resumo

View é uma tabela virtual criada a partir de uma consulta SQL.

Ela permite simplificar consultas complexas, reutilizar lógica de acesso a dados e aumentar a organização e segurança de aplicações que utilizam bancos relacionais.
