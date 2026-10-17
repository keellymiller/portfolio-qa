# BUG-003 - Botão "Add to cart" da Sauce Labs Fleece Jacket não adiciona o produto (usuário problem_user)

**Severidade:** Alta (o cliente não consegue comprar esse produto)
**Usuário:** problem_user
**Ambiente:** Windows, navegador Edge
**Data:** 16/10/2026
**Status:** Confirmado (reproduzido em dois navegadores/painéis)

## Passos para reproduzir
1. Abrir https://www.saucedemo.com
2. Entrar com o usuário `problem_user`
3. Na lista de produtos, clicar em "Add to cart" da Sauce Labs Fleece Jacket
4. Olhar o botão e o ícone do carrinho

## Resultado esperado
O botão vira "Remove" e o carrinho aumenta em 1 item.

## Resultado obtido
Nada acontece. O botão continua "Add to cart" e o carrinho não muda. Clicando mais de uma vez, o resultado é o mesmo.

## Evidências
(anexar o print do botão da Fleece Jacket depois do clique)

## Observações
Com o mesmo usuário, o botão da Sauce Labs Backpack funciona normal (vira "Remove" e o carrinho sobe para 1). Ainda não testei os outros produtos com o problem_user.
