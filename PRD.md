# PRD — Assistente Financeiro Pessoal

## 1. Visão geral do projeto

Criar um aplicativo web responsivo de organização financeira pessoal, em português brasileiro, que permita ao usuário controlar suas finanças por meio de uma conversa natural com um assistente financeiro.

O objetivo é tornar a organização financeira acessível para pessoas que não possuem conhecimentos avançados de finanças e que não gostam de preencher planilhas ou formulários extensos.

O usuário deve conseguir registrar despesas, receitas, contas futuras, metas financeiras e movimentações de faturas conversando com o assistente. O aplicativo também deve oferecer telas visuais para consultar o histórico, acompanhar o orçamento e entender a previsão de fechamento do mês.

**Princípio central:** conversar para registrar e entender as finanças; consultar telas visuais para acompanhar e analisar os resultados.

## 2. Público-alvo

Pessoas que:
- Desejam organizar melhor o próprio dinheiro.
- Não têm experiência com aplicativos financeiros complexos.
- Preferem escrever mensagens naturais em vez de preencher formulários.
- Precisam acompanhar despesas, receitas, contas futuras e metas.
- Desejam entender para onde o dinheiro está indo e como podem economizar.

## 3. Plataforma e restrições

### Plataforma
- Desenvolver primeiro como aplicativo web responsivo.
- Priorizar boa experiência em computadores e celulares.
- Estruturar o projeto para possibilitar uma futura versão mobile.
- Interface inteiramente em português brasileiro.
- Utilizar reais (R$) como moeda padrão.
- Utilizar datas no padrão brasileiro, DD/MM/AAAA.

### Restrições de custo
O MVP deve priorizar ferramentas gratuitas e funcionalidades que não dependam de serviços pagos.

Não implementar nesta primeira versão:
- Integração direta com bancos.
- Conexão via Open Finance.
- Leitura automática de PDFs.
- OCR ou leitura de fotografias de faturas.
- Serviços externos pagos de previsão financeira.
- Funcionalidades que dependam de uma API paga sem alternativa viável.

O usuário poderá colar no chat o texto copiado de uma fatura ou extrato. O aplicativo deverá interpretar o texto quando houver recursos disponíveis e oferecer uma alternativa de processamento estruturado quando a interpretação por IA não estiver disponível.

**Importante:** não afirmar que chamadas de IA em tempo de execução são gratuitas sem verificar o serviço utilizado, seus limites e custos. Não criar integrações fictícias, dados financeiros simulados apresentados como reais ou funções que apenas aparentem funcionar.

## 4. Objetivos do MVP

O MVP deverá permitir:

1. Criar uma conta e acessar os próprios dados com segurança.
2. Registrar receitas e despesas por conversa.
3. Consultar, corrigir e excluir movimentações.
4. Organizar transações por categorias.
5. Cadastrar contas, cartões e compromissos financeiros.
6. Colar texto de faturas e extratos no chat para importar movimentações em lote.
7. Revisar as movimentações antes de confirmar a importação.
8. Acompanhar um painel financeiro simples.
9. Criar e acompanhar metas financeiras.
10. Consultar despesas futuras e uma previsão de fechamento mensal.
11. Receber dicas e alertas fundamentados nos dados registrados.

## 5. Experiência principal: Assistente Financeiro

A tela principal deve ser um chat com o assistente financeiro.

O usuário deve poder escrever mensagens como:
- “Gastei R$ 42,50 no almoço.”
- “Recebi R$ 2.500 de salário.”
- “Paguei R$ 120 de energia.”
- “Quanto gastei com alimentação este mês?”
- “Quais contas vencem nos próximos sete dias?”
- “Quero economizar R$ 1.000 até março.”
- “Colei minha fatura abaixo. Separe as compras por categoria para eu conferir.”
- “Quanto ainda posso gastar este mês?”

### Comportamento do assistente

