# Terraform

Terraform é uma ferramenta de Infrastructure as Code (IaC) criada pela HashiCorp.

Ela permite criar, modificar e gerenciar infraestrutura por meio de código, principalmente em ambientes de cloud computing.

Com o Terraform, é possível automatizar a criação de recursos como:

- máquinas virtuais;
- redes;
- bancos de dados;
- containers;
- clusters Kubernetes;
- serviços em nuvem.
  
## Como funciona?

O Terraform utiliza arquivos declarativos para definir como a infraestrutura deve ser criada.

Esses arquivos descrevem:

- quais recursos devem existir;
- como eles devem ser configurados;
- como devem se relacionar.

Depois disso, o Terraform:

- cria;
- atualiza;
- remove recursos automaticamente.

## Principais benefícios

- Automação de infraestrutura;
- Padronização de ambientes;
- Escalabilidade;
- Facilidade de manutenção;
- Infraestrutura versionada com Git;
- Redução de erros manuais.

## Onde o Terraform é utilizado?

- AWS;
- GCP;
- Azure;
- Kubernetes;
- DevOps;
- CI/CD;
- Provisionamento de infraestrutura.

## Exemplo simples

```hcl
resource "google_compute_instance" "vm" {
  name         = "meu-servidor"
  machine_type = "e2-medium"
}
```
