---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Upload em massa de valores de itens de linha"
breadcrumb:
  - "Planning"
  - "Trabalhando com planos"
source_path: "it-planning/planning/enter-import-line.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Upload em massa de valores de itens de linha

Faça o upload em massa de dados carregando um arquivo CSV para o seu plano financeiro.

## Permissões

- **Os** administradores e **proprietários de processos orçamentários** podem carregar dados de itens de linha em toda a organização.
- **Os proprietários de centros de custo** podem fazer upload para os departamentos aos quais têm acesso de edição.
- **Os gerentes de projeto** podem fazer upload para os projetos aos quais têm acesso de edição.

## Modos de importação

Ao realizar um upload em massa, você poderá escolher entre os seguintes modos de importação:

|  |  |
| --- | --- |
| **Modo** | **Comportamento** |
| Substituir todos os dados | Limpa os valores existentes e os substitui inteiramente pelos valores do arquivo de importação. Cada linha importada terá um novo código de item de linha. |
| Substitua todos os dados pelo filtro de dimensão | Permite a importação de itens de linha para substituir seletivamente os dados apenas para as dimensões específicas. Os usuários podem selecionar uma ou mais dimensões para substituir seletivamente os dados. Cada linha importada terá um novo código de item de linha.  A filtragem pelas seguintes dimensões é suportada   1. Conta 2. Centro de Custos 3. Objeto de custo 4. Projeto 5. Fornecedor 6. Local 7. Dimensões personalizadas 8. Colunas personalizadas do tipo de dados Lista |
| Atualizar dados | Atualiza as linhas existentes fazendo a correspondência com o Line Item Code. Se o código externo estiver ativado, o sistema fará a correspondência entre o código do item de linha e o código externo durante o processo de atualização. Todas as linhas do arquivo de importação que não corresponderem a um código de item de linha ou código externo existente serão adicionadas como novos itens de linha, e um novo código de item de linha será gerado automaticamente. |
| Anexar dados | Adiciona todos os itens da linha do arquivo ao Plano sem modificar ou excluir os dados existentes. Use esta opção para importar apenas novos registros. Cada nova linha receberá um Código de Item de Linha exclusivo. |

## Etapas para fazer upload em massa de valores de itens de linha

1. Abra o plano e navegue até a guia Despesa apropriada (por exemplo, **Trabalho**, **Atividade de trabalho**, **Contratos**, **Ativos** ou **Outros** ).
2. Selecione o **departamento** para o qual deseja importar dados no menu Departamento.
3. Abra o menu **Ações** no canto superior direito e selecione **Importar...**
4. Carregue seu **arquivo** CSV e selecione o **modo de importação** desejado (Substituir todos os dados, Atualizar dados, Anexar dados ou Substituir todos os dados com filtro de dimensão).
   1. **Usando Substituir todos os dados com filtro de dimensão**
      1. Na caixa de diálogo Importar, clique no botão **Adicionar** **filtro** **de dimensão.**
      2. Selecione **uma dimensão** **.**
      3. Selecione um ou mais valores para a dimensão selecionada.
      4. *(Opcional)* **Adicione dimensões adicionais** e especifique valores para cada uma delas.
      5. Quando vários filtros são aplicados, os dados serão substituídos apenas para as linhas que atendem *a todos* os critérios de filtro.
   2. **Para usar qualquer outro modo de importação** (Substituir todos os dados, Atualizar dados ou Anexar dados), selecione a opção de importação desejada.
5. *(Opcional)* Ajuste as configurações de importação, como delimitador de coluna, formato de data, símbolo decimal, exibição de porcentagem e codificação de caracteres.
6. Clique em **Importar** para gerar uma visualização.
7. Revise a visualização para confirmar se os dados estão mapeados e formatados corretamente.
8. Se estiver correto, clique em **Importar** para finalizar ou em **Importar com problemas** se quiser prosseguir apesar dos avisos. Você também pode **exportar o arquivo de ajuda** para analisar detalhadamente os erros de importação.
9. Depois de concluídos, os dados são adicionados com êxito ao plano e ficam visíveis na tabela **Expenses (Despesas** ).

Observação: as colunas “Período” e “Mês” são preenchidas automaticamente com base na **Data** de início, **na Data de término** e **na Quantidade** inseridas. O sistema distribui a quantidade especificada pelos meses dentro do intervalo de datas selecionado. Os usuários podem alterar esses valores gerados automaticamente, se necessário.

## Exportar um modelo para importação

1. Abra o plano e navegue até a guia Despesa apropriada (por exemplo, **Trabalho**, **Atividade de trabalho**, **Contratos**, **Ativos** ou **Outros** ).
2. Clique no menu **Ações** no canto superior direito e selecione **Exportar modelo...**
3. Clique em **OK** para fazer o download do arquivo de modelo gerado. **Não altere os cabeçalhos ou a estrutura das colunas** - eles são necessários para a consistência da importação.
4. Preencha o modelo com seus dados de item de linha.
5. Salve o arquivo no formato.csv e importe-o novamente para o Apptio Planning quando estiver pronto.
