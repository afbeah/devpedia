# Lock

Lock é um mecanismo utilizado pelos bancos de dados para controlar o acesso simultâneo aos dados.

Seu objetivo é evitar inconsistências quando múltiplas operações tentam modificar os mesmos registros ao mesmo tempo.

## O problema

Imagine duas pessoas tentando alterar o mesmo saldo bancário.

```txt
Usuário A
↓
Atualiza saldo

Usuário B
↓
Atualiza saldo
```

Sem controle, os dados podem ficar incorretos.

## Como funciona?

Quando uma transação acessa um registro:

```txt
Registro
↓
Lock
↓
Alteração protegida
```

Outras transações precisam aguardar.

## Tipos comuns

### Shared Lock

Permite leitura simultânea.

```txt
Leitura
+
Leitura
```

### Exclusive Lock

Permite apenas uma operação de escrita.

```txt
Escrita
↓
Bloqueio exclusivo
```

## Benefícios

* Consistência;
* Integridade dos dados;
* Segurança em ambientes concorrentes.

## Desafios

* Espera entre transações;
* Redução de performance em cenários extremos.

## Relação com Transaction

Fluxo comum:

```txt
Transaction
↓
Lock
↓
Commit
```

## Resumo

Lock é um mecanismo de bloqueio utilizado pelos bancos de dados para garantir consistência e integridade durante operações concorrentes.
