# Stored Procedure

Stored Procedure é um conjunto de instruções SQL armazenadas dentro do banco de dados que podem ser executadas sempre que necessário.

Ela funciona de forma semelhante a uma função ou método em uma linguagem de programação.

## Por que utilizar?

Imagine uma operação executada frequentemente:

* cadastrar pedido;
* atualizar estoque;
* registrar pagamento.

Em vez de repetir várias consultas SQL, podemos centralizar a lógica em uma Stored Procedure.

## Exemplo

```sql
CREATE PROCEDURE GetUserById
    @UserId INT
AS
BEGIN
    SELECT *
    FROM Users
    WHERE Id = @UserId;
END
```

Execução:

```sql
EXEC GetUserById 1;
```

## Benefícios

* Reutilização de código;
* Centralização de regras;
* Redução de duplicidade;
* Melhor manutenção.

## Desafios

* Acoplamento ao banco;
* Maior complexidade para versionamento;
* Dependência da tecnologia utilizada.

## Onde é comum?

* Oracle (PL/SQL);
* SQL Server;
* PostgreSQL;
* MySQL.

## Resumo

Stored Procedure é um conjunto de instruções SQL armazenado no banco de dados que pode ser reutilizado para executar operações de forma centralizada e padronizada.
