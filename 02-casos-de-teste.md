# Casos de teste - Saucedemo

Ambiente: Windows, navegador Microsoft Edge, site https://www.saucedemo.com, testes feitos em 14 e 16/10/2026. Os casos CT11c, CT12 e CT13 foram feitos em 13/11/2026 no Google Chrome.

Como usar: cada caso foi executado no site e o resultado da coluna "Resultado obtido" é o que realmente apareceu na tela. Se falhou, o relatório está na pasta `bugs/` e o nome do arquivo está na última coluna.

Observação sobre o idioma: o site testado é todo em inglês. Aqui os nomes de botões e as mensagens de erro estão traduzidos para o português. Só ficam em inglês os nomes das contas de teste, que são os nomes reais (por exemplo `standard_user`).

Senha de todos os usuários de teste: a que aparece na própria tela de entrada do site.

| ID | O que testar | Passos | Resultado esperado | Resultado obtido | Status | Defeito |
|---|---|---|---|---|---|---|
| CT01 | Entrar com usuário válido | 1. Abrir o site. 2. Usar `standard_user` e a senha da tela. 3. Clicar em Entrar | Abre a lista de produtos | Abriu a lista de produtos, sem erros | Passou | |
| CT02 | Entrar com senha errada | 1. Usar `standard_user` com senha errada. 2. Clicar em Entrar | Mostra mensagem de erro e não entra | Mostrou mensagem de erro e não entrou | Passou | |
| CT03a | Entrar sem preencher a senha (usuário preenchido) | 1. Digitar só o usuário. 2. Clicar em Entrar | Mostra mensagem dizendo que a senha é obrigatória | Mensagem: "A senha é obrigatória" | Passou | |
| CT03b | Entrar sem preencher nada | 1. Deixar usuário e senha vazios. 2. Clicar em Entrar | Mostra mensagem de campo obrigatório | Mostrou mensagem de campo obrigatório | Passou | |
| CT04 | Entrar com usuário bloqueado | 1. Usar `locked_out_user` (usuário bloqueado). 2. Clicar em Entrar | Mostra mensagem dizendo que o usuário está bloqueado | Mensagem: "Desculpe, este usuário foi bloqueado" | Passou | |
| CT05 | Ordenar produtos por preço (menor para maior) | 1. Entrar. 2. Escolher a ordenação por preço do menor para o maior | Produtos aparecem do mais barato para o mais caro | Funcionou como esperado | Passou | |
| CT06 | Adicionar um produto ao carrinho | 1. Entrar. 2. Clicar em Adicionar ao carrinho num produto | Contador do carrinho vira 1 e o botão muda para Remover | Funcionou como esperado | Passou | |
| CT07 | Remover produto do carrinho | 1. Adicionar um produto. 2. Abrir o carrinho. 3. Clicar em Remover | Produto some do carrinho | Funcionou como esperado | Passou | |
| CT07b | Finalizar pedido com o carrinho vazio | 1. Entrar. 2. Abrir o carrinho sem produtos. 3. Clicar em Finalizar compra e seguir até o fim | O site não deve deixar finalizar um pedido vazio | O site deixou finalizar, com total $0.00 | Falhou | bugs/BUG-001-checkout-com-carrinho-vazio.md |
| CT08 | Finalizar compra com campos vazios | 1. Adicionar produto. 2. Ir para a finalização da compra. 3. Não preencher nada e clicar em Continuar | Mostra mensagem de campo obrigatório | Mensagem: "Erro: o primeiro nome é obrigatório" | Passou | |
| CT09 | Finalizar uma compra completa | 1. Adicionar produto. 2. Preencher nome, sobrenome e CEP. 3. Clicar em Continuar e depois em Finalizar | Aparece a mensagem de pedido concluído | Apareceu "Obrigado pelo seu pedido!" e o total conferiu (produto $29.99 + imposto $2.40 = $32.39) | Passou | |
| CT10 | Sair da conta | 1. Entrar. 2. Abrir o menu. 3. Clicar em Sair. 4. Tentar abrir a página da lista de produtos pelo endereço, sem estar logada | Volta para a tela de entrada e não deixa acessar sem login | Voltou para a tela de entrada e mostrou: "Você só pode acessar essa página depois de fazer login" | Passou | |
| CT11a | Fotos dos produtos com `problem_user` (usuário com problemas) | 1. Entrar com `problem_user`. 2. Olhar a lista de produtos | Cada produto mostra a sua própria foto | Todos os produtos mostram a mesma foto (um cachorro com uma bolinha de tênis) | Falhou | bugs/BUG-002-imagens-iguais-problem-user.md |
| CT11b | Adicionar a jaqueta de lã ao carrinho com `problem_user` | 1. Entrar com `problem_user`. 2. Clicar em Adicionar ao carrinho da jaqueta de lã (Fleece Jacket) | Botão vira Remover e o carrinho sobe | Nada acontece: o botão continua Adicionar ao carrinho e o carrinho não muda | Falhou | bugs/BUG-003-botao-add-to-cart-fleece-jacket.md |
| CT11c | Adicionar os outros produtos ao carrinho com `problem_user` | 1. Entrar com `problem_user`. 2. Clicar em Adicionar ao carrinho nos 6 produtos | Os 6 produtos vão para o carrinho | Só 3 foram adicionados. A camiseta Bolt e a camiseta vermelha têm o mesmo defeito da jaqueta | Falhou | bugs/BUG-003-botao-add-to-cart-fleece-jacket.md |
| CT12 | Preencher nome e sobrenome na finalização da compra com `problem_user` | 1. Entrar com `problem_user`. 2. Adicionar a mochila. 3. Ir para a finalização da compra. 4. Digitar o nome, o sobrenome e o CEP. 5. Clicar em Continuar | Cada campo guarda o que foi digitado e o site avança para o resumo | O sobrenome apagou o primeiro nome (ficou só a letra "o") e apareceu "Erro: o sobrenome é obrigatório" | Falhou | bugs/BUG-004-sobrenome-apaga-nome-problem-user.md |
| CT13 | Ordenar produtos por nome de Z para A com `problem_user` | 1. Entrar com `problem_user`. 2. Escolher a ordenação Nome de Z para A | A lista começa pela camiseta vermelha (Test.allTheThings() T-Shirt (Red)) | A lista continuou de A para Z, começando pela mochila | Falhou | bugs/BUG-005-ordenacao-z-a-nao-funciona-problem-user.md |

## Observações

- O site de treino às vezes encerra a sessão sozinho. Isso não foi tratado como defeito.
- Não foram testados: os usuários `performance_glitch_user`, `error_user` e `visual_user`, nem o site no celular.

## Testes exploratórios

Depois dos casos, testei coisas "fora do roteiro". Foi assim que encontrei o [BUG-001](bugs/BUG-001-checkout-com-carrinho-vazio.md): o site deixa finalizar um pedido com o carrinho vazio.

## Resumo

| Total de casos | Passou | Falhou | Defeitos encontrados |
|---|---|---|---|
| 17 | 11 | 6 | 5 |
