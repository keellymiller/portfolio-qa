# Casos de teste - Saucedemo

Como usar: execute cada caso no site https://www.saucedemo.com, anote o que aconteceu de verdade na coluna "Resultado obtido" e marque Passou ou Falhou. Se falhou, crie um relatório na pasta `bugs/` e coloque o nome do arquivo na última coluna.

Senha de todos os usuários de teste: a que aparece na própria tela de login do site.

| ID | O que testar | Passos | Resultado esperado | Resultado obtido | Status | Bug |
|---|---|---|---|---|---|---|
| CT01 | Login com usuário válido | 1. Abrir o site. 2. Usar `standard_user` e a senha da tela. 3. Clicar em Login | Abre a lista de produtos | (preencher) | (preencher) | |
| CT02 | Login com senha errada | 1. Usar `standard_user` com senha errada. 2. Clicar em Login | Mostra mensagem de erro e não entra | (preencher) | (preencher) | |
| CT03 | Login sem preencher nada | 1. Deixar usuário e senha vazios. 2. Clicar em Login | Mostra mensagem dizendo que o usuário é obrigatório | (preencher) | (preencher) | |
| CT04 | Login com usuário bloqueado | 1. Usar `locked_out_user`. 2. Clicar em Login | Mostra mensagem dizendo que o usuário está bloqueado | (preencher) | (preencher) | |
| CT05 | Ordenar produtos por preço (menor para maior) | 1. Entrar. 2. Escolher a ordenação por preço baixo para alto | Produtos aparecem do mais barato para o mais caro | (preencher) | (preencher) | |
| CT06 | Adicionar um produto ao carrinho | 1. Entrar. 2. Clicar em Add to cart num produto | Contador do carrinho vira 1 e o botão muda para Remove | (preencher) | (preencher) | |
| CT07 | Remover produto do carrinho | 1. Adicionar um produto. 2. Abrir o carrinho. 3. Clicar em Remove | Produto some do carrinho | (preencher) | (preencher) | |
| CT08 | Checkout com campos vazios | 1. Adicionar produto. 2. Ir ao checkout. 3. Não preencher nada e continuar | Mostra mensagem de campo obrigatório | (preencher) | (preencher) | |
| CT09 | Finalizar uma compra completa | 1. Adicionar produto. 2. Preencher nome, sobrenome e CEP. 3. Continuar e finalizar | Aparece a mensagem de pedido concluído | (preencher) | (preencher) | |
| CT10 | Logout | 1. Entrar. 2. Abrir o menu. 3. Clicar em Logout | Volta para a tela de login | (preencher) | (preencher) | |
| CT11 | Conferir produtos com o usuário `problem_user` | 1. Entrar com `problem_user`. 2. Olhar as imagens e adicionar produtos | Cada produto mostra a imagem certa e funciona normal | (preencher) | (preencher) | |

## Dica para a parte exploratória

Depois dos casos, teste coisas "fora do roteiro": voltar a página no meio do checkout, atualizar a página com o carrinho cheio, abrir o site no celular. Tudo o que achar estranho vira um relatório de bug.