O assistente deverá:
- Entender a intenção da mensagem.
- Extrair os dados financeiros disponíveis.
- Identificar informações ausentes ou ambíguas.
- Solicitar esclarecimentos quando necessário.
- Mostrar um resumo do registro antes ou depois da confirmação, conforme a complexidade.
- Informar claramente quando uma movimentação tiver sido salva.
- Permitir correções por linguagem natural.
- Consultar dados reais persistidos do usuário.
- Responder com linguagem simples, amigável, educativa e sem julgamentos.

Exemplo:

Usuário: “Gastei 35 reais na farmácia.”

Assistente: “Você quer registrar uma despesa de R$ 35,00 na categoria Saúde, com a descrição Farmácia, hoje?”

Após a confirmação ou o registro bem-sucedido, o assistente deverá informar o resultado real da operação.

Não afirmar que salvou, alterou ou excluiu dados antes que a operação tenha sido concluída.

### Interface do chat

A tela deve conter:
- Histórico de mensagens.
- Campo de texto para digitação.
- Botão para enviar mensagem.
- Indicador de processamento.
- Sugestões de perguntas ou ações úteis.
- Apresentação clara de valores, datas e categorias.
- Cartões de resumo quando ajudarem a compreender a resposta.

O chat deve continuar sendo o centro da experiência. Os dashboards e as listas complementam a conversa, sem substituí-la.

## 6. Cadastro e gerenciamento de movimentações

Cada movimentação financeira deverá ter, quando aplicável:

- Identificador único.
- Usuário proprietário.
- Tipo: receita, despesa, transferência, pagamento de fatura ou estorno.
- Descrição original.
- Valor.
- Data da movimentação.
- Categoria.
- Conta ou cartão relacionado.
- Forma de pagamento, quando conhecida.
- Status, quando aplicável.
- Indicação de origem: registro manual, conversa ou importação de texto.
- Data de criação e de atualização.

### Regras

- Valores devem ser tratados como valores monetários, evitando erros de arredondamento.
- Não inventar informações ausentes.
- Perguntar quando data, valor ou tipo não puderem ser determinados com segurança.
- Permitir editar e excluir movimentações.
- Manter a descrição original, mesmo quando uma categoria ou descrição normalizada for sugerida.
- Atualizar os indicadores e relatórios após alterações.
- Exibir valores em formato brasileiro, por exemplo, R$ 1.234,56.

### Categorias iniciais sugeridas

Despesas:
- Alimentação.
- Moradia.
- Transporte.
- Saúde.
- Educação.
- Lazer.
- Compras.
- Assinaturas.
- Contas e serviços.
- Dívidas e encargos.
- Outros.

Receitas:
- Salário.
- Trabalho autônomo.
- Rendimentos.
- Reembolsos.
- Outras receitas.

As categorias deverão ser editáveis ou ampliáveis pelo usuário futuramente. O assistente poderá sugerir categorias, mas deve permitir a correção.

## 7. Contas, cartões e pagamentos

Permitir cadastrar contas financeiras e cartões manualmente.

### Conta financeira
Campos mínimos:
- Nome.
- Tipo de conta.
- Saldo inicial, se conhecido.
- Data de referência do saldo.

### Cartão de crédito
Campos mínimos:
- Nome do cartão.
- Limite, opcional.
- Dia de fechamento, opcional.
- Dia de vencimento, opcional.

Não é necessário implementar integração bancária ou consultar saldos automaticamente.

O aplicativo deverá distinguir:
- Compras feitas no cartão.
- Pagamentos da fatura.
- Transferências entre contas próprias.
- Receitas e despesas efetivas.

### Regra contra dupla contagem

Se as compras da fatura já foram registradas como despesas, o pagamento da fatura não poderá ser contabilizado novamente como uma nova despesa de consumo.

O pagamento deverá ser tratado como liquidação de uma obrigação financeira, mantendo o histórico das compras.

Transferências entre contas do mesmo usuário não deverão ser contabilizadas como receita ou despesa.

