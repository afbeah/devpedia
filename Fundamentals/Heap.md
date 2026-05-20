# Heap

Pode se referir a duas coisas principais, dependendo do contexto, mas no mundo da ciência da computação, ele geralmente se refere a uma *estrutura de dados*.

1. Heap como estrutura de dados (mais comum)

Em ciência da computação, um *heap* é um tipo de *árvore binária* completa especializada que satisfaz a *propriedade de heap*.

- As principais características são:

  - Árvore Binária Completa

  É uma árvore onde todos os nivéis estão completamente preenchidos, exceto, possivelmente, o último, que é preenchido da esquerda para a direita.

  - Propriedade de Heap

  Define a relação de ordem entre um nó e seus filhos. 

    - Max-Heap (máximo): O valor de cada nó é maior ou igual ao valor de seus filhos. Isso garante que o maior elemento esteja sempre na raíz. (o topo da árvore)
    - Min-Heap (mínimo): O valor de cada nó é menor ou igual ao valor de seus filhos. Isso garante que o menor elemento esteja sempre na raíz.
    - Aplicações comuns:

      -> Implementação de filas de prioridade (priority queues);

      -> Usado no algoritmo de Heap Sort;

      -> Usado em algoritmos de caminho mínimo, como Dijkstra.

2. Heap como area de memória

Em gerenciamento de memória de um programa de computador, Heap (monte) é uma região de memória usada para alocação dinâmica. 

  - Alocação dinâmica: O programador solicita memória em tempo de execução para armazenar dados cujo o tamanho ou tempo de vida não é conhecido no momento da compilação (*ex: listas encadeadas, objetos grandes*);
  - Flexibilidade: Ao contrário da *stack* (pilha) que gerencia automaticamente chamadas de função e variáveis locais, a dependendo da linguagem, a memória pode precisar ser gerenciada manualmente ou automaticamente por um garbage collector.
  - Fragmentação: O heap é conhecido por poder se tornar fragmentado com muitas alocações e desalocações.

## Heap vs Stack

|         Heap         |       	 Stack        |
|         :---:        |         :---:        |
|   Memória dinâmica   |	 Memória automática | 
|    Mais flexível     |	     Mais rápida    |
|   Pode fragmentar	   |   Organização linear |
|    Objetos grandes	 |    Variáveis locais  |

