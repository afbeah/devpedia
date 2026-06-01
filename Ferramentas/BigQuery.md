# BigQuery

*BigQuery* é um serviço de Data Warehouse da **Google Cloud**.

Ele foi criado para análise de grandes volumes de dados.

## Banco tradicional

Imagine uma tabela:

```txt
100 mil registros
```

Um banco como:

- PostgreSQL
- MySQL
- MongoDB

consegue trabalhar tranquilamente.

## Quando o banco tradicional não é suficiente

Agora imagine:

```txt
5 bilhões de registros
```

ou

```txt
10 TB de dados
```

Aí entram ferramentas de Data Analytics como o BigQuery.

## Exemplo de uso real

Uma empresa pode armazenar:

- acessos ao site;
- logs;
- eventos de aplicações;
- métricas;
- vendas;
- comportamento dos usuários.

Tudo isso gera bilhões de registros.

### Exemplo:

```sql
SELECT
    country,
    COUNT(*)
FROM page_views
GROUP BY country;
```

No BigQuery essa consulta pode processar terabytes em segundos.

### Quando usar Banco Tradicional?

Para aplicações:

- APIs REST;
- E-commerce;
- Sistemas internos;
- Aplicativos.

### Exemplos:

- PostgreSQL
- MySQL
- MongoDB

### Quando usar BigQuery?

Para:

- Business Intelligence (BI)
- Data Analytics
- Dashboards
- Machine Learning
- Relatórios corporativos
- Data Warehouses

## Uma analogia simples

### PostgreSQL

É como uma biblioteca.

Você entra e pega um livro específico.

### BigQuery

É como analisar todas as bibliotecas de um país ao mesmo tempo para descobrir:

- quais livros são mais lidos;
- quais autores vendem mais;
- quais regiões leem mais determinados assuntos.

Ele não foi feito para operações transacionais do dia a dia, mas para análises massivas.

## Vantagens

- Alta escalabilidade
- Não exige gerenciamento de servidores
- Integração nativa com a Google Cloud
- Processamento de grandes volumes de dados
- Ideal para análises e relatórios