## 8. Importação de faturas e extratos por texto

### Objetivo

Permitir que o usuário copie o texto de um extrato bancário ou fatura e cole diretamente no chat, sem precisar digitar cada movimentação.

Essa funcionalidade deve ser desenvolvida sem depender de integração bancária, OCR ou leitura de arquivos.

### Fluxo esperado

1. O usuário cola o texto no chat.
2. O assistente identifica que o conteúdo pode conter várias movimentações.
3. O aplicativo interpreta as linhas e extrai os dados identificáveis.
4. O sistema apresenta uma prévia das movimentações encontradas.
5. O usuário pode corrigir valores, datas, descrições, categorias e tipos.
6. O usuário pode remover linhas inválidas ou não desejadas.
7. O sistema sinaliza possíveis duplicatas.
8. O usuário confirma quais movimentações deseja importar.
9. O sistema salva apenas os registros confirmados.
10. O assistente informa quantos registros foram importados e quais não puderam ser processados.

### Dados a extrair

- Data.
- Descrição.
- Valor.
- Tipo de movimentação, quando identificável.
- Categoria sugerida.
- Conta ou cartão, quando identificável com segurança.

Não inventar campos que não estejam presentes no texto ou que não possam ser inferidos com segurança.

### Formatos a priorizar

- Texto simples copiado de uma fatura.
- Linhas contendo data, descrição e valor.
- Texto com colunas separadas por espaços ou tabulações.
- Datas brasileiras.
- Valores como `125,90`, `R$ 125,90` e valores negativos quando houver indicação de estorno ou crédito.

A compatibilidade com formatos diferentes deverá ser testada. Não prometer que qualquer extrato de qualquer banco será interpretado perfeitamente.

### Revisão obrigatória

A prévia deve apresentar:
- Data.
- Descrição.
- Valor.
- Categoria sugerida.
- Tipo de movimentação.
- Avisos de campos incertos.
- Avisos de possíveis duplicatas.
- Opção de editar ou remover cada linha.
- Opção de confirmar a importação.

Não salvar automaticamente todas as linhas apenas porque o usuário colou um texto.

### Duplicatas e inconsistências

- Comparar data, valor, descrição e registros existentes para detectar possíveis duplicatas.
- Não excluir automaticamente registros semelhantes.
- Permitir que o usuário decida se deseja importar uma movimentação sinalizada.
- Não transformar o pagamento da fatura em nova despesa se as compras já estiverem registradas.
- Identificar possíveis estornos, pagamentos e transferências separadamente quando houver evidências suficientes.
- Se o tipo de uma linha for ambíguo, solicitar confirmação.

### Alternativa sem IA paga

Implementar primeiro um parser determinístico para formatos conhecidos e previsíveis. Se existir um recurso de IA disponível dentro do orçamento real do projeto, ele poderá ajudar a interpretar descrições e formatos variados.

Caso a interpretação por IA não esteja disponível, oferecer uma alternativa funcional para:
- Colar dados em formato estruturado.
- Interpretar linhas com colunas reconhecidas.
- Revisar os campos manualmente antes da confirmação.

Não criar um botão de importação que dependa de um serviço inexistente. Se o formato não for reconhecido, explicar a limitação e orientar o usuário a reorganizar o texto.

### Privacidade

Orientar o usuário a remover informações pessoais desnecessárias antes de colar uma fatura. Nunca solicitar senhas bancárias, códigos de segurança ou credenciais.

Guardar apenas os dados financeiros necessários. O texto bruto da fatura não deve ser armazenado permanentemente por padrão; priorizar o armazenamento das movimentações efetivamente confirmadas.

## 9. Painel financeiro

Criar uma tela de dashboard para acompanhar a situação financeira do período selecionado.

### Indicadores principais

- Receitas do mês.
- Despesas do mês.
- Saldo do período.
- Total de contas futuras em aberto.
- Valor comprometido com despesas previstas.
- Progresso das metas financeiras.

