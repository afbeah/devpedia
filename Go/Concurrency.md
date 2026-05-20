# Concurrency

## Goroutines

Se trata de um recurso central da linguagem Go, permitindo a execução de *funções* ou *métodos* de forma concorrente. Elas são como *"threads leves"*, otimizadas para trabalhar de maneira eficiente em sistemas modernos.

### Características Principais

1. Execução concorrente

   - Uma *goroutine* é iniciada com a palavra-chave **GO**, seguida de uma função ou método;
   - Quando uma função é executada como goroutine, ela roda de forma assíncrona, ou seja, de forma concorrente com outras partes do programa.
     
2. Leveza

   - Diferente das threads tradicionais, que consomem uma quantidade fixa de memória, as goroutines começam com apenas alguns kilobytes de memória. Isso permite que milhares (ou até milhões) de goroutines sejam criadas em um único programa.
  
3. Gerenciamento eficiente

   - O runtime do Go gerencia automaticamente as goroutines, multiplexando várias delas em um número limitado de threads do sistema operacional. Isso reduz a sobrecarga e melhora o desempenho.
  
4. Comunicação através de canais

   - Em Go, é recomendado utilizar channels para comunicação e sincronização entre goroutines, evitando compartilhamento direto de memória sempre que possível.


## Channels

São mecanismos que permitem a comunicação segura e sincronizada entre goroutines. Eles funcionam como 'uma via de mão única ou dupla' onde dados podem ser enviados de uma goroutine para outra. Channels ajudam a implementar a comunicação e sincronização entre goroutines sem a necessidade de usar memória compartilhada diretamente, promovendo um design concorrente mas seguro e legível.

### Características Principais

- Unidimensionais: Channels só podem transmitir um único tipo de dado, definido no momento da criação;
- Bloqueantes: Quando uma goroutine envia dados para um channel, ela bloqueia até que outra goroutine leia os dados. Da mesma forma, uma goroutine que tenta ler de um channel bloqueia até que haja dados disponíveis.
- Semáforo de sincronização implícito: Channels sincronizam automaticamente o envio e recebimento de dados entre goroutines, eliminando a necessidade de locks ou mutexes;
- Direção: Channels podem ser bidirecionais (padrão) ou limitados a apenas enviar ou receber dados.

### Quando usar Channels

- Para comunicação entre goroutines sem compartilhar memória diretamente;
- Para sincronizar a execução de diferentes partes do código;
- Para construir pipelines de processamento concorrente.

### Exemplo simples de goroutine

```go
go minhaFuncao()
```

### Exemplo de channel

```go
ch := make(chan string)

go func() {
  ch <- "Olá"
}()

mensagem := <-ch
```


     
