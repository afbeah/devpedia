# Primeiros Passos

## 01. Criando um Repositório

Para criar um repo usamos o comando:

```bash
git init
```
Desta maneira o git vai criar os arquivos necessários para inicializá-lo e estarão na pasta oculta **.git**

Após este comando o diretório atual será reconhecido pelo git como um projeto e responderá aos comandos.

## 02. Clonando um repositórios

O Ato de baixar um repositório de um servidor remoto é chamado de *clonar repo*, para esta ação usamos:

```bash
git clone LINK_DO_REPO
```

Passando a referência do respositório remoto. 

## 03. Verificando mudanças do projeto

As mudanças do projeto podem ser verificadas por:

```bash
git status
```

Este comando é utilizado frequentemente. Aqui serão mapeadas todas as alterações do projeto como: 
 - Arquivos não monitorados
 - Arquivos Modificados

Podemos também dizer que é a diferença do que já esta enviando ao servidor ou salvo no projeto.

## 04. Adicionando arquivos ao projeto 

Para adicionar arquivos novos a um projeto utilizamos:

```bash
git add
```

Podemos adicionar um arquivo específico como também diversos de uma vez. 

Somente ao adicionar os arquivos, eles serão monitorados pelo git, ou seja, se não adicionar ele não estará no controle de versão.

É interessante utilizar este comando de tempos em tempos para não perder alguma inserção/modificação por descuido.

Para adicionar apensa uma modificação:

```bash
git add nome-arquivo
```

## 05. Salvando alterações 

As alterações serão salvas usando:

```bash
git commit -m "aqui inserir o commit semantico e uma mensagem com as alterações feitas"
```

Assim como para adicionar, é possível commitar arquivos específicos ou vários de uma vez.

## 06. Enviando código

Quando finalizamos uma nova feature (feat), enviamos o código ao repo remoto, que é código-fonte. Para esta ação iremos usar o comando:

```bash
git push
```
Após esta ação o código do servidor será atualizado pelo código local enviado.

## 07. Recebendo alterações

É comum também ter que sincronizar o local com as mudanças do remoto, para esta ação usamos o comando:

```bash
git pull
```

Após o comando serão buscadas as alterações/atualizações, se encontradas elas serão unidas ao código atual existente na nossa máquina.

## 08. Removendo Arquivos

Os arquivos podem ser deletados na monitoração do git, o comando para deletar é:

```bash
git rm
```

Após deletar um aquivo do git ele não terá mais suas atualizações consideradas pelo git apenas quando for adicionado novamente. Caso o arquivo esteja em uma pasta será necessário acessar a pasta para dar o comando.
