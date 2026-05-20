# Operador Ternário

Os operadores ternários são úteis para escrever código de forma mais concisa.

O operador ternário é o único operador que aceita três operandos.

O operador ternário funciona como uma forma abreviada de uma estrutura condicional *if-else*.

# Sintaxe

**CONDIÇÃO ? VALOR_SE_VERDADEIRO : VALOR_SE_FALSO**

- A *condição* é avaliada primeiro;
- Se a *condição* for **verdadeira (True)**, a expressão retorna o *VALOR_SE_VERDADEIRO*;
- Se a *condição* for **falsa (False)**, a expressão retorna o *VALOR_SE_FALSO*

### Exemplo

Atribua a palavra *"Aprovado"* ou *"Reprovado"* com base na nota.

- Forma tradiciona:
  
```JavaScript
const nota = 7;
string Resultado;

if (nota >= 7) {
  Resultado = "Aprovado"
} else {
  Resultado = "Reprovado"
}
```

- Com operador ternário

```JavaScript
const nota = 7;

const resultado = (nota >= 7) ? "Aprovado" : "Reprovado";
```

Note que o operador ternário é uma expressão, ou seja, ele retorna um valor, o que permite atribui-lo diretamente a uma variável.

## Quando usar operador ternário?

- Condições simples;
- Atribuições rápidas;
- Retorno de valores condicionais;
- Renderização condicional em frontend.

## Quando evitar?

Evite operadores ternários muito longos ou aninhados, pois podem dificultar a leitura do código.
  
