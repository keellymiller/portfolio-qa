# Casos de teste - Saucedemo

Ambiente: Windows, navegador Edge, site https://www.saucedemo.com, testes feitos em 16/10/2026.

Como usar: cada caso foi executado no site e o resultado da coluna "Resultado obtido" é o que realmente apareceu na tela. Se falhou, o relatório está na pasta `bugs/` e o nome do arquivo está na última coluna.

Observação sobre o idioma: o site testado é em inglês. Os nomes de botões e as mensagens de erro aparecem em inglês, exatamente como estão na tela, e vêm sempre seguidos da tradução entre parênteses.

Senha de todos os usuários de teste: a que aparece na própria tela de login do site.

| ID | O que testar | Passos | Resultado esperado | Resultado obtido | Status | Bug |
|---|---|---|---|---|---|---|
| CT01 | Login com usuário válido | 1. Abrir o site. 2. Usar `standard_user` e a senha da tela. 3. Clicar em Login (Entrar) | Abre a lista de produtos | Abriu a lista de produtos, sem erros | Passou | |
| CT02 | Login com senha errada | 1. Usar `standard_user` com senha errada. 2. Clicar em Login (Entrar) | Mostra mensagem de erro e não entra | Mostrou mensagem de erro e não entrou | Passou | |
| CT03a | Login sem preencher a senha (usuário preenchido) | 1. Digitar só o usuário. 2. Clicar em Login (Entrar) | Mostra mensagem dizendo que a senha é obrigatória | `Epic sadface: Password is required` (Erro: a senha é obrigatória) | Passou | |
| CT03b | Login sem preencher nada | 1. Deixar usuário e senha vazios. 2. Clicar em Login (Entrar) | Mostra mensagem de campo obrigatório | Mostrou mensagem de campo obrigatório | Passou | |
| CT04 | Login com usuário bloqueado | 1. Usar `locked_out_user` (usuário bloqueado). 2. Clicar em Login (Entrar) | Mostra mensagem dizendo que o usuário está bloqueado | `Epic sadface: Sorry, this user has been locked out.` (Erro: este usuário foi bloqueado) | Passou | |
| CT05 | Ordenar produtos por preço (menor para maior) | 1. Entrar. 2. Escolher a ordenação por preço baixo para alto (Price low to high) | Produtos aparecem do mais barato para o mais caro | Funcionou como esperado | Passou | |
| CT06 | Adicionar um produto ao carrinho | 1. Entrar. 2. Clicar em Add to cart (Adicionar ao carrinho) num produto | Contador do carrinho vira 1 e o botão muda para Remove (Remover) | Funcionou como esperado | Passou | |
| CT07 | Remover produto do carrinho | 1. Adicionar um produto. 2. Abrir o carrinho. 3. Clicar em Remove (Remover) | Produto some do carrinho | Funcionou como esperado | Passou | |
| CT07b | Finalizar pedido com o carrinho vazio | 1. Entrar. 2. Abrir o carrinho sem produtos. 3. Clicar em Checkout (Finalizar compra) e seguir até o fim | O site não deve deixar finalizar um pedido vazio | O site deixou finalizar, com total $0.00 | Falhou | bugs/BUG-001-checkout-com-carrinho-vazio.md |
| CT08 | Checkout com campos vazios | 1. Adicionar produto. 2. Ir ao checkout (finalizar compra). 3. Não preencher nada e clicar em Continue (Continuar) | Mostra mensagem de campo obrigatório | `Error: First Name is required` (Erro: o primeiro nome é obrigatório) | Passou | |
| CT09 | Finalizar uma compra completa | 1. Adicionar produto. 2. Preencher nome, sobrenome e CEP. 3. Clicar em Continue (Continuar) e depois em Finish (Finalizar) | Aparece a mensagem de pedido concluído | Apareceu `Thank you for your order!` (Obrigado pelo seu pedido!) e o total conferiu (produto $29.99 + imposto $2.40 = $32.39) | Passou | |
| CT10 | Logout (sair da conta) | 1. Entrar. 2. Abrir o menu. 3. Clicar em Logout (Sair). 4. Tentar abrir /inventory.html pelo endereço | Volta para a tela de login e não deixa entrar sem login | Voltou para o login e mostrou `You can only access '/inventory.html' when you are logged in.` (Você só pode acessar essa página depois de fazer login) | Passou | |
| CT11a | Fotos dos produtos com `problem_user` (usuário com problemas) | 1. Entrar com `problem_user`. 2. Olhar a lista de produtos | Cada produto mostra a sua própria foto | Todos os produtos mostram a mesma foto (um cachorro com uma bolinha de tênis) | Falhou | bugs/BUG-002-imagens-iguais-problem-user.md |
| CT11b | Adicionar a Fleece Jacket (jaqueta de lã) ao carrinho com `problem_user` | 1. Entrar com `problem_user`. 2. Clicar em Add to cart (Adicionar ao carrinho) da Sauce Labs Fleece Jacket | Botão vira Remove (Remover) e o carrinho sobe | Nada acontece: o botão continua Add to cart (Adicionar ao carrinho) e o carrinho não muda | Falhou | bugs/BUG-003-botao-add-to-cart-fleece-jacket.md |

## Observações

- O site de treino às vezes encerra a sessão sozinho. Isso não foi tratado como bug.
- Não foram testados: outros produtos com o `problem_user`, os usuários `performance_glitch_user`, `error_user` e `visual_user`, nem o site no celular.

## Dica para a parte exploratória

Depois dos casos, teste coisas "fora do roteiro": voltar a página no meio do checkout, atualizar a página com o carrinho cheio, abrir o site no celular. Tudo o que achar estranho vira um relatório de bug.
