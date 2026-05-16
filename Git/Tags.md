# Tags

## 01. O que são tags?

A tag é diferente do stash, serve como um checkpoint de um branch. 

É utilizada para demarcar estágios do desenvolvimento de algum recurso.

## 02. Criando tags

Podemos criar tags nos branchs por meio do comando:

```bash
git tag -a <nome> -m "message"
```

## 03. Alterando tag

Podemos verificar uma tag com o comando:

```bash
git show <nome>
```

Podemos trocar de tags com o comando:

```bash
git checkout <nome>
```

## 04. Enviando tags

As tags podem ser enviadas ao repositório de código, sendo compartilhada entre os devs.

O comando é:

```bash
git push origin <nome>
```

Ou

```bash
git push origin --tags
```
