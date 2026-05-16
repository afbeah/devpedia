# Manipulação de Arquivos

## 01. Renomeando Arquivos

O comando: 
```bash
git mv
```

Renomeia um arquivo. 

O mesmo também pode ser movido para outra pasta e isso fará com que esse arquivo novo seja monitorado pelo git e o anterior é excluído.

## 02. Desfazendo alterações

O arquivo modificado pode ser retornado ao estado original, para essa finalidade usamos o comando:

```bash
git checkout -- nome_do_arquivo
```
Após utilizar comando, o arquivo sai do staging. Caso seja feita uma próxima alteração, ele entra em staging novamente. 

Esse comando serve *antes* de adicionar a alteração.

## 03. Desfazendo TODAS as alterações

Para alterações locais podemos utilizar o comando:

```bash
git reset
```

Podemos resetar as mudanças feitas. Geralmente utilizado com a flag **--hard**.

Todas as operações commitadas e também as pendenstes serão excluídas. Retornando o projeto para o último push.

## 04. Ignorando Arquivos

Uma técnica muito utilizada é ignorar arquivos do projeto, devemos inserir um arquivo **.gitignore** na raiz do projeto. Nele podemos iserir todos os arquivos que não devem entrar no versionamento.

Isso é útil para arquivos gerados automaticamente ou arquivos que contém informações sensíveis. 

Primeiro adicionamos dentro do **.gitignore** e aí depois a pasta será criada.

Ao inserir /* no final do arquivo dentro do .gitignore, estamos informando que tudo que estiver junto ou dentor deste arquivo também deve ser ignorado.

## 05. Verificando diferenças

O comando:

```bash
git diff
```

Serve para exibir as diferenças de um branch.

Quando utilizado as diferenças do branch atual com o remoto serão exibidas no terminal.

Podemos também verificar a diferença entre arquivos:

```bash
git diff <arquivo_a> <arquivo_b>
```

## 06. Exibindo Informações 

O comando:

```bash
git show
```

Nos dá diversas informações úteis.

Ele nos dá as informações do branch atual e também seus commits. As modificações de arquivos entre cada commit também são exibidos.
