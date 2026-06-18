# Trigger

Trigger é um mecanismo que executa automaticamente uma ação quando determinado evento ocorre em uma tabela.

Em outras palavras:

> É uma automação executada pelo próprio banco de dados.

## Eventos comuns

* INSERT
* UPDATE
* DELETE

## Exemplo

Sempre que um usuário for criado:

```txt
INSERT
↓
Trigger dispara
↓
Registrar log
```

## Exemplo SQL

```sql
CREATE TRIGGER log_user_creation
AFTER INSERT ON users
FOR EACH ROW
BEGIN
    INSERT INTO logs(message)
    VALUES('Usuário criado');
END;
```

## Casos de uso

* Auditoria;
* Histórico de alterações;
* Validação de dados;
* Atualização automática de tabelas.

## Benefícios

* Automação;
* Integridade dos dados;
* Centralização de regras.

## Desafios

* Difícil rastreamento;
* Impacto na performance;
* Pode aumentar a complexidade do banco.

## Resumo

Trigger é uma rotina automática executada pelo banco de dados em resposta a eventos como INSERT, UPDATE ou DELETE.
