# MVC

MVC (Model-View-Controller) é um padrão arquitetural utilizado para organizar aplicações através da separação de responsabilidades.

A sigla significa:

```txt id="p3z3u9"
M → Model
V → View
C → Controller
```

Seu principal objetivo é tornar o sistema mais organizado, facilitando manutenção, testes e evolução da aplicação.

## Por que utilizar MVC?

Imagine uma aplicação onde todo o código está em um único arquivo:

* regras de negócio;
* acesso ao banco;
* interface;
* validações.

Com o crescimento do sistema, a manutenção se torna difícil.

O MVC resolve esse problema separando responsabilidades.

## Como funciona?

O MVC divide a aplicação em três componentes.

```txt id="mk76sv"
Usuário
↓
Controller
↓
Model
↓
Banco de Dados
```

E depois:

```txt id="pohs8t"
Model
↓
Controller
↓
View
↓
Usuário
```

## Model

O Model representa os dados e as regras de negócio da aplicação.

Exemplos:

* Usuário;
* Pedido;
* Produto;
* Pagamento.

Também costuma ser responsável pela comunicação com a camada de persistência.

Exemplo:

```java id="hywxii"
User
Product
Order
```

O Model representa o domínio do sistema.

## View

A View é responsável pela apresentação das informações.

Seu objetivo é exibir dados para o usuário.

Exemplos:

* páginas HTML;
* telas;
* formulários;
* componentes visuais.

A View não deve conter regras de negócio complexas.

Exemplo:

```txt id="a5yktl"
Tela de Login

Tela de Produtos

Dashboard
```

## Controller

O Controller recebe as requisições e coordena o fluxo da aplicação.

Exemplo:

```txt id="zvcv9w"
Usuário
↓
Controller
↓
Model
↓
View
```

Responsabilidades comuns:

* receber requisições;
* validar entradas;
* chamar serviços;
* retornar respostas.

Exemplo:

```java id="2g0l7v"
@GetMapping("/users")
public List<User> findUsers() {

    return userService.findAll();

}
```

## Fluxo completo

Imagine uma consulta de usuários.

```txt id="twg9g5"
Usuário
↓
Controller
↓
Model
↓
Banco de Dados
↓
Model
↓
Controller
↓
View
↓
Usuário
```

Cada camada possui uma responsabilidade específica.

## Exemplo prático

Sistema de e-commerce.

### Model

```txt id="r8z6fm"
Produto
Pedido
Cliente
```

### Controller

```txt id="wyx0u0"
ProductController

OrderController
```

### View

```txt id="tzkzj4"
Página de Produtos

Carrinho de Compras
```

## Benefícios

* Separação de responsabilidades;
* Código mais organizado;
* Facilidade de manutenção;
* Melhor reutilização;
* Facilidade para testes.

## Desafios

* Aumento da quantidade de arquivos;
* Estrutura inicial mais complexa;
* Possibilidade de Controllers muito grandes.

## MVC e Arquitetura de Software

MVC é um padrão arquitetural.

Enquanto Arquitetura de Software define a organização geral do sistema, o MVC fornece uma forma específica de organizar componentes da aplicação.

Fluxo:

```txt id="y5f3bi"
Arquitetura
↓
MVC
↓
Organização do código
```

## MVC e Modelagem

A modelagem ajuda a definir entidades do sistema.

Exemplo:

```txt id="5u8k8u"
Cliente
Produto
Pedido
```

Essas entidades normalmente se tornam Models dentro do MVC.

## MVC e Repository

Em aplicações modernas, o acesso ao banco normalmente é delegado para Repositories.

Exemplo:

```txt id="qnqh22"
Controller
↓
Service
↓
Repository
↓
Banco de Dados
```

Por isso muitos projetos atuais utilizam uma adaptação do MVC tradicional.

## MVC moderno

Em aplicações atuais é comum encontrar uma estrutura como:

```txt id="47m96f"
Controller
↓
Service
↓
Repository
↓
Banco
```

Nesse modelo:

* Controller recebe requisições;
* Service contém regras de negócio;
* Repository acessa dados.

Essa abordagem reduz responsabilidades do Controller.

## Quando utilizar?

MVC é amplamente utilizado em:

* aplicações web;
* APIs;
* sistemas corporativos;
* aplicações desktop.

## Resumo

MVC (Model-View-Controller) é um padrão arquitetural que organiza aplicações através da separação entre dados, apresentação e controle.

Seu principal objetivo é tornar o sistema mais organizado, manutenível e escalável, distribuindo responsabilidades entre Model, View e Controller.
