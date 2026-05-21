# Deploy

Software deployment é o processo de disponibilizar uma aplicação para execução em um ambiente.

O deploy pode envolver:

- publicação;
- atualização;
- configuração;
- distribuição;
- inicialização do sistema.

## Ambientes comuns

O deploy pode acontecer em diferentes ambientes:

- Desenvolvimento (Development);
- Testes (Testing);
- QA (Quality Assurance);
- Homologação;
- Produção (Production).

## Como funciona?

Normalmente o fluxo de deploy envolve:

```txt
Código
   ↓
Build
   ↓
Testes
   ↓
Pipeline
   ↓
Deploy
   ↓
Servidor/Cloud
```

## Tipos de deploy

- Manual;
- Automatizado;
- Rolling Deploy;
- Blue-Green Deploy;
- Canary Deploy.

## Objetivos do deploy

- Disponibilizar novas funcionalidades;
- Corrigir bugs;
- Atualizar sistemas;
- Melhorar performance;
- Publicar novas versões.

## Ferramentas comuns

- Docker;
- Kubernetes;
- Jenkins;
- GitHub Actions;
- ArgoCD;
- Terraform.

## Benefícios da automação de deploy

- Redução de erros humanos;
- Maior velocidade de entrega;
- Mais segurança;
- Consistência entre ambientes;
- Facilidade de rollback.
