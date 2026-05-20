# cURL

curl é uma ferramenta de linha de comando utilizada para realizar transferências de dados e requisições entre clientes e servidores.

O nome cURL significa Client URL.

Ela é amplamente utilizada por:

- desenvolvedores;
- administradores de sistemas;
- engenheiros DevOps;
- profissionais de redes.

## Para que serve?

O cURL pode ser utilizado para:

- testar APIs;
- fazer requisições HTTP;
- baixar arquivos;
- enviar dados;
- testar conectividade;
- automatizar tarefas de rede.

## Protocolos suportados

O cURL suporta diversos protocolos, incluindo:

- HTTP e HTTPS;
- FTP e FTPS;
- SFTP;
- SCP;
- SMTP e SMTPS;
- LDAP e LDAPS;
- IMAP;
- POP3;
- Telnet.

## Sintaxe básica

```bash
curl [opções] [url]
```
Exemplo:

```bash
 curl https://api.github.com
```

## Downloads de arquivos

 ```bash
 curl -O arquivo.zip
```
Salva o arquivo com o mesmo nome original.

```bash
curl -o meu-arquivo.zip arquivo.zip
```
Permite definir outro nome para o arquivo.

## Casos de uso

- Testes de APIs REST;
- Automação;
- Integração entre sistemas;
- Download de arquivos;
- Debug de requisições HTTP;
- Scripts DevOps.