Os valores devem ser calculados a partir dos registros reais do usuário.

O dashboard deverá apresentar:
- Seletor de período.
- Gráfico simples de despesas por categoria.
- Resumo das movimentações recentes.
- Acesso rápido ao chat.
- Acesso à tela de despesas futuras.
- Acesso às metas.

Não exibir números fictícios como se fossem dados reais. Em uma conta sem movimentações, mostrar um estado vazio com orientação para começar a registrar receitas e despesas.

## 10. Tela de metas financeiras

Permitir que o usuário crie metas, como:
- Montar uma reserva de emergência.
- Economizar para uma viagem.
- Comprar um equipamento.
- Quitar uma dívida.

### Campos da meta
- Nome.
- Valor desejado.
- Valor já acumulado, quando informado.
- Data-alvo, opcional.
- Descrição, opcional.
- Status.

### Apresentação
- Valor desejado.
- Valor acumulado.
- Valor restante.
- Percentual de progresso.
- Prazo, quando houver.
- Mensagem amigável de acompanhamento.

O sistema não deve afirmar que um valor foi poupado ou transferido apenas porque o usuário criou uma meta. O progresso deve ser atualizado por registros confirmados ou por atualização manual explícita.

O assistente poderá ajudar a estimar quanto seria necessário economizar por mês, deixando claras as premissas utilizadas.

## 11. Tela: Despesas Futuras e Previsão de Fechamento do Mês

Esta tela deverá ajudar o usuário a entender o que ainda precisa pagar e como o mês poderá terminar.

A interface deve conter quatro seções principais.

### 11.1. Card de destaque: Termômetro do Mês

No topo, exibir um card de destaque chamado **Termômetro do Mês**.

O card deve apresentar:
- Previsão do saldo ao final do mês.
- Indicador visual simples da situação financeira.
- Frase explicativa amigável.
- Breve explicação dos fatores que influenciam a previsão.

Exemplos de mensagens, condicionadas aos dados reais:
- “Mantendo o ritmo atual, você poderá terminar o mês com saldo positivo.”
- “As contas previstas podem consumir boa parte do dinheiro disponível.”
- “Ainda faltam informações para estimar seu saldo com segurança.”

O saldo projetado deve considerar, quando os dados estiverem disponíveis:
- Saldo inicial ou saldo de referência.
- Receitas efetivamente registradas.
- Despesas efetivamente registradas.
- Receitas futuras previstas e informadas pelo usuário.
- Contas futuras pendentes.
- Compromissos financeiros e parcelas registrados.
- Estimativa de despesas variáveis, apenas quando houver histórico suficiente.

Não tratar receitas esperadas como dinheiro já recebido.

O card deve distinguir:
- Saldo atual calculado a partir dos registros.
- Saldo futuro projetado.
- Valores estimados.

Se não houver saldo inicial conhecido ou dados suficientes, mostrar uma mensagem explicativa em vez de inventar uma previsão.

### 11.2. Contas Fixas Próximas

Exibir uma lista de contas futuras, ordenada por data de vencimento.

Cada item deverá apresentar:
- Nome da conta.
- Data de vencimento.
- Valor.
- Status: pendente, paga ou atrasada.
- Indicador de proximidade do vencimento.

Permitir cadastrar, editar e marcar uma conta como paga.

Exemplos de contas:
- Aluguel.
- Energia elétrica.
- Água.
- Internet.
- Telefone.
- Assinaturas.
- Outras contas recorrentes.

Esses exemplos são sugestões de categorias, não contas que devem ser criadas automaticamente.

Não gerar contas fixas automaticamente sem autorização do usuário. A recorrência poderá ser adicionada em uma etapa posterior, caso seja possível implementá-la de forma confiável.

### 11.3. Gráfico de barras: gastos atuais versus projeção

Criar um gráfico de barras simples que compare:
- Gastos realizados até o momento no mês.
- Gastos projetados para o fechamento do mês.

