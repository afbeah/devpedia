# Index

Index (Índice) é uma estrutura utilizada pelos bancos de dados para acelerar consultas.

Seu objetivo é permitir que registros sejam encontrados mais rapidamente sem a necessidade de percorrer toda a tabela.

Em outras palavras:

> Índices existem para tornar buscas mais rápidas.

## O problema

Imagine uma tabela com:

```txt id="z6w2nk"
10 registros
```

Encontrar um usuário é simples.

Agora imagine:

```txt id="m4t8hr"
100 milhões de registros
```

Sem índices, o banco pode precisar analisar registro por registro até encontrar o resultado desejado.

Esse processo é conhecido como:

```txt id="x9c5pb"
Full Table Scan
```

ou varredura completa da tabela.

## Uma analogia simples

Imagine uma biblioteca.

Sem índice:

```txt id="c2j7md"
Procurar livro
↓
Verificar todas as prateleiras
```

Com índice:

```txt id="3v8rxt"
Consultar catálogo
↓
Encontrar localização
↓
Buscar livro
```

O índice funciona como um catálogo.

## Exemplo sem índice

Tabela:

```sql id="g8y4pz"
users
```

Consulta:

```sql id="f7m2wd"
SELECT *
FROM users
WHERE email = 'beatriz@email.com';
```

Sem índice, o banco pode precisar verificar todos os registros.

## Exemplo com índice

Criação do índice:

```sql id="n5q7la"
CREATE INDEX idx_users_email
ON users(email);
```

Agora o banco consegue localizar o registro muito mais rapidamente.

## Como funciona?

O banco cria uma estrutura auxiliar contendo referências para os dados.

Simplificando:

```txt id="y8d4cj"
email
↓
posição do registro
```

Assim a busca se torna muito mais eficiente.

## Colunas que costumam receber índices

Exemplos:

* ID;
* Email;
* CPF;
* Username;
* Chaves estrangeiras;
* Campos muito utilizados em consultas.

## Exemplo prático

Tabela:

```txt id="g1r7wn"
users
```

Consulta frequente:

```sql id="t2m8xs"
SELECT *
FROM users
WHERE cpf = '12345678900';
```

Criar um índice em:

```txt id="v6n4hb"
cpf
```

pode melhorar significativamente a performance.

## Índice Primário

Normalmente criado automaticamente através da chave primária.

Exemplo:

```sql id="u9w2ep"
CREATE TABLE users (
    id SERIAL PRIMARY KEY
);
```

O banco geralmente cria um índice para:

```txt id="h7j5rt"
id
```

## Índice Único

Garante que não existam valores duplicados.

Exemplo:

```sql id="q8k3yc"
CREATE UNIQUE INDEX idx_email
ON users(email);
```

Muito utilizado para:

```txt id="v4x1mf"
Email

CPF

Username
```

## Índices Compostos

Criados utilizando mais de uma coluna.

Exemplo:

```sql id="k3w7dh"
CREATE INDEX idx_order
ON orders(customer_id, created_at);
```

Útil para consultas que utilizam múltiplos filtros.

## Benefícios

### Consultas mais rápidas

Principal benefício.

### Melhor experiência do usuário

Menor tempo de resposta.

### Redução de carga

Menos processamento durante consultas.

## Desvantagens

### Consumo de espaço

Os índices ocupam armazenamento adicional.

### Impacto em escrita

Operações como:

```txt id="g9m2xt"
INSERT

UPDATE

DELETE
```

podem ficar mais lentas.

Isso acontece porque os índices também precisam ser atualizados.

## Quando utilizar?

Índices costumam ser indicados para colunas:

* frequentemente consultadas;
* utilizadas em filtros;
* utilizadas em ordenação;
* utilizadas em joins.

## Quando evitar?

Nem toda coluna precisa de índice.

Exemplo:

```txt id="p7v8dn"
Tabela pequena

Coluna raramente utilizada
```

Nesses casos o ganho pode ser insignificante.

## Como saber se um índice está sendo utilizado?

Ferramentas de banco de dados permitem analisar planos de execução.

Exemplo:

```sql id="c4k9xs"
EXPLAIN
SELECT *
FROM users
WHERE email = 'beatriz@email.com';
```

O banco mostra como executará a consulta.

## Relação com Query

Fluxo:

```txt id="m7h2yb"
Query
↓
Índice
↓
Melhor performance
```

Por isso índices são um dos principais mecanismos de otimização de consultas.

## Resumo

Index (Índice) é uma estrutura utilizada pelos bancos de dados para acelerar consultas.

Ele funciona como um catálogo que permite localizar registros rapidamente, reduzindo o tempo de busca e melhorando a performance de aplicações que trabalham com grandes volumes de dados.
