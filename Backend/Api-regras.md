# API Regras

Uma *API de Regras* é um tipo de API que implementa regras de negócio para um sistema. Ela recebe entradas, processa com base em regras predefinidas e retorna uma saída conforme essas regras.

Esse tipo de API é útil para separar a lógica de negócio da aplicação principal, garantindo maior flexibilidade de manutenção.

## Características 

- Independente da aplicação: Pode ser usada por diferentes sistemas sem precisar reescrever as regras;
- Baseada em lógica de negócio: Nossas regras podem ser adicionadas sem alterar o código principal da aplicação;
- Facilidade de atualização: Novas regras podem ser adicionadas sem alterar o código principal da aplicação;
- Pode usar um motor de regras: Como drools, OpenL, tablets, ou outras tecnologias específicas para gerenciar regras de forma declarativa.

## Exemplo de uso 

Imagine um sistema de crédito bancário. A API de regras pode decidir se um cliente pode não receber um empréstimo com base em critérios como:

- score de crédito;
- histórico de pagamento
- renda mensal.

A api recebe os dados do cliente e retorna uma resposta como *"Aprovado"* ou *"Reprovado"*, com justificativas baseadas nas regras definidas.