Agrupar os dados por categoria.

Requisitos:
- Legenda clara para valores realizados e projetados.
- Valores em reais.
- Categorias reais do usuário.
- Layout responsivo.
- Texto explicativo sobre o período analisado.
- Indicação de quando a projeção não puder ser calculada.

A projeção deve considerar o gasto já realizado e estimar o fechamento do mês, sem somar o valor realizado duas vezes.

Quando houver histórico suficiente, poderá utilizar o ritmo de gastos do período e os dados anteriores como referência. Não projetar valores com falsa precisão.

Quando não houver histórico suficiente, mostrar apenas os gastos realizados e informar que a projeção ainda não está disponível.

### 11.4. Dicas e Alertas do Agente Financeiro

Na parte inferior, exibir um card visualmente distinto, com ícone e título **Dicas e Alertas do Agente Financeiro**.

O card poderá apresentar:
- Categorias que estejam gastando mais do que o habitual.
- Contas próximas do vencimento.
- Risco de saldo insuficiente para compromissos conhecidos.
- Despesas variáveis que mereçam atenção.
- Possíveis oportunidades de economia.
- Perguntas para ajudar o usuário a refletir sobre seus hábitos.

As sugestões devem ser:
- Baseadas em dados disponíveis.
- Específicas e acionáveis.
- Explicadas em linguagem simples.
- Respeitosas, sem julgamentos ou alarmismo.
- Claras sobre incertezas e dados ausentes.

Não inventar hábitos financeiros, contas, receitas ou alertas. Se não houver dados suficientes, o assistente deverá explicar isso e sugerir como melhorar a análise.

### 11.5. Regras de cálculo da previsão

A previsão deverá ser reproduzível a partir dos registros e das premissas utilizados.

- Evitar dupla contagem de compras no cartão e pagamentos de fatura.
- Não contar transferências próprias como receita ou despesa.
- Não misturar valores realizados com estimativas sem identificá-los.
- Atualizar a projeção quando movimentações ou contas forem alteradas.
- Mostrar o período considerado.
- Não apresentar uma projeção como garantia de saldo futuro.
- Não depender de integração bancária ou serviço financeiro pago.

Implementar primeiro o cálculo do saldo com dados registrados e a lista de contas futuras. Adicionar projeções por categoria e recomendações personalizadas quando houver dados suficientes para fazê-las com responsabilidade.

## 12. Agente Financeiro: regras de comportamento

O agente deve ajudar o usuário a compreender e organizar as finanças, não tomar decisões financeiras por ele.

Ele deverá:
- Explicar cálculos quando solicitado.
- Distinguir fatos registrados, estimativas e sugestões.
- Usar os dados do usuário como fonte para suas respostas.
- Perguntar antes de executar ações financeiras ambíguas.
- Não inventar transações ou resultados.
- Não prometer economias garantidas.
- Evitar recomendações de investimento específicas no MVP.
- Não tratar ausência de dados como saldo zero sem explicar essa suposição.
- Não criar compromissos ou movimentações sem autorização.

## 13. Navegação e telas

Criar uma navegação simples, com as seguintes áreas:

1. **Chat:** tela principal para conversar com o assistente e registrar movimentações.
2. **Visão Geral:** dashboard com resumo financeiro.
3. **Movimentações:** histórico com busca, filtros e edição.
4. **Despesas Futuras:** Termômetro do Mês, contas próximas, gráfico de projeção e dicas.
5. **Metas:** cadastro e acompanhamento de objetivos.
6. **Contas e Cartões:** cadastro e gerenciamento manual.
7. **Configurações:** preferências, categorias e gerenciamento da conta.

Em telas menores, utilizar navegação adaptada para celular, sem perder o acesso às funções principais.

O usuário deverá conseguir voltar ao chat rapidamente de qualquer tela.

## 14. Design e experiência visual

