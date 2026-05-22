# Trace

*Distributed tracing* é uma técnica de observabilidade utilizada para rastrear o caminho de uma requisição dentro de um sistema distribuído.

O trace permite acompanhar:

- por onde uma requisição passou;
- quanto tempo levou;
- quais serviços participaram;
- onde ocorreram erros ou lentidão.

## Como funciona?

Quando uma requisição entra em um sistema:

- ela recebe um identificador único (trace id);
- cada serviço registra informações sobre aquela execução;
- essas informações são agrupadas para formar o rastreamento completo.

### Exemplo simples

```txt
Frontend
   ↓
API Gateway
   ↓
Auth Service
   ↓
Payments Service
   ↓
Database
```

O trace permite visualizar todo esse fluxo.

## Para que serve?

- Monitoramento de microsserviços;
- Diagnóstico de erros;
- Identificação de gargalos;
- Observabilidade;
- Análise de performance;
- Debug distribuído.

## Benefícios

- Maior visibilidade do sistema;
- Identificação rápida de problemas;
- Melhor análise de performance;
- Facilita troubleshooting;
- Melhor monitoramento de aplicações distribuídas.

## Ferramentas comuns

- Jaeger;
- Zipkin;
- OpenTelemetry;
- Grafana Tempo;
- Datadog.

# Trace vs Logs vs Metrics

|   Conceito   |            Objetivo             |
|     :---:    |              :---:              | 
|     Logs     |      Eventos e mensagens        | 
|   Metrics    |     Números e indicadores       |
|     Trace    |  Caminho completo da requisição |
