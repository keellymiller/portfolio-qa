# BUG-001 - Site permite finalizar pedido com o carrinho vazio

| Campo | Informação |
|---|---|
| Site | https://www.saucedemo.com |
| Teste | Exploratório (feito depois do CT07) |
| Gravidade | Média |
| Usuário usado | `standard_user` |
| Ambiente | Windows, navegador: (preencher) |
| Data | 14/10/2026 |
| Status | Confirmado (reproduzido em dois testes) |

## Passos para reproduzir

1. Entrar com `standard_user`.
2. Garantir que o carrinho está vazio (sem produtos e sem o número vermelho no ícone do carrinho).
3. Abrir o carrinho e clicar em **Checkout**.
4. Preencher nome, sobrenome e CEP com dados de teste e clicar em **Continue**.
5. Na tela de resumo (Checkout: Overview), clicar em **Finish**.

## Resultado esperado

O site deveria impedir o Checkout com o carrinho vazio, ou avisar que não há produtos para comprar.

## Resultado obtido

O site deixa seguir por todas as etapas. A tela de resumo mostra **Item total: $0** e **Total: $0.00**, e ao clicar em Finish aparece a mensagem **"Thank you for your order! Your order has been dispatched"**, como se um pedido tivesse sido feito.

## Evidências

(arraste aqui o print da tela "Checkout: Overview" com Item total $0 e o print da tela "Checkout: Complete!")

## Observações

- Acontece com o carrinho totalmente vazio, depois de remover o único produto.
- Impacto: um pedido sem produtos pode gerar registros e envios sem sentido em uma loja de verdade.
