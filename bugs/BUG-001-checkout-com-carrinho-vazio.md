# BUG-001 - Site permite finalizar pedido com o carrinho vazio

| Campo | Informação |
|---|---|
| Site | https://www.saucedemo.com |
| Teste | Exploratório (feito depois do CT07) |
| Gravidade | Média |
| Usuário usado | `standard_user` |
| Ambiente | Windows, navegador Microsoft Edge |
| Data | 14/10/2026 |
| Status | Confirmado (reproduzido em dois testes) |

Observação: o site é em inglês. Os nomes de botões e telas aparecem aqui em português, com o nome original entre parênteses.

## Passos para reproduzir

1. Entrar com `standard_user`.
2. Garantir que o carrinho está vazio (sem produtos e sem o número vermelho no ícone do carrinho).
3. Abrir o carrinho e clicar em **Finalizar compra** (Checkout).
4. Preencher nome, sobrenome e CEP com dados de teste e clicar em **Continuar** (Continue).
5. Na tela de resumo do pedido (Checkout: Overview), clicar em **Finalizar** (Finish).

## Resultado esperado

O site deveria impedir a finalização da compra com o carrinho vazio, ou avisar que não há produtos para comprar.

## Resultado obtido

O site deixa seguir por todas as etapas. A tela de resumo mostra **Total dos itens: $0** (Item total) e **Total: $0.00**, e ao clicar em Finalizar aparece a mensagem **"Obrigado pelo seu pedido! Seu pedido foi enviado"** (original do site: "Thank you for your order! Your order has been dispatched"), como se um pedido tivesse sido feito.

## Evidências

(arraste aqui a captura de tela do resumo do pedido com Total dos itens $0 e a captura da tela de pedido concluído)

## Observações

- Acontece com o carrinho totalmente vazio, depois de remover o único produto.
- Impacto: um pedido sem produtos pode gerar registros e envios sem sentido em uma loja de verdade.
