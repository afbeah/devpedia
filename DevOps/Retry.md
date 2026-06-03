# Retry

Retry é uma estratégia utilizada para tentar executar novamente uma operação que falhou.

Seu objetivo é aumentar a confiabilidade dos sistemas, permitindo que falhas temporárias sejam resolvidas sem intervenção manual.

## Por que utilizar Retry?

Nem toda falha é permanente.

Muitos erros acontecem por motivos temporários, como:

* indisponibilidade momentânea de uma API;
* problemas de rede;
* timeout de comunicação;
* sobrecarga de serviços;
* falhas temporárias de banco de dados.

Nesses casos, uma nova tentativa pode resolver o problema.

## Exemplo

Imagine que um sistema precisa enviar um e-mail.

Primeira tentativa:

```txt
Enviar e-mail
↓
Falha
↓
API indisponível
```

Com Retry:

```txt
Tentativa 1
↓
Falha
↓
Retry
↓
Tentativa 2
↓
Sucesso
```

O processamento é concluído sem necessidade de ação manual.

## Como funciona?

Quando ocorre uma falha considerada temporária:

```txt
Operação
↓
Falha
↓
Retry
↓
Nova tentativa
```

O sistema tenta executar novamente a mesma operação.

## Número de tentativas

É comum definir um limite para evitar tentativas infinitas.

Exemplo:

```txt
Tentativa 1
↓
Falha

Tentativa 2
↓
Falha

Tentativa 3
↓
Falha

Processamento encerrado
```

Após atingir o limite configurado, o sistema registra a falha.

## Retry Imediato

A nova tentativa ocorre logo após a falha.

```txt
Falha
↓
Retry imediato
↓
Nova tentativa
```

É simples, mas pode gerar sobrecarga caso o serviço ainda esteja indisponível.

## Retry com Delay

O sistema aguarda um período antes de tentar novamente.

```txt
Falha
↓
Aguardar 30 segundos
↓
Retry
```

Essa abordagem costuma ser mais segura.

## Exponential Backoff

Uma estratégia comum é aumentar o tempo de espera a cada tentativa.

Exemplo:

```txt
Tentativa 1 → 5 segundos

Tentativa 2 → 10 segundos

Tentativa 3 → 20 segundos

Tentativa 4 → 40 segundos
```

Isso reduz a pressão sobre sistemas que já estão enfrentando problemas.

## Retry e Logs

Toda tentativa deve ser registrada.

Exemplo:

```txt
[08:00] Tentativa 1 falhou
[08:00] Iniciando Retry
[08:01] Tentativa 2 executada
[08:01] Operação concluída
```

Os logs ajudam a entender:

* quantidade de tentativas;
* motivo das falhas;
* tempo até a recuperação.

## Retry e Filas

Em sistemas baseados em filas, uma mensagem pode retornar para processamento após uma falha.

Fluxo:

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

Essa abordagem aumenta a resiliência do sistema.

## Retry e Workers

Workers frequentemente utilizam Retry para lidar com falhas temporárias.

Exemplo:

```txt
Worker
↓
Chama API externa
↓
Timeout
↓
Retry
↓
Sucesso
```

Sem Retry, a tarefa seria perdida ou exigiria intervenção manual.

## Quando utilizar Retry?

Retry é recomendado para falhas temporárias.

Exemplos:

* timeout;
* indisponibilidade momentânea;
* falha de rede;
* limitação temporária de recursos.

## Quando evitar Retry?

Nem toda falha deve ser repetida.

Exemplos:

```txt
CPF inválido
E-mail inválido
Dados obrigatórios ausentes
Regra de negócio violada
```

Nesses casos, repetir a operação não resolverá o problema.

## Benefícios

* Maior confiabilidade;
* Recuperação automática;
* Menor necessidade de intervenção manual;
* Melhor experiência para usuários;
* Maior resiliência dos sistemas.

## Desafios

* Controle do número de tentativas;
* Sobrecarga de serviços;
* Processamentos duplicados;
* Monitoramento das falhas.

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

Nesse fluxo:

* Scheduler define quando executar;
* Job representa a tarefa;
* Fila armazena o trabalho;
* Worker executa;
* Logs registram a execução;
* Retry tenta recuperar falhas temporárias.

## Exemplo real

Imagine uma integração com um sistema externo.

```txt
Scheduler dispara
↓
Job de sincronização
↓
Fila
↓
Worker
↓
API indisponível
↓
Log registra erro
↓
Retry
↓
Nova tentativa
↓
Sincronização concluída
```

Sem Retry, a sincronização falharia completamente.

## Resumo

Retry é uma estratégia utilizada para repetir automaticamente operações que falharam devido a problemas temporários.

Ele aumenta a confiabilidade e a resiliência dos sistemas, permitindo recuperação automática de falhas sem necessidade de intervenção manual.
