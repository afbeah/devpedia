# Clean Code

*Clean Code* (Código Limpo) é um conjunto de práticas que tornam o código:

- fácil de ler;
- fácil de entender;
- fácil de manter;
- fácil de evoluir.

A ideia principal é:

> Código é lido muito mais vezes do que é escrito.

Por isso um código deve ser escrito pensando em quem vai lê-lo depois.

Inclusive, esse leitor pode ser você mesma daqui a seis meses.

### A definição mais famosa

Do livro Clean Code, escrito por Robert C. Martin:

*"Clean code always looks like it was written by someone who cares."*

("Código limpo sempre parece ter sido escrito por alguém que se importa.")

### O maior objetivo do Clean Code

Imagine duas situações.

Código difícil de entender

```java
public int c(List<User> l) {

    int x = 0;

    for(User u : l) {

        if(u.getA()) {
            x++;
        }
    }

    return x;
}
```

Funciona.

Mas:

- O que é c?
- O que é l?
- O que é x?
- O que significa getA()?

Código limpo

```java
public int countActiveUsers(List<User> users) {

    int activeUsers = 0;

    for(User user : users) {

        if(user.isActive()) {
            activeUsers++;
        }
    }

    return activeUsers;
}
```

Mesmo comportamento.

Muito mais legível.

## Princípios

### Nomes Importam

Uma das maiores ideias do Clean Code.

|       Ruim       |          Melhor          |
|       :---:      |           :---:          |
|      String d;   |     String birthDate;    |
| List<User> list; |  List<User> activeUsers; |

## Funções Pequenas

Funções devem fazer apenas uma coisa.

Ruim

```java
public void createUser() {

    saveUser();

    sendEmail();

    generateReport();

    updateMetrics();

    publishEvent();
}
```

Melhor

```java
public void createUser() {
    saveUser();
    notifyUser();
}
```

E cada responsabilidade fica em sua própria função.

### Uma Função Deve Ter Uma Responsabilidade

Isso conversa diretamente com o SRP do SOLID.

Ruim

```java
public void processOrder() {

    validate();

    calculatePrice();

    saveOrder();

    sendEmail();

    generatePdf();

    updateDashboard();
}
```

Melhor

```java
public void processOrder() {

    validateOrder();

    saveOrder();

    notifyCustomer();
}
```

### Evite Comentários Desnecessários

Isso costuma surpreender iniciantes.

Muita gente acredita que Clean Code significa:

```java
// Soma dois números
return a + b;
```

Mas isso não agrega informação.

Melhor:

```java
calculateTotalPrice();
```

O próprio nome já explica a intenção.

### Comentários Ainda São Úteis

Quando explicam:

- regras de negócio;
- decisões arquiteturais;
- limitações técnicas;
- integrações complexas.

### Evite Código Duplicado

Ruim

```java
calculateUserDiscount();
calculateAdminDiscount();
calculateManagerDiscount();
```

com a mesma lógica copiada.

Melhor

```java
calculateDiscount();
```

e reutilizar.

### Evite Condicionais Gigantes

Ruim

```java
if(type.equals("PIX")) {
    ...
}
else if(type.equals("CREDIT")) {
    ...
}
else if(type.equals("BOLETO")) {
    ...
}
```

Muitas vezes padrões como:

- Strategy
- Polymorphism

podem simplificar.

## Tratamento de Erros

Erro não deve ser ignorado.

Ruim

```java
try {

    saveUser();

} catch(Exception e) {

}
```

Melhor

```java
try {

    saveUser();

} catch(Exception e) {

    logger.error("Erro ao salvar usuário", e);

}
```

### Classes Pequenas

O mesmo princípio das funções.

Ruim
```txt
UserService
1500 linhas
```

Melhor
```txt
UserService
UserValidator
UserRepository
UserNotificationService
```

## Organização Importa

Uma boa estrutura facilita manutenção.

Exemplo:

```txt
src/
├── controller
├── service
├── repository
├── model
└── config
```

## Clean Code NÃO é

Muitas empresas interpretam errado.

Clean Code NÃO significa:

- código perfeito;
- arquitetura complexa;
- seguir regras cegamente;
- criar abstrações para tudo.


## Clean Code + KISS

Aqui existe uma conexão forte.

KISS diz:

> Mantenha simples.

Clean Code diz:

> Mantenha legível.

Normalmente um código simples tende a ser mais limpo.

## Clean Code + SOLID

SOLID ajuda a *estruturar*.

Clean Code ajuda a *escrever*.

## Críticas ao Clean Code

Vale conhecer porque aparece em entrevistas mais avançadas.

Hoje algumas pessoas criticam o uso excessivo das ideias do livro.

Por exemplo:

- excesso de abstrações;
- excesso de classes;
- excesso de separações.

Por isso o ideal é usar os princípios com bom senso.

## Como reconhecer um código limpo?

Faça três perguntas:

1. Eu entendo rapidamente o que esse código faz?

Se não, há um problema.

2. Um novo desenvolvedor entenderia isso?

Se não, pode melhorar.

3. Posso alterar isso sem medo?

Se não, o código provavelmente está complexo demais.

## Resumo

Clean Code é a prática de escrever código simples, legível e fácil de manter.

Seu objetivo não é apenas fazer o software funcionar, mas permitir que ele seja compreendido, testado e evoluído ao longo do tempo por qualquer desenvolvedor que trabalhe no projeto.
