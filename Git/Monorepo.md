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
