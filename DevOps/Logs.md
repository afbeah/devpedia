# Logs

Logs são registros gerados por uma aplicação para informar eventos, ações, erros ou comportamentos que ocorreram durante sua execução.

Eles funcionam como um histórico do sistema, permitindo acompanhar o que aconteceu em determinado momento.

## Por que utilizar Logs?

Imagine uma aplicação que apresentou falha durante o processamento de um pagamento.

Sem logs:

```txt
Erro aconteceu
↓
Ninguém sabe o motivo
```

Com logs:

```txt
Erro aconteceu
↓
Log registra o problema
↓
Equipe investiga
↓
Correção realizada
```

Os logs ajudam a entender o comportamento do sistema e identificar problemas rapidamente.

## O que um Log pode registrar?

Exemplos:

* início de processamento;
* finalização de tarefas;
* erros;
* requisições;
* integrações externas;
* autenticações;
* eventos importantes do negócio.

## Exemplo simples

```txt
[08:00] Job iniciado
[08:01] Processando 1.500 registros
[08:02] Job concluído com sucesso
```

## Exemplo de erro

```txt
[08:00] Iniciando integração
[08:01] Erro ao conectar na API
[08:01] Timeout após 30 segundos
```

Essas informações ajudam a identificar a causa da falha.

## Logs em Go

Exemplo utilizando o pacote padrão:

```go
log.Println("Job iniciado")
```

Saída:

```txt
2025/01/01 08:00:00 Job iniciado
```

## Logs em Java

```java
logger.info("Job iniciado");
```

Exemplo:

```java
logger.error("Erro ao processar pagamento", exception);
```

## Níveis de Log

Os sistemas normalmente classificam logs por níveis.

### INFO

Informações sobre o funcionamento normal da aplicação.

Exemplo:

```txt
Usuário autenticado
```

### WARN

Situações incomuns que merecem atenção.

Exemplo:

```txt
API respondeu lentamente
```

### ERROR

Falhas que impediram uma operação.

Exemplo:

```txt
Erro ao processar pagamento
```

### DEBUG

Informações detalhadas utilizadas durante investigação e desenvolvimento.

Exemplo:

```txt
Payload recebido da API
```

## Logs e Automação

Em processos automatizados, os logs são fundamentais para acompanhar a execução.

Exemplo:

```txt
Scheduler dispara
↓
Job iniciado
↓
Worker processa
↓
Logs registram execução
↓
Resultado
```

Sem logs, seria difícil identificar falhas ou confirmar a conclusão do processamento.

## Logs e Retry

Logs possuem uma relação direta com mecanismos de Retry.

Exemplo:

```txt
Tentativa 1
↓
Falha
↓
Log registra erro
↓
Retry
↓
Tentativa 2
```

Os logs permitem entender:

* por que ocorreu a falha;
* quantas tentativas foram realizadas;
* em qual tentativa houve sucesso.

## Boas práticas

### Registrar eventos importantes

Evite registrar informações irrelevantes.

Priorize:

* erros;
* integrações;
* eventos de negócio;
* execuções importantes.

### Utilizar níveis adequados

Use INFO, WARN, ERROR e DEBUG corretamente.

### Facilitar investigações

Os logs devem ajudar alguém a entender o que aconteceu.

### Evitar dados sensíveis

Não registre:

* senhas;
* tokens;
* dados bancários;
* informações pessoais sensíveis.

## Benefícios

* Facilidade de monitoramento;
* Investigação de falhas;
* Auditoria;
* Observabilidade;
* Apoio ao suporte técnico.

## Relação com outros conceitos

Fluxo comum:

```txt
Scheduler
↓
Job
↓
Mensagem
↓
Fila
↓
Worker
↓
Logs
↓
Retry
↓
Resultado
```

Nesse fluxo, os Logs registram tudo o que acontece durante o processamento.

Eles permitem acompanhar execuções, identificar erros e fornecer informações para mecanismos de Retry e monitoramento.

## Resumo

Logs são registros gerados por sistemas para documentar eventos, operações e falhas ocorridas durante a execução de uma aplicação.

Eles são essenciais para monitoramento, investigação de problemas, auditoria e observabilidade, sendo uma das principais ferramentas para entender o comportamento de sistemas em produção.
