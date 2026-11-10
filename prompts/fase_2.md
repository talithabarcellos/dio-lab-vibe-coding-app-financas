Vamos implementar agora a **Fase 2 — Núcleo Financeiro**, mantendo a arquitetura e o banco de dados estabelecidos na fase anterior.

Implemente:

1. Cadastro de receitas e despesas.
2. Categorias de receitas e despesas.
3. Cadastro manual de contas financeiras e cartões.
4. Histórico de movimentações com filtros por período, categoria e tipo.
5. Funcionalidades para visualizar, editar e excluir movimentações.
6. Campos para data, descrição, valor, categoria, tipo e conta ou cartão relacionado, quando aplicável.
7. Persistência real dos dados, respeitando o usuário autenticado.
8. Cálculo dos totais de receitas, despesas e saldo do período.

**Regras financeiras obrigatórias:**

- Utilize valores monetários com precisão adequada.
- Transferências entre contas próprias não podem ser contabilizadas como receitas ou despesas.
- O pagamento de uma fatura não pode duplicar as despesas das compras já registradas.
- Não invente informações ausentes.
- Atualize os totais após qualquer alteração ou exclusão.
- Não contabilize registros ainda não confirmados.
- Mostre estados vazios quando o usuário ainda não tiver movimentações.

Crie testes para validar os cálculos, a persistência e a edição dos registros.

Não implemente o chat, a importação de faturas ou as previsões nesta fase. Ao finalizar, apresente o que funciona, os testes realizados e eventuais limitações antes de avançarmos.