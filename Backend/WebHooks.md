# WebHooks

Um Webhook é uma forma de uma aplicação enviar informações *automaticamente* para outra aplicação em tempo real, quando um determinado evento acontece.

Pensa nele como um *"retorno de chamada"* (*callback*) baseado em eventos. 

Em vez de um sistema ficar verificando constantemente ("polling") se algo novo aconteceu (como mensagens, pagamentos ou atualizações), o webhook *avisa instantaneamente* seu sistema quando o evento ocorre. 

## Para que serve?

São usados para automatizar comunicações entre sistemas.

Exemplos 

  1. Notificações em tempo real
     
     -> Quando um pagamento é confirmado. (notificação bancária)
     
     -> Quando um formulário é preenchido. (Typeform enviando dados)

  2. Integração entre apps
     
     -> Github envia um alerta para o Slack quando alguém abre um *pull request*
     
     -> Quando um pedido é feito no Shopify, um webhook pode disparar um e-mail de confirmação.

  3. Chatbots e mensagens

     -> Serviços como Whatsapp ou Telegram usam webhooks para repassar mensagens recebidas ao seu sistema.


## Como funciona?

  1. Uma URL é configurada por meio de um endpoint no sistema para receber os dados;
  2. Quando o evento acontece, a aplicação externa *envia um POST* com os dados para essa URL;
  3. O sistema processa a informação.

## Exemplo simples de fluxo

```txt
Usuário faz pagamento
        ↓
Banco confirma pagamento
        ↓
Webhook é disparado
        ↓
Seu sistema recebe os dados
        ↓
Pedido é aprovado automaticamente
```

> IPC:
>
> Webhook ≠ API.
> 
> API
> Realiza uma requisição pra buscar dados
> ("Me dê os novos pedidos")
>
> Webhook
>
> O servidor envia os dados quando algo relevante acontece
> ("Ei, tem um pedido novo")
