# Remoto

## 01. Utilizando remote

O comando 

```bash
git remote
```

Podemos fazer algumas alterações como adicionar um repo para trackear ou remover.

Quando criamos um repo remoto, adicionamos ele ao git com:

```bash
git remote add origin <link>
```

## 02. Recebendo alterações 

O comando:

```bash
git pull
```

Serve para recebermos atualizações do repositório remoto. Cda branch pode ser atualizado com o mesmo comando.

Utilizamos para atualizar a master/main do repo como também quando trabalhamos em conjunto e queremos receber as atualizações de outros devs.

O git pull realiza duas operações em sequência. Primeiro, ele faz um git fetch para trazer as atualizações do repo remoto para o seu repo local, como o fetch. Depois, ele faz um merge automático dessas mudanças no seu branch atual. Em resumo, o git pull atualiza seu repositório local e incorpora automaticamente as mudanças mais recentes mo seu código. 

## 03. Enviando alterações

O comando:

```bash
git push
```

Faz o inverso do pull, ele envia as alterações para o repo remoto.

Serve também para enviar as atualizações de um branch específico para outro dev ou quando terminamos uma tarefa e precisamos enviar ao repo.
