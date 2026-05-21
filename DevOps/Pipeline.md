# Pipeline

Software delivery pipeline é um fluxo automatizado utilizado no desenvolvimento de software para executar etapas como:

- build;
- testes;
- validação;
- análise;
- deploy.

O objetivo de um pipeline é automatizar processos repetitivos, reduzir erros humanos e garantir maior consistência durante a entrega do software.

## Como funciona?

Um pipeline normalmente executa etapas em sequência, como:

```txt
Código
   ↓
Build
   ↓
Testes
   ↓
Lint
   ↓
Deploy
```

## Etapas comuns de um pipeline

- Compilação de código;
- Testes unitários;
- Lint e análise estática;
- Verificações de segurança;
- Build de aplicações;
- Geração de artefatos/binários;
- Deploy automatizado.

## Benefícios

- Automação;
- Padronização;
- Menos erros humanos;
- Entregas mais rápidas;
- Maior confiabilidade;
- Integração contínua.

## Ferramentas comuns

- GitHub Actions;
- Jenkins;
- GitLab CI;
- CircleCI;
- Azure DevOps;
- ArgoCD.

## Relação com CI/CD

Pipelines são amplamente utilizados em processos de:

- CI (Continuous Integration);
- CD (Continuous Delivery/Deployment).

## Exemplo prático

Sempre que um desenvolvedor faz um git push:

1. O pipeline inicia automaticamente;
2. O sistema roda testes;
3. Verifica qualidade do código;
4. Faz build da aplicação;
5. Realiza deploy automático.

