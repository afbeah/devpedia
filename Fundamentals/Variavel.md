# Variável ≠ Variável de Ambiente

Variáveis e variáveis de ambiente possuem objetivos diferentes dentro do desenvolvimento de software.

## Variável

Uma variável é utilizada dentro do código para armazenar dados usados durante a execução do programa.

Ela pode guardar:

- números;
- textos;
- listas;
- objetos;
- resultados de cálculos;
- estados da aplicação.

Exemplo:

```env
const nome = "Beatriz";
```

## Variável de ambiente

Uma variável de ambiente é utilizada para configurar o ambiente de execução da aplicação.

Ela normalmente armazena:

- senhas;
- tokens;
- URLs;
- portas;
- chaves de API;
- configurações do sistema.

Essas variáveis ficam fora do código-fonte.

Exemplo:

```env
DATABASE_URL=postgres://localhost:5432/app
API_KEY=123456
PORT=3000
```

## Principais diferenças
|             Variável          |   	 Variável de ambiente       |
|              :---:            |             :---:               |
|     Existe dentro do código	  |      Existe fora do código      |
|   Armazena dados da aplicação |      Configura o ambiente       |
|  É criada pelo desenvolvedor	|  É definida no sistema/ambiente |
|    Usada durante a execução	  |     Usada para configuração     |

## Por que usar variáveis de ambiente?

- Segurança;
- Flexibilidade;
- Configuração por ambiente;
- Evitar dados sensíveis no código;
- Facilitar deploys.
