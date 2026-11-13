# Testes de API - JSONPlaceholder

API testada: https://jsonplaceholder.typicode.com (API pública feita para treino de testes)
Ferramenta: Postman
Data: 13/11/2026

## Como rodar os testes

1. Abrir o Postman e clicar em Importar (Import)
2. Escolher o arquivo [`jsonplaceholder.postman_collection.json`](jsonplaceholder.postman_collection.json)
3. Clicar com o botão direito na coleção e escolher Executar coleção (Run collection)

Cada requisição já tem os testes escritos na aba Testes (Tests), que conferem o código de status e o conteúdo da resposta.

## Casos de teste

| ID | Método | Endereço | O que é conferido | Status |
|---|---|---|---|---|
| CT-API-01 | GET | `/posts/1` | Status 200, resposta em menos de 2 segundos, id certo e todos os campos | Passou |
| CT-API-02 | GET | `/posts/9999` | Status 404 para um post que não existe (teste negativo) | Passou |
| CT-API-03 | GET | `/posts?userId=1` | Status 200, 10 posts e todos do usuário 1 | Passou |
| CT-API-04 | POST | `/posts` | Status 201, título igual ao enviado e id novo (101) | Passou |
| CT-API-05 | PUT | `/posts/1` | Status 200 e título atualizado | Passou |
| CT-API-06 | PATCH | `/posts/1` | Status 200, só o título muda | Passou |
| CT-API-07 | DELETE | `/posts/1` | Status 200 | Passou |

## Observação

A JSONPlaceholder é uma API de simulação: ela responde como se tivesse criado, alterado ou apagado os dados, mas não salva nada de verdade. Por isso, se eu fizer um GET depois do POST, o post de id 101 não aparece.
