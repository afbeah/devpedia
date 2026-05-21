# Cors

*Cross-Origin Resource Sharing* é um mecanismo de segurança implementado pelos navegadores para controlar como os recursos de uma página web podem ser acessados por outro domínio diferente daquele que a originou.

## Explicando de forma simples...

- Domínios diferentes: Imagine que você esta visitando um site (*dominio A*), mas esse site precisa buscar dados para outro servidor (*dominio B*). Por padrão, os navegadores bloqueiam essas solicitações para garantir que seu navegador não interaja com fontes potencialmente inseguras.
- Cors permite exceções: Com o Cors, o servidor do *dominio B* pode configurar permissões para permitir que o site do *dominio A* acesse seus recursos de forma segura.

## Exemplo prático...

Se você estiver no site MEUSITE.com e ele precisa carregar dados de API.EXEMPLO.com permite que MEUSITE.com acesse seus dados. Isso é feito através de cabeçalhos HTTP específicos (como Access-Control-Allow-Origin). Se as permissões estiverem configuradas corretamente, o navegador permite a comunicação; caso contrário, bloqueia a requisição.

## Para que serve o Cors?

- Segurança: Evita que páginas maliciosas carreguem recursos de outros sites sem permissão;
- Controle: Permite que os Devs definam de forma segura quais sites podem acessar os recursos de seu servidor.

### Em resumo...

... Cors é uma maneira de controlar o acesso entre diferentes sites para proteger seus dados e garantir que apenas sites autorizados possam interagir com o servidor.

> é uma regra de segurança dos navegadores que impede que um site pegue informação de outro site sem permissão.
