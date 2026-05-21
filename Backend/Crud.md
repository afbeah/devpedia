# CRUD

É um conceito fundamental no desenvolvimento de software e bancos de dados. O termo vem do inglês e representa as quatro operações básicas de persistência de dados. 

- **C**:  *CREATE* (criar) - Inserir novos dados em um banco ou sistema.
  > Cadastrar um novo usuário.
- **R**: *READ* (ler) - Consultar, listar ou recuperar dados armazenados.
  > listar todos os livros de uma biblioteca digital.
- **U**: *UPDATE* (atualizar) - Alterar informações já existentes.
  > atualizar o endereço de um cliente.
- **D**: *DELETE* (excluir) - Remover dados do sistema.
  > excluir uma publicação ou conta de usuário.

Em um banco de dados relacional, cada operação *CRUD* corresponde a um comando SQL.

- CREATE = INSERT INTO;
- READ = SELECT;
- UPDATE = UPDATE;
- DELETE - DELETE FROM.

No desenvolvimento web, o *CRUD* costuma ser mapeado para os métodos http.

- POST -> CREATE;
- GET -> READ;
- PUT/PATCH -> UPDATE;
- DELETE -> DELETE;

Praticamente toda aplicação que lida com dados implementa operações *CRUD* de alguma forma. É a base de sistemas como redes sociais, e-commerce, ERPs, APIs REST, etc...
