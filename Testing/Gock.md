# Gock

O *gock* é uma biblioteca de *mocking HTTP* para a linguagem Go.

Ela é utilizada principalmente em testes automatizados para simular requisições HTTP e respostas de APIs externas, evitando chamadas reais durante a execução dos testes.

Com o Gock, é possível:
  - interceptar requisições HTTP;
  - definir respostas falsas (*mock responses*);
  - testar cenários de sucesso e erro;
  - tornar os testes mais rápidos e previsíveis.

## Por que usar o Gock?

Em testes unitários, não é recomendado depender de:
  - APIs reais;
  - internet;
  - serviços externos;
  - ambientes instáveis.

O Gock resolve isso simulando o comportamento dessas APIs dentro do teste.

## Exemplo simples

```Go
package main

import(
  "fmt"
  "net/http"

  "github.com/h2non/gock"
)

func main(){
  defer gock.Off()

  gock.New("https://api.exemplo.com").
    Get("/users").
    Reply(200).
    JSON(map[string]string{
      "name": "Beatriz",
    })

  http.Get("https://api.exemplo.com/users")

  fmt.Println("Mock executado com sucesso")
}
```

## Casos de uso

- Teste unitários;
- Simulação de APIs externas;
- Testes de erro e timeout;
- Desenvolvimento desacoplado;
- Validação de integração HTTP.

## Conceitos relacionados 

- Mocking;
- Testes unitários;
- APIs REST;
- Integração entre serviços
