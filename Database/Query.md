# Query

Uma **Query** é uma instrução enviada a um banco de dados com o objetivo de consultar ou manipular informações armazenadas.

O termo "query" significa literalmente "consulta", mas na prática ele é utilizado para qualquer comando executado contra um banco de dados.

## O que uma Query pode fazer?

Uma query pode ser utilizada para:

* Consultar dados;
* Inserir registros;
* Atualizar informações;
* Remover registros;
* Agrupar resultados;
* Relacionar dados de múltiplas tabelas.

## Consultando dados

A operação mais comum é a consulta de informações.

```sql
SELECT * FROM users;
```

Essa query retorna todos os registros da tabela `users`.

### Filtrando resultados

```sql
SELECT *
FROM users
WHERE age > 18;
```

Nesse caso, apenas usuários maiores de 18 anos serão retornados.

## Manipulando dados

### Inserindo registros

```sql
INSERT INTO users (name, age)
VALUES ('Beatriz', 24);
```

### Atualizando registros

```sql
UPDATE users
SET age = 25
WHERE id = 1;
```

### Removendo registros

```sql
DELETE FROM users
WHERE id = 1;
```

## Como uma Query funciona?

Quando uma query é enviada ao banco de dados, geralmente ocorre o seguinte fluxo:

1. O banco recebe a instrução.
2. A sintaxe é validada.
3. Um plano de execução é criado.
4. Os dados são localizados.
5. O resultado é retornado.

Esse processo acontece em milissegundos na maioria das aplicações.

## Performance de Queries

A forma como uma query é escrita pode impactar diretamente a performance do sistema.

Por exemplo:

```sql
SELECT *
FROM users;
```

Em uma tabela com milhões de registros, essa consulta pode ser custosa.

Muitas vezes é mais eficiente buscar apenas os dados necessários:

```sql
SELECT id, name
FROM users;
```

## Índices (Indexes)

Os índices são estruturas criadas para acelerar consultas.

Sem índice, o banco pode precisar percorrer todos os registros da tabela para encontrar um resultado.

Com índice, a busca é muito mais rápida.

### Exemplo

```sql
CREATE INDEX idx_email
ON users(email);
```

Agora consultas por email tendem a ser executadas de forma mais eficiente.

## Queries Complexas

À medida que uma aplicação cresce, as consultas costumam se tornar mais sofisticadas.

### JOIN

Permite relacionar dados de diferentes tabelas.

```sql
SELECT
    users.name,
    orders.total
FROM users
JOIN orders
ON users.id = orders.user_id;
```

### GROUP BY

Permite agrupar informações.

```sql
SELECT
    city,
    COUNT(*)
FROM users
GROUP BY city;
```

### Subquery

Permite executar uma consulta dentro de outra.

```sql
SELECT *
FROM users
WHERE id IN (
    SELECT user_id
    FROM orders
);
```

## Query Optimization

Query Optimization é o processo de melhorar consultas para reduzir tempo de execução e consumo de recursos.

Algumas boas práticas incluem:

* Buscar apenas os campos necessários;
* Utilizar índices adequadamente;
* Evitar consultas desnecessárias;
* Filtrar dados sempre que possível;
* Analisar planos de execução para identificar gargalos.

## Resumo

Queries são a principal forma de comunicação entre uma aplicação e um banco de dados.

Praticamente toda operação realizada em sistemas que utilizam bancos de dados depende da execução de uma ou mais queries.
