---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Funções da tabela"
breadcrumb: []
source_path: "studio/data_studio/table-functions.html"
images:
  - "resources/images/icons/dropdown.png"
  - "resources/images/studio_images/datapath-databases.png"
  - "resources/images/studio_images/studioimages/datapath-1.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Funções da tabela

**Aplica-se a** : TBM Studio 12.0 e posterior

## Como as funções de tabela são usadas em um caminho?

1. Na visualização TBM Studio **Project Explorer**, selecione **Tables (Tabelas** ).
2. Selecione uma tabela (por exemplo, nome da tabela: XYZ) **>** Check out XYZ).
3. Adicione uma etapa do modelo **>** selecione **Modelo** **>** selecione XYZ **>** selecione **Usar identificador de objeto**.
4. Selecione o menu suspenso **>** selecione **Application Family** e **Application Function** **>** selecione **Save**.
5. Agora, você precisa criar um novo relatório. Selecione **Novo** **> Relatório** **>** Escrever um nome de relatório **>** **Ok**. **Observação:** Você precisa iniciar o nome do relatório com Texto, e não com números.
6. Selecione a tabela XYZ na **seção Ad Hoc Component Configuration**.
7. No **Project Explorer**, expanda ![](../../../../../03-media/apptio-tbm-studio/resources/images/icons/dropdown.png) ao lado da tabela XYZ e arraste **Application Family** para **Rows**. Os componentes da tabela são carregados com agrupamento automático.
8. Clique com o botão direito do mouse dentro da tabela **>** selecione Show full datapath (Mostrar caminho de dados completo). Você pode ver as funções de tabela GROUPBY, SORT e LIMIT\_COLUMNS.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/datapath-1.png)
9. Para aplicar o!FILTRO nessa tabela, clique em **OK** para sair dessa janela.
10. Agora, suponha que você não queira usar bancos de dados. Coloque!Bancos de dados aqui:

    ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/datapath-databases.png)
11. Os bancos de dados não estão mais lá. Agora, clique com o botão direito do mouse dentro da tabela **>** selecione **Show Full Data Path (Mostrar caminho completo dos dados** ). Agora você pode ver o!Função de filtro

## Como usar essas funções de tabela para obter seus valores em uma tabela editável?

1. Confira uma tabela editável.
2. Selecione **Configure Columns (Configurar colunas) >** selecione **Add a new column (Adicionar uma nova coluna) >** selecione **Possible Values (Valores possíveis) >**.
3. Você pode colocar a sintaxe da função da tabela em **Valores possíveis >** selecione **Salvar >** selecione **Tabela editável** no pipeline.
4. Depois que a tabela for carregada, você terá uma nova coluna. Você pode clicar nas células da nova coluna para selecionar no menu suspenso com as funções da tabela.

Saiba mais sobre as várias funções de tabela para obter seus valores na tabela editável:

- [!GROUPBY[]](groupby.html)
- [!LIMIT\_COLUMNS[]](limit-columns.html "Determina as colunas exibidas em uma tabela. Você pode limitar as colunas usando a faixa de opções.")
- [!SORT[]](sort.html "Classifica uma tabela em uma ou mais colunas especificadas na tabela. Você pode classificar uma tabela usando a faixa de opções. O!A função SORT pode ser aplicada usando uma, duas ou mais colunas em uma tabela.")

**Tópico pai:** [Tabelas editáveis: Acomodando a entrada do usuário](../../studio/data_studio/editabletables.html "Aplica-se a: TBM Studio 12.6 e posterior")
