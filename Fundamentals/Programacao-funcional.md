# Programação Funcional

É um paradigma de programação que trata a computação como a avaliação de funções matemáticas, priorizando o uso de funções puras e imutabilidade de dados.

Isso significa que as funções não possuem efeitos colaterais (sempre retornam o mesmo resultado para a mesma entrada) e os dados não são modificados, mas sim substituídos por novas versões. Essa abordagem leva a um código mais prevísivel, fácil de testar, modular e reutilizável.

## Conceitos chave

1. Funções Puras: São funções que sempre produzem a mesma saída para a mesma entrada, sem alterar qualquer estado externo. (sem efeito colateral);
2. Imutabilidade: Os dados não podem ser alterados após sua criação. Em vez de modificar um dado, você cria uma nova versão dele, semelhante a montar peças de lego;
3. Funções em Ordem Superior: Funções que podem receber outras funções como argumentos ou retornar funções como resultado. Isso permite a criação de abstrações mais poderosas e a composição de código;
4. Programação Declarativa: Em vez de especificar "como" fazer algo (programação imperativa), você descreve "o que " deve ser feito.

## Benefícios

1. Código mais fácil de testar e depurar

As funções puras tornam o comportamento do código mais previsível e isolado, simplificando a identificação de erros.

2. Maior modularidade e reutilização

A composição de funções pequenas e reutilizáveis torna o código mais flexível.

3. Facilidade de paralelismo

A ausência do estado compartilhado e a imutabilidade facilitam a execução de código em paralelo sem a necessidade de complexos mecanismos de sincronização.

## Exemplos comuns em programação funcional

- map();
- filter();
- reduce();
- composição de funções;
- recursão.

## Linguagens que utilizam programação funcional

- Haskell;
- Elixir;
- Scala;
- Clojure;
- JavaScript;
- Kotlin;
- Python.
