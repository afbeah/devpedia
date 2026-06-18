# Deadlock

Deadlock é uma situação onde duas ou mais transações ficam bloqueadas esperando recursos que estão sendo utilizados umas pelas outras.

Como consequência, nenhuma delas consegue continuar.

## Exemplo

Imagine duas transações.

### Transação A

```txt
Bloqueia Conta A
↓
Tenta acessar Conta B
```

### Transação B

```txt
Bloqueia Conta B
↓
Tenta acessar Conta A
```

Resultado:

```txt
A espera B

B espera A
```

Nenhuma consegue prosseguir.

## Fluxo

```txt
Transação A
↓
Lock Recurso 1

Transação B
↓
Lock Recurso 2

A espera Recurso 2

B espera Recurso 1
```

Deadlock.

## Como os bancos resolvem?

A maioria dos bancos detecta automaticamente o problema.

Exemplo:

```txt
Deadlock detectado
↓
Uma transação é cancelada
↓
Rollback
```

A outra continua normalmente.

## Como evitar?

### Ordem consistente

Sempre acessar recursos na mesma ordem.

### Transações curtas

Manter transações rápidas.

### Reduzir bloqueios

Evitar manter locks por longos períodos.

## Relação com Lock

Fluxo:

```txt
Lock
↓
Concorrência
↓
Deadlock
```

Deadlock é uma consequência possível do uso de locks.

## Resumo

Deadlock é uma situação de bloqueio mútuo entre transações, onde nenhuma consegue continuar sua execução. Os bancos de dados normalmente detectam e resolvem esse problema automaticamente através de rollback de uma das transações.
