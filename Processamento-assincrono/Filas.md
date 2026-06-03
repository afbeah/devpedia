# Filas

Uma **Fila (Queue)** é uma estrutura utilizada para armazenar tarefas, mensagens ou eventos que aguardam processamento.

Ela funciona como uma área intermediária entre quem produz uma tarefa e quem irá executá-la.

## Por que utilizar filas?

Imagine uma aplicação que precisa:

* enviar e-mails;
* gerar relatórios;
* processar pagamentos;
* sincronizar dados.

Executar tudo imediatamente pode deixar o sistema lento.

Com filas, as tarefas são armazenadas e processadas posteriormente.

## Fluxo de funcionamento

```txt
Aplicação
↓
Fila
↓
Worker
↓
Processamento
```

A aplicação envia a tarefa para a fila e continua seu trabalho normalmente.

O Worker processa a tarefa quando estiver disponível.

## Exemplo

Sem fila:

```txt
Usuário realiza cadastro
↓
Sistema salva usuário
↓
Sistema envia e-mail
↓
Sistema gera relatório
↓
Sistema responde usuário
```

Com fila:

```txt
Usuário realiza cadastro
↓
Sistema salva usuário
↓
Tarefa enviada para fila
↓
Sistema responde usuário
```

Depois:

```txt
Fila
↓
Worker
↓
Enviar e-mail
↓
Gerar relatório
```

## FIFO

A maioria das filas segue o princípio FIFO:

> First In, First Out

("Primeiro a entrar, primeiro a sair.")

Exemplo:

```txt
Fila:
[Job 1]
[Job 2]
[Job 3]
```

Ordem de processamento:

```txt
Job 1
↓
Job 2
↓
Job 3
```

## Benefícios

* Desacoplamento entre sistemas;
* Processamento assíncrono;
* Melhor performance;
* Escalabilidade;
* Maior resiliência.

## Filas e Workers

As filas normalmente não executam tarefas.

Elas apenas armazenam mensagens.

Quem realiza o processamento é o Worker.

Fluxo:

```txt
Aplicação
↓
Fila
↓
Worker
↓
Resultado
```

## Filas e Retry

Quando ocorre uma falha, a mensagem pode retornar para a fila.

Exemplo:

```txt
Fila
↓
Worker
↓
Falha
↓
Retry
↓
Fila
↓
Nova tentativa
```

Isso aumenta a confiabilidade do sistema.

## Exemplos de uso

* envio de e-mails;
* geração de PDFs;
* processamento de imagens;
* integração com APIs externas;
* processamento de pagamentos;
* sincronização entre sistemas.

## Tecnologias comuns

* RabbitMQ;
* Kafka;
* Amazon SQS;
* Redis Streams.

## Relação com outros conceitos

Fluxo comum:

```txt
Scheduler
↓
Job
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

Nesse cenário:

* Scheduler define quando executar;
* Job representa a tarefa;
* Fila armazena a tarefa;
* Worker executa a tarefa;
* Logs registram a execução;
* Retry trata falhas;
* Resultado representa a saída do processamento.

## Resumo

Filas são estruturas utilizadas para armazenar tarefas ou mensagens que aguardam processamento.

Elas ajudam a desacoplar sistemas, melhorar performance e permitir processamento assíncrono através de Workers.
