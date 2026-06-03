# Scheduler

Um **Scheduler** é um mecanismo responsável por agendar a execução de tarefas em horários ou intervalos específicos.

Seu objetivo é automatizar processos que precisam ocorrer de forma periódica ou programada.

O Scheduler não executa a tarefa diretamente. Ele apenas determina quando ela deve ser iniciada.

## Por que utilizar um Scheduler?

Imagine uma aplicação que precisa:

* gerar relatórios diariamente;
* realizar backups;
* sincronizar dados;
* enviar notificações;
* atualizar informações entre sistemas.

Executar essas tarefas manualmente seria inviável.

O Scheduler permite que elas sejam executadas automaticamente.

## Como funciona?

O Scheduler monitora regras de agendamento.

Quando o horário ou condição configurada é atingido, ele dispara a execução da tarefa.

Exemplo:

```txt id="8ojyy7"
08:00
↓
Scheduler dispara
↓
Job de geração de relatório
```

Outro exemplo:

```txt id="o93hdf"
00:00
↓
Scheduler dispara
↓
Job de backup
```

## Exemplos de agendamento

### Horário específico

```txt id="zfhgdx"
Todo dia às 08:00
```

### Intervalo fixo

```txt id="dcbyv1"
A cada 5 minutos
```

### Agendamento semanal

```txt id="zt7ggu"
Toda segunda-feira às 09:00
```

### Agendamento mensal

```txt id="u3t1hv"
Primeiro dia de cada mês
```

## Scheduler x Job

Esses conceitos costumam ser confundidos.

### Scheduler

Define quando uma tarefa deve ser executada.

Exemplo:

```txt id="3y4jyo"
Todo dia às 00:00
```

### Job

Representa a tarefa que será executada.

Exemplo:

```txt id="zmknhn"
Gerar relatório
```

Fluxo:

```txt id="f4v3lk"
Scheduler
↓
Dispara
↓
Job
```

## Scheduler x Worker

### Scheduler

Responsável pelo agendamento.

### Worker

Responsável pela execução.

Fluxo:

```txt id="iqk8ta"
Scheduler
↓
Job
↓
Fila
↓
Worker
```

O Scheduler define o momento.

O Worker realiza o trabalho.

## Ferramentas comuns

### Cron

Muito utilizado em sistemas Linux.

Exemplo:

```txt id="2d9fd7"
0 8 * * *
```

Executa uma tarefa todos os dias às 08:00.

### Kubernetes CronJob

Permite agendar tarefas em ambientes Kubernetes.

### Quartz Scheduler

Biblioteca bastante utilizada em aplicações Java.

### Cloud Schedulers

Serviços de nuvem que permitem agendamentos gerenciados.

Exemplos:

* Google Cloud Scheduler;
* AWS EventBridge;
* Azure Scheduler.

## Benefícios

* Redução de tarefas manuais;
* Execuções previsíveis;
* Automação de processos recorrentes;
* Maior produtividade;
* Menor risco de esquecimento.

## Desafios

* Controle de falhas;
* Monitoramento das execuções;
* Dependência do ambiente de agendamento;
* Gerenciamento de concorrência.

## Relação com outros conceitos

Em sistemas modernos, o Scheduler normalmente faz parte de um fluxo maior:

```txt id="hwg85j"
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

Nesse fluxo:

* Scheduler define quando executar;
* Job representa a tarefa;
* Fila armazena o trabalho;
* Worker processa;
* Logs registram a execução;
* Retry trata falhas.

## Exemplos de uso

* geração de relatórios;
* backups automáticos;
* sincronização de dados;
* limpeza de arquivos temporários;
* envio de notificações;
* atualização de métricas.

## Resumo

Scheduler é um mecanismo responsável por agendar a execução de tarefas.

Seu papel é definir quando uma atividade deve ocorrer, permitindo a automação de processos recorrentes e servindo como ponto inicial de diversos fluxos automatizados.
