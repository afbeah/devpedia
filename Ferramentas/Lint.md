# Lint

Linter é uma ferramenta utilizada para analisar código-fonte e identificar:

- erros;
- inconsistências;
- más práticas;
- problemas de estilo;
- violações de padrões.

O lint ajuda a manter a qualidade e padronização do código antes mesmo da execução da aplicação.

## Para que serve?

Lint é utilizado para:

- melhorar legibilidade;
- evitar bugs;
- padronizar código;
- reforçar boas práticas;
- automatizar revisão de estilo.

## Benefícios

- Código mais limpo;
- Melhor manutenção;
- Redução de erros;
- Padronização entre equipes;
- Feedback rápido durante o desenvolvimento.

## O que um lint pode detectar?

- Variáveis não utilizadas;
- Erros de sintaxe;
- Imports desnecessários;
- Problemas de formatação;
- Código duplicado;
- Más práticas.

## Exemplos por linguagem

|       Linguagem        |     Ferramenta      |
|         :---:          |        :---:        |
| JavaScript/TypeScript  |        ESLint       |
|         Python         |   Pylint / Flake8   | 
|           Go           |     golangci-lint   | 
|          Java          |      Checkstyle     |
|          C/C++         |       Cppcheck      |

## Integração com desenvolvimento

Linters normalmente são integrados com:

- IDEs;
- pipelines CI/CD;
- Git hooks;
- Husky;
- pre-commit hooks.

## Exemplo comum

Durante um git commit, o lint pode bloquear commits com:

- erros;
- formatação incorreta;
- código fora do padrão.
