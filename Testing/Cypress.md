# Cypress

Cypress é uma ferramenta de testes automatizados utilizada principalmente para testar aplicações web.

Ela permite simular ações reais de usuários, como:

* clicar em botões;
* preencher formulários;
* navegar entre páginas;
* validar informações na tela.

O Cypress é amplamente utilizado para testes End-to-End (E2E), mas também oferece suporte para testes de integração e testes de componentes.

## O que é um teste End-to-End?

Um teste End-to-End (E2E) valida o funcionamento completo de uma funcionalidade, simulando a experiência de um usuário real.

Exemplo:

```txt
Usuário acessa login
↓
Preenche e-mail
↓
Preenche senha
↓
Clica em Entrar
↓
Sistema autentica
↓
Dashboard é exibido
```

O teste verifica todo o fluxo.

## Como o Cypress funciona?

O Cypress executa os testes diretamente no navegador.

Isso permite:

* visualizar a execução;
* inspecionar elementos;
* acompanhar requisições;
* identificar erros com facilidade.

## Exemplo simples

```javascript
describe('Login', () => {

  it('deve realizar login com sucesso', () => {

    cy.visit('/login');

    cy.get('#email')
      .type('usuario@email.com');

    cy.get('#password')
      .type('123456');

    cy.get('button')
      .click();

    cy.contains('Dashboard');
  });

});
```

Nesse exemplo o Cypress:

1. Acessa a página de login;
2. Preenche os campos;
3. Clica no botão;
4. Verifica se a Dashboard foi exibida.

## Principais comandos

### Acessar uma página

```javascript
cy.visit('/login');
```

### Encontrar um elemento

```javascript
cy.get('#email');
```

### Digitar informações

```javascript
cy.type('teste@email.com');
```

### Clicar

```javascript
cy.click();
```

### Validar conteúdo

```javascript
cy.contains('Dashboard');
```

## Benefícios

* Fácil configuração;
* Execução rápida;
* Interface visual amigável;
* Boa documentação;
* Simulação próxima do comportamento real do usuário.

## Limitações

* Focado em aplicações web;
* Consome mais recursos do que testes unitários;
* Testes E2E costumam ser mais lentos que testes unitários.

## Cypress x Testes Unitários

### Teste Unitário

Valida pequenas partes do sistema.

Exemplo:

```txt
Função
↓
Entrada
↓
Saída esperada
```

### Cypress

Valida fluxos completos da aplicação.

Exemplo:

```txt
Login
↓
Autenticação
↓
Dashboard
```

## Quando utilizar?

O Cypress é recomendado para:

* testes de login;
* cadastro de usuários;
* fluxos de compra;
* validação de formulários;
* navegação entre páginas;
* validação de integrações visíveis ao usuário.

## Resumo

Cypress é uma ferramenta de testes automatizados voltada principalmente para testes End-to-End em aplicações web.

Ela permite simular o comportamento real dos usuários, ajudando a garantir que funcionalidades completas continuem funcionando corretamente após alterações no sistema.
