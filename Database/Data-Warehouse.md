# Data Warehouse

Data Warehouse é um repositório centralizado utilizado para armazenar dados históricos de diferentes fontes com foco em análise e geração de relatórios.

Seu objetivo não é operar aplicações do dia a dia, mas permitir consultas analíticas sobre grandes volumes de dados.

## O que é um Data Warehouse?

Imagine uma empresa que possui informações espalhadas em vários sistemas:

* vendas;
* financeiro;
* estoque;
* marketing;
* atendimento.

Cada sistema possui seu próprio banco de dados.

O Data Warehouse centraliza essas informações para análise.

```txt
Sistema de Vendas
       ↓
Sistema Financeiro
       ↓
Sistema de Estoque
       ↓
Data Warehouse
```

## Por que utilizar?

Sistemas operacionais normalmente são otimizados para transações.

Exemplos:

* criar pedidos;
* atualizar usuários;
* processar pagamentos.

Já o Data Warehouse é otimizado para análises.

Exemplos:

* relatórios corporativos;
* dashboards;
* indicadores de negócio;
* Business Intelligence.

## Como os dados chegam ao Data Warehouse?

Normalmente através de processos ETL ou ELT.

```txt
Fontes de Dados
↓
ETL / ELT
↓
Data Warehouse
```

## Exemplo prático

Imagine um e-commerce.

Pergunta:

```txt
Qual região gerou mais vendas nos últimos 5 anos?
```

Essa consulta pode exigir milhões de registros.

O Data Warehouse foi projetado para responder esse tipo de pergunta de forma eficiente.

## Banco Operacional x Data Warehouse

| Banco Operacional       | Data Warehouse     |
| ----------------------- | ------------------ |
| Transações              | Análises           |
| Atualizações frequentes | Consultas massivas |
| Dados atuais            | Dados históricos   |
| OLTP                    | OLAP               |

## Exemplos de Data Warehouse

* BigQuery;
* Snowflake;
* Amazon Redshift;
* Azure Synapse.

## Data Warehouse e BigQuery

BigQuery é uma plataforma que pode ser utilizada como Data Warehouse.

Fluxo:

```txt
Aplicações
↓
ETL / ELT
↓
BigQuery
↓
Análises
↓
Dashboards
```

## Benefícios

* Centralização dos dados;
* Melhor desempenho para análises;
* Histórico consolidado;
* Apoio à tomada de decisão;
* Integração entre sistemas.

## Desafios

* Custos de armazenamento;
* Governança dos dados;
* Complexidade de integração;
* Controle da qualidade das informações.

## Data Warehouse e Business Intelligence

Ferramentas de BI normalmente consomem dados de um Data Warehouse.

Exemplos:

* Power BI;
* Looker;
* Tableau.

Fluxo:

```txt
Data Warehouse
↓
Dashboard
↓
Tomada de decisão
```

## Relação com outros conceitos

Fluxo comum:

```txt
Query
↓
ETL / ELT
↓
Data Warehouse
↓
BigQuery
↓
Dashboard
```

## Resumo

Data Warehouse é um repositório centralizado de dados voltado para análises e relatórios.

Ele consolida informações de diferentes sistemas e permite consultas analíticas eficientes sobre grandes volumes de dados, sendo um dos principais componentes de soluções de Business Intelligence.
