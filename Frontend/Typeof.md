# Typeof

O *typeof* é um operador presente em várias linguagens de programação (como JavaScript, TypeScript, Python e outras) que retorna o tipo de dado de uma variável, valor ou expressão. Ele é especialmente útil para depurar/debugar código ou validar entradas.

## Como funciona em diferentes linguagens?

1. Javascript

Em JavaScript, *typeof* retorna uma string indicando o tipo do operando 

  ```js
  console.log(typeof 42);
  "number"
  ````

  ```js 
  console.log(typeof "deepseek");
  "string" 
  ```
  
  ```js
  console.log(typeof true)
  "boolean"
  ```

2. Python

Em python, usa-se a função *type()* (equivalente ao typeof)

  ```python
  print(type(42))
  <class 'int'>
  ```

  ```python
  print (type("deepseek"))
  <class 'str'>
  ```

  ```python
  print (type(True))
  <class 'bool'>
  ```

  ```python
  print (type([1,2]))
  <class 'list'>
  ```

## Quando usar?

-> Validar dados 

-> depurar/debugar

-> programação genérica
