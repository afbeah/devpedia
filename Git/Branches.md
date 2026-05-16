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
