# Yarn

O *Yarn* é um gerenciador de pacotes para JavaScript, foi lançado pelo Facebook em 2016 para resolver alguns problemas do *NPM*, como lentidão e inconsistência na instalação de pacotes. Ele permite instalar, atualizar e gerenciar dependências de projetos JavaScript.
O Yarn é um *gerenciador de pacotes para JavaScript*, criado como uma alternativa mais como alternativa mais rápida, segura e eficiente ao *npm - node package manager*. Ele é amplamente utilizado em projetos que utilizam *Node.js* e frameworks como React, Vue.js e Angular.

## Principais Recursos do Yarn

- Performance rápida: O Yarn faz download paralelo de pacotes, tornando a instalação mais rápida que o npm;
- Cache de pacotes: Ele salva os pacotes localmente, evitando novos downloads desnecessários;
- Determinismo (lockfile): Garante que todos os membros de um projeto tenham as mesmas versões de dependências por meio do arquivo *yarn.lock*;
- Modo Offline: Se um pacote já foi baixado antes, ele pode ser instalado sem conexão com a internet.
- Segurança aprimorada: o yarn verifica a integridade dos pacotes baixados, reduzindo o risco de instalar código malicioso.

> O yarn é uma excelente alternativa ao npm, especialmente em projetos grandes, pois oferece mais velocidade, segurança e estabilidade.

## Comandos básicos do Yarn

```bash
yarn install
yarn add react
yarn remove axios
yarn dev

```

## Yarn vs npm

- npm → gerenciador padrão do Node.js;
- Yarn → alternativa focada em performance e consistência;
- Ambos gerenciam dependências JavaScript.
