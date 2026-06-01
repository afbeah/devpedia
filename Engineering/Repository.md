# Repository

O termo **Repository** pode possuir significados diferentes dependendo do contexto.

Por exemplo:

* Um repositório Git no GitHub;
* Um padrão arquitetural utilizado em aplicações;
* Um local centralizado para armazenamento de informações.

Neste artigo, o foco será no **Repository Pattern**, um padrão amplamente utilizado para abstrair o acesso aos dados de uma aplicação.

## O que é um Repository?

Um Repository é uma camada responsável por intermediar a comunicação entre a aplicação e a fonte de dados.

Seu objetivo é encapsular operações de persistência, permitindo que as regras de negócio não precisem conhecer detalhes do banco de dados.

Em vez de acessar o banco diretamente:

```java
Connection connection = ...
```

a aplicação utiliza um Repository:

```java
userRepository.findById(id);
```

## Problema sem Repository

Imagine uma aplicação onde consultas ao banco estão espalhadas por diversos serviços.

```java
public class UserService {

    public User findUser(Long id) {
        // consulta SQL aqui
    }
}
```

```java
public class OrderService {

    public User findUser(Long id) {
        // mesma consulta SQL aqui
    }
}
```

Nesse cenário:

* existe duplicação de código;
* manutenção se torna mais difícil;
* testes ficam mais complexos.

## Utilizando Repository

```java
public interface UserRepository {

    User findById(Long id);

    void save(User user);
}
```

Implementação:

```java
public class MySqlUserRepository
        implements UserRepository {

    @Override
    public User findById(Long id) {
        // consulta ao banco
    }

    @Override
    public void save(User user) {
        // persistência
    }
}
```

Uso:

```java
public class UserService {

    private UserRepository repository;

    public UserService(UserRepository repository) {
        this.repository = repository;
    }
}
```

Agora a regra de negócio não conhece detalhes da persistência.

## Benefícios

* Separação de responsabilidades;
* Menor acoplamento;
* Código mais organizado;
* Facilidade para testes;
* Facilidade para trocar tecnologias de banco de dados.

## Repository e SOLID

O padrão Repository está fortemente relacionado ao princípio DIP (Dependency Inversion Principle).

Em vez de depender de uma implementação específica:

```java
MySqlUserRepository
```

a aplicação depende de uma abstração:

```java
UserRepository
```

Isso reduz o acoplamento e facilita a evolução do sistema.

## Repository no Spring Boot

O Spring possui suporte nativo ao padrão Repository.

Exemplo:

```java
@Repository
public interface UserRepository
        extends JpaRepository<User, Long> {
}
```

Nesse caso, o framework cria automaticamente diversas operações de persistência.

## Repository em Go

Em Go, o padrão Repository normalmente é implementado através de interfaces.

Primeiro é definido um contrato:

```go
type UserRepository interface {
    FindByID(id int) (*User, error)
    Save(user *User) error
}
```

Depois uma implementação concreta:

```go
type PostgresUserRepository struct {
    db *sql.DB
}
```

```go
func (r *PostgresUserRepository) FindByID(id int) (*User, error) {
    // consulta ao banco
}
```

```go
func (r *PostgresUserRepository) Save(user *User) error {
    // persistência
}
```

A regra de negócio depende apenas da interface:

```go
type UserService struct {
    repository UserRepository
}
```

Dessa forma é possível trocar PostgreSQL, MongoDB ou qualquer outra tecnologia sem alterar as regras de negócio.

## Estrutura comum em Go

Uma organização frequentemente encontrada em projetos Go:

```text
internal/
├── handlers
├── services
├── repositories
├── models
└── database
```

Ou:

```text
internal/
├── user
│   ├── handler.go
│   ├── service.go
│   ├── repository.go
│   └── model.go
```

O arquivo `repository.go` normalmente concentra as operações de acesso aos dados.

## Repository x Repositório Git

É importante não confundir os conceitos.

### Repositório Git

Local onde o código-fonte é armazenado e versionado.

Exemplos:

* GitHub;
* GitLab;
* Bitbucket.

### Repository Pattern

Padrão arquitetural responsável por abstrair o acesso aos dados da aplicação.

Apesar do mesmo nome, os conceitos possuem finalidades diferentes.

## Resumo

Repository é um padrão de arquitetura utilizado para centralizar e abstrair operações de acesso a dados.

Ele ajuda a reduzir acoplamento, melhorar a organização do código e facilitar a manutenção da aplicação.

Em linguagens como Java e Go, o padrão é amplamente utilizado para separar regras de negócio da camada de persistência, tornando o sistema mais flexível e fácil de evoluir.
