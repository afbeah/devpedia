# YAGNI

**YAGNI** significa:

> You Aren't Gonna Need It

("Você não vai precisar disso.")

O princípio defende que funcionalidades devem ser implementadas apenas quando forem realmente necessárias.

## O problema

Muitos desenvolvedores tentam prever necessidades futuras e acabam criando código para cenários que talvez nunca existam.

Isso gera:

* complexidade desnecessária;
* código difícil de manter;
* funcionalidades não utilizadas.

## Exemplo

Imagine um sistema que atualmente aceita apenas PIX.

### Desnecessário

```java
public interface PaymentMethod {
    void pay();
}

public class PixPayment implements PaymentMethod {
}

public class CreditCardPayment implements PaymentMethod {
}

public class BoletoPayment implements PaymentMethod {
}

public class CryptoPayment implements PaymentMethod {
}
```

Se apenas PIX existe hoje, as demais implementações foram criadas sem necessidade.

### Melhor

```java
public class PixPayment {

    public void pay() {
        // lógica de pagamento
    }
}
```

Quando surgir a necessidade de outros métodos, o sistema pode evoluir.

## Benefícios

* Menos código;
* Menos manutenção;
* Menor complexidade;
* Desenvolvimento mais rápido.

## YAGNI não significa

* Ignorar arquitetura;
* Escrever código descartável;
* Não pensar no futuro.

Significa apenas evitar implementar funcionalidades antes da hora.

## YAGNI e KISS

Os dois princípios possuem uma relação forte.

### KISS

> Mantenha simples.

### YAGNI

> Não implemente o que ainda não precisa existir.

Juntos, ajudam a reduzir complexidade desnecessária.

## Resumo

YAGNI é o princípio que incentiva o desenvolvimento baseado em necessidades reais, evitando funcionalidades prematuras e abstrações desnecessárias.
