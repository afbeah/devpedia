# Grafana

Imagine que você tem muitos dados, com métricas de servidores, informações de tráfego de um site ou até mesmo de métricas de sensores. É difícil entender tudo isso apenas olhando para números. O *Grafana* é uma plataforma de código aberto que transforma esses números em gráficos e painéis interativos e fáceis de ler.

Ele funciona como um *"tradutor visual"* dos seus dados. Em vez de uma tabela gigante, veremos painéis com gráficos, medidores, mapas e alertas. Isso te ajuda a entender rapidamente o que está acontecendo no seu sistema. 

## Principais conceitos do Grafana

1. Fonte de dados (Data Source)

   É de onde o Grafana pega os dados. Ele não armazena os dados, apenas se conecta a outras ferramentas que fazem isso.

   *Exemplo*: Prometheus, InfluxDB, ElasticSearch ou até mesmo banco de dados PostgreSQL.

2. Painel (Dashboard)

   É a "tela principal", onde organiza os gráficos e informações. Pode ter um painel para monitorar o desempenho dos seus servidores, outro para as vendas de e-commerce, e assim por diante.

3. Painel (panel)

   É o componente individual dentro de um painel. Cada painel mostra um tipo de visualização, como um gráfico de linha, um gráfico de setores ou uma tabela.

4. Alerta (Alert)

   Um das funções mais poderosas. Você pode configurar regras para que o Grafana te avise quando algo sai do padrão.

   *Exemplo*: "Me avise se o uso da CPU de um servidor passar de 90% por mais de 5 minutos".

## Por quê o Grafana é tão popular?

- Flexibilidade: Ele se conecta a uma grande variedade de fontes de dados.
- Visualização Poderosa: Os painéis são altamente personalizáveis e bonitos.
- Comunidade: Por ser de código aberto, tem uma comunidade enorme que cria plugins e novos painéis o tempo todo.
- Gratuito: A versão principal é de código aberto e gratuita.
- Alertas: A capacidade de configurar alertas proativamente é crucial para a operação de sistemas.

## Grafana != Power Bi

O *Grafana* é uma ferramenta **focada em dados operacionais**, ou seja, dados que mudam rapidamente e precisam de monitoramento contínuo. Ele nasceu para atender engenheiros, desenvolvedores e administradores de sistemas que precisam acompanhar métricas em tempo real.

O *Power bi*, da Microsoft, é uma ferramenta **focada em dados de negócios e relatórios estratégicos**. Ele foi desenvolvido para analisar dados, gerentes e executivos que precisam tomar decisões baseadas em informações históricas e estatísticas.

Em poucas palavras: Se precisa monitorar a "saúde" de um sistema em tempo real use o Grafana. Se precisa entender o "porquê" das métricas de negócio e fazer análises estratégicas, o Power Bi é a escolha ideal. Eles não são concorrentes diretos, mas sim ferramentas complementares para diferentes necessidades de uma organização. 

## Ferramentas que normalmente trabalham junto com Grafana

- Prometheus → métricas;
- Loki → logs;
- Tempo → tracing;
- Elasticsearch → busca e análise de logs;
- PostgreSQL → dados relacionais.
