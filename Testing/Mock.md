# Mock

Mock é uma técnica utilizada em testes para simular o comportamento de dependências externas.

Seu objetivo é permitir que uma funcionalidade seja testada de forma isolada, sem depender de bancos de dados, APIs, filas, sistemas externos ou qualquer outra infraestrutura.

## Por que utilizar Mock?

Imagine uma função responsável por buscar um usuário.

```go
func GetUser(id int) (*User, error) {
    return repository.FindByID(id)
}
```

Durante um teste, não é interessante depender de um banco de dados real.

Isso pode tornar os testes:

* lentos;
* complexos;
* difíceis de reproduzir;
* dependentes do ambiente.

Para resolver esse problema, utiliza-se um Mock.

## O que um Mock faz?

Um Mock cria uma implementação falsa de uma dependência.

Em vez de acessar um banco real:

```txt
Teste
↓
Banco de Dados
```

utiliza-se uma versão simulada:

```txt
Teste
↓
Mock
```

Isso permite controlar exatamente o comportamento esperado.

## Exemplo em Go

Interface:

```go
type UserRepository interface {
    FindByID(id int) (*User, error)
}
```

Implementação utilizada em produção:

```go
type PostgresUserRepository struct {}
```

Implementação utilizada em testes:

```go
type MockUserRepository struct {}
```

```go
func (m MockUserRepository) FindByID(id int) (*User, error) {

    return &User{
        Name: "Beatriz",
    }, nil
}
```

O teste passa a utilizar o Mock em vez do banco real.

## Exemplo de teste

```go
func TestGetUser(t *testing.T) {

    repository := MockUserRepository{}

    user, err := repository.FindByID(1)

    if err != nil {
        t.Fail()
    }

    if user.Name != "Beatriz" {
        t.Fail()
    }

}
```

O teste não depende de infraestrutura externa.

## Benefícios

* Testes mais rápidos;
* Maior previsibilidade;
* Isolamento da lógica de negócio;
* Menor dependência de infraestrutura;
* Facilidade para reproduzir cenários.

## Simulando erros

Mocks também podem ser utilizados para simular falhas.

Exemplo:

```go
func (m MockUserRepository) FindByID(id int) (*User, error) {

    return nil, errors.New("database unavailable")
}
```

Dessa forma é possível testar cenários de erro sem derrubar um banco real.

## Mock x Banco Real

### Banco Real

```txt
Teste
↓
Banco
↓
Dados reais
```

Vantagem:

* comportamento real do sistema.

Desvantagem:

* maior complexidade;
* execução mais lenta.

### Mock

```txt
Teste
↓
Mock
↓
Resposta simulada
```

Vantagem:

* rapidez;
* previsibilidade;
* isolamento.

Desvantagem:

* não valida integrações reais.

## Mock e Repository

O padrão Repository é um dos locais onde Mocks são mais utilizados.

Exemplo:

```go
type UserRepository interface {
    FindByID(id int) (*User, error)
}
```

Produção:

```go
PostgresUserRepository
```

Teste:

```go
MockUserRepository
```

A regra de negócio continua utilizando a mesma interface.

## Mock e Testes Unitários

Mocks são amplamente utilizados em testes unitários.

Fluxo:

```txt
Código
↓
Mock
↓
Teste
```

Isso permite validar apenas a lógica da unidade que está sendo testada.

## Mock e Gock

O Gock é uma biblioteca utilizada em Go para criar Mocks de requisições HTTP.

Exemplo:

```txt
Mock
↓
Conceito

Gock
↓
Ferramenta
```

O Gock permite simular respostas de APIs externas durante os testes.

## Quando utilizar?

Mocks são recomendados quando:

* existe dependência de banco de dados;
* existe integração com APIs externas;
* existem filas ou sistemas de mensageria;
* deseja-se criar testes rápidos e previsíveis.

## Quando evitar?

Nem todos os testes devem utilizar Mocks.

Testes de integração costumam utilizar dependências reais para validar o comportamento completo do sistema.

## Resumo

Mock é uma técnica utilizada para simular o comportamento de dependências externas durante testes.

Seu principal objetivo é permitir que a lógica da aplicação seja testada de forma isolada, rápida e previsível, sem depender de infraestrutura real como bancos de dados, APIs ou sistemas externos.
