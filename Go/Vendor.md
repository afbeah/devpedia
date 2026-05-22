# Vendor

A pasta vendor é um diretório criado para armazenar cópias locais das dependências utilizadas pelo projeto. Essas dependências são as bibliotecas, frameworks e outros pacotes que o projeto utiliza para funcionar corretamente. Em vez de baixar essas dependências diretamente de um repositório externo toda vez que alguém clona um projeto, elas são copiadas para a pasta vendor e versionadas junto com o código do projeto.

- Tamanho: A pasta vendor pode se tornar muito grande, especialmente em projetos com muitas dependências, o que aumentaria significativamente o tamanho do repositório;
- Redundância: As dependências podem ser facilmente instaladas novamente a partir do arquivo de configuração do gerenciador de pacotes;
- Flexibilidade: Ignorar a pasta vendor permite que cada desenvolvedor tenha a sua própria cópia das dependências, o que pode ser útil em alguns cenários.

A pasta VENDOR é uma ferramenta essencial para gerenciar as dependências de um projeto. Ela garante a reprodutibilidade, o isolamento e a otimização do desenvolvimento. Embora seja importante para o projeto, ela geralmente é ignorada no controle de versão para manter o repositório mais limpo e eficiente.

## Para que serve?

A pasta vendor ajuda a:

- garantir reprodutibilidade;
- evitar dependência de downloads externos;
- facilitar builds;
- manter versões consistentes;
- isolar dependências do projeto.

## Como funciona?

Em alguns ecossistemas, as dependências baixadas são copiadas para a pasta vendor.

Exemplos:
  - Go (go mod vendor);
  - PHP (Composer);
  - Ruby (Bundler).

## Benefícios

- Builds reproduzíveis;
- Dependências locais;
- Maior estabilidade;
- Controle de versões específicas;
- Facilidade em ambientes isolados.
  
## Desvantagens

- Repositório maior;
- Mais arquivos versionados;
- Possível redundância;
- Atualizações mais pesadas.


## Vendor e .gitignore

Dependendo do projeto, a pasta vendor pode:
  - ser versionada;
  - ou ignorada no .gitignore.

Isso varia conforme:
  - linguagem;
  - estratégia da equipe;
  - pipeline;
  - ambiente de deploy.

## Exemplo no Go

```go
go mod vendor
```

Esse comando copia as dependências do projeto para a pasta vendor.
