# Monorepo

Monorepo é uma estratégia de organização de código onde múltiplos projetos são mantidos dentro de um único repositório.

Ao invés de separar cada aplicação em repositórios diferentes (multirepo), o monorepo centraliza:

- aplicações;
- bibliotecas;
- serviços;
- componentes;
- configurações

em um único lugar.

## Características

- Compartilhamento de código;
- Dependências centralizadas;
- Padronização;
- Visibilidade entre equipes;
- Gerenciamento unificado;
- Integração facilitada.

## Exemplo de estrutura

```txt
repo/
├── frontend/
├── backend/
├── mobile/
└── shared/
```

## Benefícios

- Reutilização de código;
- Padronização de arquitetura;
- Facilidade de integração;
- Melhor colaboração;
- Versionamento centralizado.

## Desafios

- Repositórios maiores;
- Builds mais complexos;
- Pipeline mais pesado;
- Necessidade de ferramentas específicas.

## Ferramentas comuns em monorepo

- Nx
- Turborepo;
- Lerna;
- Bazel;
- pnpm workspaces.

## Monorepo vs Multirepo

|            Monorepo         |         Multirepo         |
|              :---:          |           :---:           |
|     Um único repositório    |    Vários repositórios    |
| Compartilhamento facilitado |      Maior isolamento     |
|    Gestão centralizada      |       Gestão separada     |
|     Melhor integração       |      Menor acoplamento    |

## Quando utilizar?

Monorepo costuma ser uma boa escolha quando:

- múltiplos projetos compartilham código;
- existe um Design System compartilhado;
- frontend e backend evoluem juntos;
- há necessidade de padronização entre equipes;
- a organização possui vários sistemas relacionados.

## Quando evitar?

Monorepo pode não ser a melhor escolha quando:

- os projetos são totalmente independentes;
- as equipes possuem pouca interação;
- não existe compartilhamento de código;
- a infraestrutura não suporta pipelines mais complexas.

Nesses casos, uma estratégia de multirepo pode ser mais adequada.

## Exemplo real

Imagine uma empresa que possui:

- Portal Web;
- Aplicativo Mobile;
- API Principal;
- Biblioteca Compartilhada de Componentes.

Em um Monorepo a estrutura poderia ser:

```txt
empresa/
├── apps/
│   ├── web/
│   ├── mobile/
│   └── api/
│
└── libs/
    └── shared/
