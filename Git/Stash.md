# Stash 

## 01. O que é Stash?

Podemos salvar as modificações atuais para prosseguir com uma outra abordagem de solução e não perde o código. O comando para esta ação é o:

```bash
git stash
```

Após o comando o git será resetado para a sua versão mais recente no repo.

## 02. Recuperando Stash

Podemos verificar as stashs criadas pelo comando:

```bash
git stash list
```

També podemos recuperar a stash com o comando:

```bash
git stash apply <n°>
```

Desta maneira podemos continuar de onde paramos com os arquivos adicionados a stash.

O comando:

```bash
git stash show -p <n°_da_stash>
```

Permite que vejamos o que tem de modificação naquela stash.

## 03. Removendo Stash 

Para limpar totalmente as stash de um branch podemos utilizar o comando:

```bash
git stash clear
```

Caso seja necessário deletar uma stash específica podemos usar o comando:

```bash
git stash drop <nome>
```

