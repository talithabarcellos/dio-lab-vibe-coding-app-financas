Vamos implementar a **Fase 4 — Importação Conversacional de Faturas e Extratos**.

O objetivo é permitir que o usuário copie o texto de uma fatura de cartão ou extrato bancário e cole diretamente no chat para organizar várias movimentações de uma vez.

Não implemente integração bancária, leitura de PDFs, OCR ou processamento de imagens.

### Fluxo obrigatório

1. O usuário cola o texto no chat.
2. O sistema identifica as possíveis movimentações.
3. O aplicativo extrai as datas, descrições, valores, tipos e categorias quando possível.
4. O assistente apresenta uma prévia editável.
5. O usuário pode corrigir ou remover linhas.
6. O sistema sinaliza possíveis duplicatas.
7. O usuário confirma quais registros deseja importar.
8. Somente os registros confirmados são salvos.
9. O assistente informa quantas movimentações foram importadas e quais apresentaram problemas.

### Regras importantes

- Não salvar automaticamente todas as linhas coladas.
- Não inventar valores, datas ou descrições.
- Não descartar possíveis duplicatas sem consultar o usuário.
- Não contabilizar o pagamento da fatura como uma nova despesa se as compras já estiverem registradas.
- Diferenciar compras, pagamentos, transferências e estornos quando houver informações suficientes.
- Preservar a descrição original.
- Permitir importação parcial quando apenas algumas linhas forem válidas.
- Não guardar o texto bruto da fatura permanentemente por padrão.

### Solução de baixo custo

Implemente primeiro um parser para formatos de texto conhecidos, incluindo datas brasileiras e valores como `125,90`.

Se houver uma solução de IA disponível dentro do orçamento real do projeto, ela poderá auxiliar na interpretação de formatos variados. Caso contrário, ofereça um modo estruturado de colagem e revisão manual.

Não invente uma integração nem apresente uma funcionalidade simulada como concluída.

Ao terminar, teste a importação de múltiplas linhas, os valores, as datas, as duplicatas, as linhas inválidas e a confirmação antes de salvar.