# Observabilidade

Observabilidade é a capacidade de compreender rapidamente o comportamento de um sistema através da análise de Logs, Métricas e Traces.

Seu principal objetivo é permitir que equipes identifiquem, investiguem e resolvam problemas em aplicações e infraestruturas de forma eficiente.

Observabilidade permite que equipes respondam rapidamente perguntas fundamentais sobre um sistema:

* O que aconteceu?
* Onde aconteceu?
* Como aconteceu?
* Por que aconteceu?

Quanto mais rapidamente essas perguntas forem respondidas, menor tende a ser o tempo necessário para diagnosticar e corrigir problemas.

Em outras palavras:

> Observabilidade permite responder não apenas que existe um problema, mas também por que ele aconteceu.

## O problema

Imagine uma aplicação em produção.

Um usuário relata:

```txt
O sistema está lento.
```

Sem observabilidade, a equipe precisa fazer suposições.

Perguntas comuns:

* O problema está na API?
* O banco de dados está lento?
* Existe alguma falha de rede?
* Algum serviço está indisponível?
* Quando o problema começou?

Sem informações suficientes, identificar a causa pode ser difícil e demorado.

## Monitoramento x Observabilidade

Os conceitos são relacionados, mas não são a mesma coisa.

### Monitoramento

Responde:

> Existe algum problema?

Exemplos:

* CPU acima de 90%;
* Memória esgotando;
* Serviço fora do ar;
* Erros aumentando.

### Observabilidade

Responde:

> Por que o problema aconteceu?

Exemplo:

```txt
API lenta
↓
Endpoint específico
↓
Consulta SQL lenta
↓
Falta de índice
```

A observabilidade ajuda a encontrar a causa raiz dos problemas.

## Os Três Pilares da Observabilidade

A observabilidade moderna é baseada em três pilares principais.

### Logs

Logs registram eventos ocorridos dentro da aplicação.

Exemplos:

```txt
Usuário autenticado

Pedido criado

Erro ao processar pagamento
```

Os logs ajudam a entender o que aconteceu.

### Métricas

Métricas são valores numéricos coletados ao longo do tempo.

Exemplos:

```txt
Uso de CPU

Uso de memória

Latência

Quantidade de requisições

Taxa de erros
```

As métricas ajudam a identificar tendências e comportamentos anormais do sistema.

### Traces

Traces mostram o caminho percorrido por uma requisição através de múltiplos componentes.

Exemplo:

```txt
Frontend
↓
API Gateway
↓
User Service
↓
Payment Service
↓
Database
```

Os traces ajudam a identificar gargalos, dependências e falhas em sistemas distribuídos.

## Resumindo os Três Pilares

| Pilar    | Pergunta Principal                  |
| -------- | ----------------------------------- |
| Logs     | O que aconteceu?                    |
| Métricas | Existe algum comportamento anormal? |
| Traces   | Onde e como o problema ocorreu?     |

## Exemplo Prático

Imagine uma requisição de pagamento.

Fluxo:

```txt
Usuário
↓
API Gateway
↓
Order Service
↓
Payment Service
↓
Banco de Dados
```

A aplicação apresenta lentidão.

Com observabilidade:

### Métricas

Identificam aumento da latência.

### Logs

Mostram erros de conexão.

### Traces

Revelam que a lentidão ocorre durante o acesso ao banco.

A combinação dos três pilares permite localizar rapidamente a origem do problema.

## Observabilidade em Microsserviços

Em arquiteturas monolíticas normalmente existe apenas uma aplicação.

Em microsserviços:

```txt
Frontend
↓
API Gateway
↓
User Service
↓
Order Service
↓
Payment Service
↓
Notification Service
```

A complexidade aumenta significativamente.

A observabilidade torna-se fundamental para compreender a interação entre os serviços e localizar falhas rapidamente.

## Ferramentas Comuns

### Logs

Ferramentas utilizadas para armazenamento e consulta de logs:

* Elasticsearch;
* Loki;
* Splunk.

### Métricas

Ferramentas utilizadas para coleta de métricas:

* Prometheus.

### Visualização

Ferramentas utilizadas para dashboards e monitoramento:

* Grafana.

### Tracing

Ferramentas utilizadas para rastreamento distribuído:

* Jaeger;
* Zipkin;
* OpenTelemetry.

## Benefícios

### Diagnóstico mais rápido

Problemas podem ser identificados com maior velocidade.

### Redução do tempo de indisponibilidade

Facilita a recuperação de incidentes.

### Melhor experiência do usuário

Permite identificar gargalos antes que afetem muitos usuários.

### Maior confiabilidade

Ajuda a manter sistemas estáveis e previsíveis.

## Desafios

### Volume de dados

Logs, métricas e traces podem gerar grandes quantidades de informação.

### Custos

Armazenamento e processamento podem se tornar caros.

### Complexidade

Implementar observabilidade exige planejamento, padronização e governança.

## Como a Observabilidade é Utilizada

Fluxo comum de investigação:

```txt
Problema Reportado
↓
Métricas
↓
Identificar comportamento anormal
↓
Trace
↓
Localizar o serviço afetado
↓
Logs
↓
Descobrir a causa raiz
↓
Correção
```

Esse fluxo permite reduzir significativamente o tempo necessário para diagnosticar incidentes em produção.

## Relação com outros conceitos

A observabilidade utiliza informações produzidas pelas aplicações:

```txt
Aplicação
↓
Logs

Aplicação
↓
Métricas

Aplicação
↓
Traces
```

Esses dados são coletados e analisados por ferramentas especializadas.

Exemplo:

```txt
Prometheus
↓
Grafana
↓
Dashboards

Logs
↓
Investigação

Traces
↓
Diagnóstico
```

## Relação com o DevPedia

A observabilidade conecta diversos conceitos já documentados:

```txt
Observabilidade
├── Logs
├── Trace
├── Grafana
├── Prometheus
├── Microsserviços
├── Event-Driven Architecture
└── Sistemas Distribuídos
```

Por isso é considerada uma das disciplinas mais importantes em ambientes modernos de software.

## Resumo

Observabilidade é a capacidade de compreender o comportamento interno de um sistema através dos dados que ele produz.

Ela utiliza Logs, Métricas e Traces para ajudar equipes a monitorar aplicações, diagnosticar problemas, identificar gargalos e garantir a confiabilidade de sistemas distribuídos e ambientes de produção.
