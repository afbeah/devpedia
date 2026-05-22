# Logs

  São registros estruturados ou textuais que documentam acontecimentos, comportamentos, erros e estados de uma aplicação, sistema ou serviço ao longo do tempo. Log não é só *"uma mensagem no console"*, é uma fonte de observabilidade do sistema.

  Eles servem para responder perguntas como:

  - O que aconteceu?
  - Quando aconteceu?
  - Em qual parte do sistema aconteceu?
  - Com qual usuário, requisição ou processo aconteceu?
  - Deu certo ou deu errado?
  - Qual era o contexto naquele momento?

## Para que servem os logs?

  As funcionalidades mais comuns dos logs em um projeto são:

  1. Identificar erros.

     Quando algo quebra, o log ajuda a descobrir:

       - Onde aconteceu?
       - Em que momento?
       - Qual foi a causa?
       - Qual stack trace foi gerada?

     ex: *falha ao conectar no banco*, *erro ao salvar usuário*, *token inválido*, *timeout em API externa*

  2. Acompanhar o fluxo da aplicação
 
     É possível ver o caminho que uma execução percorreu.
     ex:
       - Requisição recebida;
       - Validação iniciada;
       - Usuário encontrado;
       - Pagamento processado;
       - Resposta enviada.

  3. Monitoramento e observabilidade

     Logs ajudam equipes a monitorarem sistemas em produção.
     ex:
       - Quantos erros aconteceram hoje?
       - Quais endpoints falham mais?
       - Qual serviço está mais lento?
       - Qual evento aconteceu antes de uma queda?

  4. Auditoria e rastreabilidade

     Em muitos sistemas, é importante registrar ações importantes.
     ex:
       - Usuário x alteração de senha;
       - Administrador deletou um registro;
       - Contrato aprovado;
       - Pagamento estornado.

  5. Debug e manutenção

     Durante o desenvolvimento, logs ajudam a enxergar o estado interno da aplicação
     ex:
       - Valor de uma variável;
       - retorno de uma function;
       - conteúdo de um response da API;
       - etapa onde o código parou.

  6. Apoiar decisões técnicas e de negócios

     Logs também podem mostrar padrões de uso.
     ex:
       - Qual funcionalidade é mais usada;
       - Qual tela tem mais falhas;
       - Em qual etapa usuários abandonam um fluxo.

## Onde encontrar logs?

  Depende muito de onde a aplicação está rodando:

  1. No Console/ Terminal

     Durante o desenvolvimento é o lugar mais comum.
     ex:
       - console.log() - JavaScript;
       - fmt.Println() - Go;
       - System.out.println() - Java;
       - log.println() - Go.
    
  2. Em arquivos.log

     Muitas aplicações gravam logs em arquivos.
     ex:
       - app.log;
       - error.log;
       - access.log.

     Esses arquivos podem ficar:
       - dentro de diretórios específicos do sistema;
       - dentro da pasta do projeto;
       - no servidor.

  3. Em plataformas de nuvem

     Quando a aplicação está em produção, os logs costumam ir para serviços centralizados.
     ex:
       - logs do Docker;
       - logs do Kubernetes;
       - AWS CloudWatch Logs;
       - logs do Google Cloud;
       - logs do Azure.

  4. Em ferramentas de monitoramento e observabilidade

     Empresas costumam usar ferramentas específicas para coletar, armazenar, buscar e visualizar logs.
     ex:
       - ElasticSearch + Kibana;
       - Grafana Loki;
       - Datadog;
       - Splunk;
       - New Relic.

  5. Em servidores web e proxies

     Além dos logs da aplicação, existem logs de infra.
     ex:
       - Nginx;
       - Apache;
       - Load Balancer;
       - Banco de dados;

## Como é composto um log

   Um log geralmente tem alguns elementos básicos:

   - Timestamp: Quando aconteceu?:
   - Nível do log: Gravidade/Importância;
   - Mensagem: O que aconteceu?
   - Origem: Arquivo/ Classe/ Módulo/ Serviço;
   - Contexto: Dados adicionais;
   - Identificador de correlação: ID da requisição, ID do usuário, ID da transação.

## Exemplo

- 2026-04-02 10:15:23 INFO SERVICE - Usuário criado com sucesso.
  UserID - 42

## Níveis de log

|    Nível   |          	Uso          |
|    :---:   |           :---:         |
|    INFO    |      Eventos normais    |
|    WARN    |  Situações inesperadas  |
|    ERROR   |         Falhas          |
|    DEBUG   |  Informações detalhadas | 
|    TRACE   |  Rastreamento profundo  |
|    FATAL   |       Erro crítico      |


## Logs estruturados

```JSON
{
  "timestamp": "2026-04-02T10:15:23Z",
  "level": "INFO",
  "service": "user-service",
  "message": "Usuário criado com sucesso",
  "userId": 42
}
```

## Boas práticas

- Não logar senhas;
- Não expor tokens;
- Padronizar formato;
- Usar níveis corretamente;
- Adicionar contexto útil;
- Utilizar correlation IDs.

  