Criar uma interface moderna, acolhedora, clara e organizada, com aparência de produto financeiro confiável.

Diretrizes:
- Evitar aparência excessivamente corporativa ou complexa.
- Utilizar hierarquia visual clara.
- Destacar valores e informações importantes sem sobrecarregar a tela.
- Utilizar cards para resumos e seções.
- Utilizar gráficos simples, com legendas legíveis.
- Adotar cores consistentes para receitas, despesas, pendências e projeções.
- Não depender exclusivamente de cores para transmitir status.
- Garantir contraste, legibilidade e navegação por teclado.
- Criar estados de carregamento, sucesso, erro e ausência de dados.
- Evitar telas cheias de informações irrelevantes.
- Utilizar linguagem acessível, evitando jargões financeiros.

## 15. Arquitetura e persistência dos dados

Utilizar a estrutura de backend e banco de dados compatível com o ambiente disponível no Lovable, priorizando opções gratuitas com limites claros.

A aplicação precisa de persistência real. Os dados não podem desaparecer quando o usuário atualiza a página ou encerra a sessão.

Entidades principais sugeridas:
- Usuários.
- Contas financeiras.
- Cartões.
- Categorias.
- Movimentações.
- Contas futuras.
- Metas financeiras.
- Preferências do usuário.

Cada registro financeiro deverá estar associado ao usuário correto.

### Segurança

- Implementar autenticação quando houver dados pessoais persistidos.
- Restringir o acesso aos registros ao respectivo proprietário.
- Utilizar regras de segurança no banco de dados, além de controles na interface.
- Nunca expor chaves secretas no código do frontend.
- Não armazenar senhas bancárias.
- Não enviar dados desnecessários a serviços externos.
- Não registrar conteúdo financeiro sensível em logs desnecessários.
- Tratar erros sem revelar informações privadas.
- Fornecer uma forma de sair da conta.
- Prever exclusão dos dados do usuário conforme as funcionalidades e os recursos disponíveis.

Antes de implementar qualquer serviço externo, verificar se exige cadastro, chave de API, cobrança ou limite de uso. Não simular integração real com um serviço indisponível.

## 16. Regras de integridade financeira

As seguintes regras devem ser respeitadas em todas as telas e operações:

1. Cada movimentação confirmada deve ser persistida uma única vez.
2. Operações de importação devem evitar duplicações e sinalizar possíveis correspondências.
3. O pagamento da fatura não deve duplicar despesas já registradas pelas compras.
4. Transferências entre contas próprias não devem aumentar ou reduzir artificialmente a renda ou os gastos totais.
5. Estornos e reembolsos devem ser identificados de forma consistente.
6. Valores desconhecidos não podem ser inventados.
7. Os relatórios devem ser calculados a partir dos registros persistidos.
8. Alterações ou exclusões devem refletir nos totais e gráficos.
9. Projeções devem ser claramente identificadas como estimativas.
10. Registros não confirmados não devem ser contabilizados nos relatórios.

## 17. Estratégia de implementação por fases

Desenvolver o aplicativo incrementalmente, garantindo que cada fase funcione antes de avançar.

### Fase 1 — Fundação
- Estrutura do projeto.
- Design responsivo.
- Autenticação.
- Banco de dados persistente.
- Proteção dos dados por usuário.
- Navegação principal.

### Fase 2 — Núcleo financeiro
- Cadastro manual de receitas e despesas.
- Categorias.
- Contas e cartões básicos.
- Histórico de movimentações.
- Edição e exclusão.
- Regras de cálculo financeiro.

### Fase 3 — Chat financeiro
- Interface de conversa.
- Interpretação de mensagens para registrar movimentações.
- Perguntas de esclarecimento.
- Confirmação das operações.
- Consulta de dados reais.
- Tratamento de erros e indisponibilidade de IA.

