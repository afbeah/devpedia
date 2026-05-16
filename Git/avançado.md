# Avançado

## 01. Submódulos

É a maneira que temos de possuir dois ou mais projetos em um só repostiório.

Podemos adicionar uma dependência ao nosso projeto atual, porém mantendo suas estruturas separadas.

Para adicionar o submódulo utilizamos o comando:

```bash
git submodule add <repo>
```

Para verificar os submódulos o comando é:

```bash
git submodules
```

## 02. Atualizando submódulos

Para atualizar um submódulo primeiro devemos commitar as mudanças, e para enviar para o repo do submódulo utilizamos:

```bash
git push --recurse -submodules-on-demand
```

Este fluxo fará a atualização apenas do submódulo.


## 03. Reflog

O comando:

```bash
git reflog
```

Vai mapear todos os seus passos no repositório, até  uma mudança de branch é inserida nesse log.

Já o:

```bash
git log
```

Apenas armazena os commits de um branch.

Os reflogs ficam até expirar, o tempo de expiraçãopadrão é de 30 dias.

## 04. Log resumido

O comando:

```bash
git shortlog
```

Nos dá um log resumido do projeto. Cada commit será unido por um nome do autor.

É possível então saber quais commits foram enviados ao projeot e por quem.
