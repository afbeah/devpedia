# Defer

Em Go, defer é uma palavra-chave utilizada para adiar a execução de uma função até que a função atual finalize sua execução.

As funções adiadas são executadas automaticamente antes do retorno da função.

## Como funciona?

Quando uma função é marcada com defer, ela entra em uma pilha de execução.

O comportamento segue o modelo LIFO (Last In, First Out):

- a última função adicionada;
- será a primeira executada.


## Exemplo simples

```go
func main() {
    defer fmt.Println("Fim")
    
    fmt.Println("Início")
}
```

Saída:

```go
Início
Fim
```

## Ordem de execução

```go
defer fmt.Println("1")
defer fmt.Println("2")
defer fmt.Println("3")
```

Resultado:

```go
3
2
1
```


## Quando usar defer?

- Fechar arquivos;
- Encerrar conexões;
- Liberar recursos;
- Fechar banco de dados;
- Unlock de mutex;
- Logs de finalização.

  
## Benefícios

- Código mais limpo;
- Menor risco de vazamento de recursos;
- Melhor organização do fluxo;
- Facilita operações de cleanup.
