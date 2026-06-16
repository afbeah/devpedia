# ELT

ELT é um processo utilizado para extrair, carregar e transformar dados.

A sigla significa:

```txt
E → Extract
L → Load
T → Transform
```

Em português:

```txt
Extrair
Carregar
Transformar
```

Assim como o ETL, o objetivo do ELT é preparar dados para análises, relatórios e Business Intelligence (BI).

A principal diferença está na ordem das etapas.

## ETL x ELT

### ETL

```txt
Extract
↓
Transform
↓
Load
```

Os dados são transformados antes de serem carregados.

### ELT

```txt
Extract
↓
Load
↓
Transform
```

Os dados são carregados primeiro e transformados depois.

## Como funciona?

### Extract

Os dados são coletados de diferentes fontes.

Exemplos:

* PostgreSQL;
* MySQL;
* MongoDB;
* APIs;
* arquivos CSV.

### Load

Os dados são enviados diretamente para o destino.

Exemplo:

```txt
PostgreSQL
↓
BigQuery
```

Os dados chegam ao ambiente analítico sem grandes transformações.

### Transform

As transformações ocorrem dentro do próprio ambiente de destino.

Exemplo:

```sql
SELECT
    country,
    COUNT(*)
FROM users
GROUP BY country;
```

Nesse modelo, o BigQuery realiza o processamento.

## Por que o ELT surgiu?

Antigamente era caro armazenar e processar grandes volumes de dados.

Por isso os dados eram transformados antes do carregamento.

Ferramentas modernas como:

* BigQuery;
* Snowflake;
* Databricks;

possuem grande capacidade de processamento.

Isso permitiu mover a etapa de transformação para o destino.

## Exemplo

```txt
Sistema de Vendas
↓
BigQuery
↓
Transformação
↓
Dashboard
```

## Benefícios

* Processamento escalável;
* Menor complexidade inicial;
* Aproveitamento do poder computacional do destino;
* Maior flexibilidade para análises futuras.

## Desafios

* Maior consumo de armazenamento;
* Necessidade de governança dos dados;
* Controle das transformações.

## ELT e BigQuery

BigQuery é uma das plataformas que popularizaram o modelo ELT.

Fluxo comum:

```txt
Banco de Dados
↓
Carga
↓
BigQuery
↓
Transformação
↓
Relatórios
```

## Resumo

ELT é uma estratégia de processamento de dados onde a transformação ocorre após a carga dos dados no ambiente de destino.

Essa abordagem é amplamente utilizada em plataformas modernas de análise de dados como BigQuery, Snowflake e Databricks.
