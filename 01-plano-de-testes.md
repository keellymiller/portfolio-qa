# Plano de testes - Saucedemo

## 1. O que eu vou testar

O site https://www.saucedemo.com, uma loja de demonstração feita para treinar testes (o site é todo em inglês). Vou testar o que uma pessoa usa no dia a dia da loja: entrar, ver os produtos, colocar no carrinho e finalizar a compra.

## 2. O que está dentro e o que está fora

**Dentro:** entrada na conta, lista de produtos (ordenar), carrinho, finalização da compra e saída da conta.

**Fora:** testes de segurança, de desempenho e de automação. Aqui é só teste manual funcional.

## 3. Como eu vou testar

- Teste funcional manual, seguindo os casos de teste do arquivo `02-casos-de-teste.md`
- Teste exploratório: depois dos casos, eu navego livremente procurando coisas estranhas
- Cada falha vira um relatório de defeito (bug) na pasta `bugs/`

## 4. Ambiente

- Site: https://www.saucedemo.com
- Navegador: Microsoft Edge
- Sistema: Windows
- Data dos testes: 14 e 16/10/2026

## 5. Usuários de teste

Os usuários de teste aparecem na própria tela de entrada do site (é um site de demonstração público). Os nomes ficam em inglês porque são os nomes reais das contas:

- `standard_user` (usuário normal)
- `locked_out_user` (usuário bloqueado)
- `problem_user` (usuário com problemas conhecidos)
- `performance_glitch_user` (usuário com lentidão)

## 6. Quando eu considero que terminei

- Todos os casos de teste foram executados
- Cada falha tem um relatório de defeito
- O resultado de cada caso está preenchido
