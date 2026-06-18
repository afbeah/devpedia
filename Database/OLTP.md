# OLTP

OLTP (Online Transaction Processing) é um modelo de processamento de dados focado em operações transacionais do dia a dia.

Seu objetivo é permitir que aplicações realizem inserções, atualizações, consultas e remoções de dados de forma rápida e consistente.

## O que significa OLTP?

A sigla significa:

```txt
Online Transaction Processing
```

Em português:

```txt
Processamento de Transações Online
```

O termo "transação" refere-se às operações executadas pelos usuários em sistemas operacionais.

## Exemplos de transações

Imagine um e-commerce.

Ações como:

* criar pedido;
* cadastrar usuário;
* atualizar estoque;
* processar pagamento;
* alterar endereço.

são consideradas transações.

Exemplo:

```txt
Cliente
↓
Realiza pedido
↓
Banco registra pedido
```

## Características

### Grande volume de operações

Um sistema OLTP executa milhares ou milhões de transações diariamente.

### Resposta rápida

As operações precisam ser concluídas rapidamente.

Exemplo:

```txt
Consultar usuário
↓
Milissegundos
```

### Dados atuais

Normalmente trabalha com dados recentes e operacionais.

### Integridade

Os dados devem permanecer consistentes.

## Bancos OLTP

Exemplos comuns:

* PostgreSQL;
* MySQL;
* SQL Server;
* Oracle;
* MongoDB.

Esses bancos são utilizados em aplicações do dia a dia.

## Exemplo prático

Sistema bancário:

```txt
Transferência
↓
Atualiza saldo
↓
Registra movimentação
```

O processamento precisa ser rápido e consistente.

## ACID

OLTP normalmente utiliza os princípios ACID.

### Atomicidade

Tudo acontece ou nada acontece.

### Consistência

Os dados permanecem válidos.

### Isolamento

Transações não interferem umas nas outras.

### Durabilidade

Após confirmação, os dados são preservados.

## OLTP e Arquitetura

Fluxo comum:

```txt
Frontend
↓
API
↓
Banco OLTP
```

O banco suporta as operações da aplicação.

## Benefícios

* Alta velocidade;
* Consistência;
* Confiabilidade;
* Suporte a operações transacionais.

## Limitações

Não foi projetado para análises massivas.

Exemplo:

```txt
10 anos de vendas
+
Bilhões de registros
```

Esse tipo de consulta costuma ser melhor atendido por sistemas analíticos.

## OLTP x OLAP

OLTP:

```txt
Operações do dia a dia
```

OLAP:

```txt
Análises e relatórios
```

## Exemplos reais

Aplicações como:

* Internet Banking;
* E-commerce;
* Sistemas ERP;
* Aplicativos Mobile;

normalmente utilizam bancos OLTP.

## Resumo

OLTP (Online Transaction Processing) é um modelo de processamento voltado para operações transacionais do dia a dia.

Seu foco é fornecer rapidez, consistência e confiabilidade para aplicações que realizam inserções, consultas, atualizações e remoções de dados continuamente.
