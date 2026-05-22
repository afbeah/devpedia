# Containers

Nada mais é que um ambiente isolado, disposto em um servidor, que divide um único host de controle. Vamos voltar ao exemplo dos containers tradicionais para explicar melhor este conceito.

"um navio cargueiro pode carregar diversos containers dentro. Caso um dos recipientes seja danificado, os demais não são afetados. Afinal, são isolados, protegidos e estão carregando seus próprios produtos"

Trazendo para o mundo do desenvolvimento, cada container possui uma função e sua responsabilidade. Caso um deles sofra um dano, o funcionamento do sistema não para e a função afetada é redirecionada para um novo container.

Em uma máquina virtual tudo roda em um mesmo sistema operacional. Em caso de pane todas as funcionalidades são afetadas.

No caso dos containers, a ideia é que cada um fala apenas uma coisa e assuma uma só responsabilidade. Ou seja, seria um rodando com apache e outro com php, por exemplo.

Desta forma, é possível os processos de cada ferramenta, garantindo que nenhuma atrapalhe o funcionamento da outra.

Para serviços web, por exemplo, os containers deixam a infraestrutura muito mais intercambiável, eficiente e flexível.

> Um container é uma tecnologia que permite empacotar um aplicativo com todas as suas dependências (bibliotecas, configurações, arquivos) em uma única unidade isolada e portátil. Pense nele como uma caixa mágica que contém tudo o que seu software precisa para funcionar, independentemente do ambiente (Windows, Linux, Mac, Nuvem, etc)

## Como funciona?

1. Isolamento: Usa recursos do SO para criar um ambiente isolado;
2. Leveza: Não precisa de um SO completo (diferentes de máquinas virtuais);
3. Portabilidade: Roda igual em qualquer lugar que tenha um Docker ou outro runtime de containers.

## Por que usar?

- Consistência: Funciona igual no pc e na nuvem;
- Eficiência: Otimiza recursos do sistema;
- DevOps: Facilita CI/CD e escalabilidade.

## O que tem dentro de um container?

- Aplicação (node, python)
- Dependências (bibliotecas, frameworks)
- Configurações (variáveis de ambientes, arquivos)
- Metadados (como executar, portas)
