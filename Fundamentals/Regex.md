# Regex

*Expressão regular* é uma forma de descrever padrões de texto usando uma linguagem especial.

Ou seja, em vez de procurar por um texto fixo, você pode procurar *padrões*.

- "Qualquer número"
- "Qualquer sequência de letras"
- "Um e-mail válido"
- "Sequência com o mesmo número repetido"
- e mais...

## Onde Regex é usado?

- Validação de formulários;
- Busca de padrões;
- APIs;
- Backend;
- Banco de dados;
- Logs;
- Segurança;
- Parsing de texto.

## Exemplo

|       Padrão      |      Regex     |        Significado         |
|       :---:       |      :---:     |           :---:            |
|      Um número    |       \d       |  Qualquer digito de 0-9    |
|      Uma letra    |     [a-zA-Z]   | Qualquer letra min ou maiu | 
|    3n° seguidos   |      \d{3}     |    Exatamente 3 digitos    |
| 1n° repetido 10x  |  ^(\d)\1{9}$   |       1 mesmo n° 10x       |
|   e-mail simples  | ^\S+@\S+\.\S+$ |      Texto@texto.texto     |

### Resumindo
> Regex = forma de procurar padrões em texto (não valores fixos)

**/^(\d)\1{10,13}$/**

-> Lê-se assim:

**^** = começo do texto
**(\d)** = um dígito (0-9) que será "guardado"
**\1{10,13}** = repete o mesmo digito de antes, de 10 até 13x
**$** = final do texto
