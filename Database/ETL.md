# ETL

ETL é um processo utilizado para coletar, transformar e carregar dados entre diferentes sistemas.

A sigla significa:

```txt
E → Extract
T → Transform
L → Load
```

Em português:

```txt
Extrair
Transformar
Carregar
```

O objetivo do ETL é preparar dados para análise, relatórios, dashboards e sistemas de Business Intelligence (BI).

## Por que utilizar ETL?

Imagine que uma empresa possua informações espalhadas em vários sistemas:

* banco de dados da aplicação;
* planilhas Excel;
* APIs externas;
* arquivos CSV;
* sistemas legados.

Cada fonte possui formatos diferentes.

O ETL permite consolidar essas informações em um único local.

## Como funciona?

O processo ocorre em três etapas.

```txt
Extract
↓
Transform
↓
Load
```

## Extract (Extração)

Nesta etapa os dados são coletados da origem.

Exemplos de fontes:

* PostgreSQL;
* MySQL;
* MongoDB;
* APIs;
* arquivos CSV;
* planilhas.

Exemplo:

```txt
Sistema de vendas
↓
Extrair pedidos
```

O objetivo é apenas obter os dados.

Nenhuma transformação ocorre neste momento.

## Transform (Transformação)

Nesta etapa os dados são tratados.

Exemplos:

* remover registros inválidos;
* corrigir formatos;
* padronizar informações;
* calcular métricas;
* combinar dados de diferentes fontes.

Exemplo:

Dados recebidos:

```txt
Nome: joão
Nome: JOÃO
Nome: João
```

Após transformação:

```txt
Nome: João
```

Outro exemplo:

```txt
Data: 2025-01-01
Data: 01/01/2025
```

Após padronização:

```txt
2025-01-01
```

## Load (Carga)

Após a transformação, os dados são carregados para o destino.

Exemplos:

* Data Warehouse;
* BigQuery;
* PostgreSQL;
* sistemas analíticos;
* ferramentas de BI.

Fluxo:

```txt
Dados tratados
↓
BigQuery
```

ou

```txt
Dados tratados
↓
Data Warehouse
```

## Exemplo completo

Imagine uma empresa de e-commerce.

```txt
Banco de Pedidos
+
Banco de Clientes
+
Planilhas Financeiras
```

Processo:

```txt
Extract
↓
Coletar dados

Transform
↓
Limpar e padronizar

Load
↓
BigQuery
```

Depois disso, dashboards e relatórios podem ser gerados.

## ETL e BigQuery

Uma das utilizações mais comuns do ETL é alimentar ambientes analíticos como o BigQuery.

Fluxo:

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

* PostgreSQL armazena os dados operacionais;
* ETL prepara os dados;
* BigQuery realiza análises em larga escala.

## Benefícios

* Centralização de dados;
* Melhoria da qualidade das informações;
* Padronização;
* Facilidade para análises;
* Integração entre sistemas.

## Desafios

* Processamento de grandes volumes;
* Complexidade das transformações;
* Custos de processamento;
* Monitoramento dos fluxos.

## Ferramentas comuns

* Apache Airflow;
* Talend;
* Pentaho;
* Informatica;
* Google Dataflow;
* AWS Glue.

## ETL e Automação

Processos ETL normalmente são automatizados.

Exemplo:

```txt
Scheduler
↓
Job ETL
↓
Extract
↓
Transform
↓
Load
↓
Logs
↓
Resultado
```

Nesse cenário, conceitos como Scheduler, Job, Logs e Retry podem ser utilizados para garantir a execução do processo.

## ETL x ELT

Embora parecidos, existem diferenças.

### ETL

```txt
Extrair
↓
Transformar
↓
Carregar
```

A transformação ocorre antes da carga.

### ELT

```txt
Extrair
↓
Carregar
↓
Transformar
```

A transformação ocorre após os dados serem carregados no destino.

Ferramentas modernas como BigQuery costumam utilizar bastante ELT.

## Resumo

ETL é um processo utilizado para extrair dados de diferentes fontes, transformá-los e carregá-los em um sistema de destino.

Ele é amplamente utilizado em ambientes de Business Intelligence, Analytics e Data Warehouses para garantir que os dados estejam organizados, padronizados e prontos para análise.
