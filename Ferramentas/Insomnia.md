# Insomnia

É um programa que ajuda desenvolvedores a testar APIs, que são maneiras de diferentes programas se comunicarem entre si. Pense na API como um garçom em um restaurante, você faz um pedido (*requisição*) e o garçom (*API*) leva o pedido a cozinha (*servidor*) e traz a comida (*resposta*) para você.

Imagine que você esta criando um site e quer garantir que quando alguém clica em um botão, ele envia a informação correta ao servidor e recebe a resposta esperada. O **Insomnia** permite que você teste isso rapidamente. 

## O que você pode fazer com Insomnia?

- Enviar Pedidos: É possível enviar requisições a um servidor para verificar como ele responde. Esses pedidos podem ser diferentes tipos, como pegar informações (*GET*) ou enviar os dados (*POST*);
- Ver Respostas: Quando envia uma requisição, o servidor responde. O insomnia mostra essa resposta para que você possa ver se tudo está funcionando corretamente;
- Testar Autenticação: As vezes, você precisa se identificar antes de fazer uma requisição, como fazer uma requisição, como fazer login num site. O insomnia pode ajudar a testar esses processos de autenticação;
- Trabalhar com diferentes ambientes: Se você está testando seu programa em diferentes situações, o insomnia ajuda a gerenciar essas diferenças.

## Por que isso é útil?

- Economiza tempo: Podemos rapidamente testar e ver se algo está funcionando sem precisar escrever código ou abrir um navegador.
- Facilita a colaboração: Você pode salvar suas requisições e compartilhá-las com outras pessoas da sua equipe.
- Simplifica a depuração: Se algo der errado, você pode facilmente ver o que está acontecendo e corrigir o problema.

> Ajuda Devs a criar, organizar e testar solicitações de API de forma eficiente.

## Interface Principal

- Workspace: Um espaço de trabalho onde é possível organizar as solicitações;
- Collections: Dentro do workspace, é possível criar coleções para organizar suas solicitações relacionadas por projeto ou finalidade;
- Requests: Dentro de uma coleção é possível criar solicitações individuais para diferentes endpoints da API.

## Criando e testando ua solicitação de API

1. Nova solicitação: Clique em "New Request" de dê um nome à solicitação;
2. Selecione o Método HTTP: Escolha o métod adequado para a solicitação (GET, POST, PUT, DELETE, etc);
3. URL do endpoint: Insira o URL do endpoint da API que você deseja testar;
4. Headers: Adicione quaisquer cabeçalhos necessários, como `Content-Type`, `Authorization`, etc;
5. Body: Se a solicitação requer um corpo, você pdoe inserir o conteúdo no formato JSON, XML ou outro formato suportado;
6. Authentication: Configura a autenticação, se necessário. O insomnia suporta vários métodos de autenticação, incluindo basic auth, bearer, token, oauth 2.0, etc;
7. Enviar solicitação: Clique em "send" para enviar a solicitação. O insomnia exiborá a resposta da API, incluindo o status http, cabeçalhos e corpo da resposta.