### Fase 4 — Importação por texto
- Colagem de faturas e extratos no chat.
- Parser para formatos conhecidos.
- Prévia das movimentações.
- Edição e remoção de linhas.
- Detecção de possíveis duplicatas.
- Confirmação antes de salvar.
- Alternativa estruturada caso não haja IA disponível.

### Fase 5 — Dashboard e metas
- Indicadores financeiros.
- Gráficos por categoria.
- Histórico filtrável.
- Cadastro e acompanhamento de metas.
- Estados vazios e mensagens educativas.

### Fase 6 — Despesas futuras
- Cadastro de contas futuras.
- Lista de vencimentos.
- Termômetro do Mês.
- Cálculo de saldo projetado.
- Gráfico de gastos atuais versus projeção.
- Dicas e Alertas do Agente Financeiro.

### Fase 7 — Validação
- Testes de cálculos.
- Testes de importação.
- Testes de duplicidade.
- Testes de autenticação e isolamento de dados.
- Testes em computadores e celulares.
- Revisão de erros e mensagens.
- Verificação de custos, limites e dependências externas.

Não implementar todas as fases de uma vez. Priorizar um fluxo funcional de ponta a ponta e validar antes de ampliar o escopo.

## 18. Critérios de aceitação do MVP

O MVP será considerado funcional quando:

- O usuário conseguir criar uma conta e acessar seus próprios dados.
- Os registros continuarem disponíveis após recarregar a página.
- For possível registrar, consultar, editar e excluir receitas e despesas.
- O chat conseguir conduzir o registro de uma movimentação sem inventar campos.
- Os cálculos do dashboard corresponderem às movimentações persistidas.
- O usuário conseguir colar um texto estruturado de fatura e revisar os registros encontrados.
- Nenhuma movimentação importada for salva sem a confirmação exigida pelo fluxo.
- Possíveis duplicatas forem sinalizadas.
- O pagamento de uma fatura não duplicar os gastos de compras já registradas.
- O usuário conseguir cadastrar contas futuras e metas.
- A tela de despesas futuras diferenciar valores realizados e projetados.
- O sistema não inventar previsões quando faltarem dados.
- As informações de um usuário não puderem ser acessadas por outro.
- O aplicativo apresentar mensagens compreensíveis em situações de erro, ausência de dados ou indisponibilidade de IA.
- As funções principais puderem ser utilizadas em computador e celular.

## 19. Funcionalidades futuras, fora do MVP

Considerar somente após a validação da versão inicial:
- Importação de arquivos CSV.
- Leitura de PDFs e imagens, caso exista uma solução viável dentro do orçamento.
- Integração bancária e Open Finance.
- Parcelamentos avançados de cartão.
- Recorrência automatizada de contas.
- Alertas proativos e notificações.
- Aplicativo mobile nativo.
- Previsões financeiras mais avançadas.
- Exportação de relatórios.
- Personalização avançada de categorias e regras.

## 20. Instruções finais para o desenvolvimento no Lovable

Antes de escrever grandes quantidades de código:

1. Analise este PRD e identifique a arquitetura mínima necessária.
2. Separe as funcionalidades em fases.
3. Verifique quais recursos exigem serviços externos, chaves, créditos ou cobranças.
4. Apresente as limitações de custo e proponha alternativas gratuitas quando existirem.
5. Não implementar integrações bancárias, OCR ou leitura de PDFs/imagens no MVP.
6. Não criar dados financeiros fictícios como se fossem reais.
7. Não construir apenas telas estáticas: priorizar operações funcionais, persistência real e regras financeiras corretas.
8. Não afirmar que uma funcionalidade está pronta sem testá-la.
9. Começar pela Fase 1 e pela estrutura necessária para o núcleo financeiro.
10. Após cada fase, verificar o funcionamento e corrigir erros antes de prosseguir.

O resultado desejado é um assistente financeiro pessoal simples, confiável e acolhedor, que reduza o trabalho manual e ajude o usuário a compreender melhor suas finanças, com foco em funcionalidade real, segurança e baixo custo.
