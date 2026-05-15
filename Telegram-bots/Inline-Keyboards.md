# Inline Keyboards

No contexto de bots no telegram, um **INLINE KEYBOARD** (ou teclado inline) é um conjunto de botões que aparece acoplado diretamente a uma mensagem, em vez de aparecer como um teclado separado.

### Características
- Ficam dentro da própria mensangem (embaixo dela)
- Não somem após o clique (a menos que isso seja programado)
- Podem disparar ações como:
 - Enviar dados de volta ao Bot (com callback data)
 - Abrir um link externo (com url)
 - Iniciar outra conversa
 - Abrir ym switch inline para outro chat

Ex: Básico em JSON para uso via API do telegram

```bash
{
  "text": "Escolha uma opção:"
  "reply_markup": {
      "inline_keyboard": [
          [
              {"text": "Ver Noticias", "useCallback_data":"Noticias"}
          ],
          [
              {"text": "Loja Oficial", "URL": "Insira a URL"}
          ],
      ]
  }
}
```

**-> Na Prática**

- O usuário clica em um botão.
- O Bot recebe o Callback_data e responde com outra mensagem.
