# Branches

## 01. O que é Branch?

É a forma que o git separa as versões dos projetos. Quando um projeto é criado ele inicia na **branch main** ou **branch master**, estamos trabalhando nela até este ponto do curso.

Geralmente cada nova feature de um projeto fica em um branch.

Após a finalização das alterações os branchs são unidos para ter o código-fonte final. 

## 02. Criando Branches

Para visualizar as branchs disponíveis basta digitar:

```bash
git branch
```

Para criar um branch precisa utilizar o comando:

```bash
git branch <nome>
```

## 03. Mudando de Branch

Podemos mudar para o outro branch utilizando o comando:

```bash
git checkout <nome>
```

Este comando também é utilizado para dispensar mudanças de um arquivo.

Alterando o branch podemos levar alterações que não foram commitadas junto, tomem cuidado.

> Para **criar** e **mudar** para a branch criada de uma vez usamos o comando:
```bash
git checkout -b <nome>
```

## 04. Unindo branches

O código de dois branches distintos pode ser unido pelo comando:

```bash
git merge <nome>
```

Outro comando para a lista dos mais usados. Normalmente é por meio dele que recebemos as atualizações de outros devs.

## 05. Deletando Branches

Podemos deletar um branch com a flag **-D** ou **--Delete**.

Não é comum deletar um branch, normalmente guardamos o histórico do trabalho. 

Geralmente se usa o delete quando o branch foi criaso errado. 

## 06. Encontrando Branches

Branches novos são criados a todo momento e o seu git pode não estar mapeando eles.

Com o comando: 

```bash
git fetch
```

Você é atualizado de todos os branches e tags que ainda não estão reconhecidos por você.

Este comando é útil para utilizar o branch de algum outro dev do time. 

O git fetch busca todos os commits do repositório remoto que ainda não estão no seu repositório local. Ele atualiza o seu "espelho" do repo remoto, mas não faz alterações no seu código local. Ou seja, ele traz as atualizalões para que você possa visualizá-las, mas não integra essas mudanças ao seu trabalho atual.
