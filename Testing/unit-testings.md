# Testes Unitários

São testes automatizados que verificam uma pequena unidade isolada de código, geralmente uma função, um método ou uma classe. O objetivo é garantir que essa unidade específica funcione corretamente sob diversas condições.

## Objetivo

Isolar cada parte do código e testar individualmente.

## Benefícios

- Detectar bugs precocemente;
- Facilitar refatoração;
- Servir como documentação do código;
- Melhorar a arquitetura (código testável é geralmente mais modular)

## Princípio FIRST

  - **F** -> **Fast** (rápido): Os testes devem ser rápidos para que possam ser executados com frequência. Testes lentos desmotivam a execução regular.
  - **I** -> **Independent** (independente): Cada teste deve ser independente dos outros. A falha de um teste não deve afetar o resultado de outros.
  - **R** -> **Repeatable** (repetível): Os testes devem reproduzir o mesmo resultado sempre que forem executados, em qualquer ambiente (fatores externos não devem influenciar).
  - **S** -> **Self-Validating** (auto-validável): O teste deve determinar automaticamente se o resultado está correto, sem a necessidade de intervenção manual para verificar o resultado.
  - **T** -> **Timely** (oportuno): Os testes devem ser escritos o mais cedo possível no processo de desenvolvimento, idealmente junto com o código (Test-Driven Development - TDD).

## Estrutura AAA

1. Identificar a unidade a ser testada

Escolha uma função, método ou classe específica que você deseja verificar.

2. Defina o cenário de testes

  Pense em diferentes entradas, condições de contorno e casos de uso para a unidade. Considere: 
  
    - Casos comuns (Happy Path): Entradas válidas que devem produzir o resultado esperado.

    - Casos de borda: Entradas nos limites dos valores válidos ( mínimo, máximo, nulo, vazio)
    
    - Casos Excepcionais (Sad Path): Entradas válidas ou condições de erro que devem levar a um comportamento específico (lançamento de exceções, retorno de erros)

3. Configure o ambiente de teste (Arrange): Prepare os dados de entrada necessários para o teste e qualquer objeto dependente (mocks, stubs)
4. Execute a unidade sob testes (Act): Chame a função, o método ou interaja com a classe que você está testando, fornecendo os dados de entrada preparados.
5. Verifique o resultado (Assert): Use asserções para comparar o resultado real da execução com o resultado esperado. As bibliotecas de teste unitário fornecem várias funções de asserção. (ex: assertEquals, assertTrue, assertFalse, assertThrows)
6. Limpe o ambiente de teste (cleanup-opcional): Se necessário, desfaça qualquer configuração realizada para o teste. (ex: liberar recursos, restaurar o estado)

## Cobertura de testes

É uma métrica que indica a porcentagem do seu código que é exercitada pelos testes unitários. Embora uma alta cobertura não garanta a ausência de bugs, ela pode dar uma indicação de quão bem seu código está sendo testado.

## O que NÃO é um teste unitário?

- Testes que dependem de banco de dados real;
- Testes que fazem chamadas HTTP reais;
- Testes que dependem de APIs externas;
- Testes que precisam de múltiplos serviços funcionando;
- Testes lentos ou altamente acoplados.
