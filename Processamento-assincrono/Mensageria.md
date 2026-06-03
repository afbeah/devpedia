# Mensageria

Mensageria é uma forma de comunicação entre sistemas através da troca de mensagens.

Em vez de um sistema chamar diretamente outro sistema, ele envia uma mensagem para um intermediário responsável por entregar essa informação ao destino correto.

Essa abordagem reduz o acoplamento entre aplicações e aumenta a escalabilidade da arquitetura.

## Por que utilizar Mensageria?

Imagine dois sistemas:

```txt
Sistema A
↓
Sistema B
```

Sem mensageria, o Sistema A depende diretamente do Sistema B.

Se o Sistema B estiver indisponível:

```txt
Sistema A
↓
Falha
↓
Sistema B indisponível
```

Com mensageria:

```txt
Sistema A
↓
Broker
↓
Sistema B
```

A mensagem pode ficar armazenada até que o Sistema B esteja disponível.

## Conceitos principais

### Produtor (Producer)

É o sistema responsável por enviar mensagens.

Exemplo:

```txt
Sistema de Pedidos
↓
Envia mensagem
```

### Consumidor (Consumer)

É o sistema responsável por receber e processar mensagens.

Exemplo:

```txt
Sistema de Notificações
↓
Recebe mensagem
```

### Mensagem

Representa a informação transmitida entre sistemas.

Exemplo:

```json
{
  "orderId": 123,
  "status": "CREATED"
}
```

### Broker

É o intermediário responsável por receber, armazenar e distribuir mensagens.

Exemplos:

* RabbitMQ;
* Kafka;
* Amazon SQS.

## Fluxo de funcionamento

```txt
Producer
↓
Broker
↓
Consumer
```

Exemplo:

```txt
Sistema de Pedidos
↓
RabbitMQ
↓
Worker
↓
Envio de E-mail
```

## Exemplo real

Imagine um e-commerce.

Quando um pedido é criado:

```txt
Pedido criado
↓
Mensagem publicada
↓
Broker
```

Diversos sistemas podem consumir essa informação:

```txt
Pedido criado
↓
Broker
├── Sistema de Estoque
├── Sistema de Pagamento
├── Sistema de Notificação
└── Sistema de Relatórios
```

Cada sistema processa a mesma informação de forma independente.

## Benefícios

* Menor acoplamento;
* Maior escalabilidade;
* Processamento assíncrono;
* Maior resiliência;
* Facilidade de integração entre sistemas.

## Desafios

* Monitoramento das mensagens;
* Controle de falhas;
* Retries;
* Duplicidade de mensagens;
* Complexidade arquitetural.

## Mensageria e Filas

Filas são uma das formas mais comuns de implementar mensageria.

Fluxo:

```txt
Aplicação
↓
Fila
↓
Worker
↓
Processamento
```

A fila armazena mensagens até que um consumidor esteja disponível.

## Mensageria e Workers

Workers frequentemente atuam como consumidores de mensagens.

Exemplo:

```txt
Aplicação
↓
RabbitMQ
↓
Worker
↓
Processamento
```

O Worker permanece aguardando mensagens e as processa conforme chegam.

## Mensageria e Automação

Muitas automações corporativas utilizam mensageria para distribuir tarefas.

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

Nesse modelo, a mensageria permite que os componentes trabalhem de forma desacoplada.

## RabbitMQ x Kafka

### RabbitMQ

Mais utilizado para:

* filas;
* processamento de tarefas;
* comunicação entre aplicações.

### Kafka

Mais utilizado para:

* eventos;
* streaming de dados;
* processamento em larga escala;
* arquiteturas distribuídas.

## Quando utilizar?

Mensageria é recomendada quando:

* sistemas precisam se comunicar;
* existe processamento assíncrono;
* há necessidade de escalabilidade;
* deseja-se reduzir dependências diretas entre aplicações.

## Resumo

Mensageria é um modelo de comunicação entre sistemas baseado na troca de mensagens.

Ela permite que aplicações se comuniquem de forma desacoplada, escalável e resiliente, sendo amplamente utilizada em arquiteturas modernas para integração de serviços, automações e processamento assíncrono.
