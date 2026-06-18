# Data Lake

Data Lake é um repositório centralizado utilizado para armazenar grandes volumes de dados em seu formato original.

Diferente de um Data Warehouse, os dados não precisam estar previamente estruturados ou transformados.

Seu objetivo é armazenar dados de diversas fontes para uso futuro.

## O que é um Data Lake?

Imagine uma empresa que recebe dados de:

* sistemas internos;
* APIs;
* arquivos CSV;
* imagens;
* vídeos;
* logs;
* sensores IoT.

Um Data Lake permite armazenar tudo isso em um único local.

```txt id="xq8m3w"
APIs
↓
CSV
↓
Logs
↓
Vídeos
↓
Data Lake
```

## Por que utilizar?

Nem sempre sabemos como os dados serão utilizados no futuro.

Em vez de transformar tudo imediatamente, os dados podem ser armazenados primeiro.

Exemplo:

```txt id="4bnz8f"
Coletar agora
↓
Analisar depois
```

Esse é um dos princípios do Data Lake.

## Características

### Armazenamento de dados brutos

Os dados são armazenados em seu formato original.

Exemplo:

```txt id="zw1f2q"
JSON

CSV

XML

Imagem

Vídeo
```

### Grande volume de dados

Projetado para armazenar:

```txt id="nsw5k6"
Terabytes

Petabytes
```

de informações.

### Flexibilidade

Permite armazenar dados estruturados e não estruturados.

## Dados Estruturados

Exemplo:

```txt id="ph8v4x"
Tabela de clientes

Tabela de pedidos
```

## Dados Semi-Estruturados

Exemplo:

```txt id="b8t9zc"
JSON

XML
```

## Dados Não Estruturados

Exemplo:

```txt id="e7h2mq"
Imagens

Vídeos

Áudios

Documentos
```

## Exemplo prático

Uma plataforma de streaming pode armazenar:

```txt id="r2z5jd"
Logs de acesso

Vídeos

Informações dos usuários

Eventos da aplicação
```

Tudo dentro de um Data Lake.

## Data Lake x Data Warehouse

### Data Lake

```txt id="t9m2hp"
Dados brutos

Diversos formatos

Alta flexibilidade
```

### Data Warehouse

```txt id="7v4xnb"
Dados estruturados

Prontos para análise

Foco em BI
```

## Comparação

| Data Lake                       | Data Warehouse              |
| ------------------------------- | --------------------------- |
| Dados brutos                    | Dados processados           |
| Estruturados e não estruturados | Principalmente estruturados |
| Alta flexibilidade              | Alta organização            |
| Armazenamento                   | Análise                     |

## Relação com ETL e ELT

Fluxo tradicional:

```txt id="q1m4ec"
Dados
↓
ETL
↓
Data Warehouse
```

Fluxo moderno:

```txt id="v6h8rt"
Dados
↓
Data Lake
↓
ELT
↓
Data Warehouse
```

## Data Lake e BigQuery

Uma arquitetura comum é:

```txt id="f5k7na"
Data Lake
↓
BigQuery
↓
Dashboard
```

O Data Lake armazena os dados.

O BigQuery realiza análises.

## Ferramentas comuns

Exemplos:

* Google Cloud Storage;
* Amazon S3;
* Azure Data Lake Storage;
* Hadoop HDFS.

## Benefícios

### Escalabilidade

Permite armazenar grandes volumes de dados.

### Flexibilidade

Aceita diversos formatos.

### Baixo custo

Armazenamento geralmente mais barato que plataformas analíticas.

### Preservação dos dados

Mantém os dados originais para futuras análises.

## Desafios

### Governança

Controlar quem acessa os dados.

### Qualidade

Dados brutos podem conter inconsistências.

### Organização

Sem processos adequados, o Data Lake pode se transformar em um:

```txt id="u9y4hz"
Data Swamp
```

ou seja, um repositório desorganizado e difícil de utilizar.

## Data Swamp

É um Data Lake mal gerenciado.

Características:

* dados duplicados;
* falta de documentação;
* ausência de catalogação;
* dificuldade para encontrar informações.

## Relação com outros conceitos

Fluxo comum:

```txt id="k8n3xb"
OLTP
↓
ETL / ELT
↓
Data Lake
↓
Data Warehouse
↓
OLAP
↓
Dashboard
```

## Resumo

Data Lake é um repositório centralizado capaz de armazenar grandes volumes de dados em seu formato original.

Ele permite armazenar dados estruturados, semi-estruturados e não estruturados, servindo como base para análises, processamento e iniciativas de Business Intelligence e Big Data.
