# Hooks

Em React, Hooks são funções especiais que permitem utilizar recursos como:

- estado;
- efeitos colaterais;
- contexto;
- referências;
- ciclo de vida

em componentes funcionais.

Os Hooks foram introduzidos para simplificar o reaproveitamento de lógica e reduzir a necessidade de componentes de classe.

## Hooks mais comuns

- useState → gerenciamento de estado;
- useEffect → efeitos colaterais;
- useContext → compartilhamento de contexto;
- useRef → referências mutáveis;
- useMemo → otimização de performance;
- useCallback → memorização de funções.

## Regras importantes

- Hooks devem começar com o prefixo use;
- Hooks só podem ser chamados no topo do componente;
- Hooks não devem ser chamados dentro de loops ou condicionais.

## Hooks customizados

Também é possível criar Hooks personalizados para reutilizar lógica entre componentes.

Exemplo:

```JavaScript
function useCounter() {
  const [count, setCount] = useState(0);

  return { count, setCount };
}
```

## Benefícios

- Reutilização de lógica;
- Código mais organizado;
- Componentes mais simples;
- Melhor separação de responsabilidades.
