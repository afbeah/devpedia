## SOLID

*SOLID* é um conjunto de 5 princípios de design de software orientado a objetos.

O objetivo é criar código:

- mais organizado;
- mais fácil de manter;
- mais fácil de testar;
- mais fácil de evoluir.

O nome SOLID é um acrônimo:

|   Letra    |             Princípio              |
|   :---:    |               :---:                |    
|     S      |   Single Responsibility Principle  |
|     O      |        Open/Closed Principle       |  
|     L      |    Liskov Substitution Principle   |
|     I      |   Interface Segregation Principle  |
|     D      |	  Dependency Inversion Principle  |

## Antes de decorar, entenda o propósito

Imagine um sistema crescendo durante anos.

Sem boas práticas você acaba com:

```txt
Classe gigante
↓
Muitos acoplamentos
↓
Mudanças quebram funcionalidades
↓
Código difícil de testar
↓
Manutenção cara
```

SOLID tenta evitar exatamente isso.

## S — Single Responsibility Principle (SRP)

Uma classe deve ter apenas um motivo para mudar.

### Exemplo ruim

```java
public class UserService {

    public void saveUser() {
        // salva usuário
    }

    public void sendEmail() {
        // envia email
    }

    public void generateReport() {
        // gera relatório
    }
}
```

Essa classe faz:

- cadastro;
- email;
- relatório.

Ela possui várias responsabilidades.

```txt
Melhor
UserService
EmailService
ReportService
```

Cada classe cuida de uma coisa.

## O — Open/Closed Principle (OCP)

Entidades devem estar abertas para extensão e fechadas para modificação.

Imagine:

```java
public class PaymentService {

    public void pay(String type) {

        if(type.equals("PIX")) {
            ...
        }

        if(type.equals("CREDIT")) {
            ...
        }
    }
}
```

Quando surge um novo método:

```txt
Boleto
```

você precisa alterar a classe.

Melhor:

```java
interface PaymentMethod {
    void pay();
}
PixPayment
CreditCardPayment
BoletoPayment
```

Novos métodos podem ser adicionados sem modificar o código existente.

## L — Liskov Substitution Principle (LSP)

Uma classe filha deve poder substituir a classe pai sem quebrar o sistema.

Exemplo clássico:
```java
Animal
Dog extends Animal
```
Tudo bem.

Mas imagine:

```java
Bird
```
e depois:

```java
Penguin extends Bird
```
Se a classe Bird possuir:

```java
fly()
```

o pinguim quebra a lógica porque não voa.

A herança foi mal modelada.

## I — Interface Segregation Principle (ISP)

Nenhuma classe deve ser obrigada a implementar métodos que não utiliza.

Exemplo ruim:

```java
interface Worker {

    void work();

    void eat();

    void sleep();
}
```

Agora um robô precisa implementar:

```java
eat()
sleep()
```

mesmo sem precisar.

Melhor:

```java
Workable
```
```java
Eatable
```
```java
Sleepable
```

Interfaces menores e mais específicas.

## D — Dependency Inversion Principle (DIP)

Esse costuma ser o mais importante em aplicações modernas.

Dependa de abstrações, não de implementações.

Exemplo ruim

```java
public class UserService {

    private MySQLRepository repository =
        new MySQLRepository();
}
```
UserService está acoplado ao MySQL.

Melhor

```java
public interface UserRepository {
}
```
```java
public class MySQLRepository
    implements UserRepository {
}
```
```java
public class MongoRepository
    implements UserRepository {
}
```
```java
public class UserService {

    private UserRepository repository;
}
```

Agora você pode trocar:

```txt
MySQL
↓
MongoDB
↓
PostgreSQL
```

sem alterar a regra de negócio.

## Onde você já viu SOLID sem perceber?

Quando estudou Spring Boot.

Por exemplo:

```java
@Service
public class UserService
```
```java
@Repository
public class UserRepository
```

Isso já é uma aplicação do SRP.

Quando utilizou:

```java
@Autowired
```

ou injeção de dependência via construtor:

```java
public UserService(UserRepository repository)
```
você estava aplicando DIP.

## SOLID no mundo real

Nem todo projeto segue SOLID perfeitamente.

Mas esses princípios ajudam a:

- reduzir acoplamento;
- melhorar testes unitários;
- facilitar manutenção;
- tornar o código mais escalável.

Por isso aparecem tanto em vagas para:

- Java;
- Spring Boot;
- C#;
- Go;
- Node.js;
- Arquitetura de Software.
