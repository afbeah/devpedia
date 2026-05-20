# NPM

O *NPM - node package manager* é o gerenciador de pacotes padrão do *Node.js*. Ele permite instalar, gerenciar e compartilhar bibliotecas, frameworks e ferramentas para projetos JavaScript.

Criado em 2010, o NPM é o *maior repositório de pacotes do mundo*, contendo milhões de bibliotecas usadas em projetos de Frontend e Backend.

## Principais recursos

- Gerenciamento de dependências: Permite instalar e gerenciar bibliotecas e frameworks de forma eficiente.
- Repositório de pacotes: O NPM possui um vasto catálogo de pacotes que podem ser instalados diretamente no seu projeto.
- Scripts automatizados: No *package-json*, é possível definir scripts para rodar comandos. (ex: iniciar servidores, executar testes ou gerar builds)
- Controle de versão de dependências: Usa o arquivo *package-lock-json* para garantir que todos tenham as mesmas versões de dependências.
- Gerenciamento global e local de pacotes: Você pode instalar pacotes localmente (para um projeto) ou globalmente (para todo o sistema).

> O npm é uma ferramenta essencial para qualquer desenvolvedor JavaScript. Se você usa *Node.js* o npm será seu principal aliado para instalar pacotes, gerenciar dependências e automatizar tarefas.

## Comandos básicos do npm

```bash
npm install
npm install express
npm run dev
npm uninstall axios
```

## Arquivos importantes do npm

- package.json → configurações e dependências do projeto;
- package-lock.json → controle exato das versões instaladas;
- node_modules → diretório onde os pacotes são instalados.
