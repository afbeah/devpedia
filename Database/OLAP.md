# OLAP

OLAP (Online Analytical Processing) é um modelo de processamento de dados focado em análises, relatórios e tomada de decisão.

Seu objetivo é permitir consultas complexas sobre grandes volumes de dados históricos.

## O que significa OLAP?

A sigla significa:

```txt
Online Analytical Processing
```

Em português:

```txt
Processamento Analítico Online
```

Diferente do OLTP, que é focado em operações do dia a dia, o OLAP é voltado para análise de dados.

## Por que utilizar OLAP?

Imagine uma empresa que deseja responder perguntas como:

* Qual região vendeu mais nos últimos 5 anos?
* Qual produto gerou mais receita?
* Qual foi o crescimento das vendas por trimestre?
* Quais clientes mais compram?

Responder essas perguntas pode exigir milhões ou bilhões de registros.

Esse é o cenário ideal para OLAP.

## Características

### Grandes volumes de dados

Sistemas OLAP são projetados para trabalhar com:

```txt
Milhões
Bilhões
Trilhões
```

de registros.

### Consultas complexas

Exemplo:

```sql
SELECT
    region,
    SUM(total_sales)
FROM sales
GROUP BY region;
```

Essas consultas podem processar enormes quantidades de dados.

### Dados históricos

OLAP normalmente utiliza dados acumulados ao longo do tempo.

Exemplo:

```txt
5 anos de vendas

10 anos de acessos

Histórico financeiro
```

### Foco em análise

O objetivo principal não é alterar dados, mas extrair informações.

## Exemplo prático

Imagine uma rede de lojas.

Pergunta:

```txt
Qual produto vendeu mais no último ano?
```

Fluxo:

```txt
Data Warehouse
↓
Consulta OLAP
↓
Relatório
```

## Ferramentas OLAP

Exemplos:

* BigQuery;
* Snowflake;
* Amazon Redshift;
* Azure Synapse.

Essas plataformas são otimizadas para análise de dados.

## OLAP e Data Warehouse

OLAP costuma trabalhar sobre Data Warehouses.

Fluxo:

```txt
Sistemas Operacionais
↓
ETL / ELT
↓
Data Warehouse
↓
OLAP
↓
Dashboard
```

## OLAP e BigQuery

BigQuery é um exemplo clássico de plataforma OLAP.

Exemplo:

```txt
PostgreSQL
↓
ETL
↓
BigQuery
↓
Dashboard
```

Nesse cenário:

* PostgreSQL suporta operações transacionais;
* BigQuery suporta análises massivas.

## Benefícios

### Análises rápidas

Consultas complexas executadas em segundos.

### Apoio à tomada de decisão

Permite gerar indicadores de negócio.

### Escalabilidade

Projetado para grandes volumes de dados.

### Integração com BI

Ferramentas como:

* Power BI;
* Tableau;
* Looker;

consomem dados OLAP.

## Limitações

### Não é ideal para transações

Exemplo:

```txt
Cadastrar usuário

Atualizar estoque

Processar pagamento
```

Essas operações pertencem ao mundo OLTP.

### Custos

Consultas analíticas podem consumir muitos recursos.

## OLTP x OLAP

### OLTP

Foco:

```txt
Operações do dia a dia
```

Exemplos:

```txt
Criar pedido

Cadastrar usuário

Atualizar estoque
```

Bancos comuns:

* PostgreSQL;
* MySQL;
* MongoDB.

### OLAP

Foco:

```txt
Análise de dados
```

Exemplos:

```txt
Relatórios

Dashboards

Business Intelligence
```

Ferramentas comuns:

* BigQuery;
* Snowflake;
* Redshift.

## Comparação

| OLTP            | OLAP                |
| --------------- | ------------------- |
| Transações      | Análises            |
| Dados atuais    | Dados históricos    |
| Muitas escritas | Muitas leituras     |
| Resposta rápida | Consultas complexas |
| PostgreSQL      | BigQuery            |

## Relação com outros conceitos

Fluxo comum:

```txt
OLTP
↓
ETL / ELT
↓
Data Warehouse
↓
OLAP
↓
Dashboard
```

Esse é um dos fluxos mais comuns em ambientes de Business Intelligence.

## Resumo

OLAP (Online Analytical Processing) é um modelo de processamento voltado para análises e relatórios sobre grandes volumes de dados.

Seu foco é transformar dados históricos em informações úteis para apoiar decisões de negócio, sendo amplamente utilizado em Data Warehouses, Business Intelligence e plataformas como BigQuery.
