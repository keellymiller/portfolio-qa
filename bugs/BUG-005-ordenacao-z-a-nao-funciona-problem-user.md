# BUG-005 - Ordenar produtos por nome de Z para A não muda a lista (usuário problem_user)

**Gravidade:** Média (atrapalha a busca de produtos, mas não impede a compra)
**Usuário:** problem_user
**Ambiente:** Windows, navegador Google Chrome
**Data:** 13/11/2026
**Status:** Confirmado

Observação: o site é em inglês. Os nomes de botões aparecem aqui em português, com o nome original entre parênteses.

## Passos para reproduzir
1. Abrir https://www.saucedemo.com
2. Entrar com o usuário `problem_user`
3. Na lista de produtos, abrir a ordenação e escolher Nome de Z para A (Name (Z to A))

## Resultado esperado
A lista fica em ordem alfabética inversa, começando pela camiseta vermelha (Test.allTheThings() T-Shirt (Red)).

## Resultado obtido
A lista continua de A para Z, começando pela mochila (Sauce Labs Backpack), e a ordenação volta a mostrar "Name (A to Z)".

## Evidências
A tela depois de escolher Z para A fica igual à da evidência do [BUG-002](BUG-002-imagens-iguais-problem-user.md): a mochila continua em primeiro lugar.

## Observações
Com o usuário standard_user a ordenação por preço funciona normal (ver CT05).
