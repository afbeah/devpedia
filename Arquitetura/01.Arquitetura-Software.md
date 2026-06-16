# Arquitetura de Software

Arquitetura de Software é a forma como um sistema é estruturado e organizado para atender requisitos funcionais e não funcionais.

Ela define como os componentes de uma aplicação se relacionam, se comunicam e evoluem ao longo do tempo.

Em outras palavras:

> Arquitetura é o conjunto de decisões que define como um sistema será construído.

## Por que Arquitetura é importante?

Todo software resolve um problema.

Porém, conforme o sistema cresce, surgem novos desafios:

* manutenção;
* escalabilidade;
* desempenho;
* segurança;
* integração;
* evolução do produto.

A arquitetura ajuda a organizar a solução para lidar com esses desafios.

## Uma analogia simples

Imagine a construção de uma casa.

Antes de levantar as paredes, existe um projeto definindo:

* quantidade de cômodos;
* localização das portas;
* instalações elétricas;
* encanamento.

Na engenharia civil isso é chamado de arquitetura.

No desenvolvimento de software acontece algo parecido.

Antes de implementar funcionalidades, é necessário definir como o sistema será organizado.

## O que a Arquitetura define?

Uma arquitetura normalmente define:

### Estrutura do sistema

Como a aplicação será dividida.

Exemplo:

```txt id="vjwbef"
Frontend
↓
API
↓
Banco de Dados
```

### Comunicação

Como os componentes trocam informações.

Exemplo:

```txt id="95a6ui"
API REST

Mensageria

Eventos

Filas
```

### Organização do código

Como responsabilidades serão distribuídas.

Exemplo:

```txt id="r3wznn"
Controller
↓
Service
↓
Repository
```

### Fluxo de dados

Como as informações percorrem o sistema.

Exemplo:

```txt id="ntv2l4"
Usuário
↓
API
↓
Banco
↓
Resposta
```

## Objetivos da Arquitetura

Uma boa arquitetura busca:

* facilitar manutenção;
* reduzir complexidade;
* melhorar escalabilidade;
* aumentar reutilização;
* permitir evolução do sistema.

## Arquitetura x Código

Esses conceitos costumam ser confundidos.

### Código

Resolve uma funcionalidade.

Exemplo:

```java
calculatePrice();
```

### Arquitetura

Define onde essa funcionalidade deve estar e como ela se relaciona com o restante do sistema.

## Arquitetura e Clean Code

Clean Code preocupa-se com:

```txt id="76yx8x"
Como escrever código
```

Arquitetura preocupa-se com:

```txt id="jqkk9q"
Como organizar o sistema
```

Os dois conceitos se complementam.

## Arquitetura e SOLID

SOLID ajuda a criar componentes mais organizados.

A arquitetura utiliza esses componentes para construir sistemas maiores.

Fluxo:

```txt id="7dptcx"
SOLID
↓
Componentes bem estruturados
↓
Arquitetura
↓
Sistema organizado
```

## Arquiteturas comuns

Existem diversos estilos arquiteturais.

### Monolito

Toda a aplicação está em um único sistema.

```txt id="7vx6u4"
Frontend
+
Backend
+
Banco
```

### Microsserviços

O sistema é dividido em serviços independentes.

```txt id="4y9mb5"
Usuários
Pedidos
Pagamentos
Notificações
```

### Event Driven

Os componentes se comunicam através de eventos.

```txt id="4i1c1s"
Evento
↓
Fila
↓
Consumer
```

### Clean Architecture

Organiza o sistema em camadas e separa regras de negócio da infraestrutura.

## Arquitetura e Escalabilidade

À medida que o sistema cresce, a arquitetura torna-se cada vez mais importante.

Exemplo:

```txt id="i8s4s0"
10 usuários
↓
Arquitetura simples
```

```txt id="smlt54"
10 milhões de usuários
↓
Arquitetura robusta
```

A mesma solução pode não funcionar em cenários diferentes.

## Arquitetura e Processamento Assíncrono

Conceitos como:

* Scheduler;
* Job;
* Worker;
* Mensageria;
* Filas;
* Retry;

também fazem parte de decisões arquiteturais.

Exemplo:

```txt id="56fbp5"
Scheduler
↓
Job
↓
Fila
↓
Worker
```

Essa é uma escolha de arquitetura para processamento assíncrono.

## Características de uma boa arquitetura

Uma boa arquitetura normalmente é:

* simples;
* compreensível;
* escalável;
* flexível;
* testável;
* fácil de manter.

## Arquitetura NÃO é

Arquitetura não significa:

* utilizar muitas tecnologias;
* criar sistemas complexos;
* adicionar camadas desnecessárias;
* seguir padrões sem necessidade.

Uma arquitetura simples pode ser excelente.

## Resumo

Arquitetura de Software é a forma como um sistema é estruturado e organizado.

Ela define como os componentes se relacionam, como os dados circulam e como a aplicação pode evoluir ao longo do tempo.

Seu principal objetivo é criar sistemas que sejam sustentáveis, escaláveis e fáceis de manter conforme crescem.
