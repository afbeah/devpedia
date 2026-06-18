# DRY

**DRY** significa:

> Don't Repeat Yourself

("Não se repita.")

O princípio DRY defende que uma informação, regra de negócio ou lógica deve existir em apenas um lugar do sistema.

O objetivo é evitar duplicação de código, facilitando manutenção, correções e evolução do software.

## Por que evitar duplicação?

Imagine que uma mesma lógica esteja copiada em vários lugares.

Se uma regra mudar, será necessário alterar todos os pontos onde ela foi replicada.

Isso aumenta:

* risco de bugs;
* inconsistências;
* custo de manutenção.

## Exemplo

### Ruim

```java
public double calculateUserDiscount() {
    return price * 0.10;
}

public double calculateAdminDiscount() {
    return price * 0.10;
}

public double calculateManagerDiscount() {
    return price * 0.10;
}
```

A mesma lógica foi repetida três vezes.

### Melhor

```java
public double calculateDiscount() {
    return price * 0.10;
}
```

Agora existe apenas uma fonte de verdade para essa regra.

## Benefícios

* Menos código para manter;
* Menor chance de erros;
* Maior consistência;
* Facilidade para alterações futuras.

## Cuidado

DRY não significa transformar tudo em uma abstração.

Às vezes duas implementações parecidas representam regras diferentes e devem permanecer separadas.

O objetivo é eliminar duplicações reais, não criar complexidade desnecessária.

## DRY e Clean Code

O princípio DRY está diretamente relacionado ao Clean Code.

Código duplicado geralmente é mais difícil de entender, manter e evoluir.

## Resumo

DRY é o princípio que incentiva a centralização de conhecimento e regras de negócio, evitando repetições desnecessárias dentro do sistema.
