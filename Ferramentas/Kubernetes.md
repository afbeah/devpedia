# Kubernetes

É uma plataforma Open-Source de orquestração de containers. Ele foi criado originalmente pelo Google.

Em termos simples, o *Kubernetes* ajuda a implantar, gerenciar e escalar aplicações em containers (como os criados com Docker) de forma automatizada e eficiente.

## O que ele faz?

- Orquestra containers -> Distribui e gerencia containers (ex: Docker) em vários serviços;
- Balanceamento de carga -> Distribui o tráfego entre instâncias da aplicação;
- Autoescalabilidade -> Aumenta ou reduz automaticamente o número de instâncias com base na carga;
- Atualizações sem downtime -> Permite atualizar aplicações sem interromper o serviço;
- Autocorreção -> Reinicia containers que falharam, substitui containers com falhas automaticamente;
- Gerenciamento de configurações e segredos -> Armazena variáveis de ambiente e senhas de forma segura.

## Conceitos Básicos

- Pod = Unidade mínima do Kubernetes (geralmente contém um container);
- Node = Máquina (física ou virtual) onde os pods rodam;
- Cluster = Conjunto de nodes gerenciados pelo Kubernete;
- Deployment = Descreve como o Kubernetes deve implantar e gerenciar uma aplicação;
- Service = Expõe um grupo de pods e fornece um ponto de acesso.

## Quando usar Kubernetes?

- Aplicações com muitos containers;
- Microsserviços;
- Ambientes com alta escalabilidade;
- Sistemas distribuídos;
- Plataformas em nuvem;
- Ambientes de alta disponibilidade.
