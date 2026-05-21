# --no-verify

O parâmetro --no-verify é utilizado em comandos do Git para ignorar a execução automática de hooks configurados no repositório.

Ele normalmente é usado com comandos como:

```bash
git commit --no-verify
```
ou:

```bash
git push --no-verify
```

## Ferramentas como Husky utilizam hooks para:

- rodar testes;
- validar commits;
- executar linters;
- verificar padrões de código.

## Quando o --no-verify é usado?

Geralmente em situações excepcionais, como:

- bugs em hooks;
- falhas temporárias de lint;
- problemas no Husky;
- emergências de deploy;
- validações quebradas incorretamente.

### Atenção

Usar --no-verify ignora validações importantes do projeto.

Isso pode permitir:

- commits com erros;
- código quebrado;
- falha em padrões da equipe;
- problemas em produção.

Por isso, deve ser utilizado apenas em último caso.

## Exemplo

```bash
git commit -m "fix: hotfix urgente" --no-verify
```
