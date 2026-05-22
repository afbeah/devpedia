# CI/CD

CI/CD é um conjunto de práticas utilizadas para automatizar integração, testes e entrega de software.

CI/CD significa:

- CI → Continuous Integration;
- CD → Continuous Delivery ou Continuous Deployment.

## Continuous Integration (CI)

*Continuous Integration* é a prática de integrar continuamente alterações de código feitas pelos desenvolvedores em um repositório compartilhado.

O objetivo é:

- detectar erros rapidamente;
- evitar conflitos;
- melhorar colaboração;
- automatizar validações.

### O que acontece em um pipeline de CI?

Um pipeline de CI normalmente executa:

- Build da aplicação;
- Testes automatizados;
- Lint;
- Análise estática;
- Verificações de segurança;
- Geração de artefatos.

## Continuous Delivery (CD)

*Continuous Delivery* é a prática de preparar automaticamente novas versões da aplicação para deploy.

O sistema fica sempre pronto para publicação.

## Continuous Deployment

*Continuous Deployment* vai além:

- o deploy acontece automaticamente;
- sem intervenção manual;
- após todas as validações passarem.

## Fluxo comum de CI/CD

```txt
Código
   ↓
Git Push
   ↓
Pipeline CI
   ↓
Testes
   ↓
Build
   ↓
Deploy
```

## Benefícios

- Entregas mais rápidas;
- Redução de erros;
- Automação;
- Feedback rápido;
- Maior qualidade do código;
- Deploys mais seguros.

## Ferramentas comuns

- GitHub Actions;
- Jenkins;
- GitLab CI;
- CircleCI;
- Azure DevOps;
- ArgoCD.
