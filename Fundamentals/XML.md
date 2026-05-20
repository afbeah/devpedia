# XML

*Extensible Markup Language* - Linguaguem de marcação extensível

O XML é uma linguagem de marcação que permite organizar dados e informações de forma padronizada, garantindo que diferentes sistemas sejam capazes de interpretá-las.

A linguagem surgiu com o intuito de ser um formato de arquivo que facilitasse a troca de dados de maneira simples e flexível. Seu funcionamento é feito por meio de *tags*, que podem ser personalizadas de acordo com a necessidade de uso.

De forma simples, o XML é uma linguagem de marcação muito parecida com o *HTML*, mas com uma diferença fundamental.

1. Propósito

- O HTML é usado para exibir dados na tela (como um navegador mostra). Ele tem tags pré-definidas
- O XML é usado para armazenar e transportar dados. Ele não define como os dados devem ser exibidos, mas sim o que os dados são

2. Extensibilidade

Em XML, as próprias tags definem para descrever seus dados. É por isso que é "extensível".

## Exemplo

Se quisesse descrever um livro, em XML você criaria suas tags.

```xml
<livro>
  <titulo> Presságios do Amor </titulo>
  <autor> Alexandria Bellefleur </autor>
  <ano> 2021 </ano>
  <genero> Romance </genero>
</livro>
```

## Principais Características do XML

- Estrutura hierárquica: Os dados são organizados em uma estrutura de árvore
- Legível por humanos e máquinas: Sua sintaxe simples facilita a leitura tanto por pessoas quanto por programas
- Regras rígidas: Ao contrário do HTML, o xml é muito mais rigoroso com a sintaxe

## Onde o XML é usado?

Ele é amplamente usado para:

- Troca de dados entre sistemas diferentes;
- Formato de documentos;
- Arquivos de configuração de software.

## Regras básicas do XML

- Toda tag deve ser fechada;
- Tags são sensíveis a maiúsculas e minúsculas;
- Deve existir um elemento raiz;
- A estrutura deve ser válida e bem formada.

## Onde XML ainda é muito utilizado?

- APIs legadas;
- Arquivos de configuração;
- Sistemas corporativos;
- Integrações bancárias;
- Documentos SOAP;
- Android.
