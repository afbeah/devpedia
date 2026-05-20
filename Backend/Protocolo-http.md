# Protocolos HTTP

São usados para indicar a ação que deve ser usada em um recurso específico da web.

1. GET: Recupera dados do servidor.
  - Utilizado para buscar informações sem alterar o estado do recurso. (*ex: pegar dados de um banco de dados*)
    - GET /usuarios/1 HTTP/1.1
    
2. POST: Envia dados ao servidor para criar um novo recurso.
  - Usados para criar novos recursos (*ex: adicionar um novo usuário ao banco de dados*)
    - POST /usuarios HTTP/1.1
    - Content-Type: application/json
      
    ```bash
     {
       "nome":"João",
       "e-mail":"joao@example.com"
     }
    ```

3. PUT: Envia dados ao servidor para atualizar um recurso existente.
  - Usado para atualizar completamente um recurso existente (*ex: atualizar as informações de um usuário*)
    - PUT / usuarios/1 HTTP/1.1
    - Content-Type: application/json

    ```bash
    {
      "nome": "joão",
      "e-mail": "joao@example.com"
    }
    ```

4. PATCH: Envia dados ao servidor para atualizar parcialmente um recurso.
   - Usado para fazer atualizações parciais em um recurso (*ex: Usado para atualizar parcialmente um recurso existente*)
   - PATCH /usuarios/1 HTTP/1.1
   - Content-Type: application/json

   ```bash
   {
     "e-mail": "joao.silva@example.com"
   }
   ```

5. DELETE: Remove um recurso do servidor.
   - Usado para deletar um recurso (*ex: remover um usuário do banco de dados*)
   - DELETE/USUARIOS/1 http/1.1
  
6. HEAD: Recupera os cabeçalhos da resposta sem o corpo.
   - Usado para verificar o que um GET retornaria sem transferir o corpo da resposta. Útil para verificar se um recurso existe ou checar suas metainformações.
   - HEAD /usuarios/1 HTTP/1.1

7. OPTIONS: Descreve as opções de comunicação com o recurso.
    - Usado para determinar os métodos http que o servidor suporta para um recurso específico
    - OPTIONS /usuarios/1 HTTP/1.1

8. TRACE: Realiza um teste loop-back de mensagem ao longo do a caminho até o recurso.
   - Usado para fins de diagnósticos
   - TRACE /usuarios HTTP/1.1

9. CONNECT: Estabelece um túnel para o servidor identificado pelo recurso.
    - Usado principalmente com proxies que podem se transformar em túneis http/TLS.
    - CONNECT www.example.com:443 http/1.1

Esses métodos ajuda a definir a ação que será realizada. Ao interagir com um servidor e manipular seus recursos dependendo do método, o servidor sabe como lidar com a requisição e que tipo de resposta retornar.

> O protocolo de comunicação http serve para habilitar a transferência de informações entre clientes e servidores conectados na web

### Métodos mais usados no desenvolvimento web

|   Método   |           Objetivo         |
|   :---:    |            :---:           |
|    GET     |          Buscar dados      |
|    POST	   |         Criar recurso      |
|    PUT	   |   Atualizar completamente  |
|   PATCH	   |    Atualizar parcialmente  |
|   DELETE	 |      Remover recurso       |

### Status HTTP comuns
|  Código  | 	      Significado      |
|  :---:   |         :---:           |
|   200    |           OK            |
|   201	   |         Criado          |
|   400	   |       Bad Request       |
|   401	   |       Unauthorized      |
|   404	   |        Not Found        |
|   500    |	 Internal Server Error |

## Resumindo

O protocolo http tem o funcionamento padrão de comunicação no molde cliente-servidor. Os clientes (navegadores ou aplicações web) fazem solicitações aos servidores, que retornam as requisições feitas.

Em termos de fluxo, o cliente envia uma solicitação com métodos http específicos para o servidor, além de caminhos e informações adicionais. Vale destacar que cada método corresponde a uma requisição específica.

O servidor então processa a solicitação e envia códigos numéricos (STATUS HTTP) como resposta para indicar se a requisição foi recebida e a ação foi executada, se houve algum tipo de erro ou se mais ações são necessárias. 

Importante frisar que versões do protocolo http mais recente apresentam melhorias de desempenho e segurança durante a navegação, embora o conceito de comunicação cliente-servidor seja o mesmo.
