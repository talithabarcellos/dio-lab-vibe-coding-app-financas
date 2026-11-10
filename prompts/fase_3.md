Vamos implementar a **Fase 3 — Chat Financeiro**, que será a principal forma de interação do usuário com o aplicativo.

O chat deverá permitir registrar e consultar movimentações financeiras usando linguagem natural.

Exemplos de mensagens:

- “Gastei R$ 42,50 no almoço.”
- “Recebi R$ 2.500 de salário.”
- “Paguei R$ 120 de energia ontem.”
- “Quanto gastei com alimentação este mês?”
- “Quais foram minhas maiores despesas?”
- “Mostre minhas movimentações desta semana.”

### Comportamento esperado

- Interpretar a intenção da mensagem.
- Extrair data, descrição, valor, tipo e categoria quando disponíveis.
- Solicitar esclarecimentos quando houver ambiguidades importantes.
- Sugerir categorias sem impedir que o usuário as corrija.
- Registrar movimentações no banco de dados real.
- Consultar os dados existentes para responder às perguntas.
- Confirmar quando uma operação tiver sido concluída.
- Exibir erros de forma clara, sem afirmar que uma operação foi realizada quando falhou.

### Interface

Crie uma tela de conversa agradável, responsiva e simples, contendo histórico de mensagens, campo de digitação, botão de envio, indicador de processamento e sugestões de perguntas úteis.

O chat deve ser integrado às movimentações reais do usuário. Não utilize respostas fixas ou dados fictícios para simular inteligência.

### Restrição de custos

Antes de escolher um modelo de IA ou serviço externo, verifique se há custos, limites de uso ou necessidade de créditos adicionais. Não presuma que o uso em tempo de execução é gratuito apenas porque o projeto está sendo desenvolvido no Lovable.

Se não houver uma opção de IA viável dentro do orçamento, implemente uma alternativa funcional para comandos e formatos reconhecidos, com possibilidade de confirmação manual. Informe claramente as limitações.

Não implemente ainda a importação em lote de faturas nem as funcionalidades avançadas de previsão.

Ao finalizar, teste o registro, a consulta, as ambiguidades, os erros e a persistência das operações. Informe os resultados antes de avançarmos.