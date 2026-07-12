---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Recomendações para agrupamento numérico"
breadcrumb:
  - "TBM Studio"
  - "Solução de problemas e suporte"
  - "Explicação das mensagens de erro"
source_path: "studio/troubleshooting/numeric-grouping-tables-reports.html"
images:
  - "resources/images/studio_images/adhoc-component.png"
  - "resources/images/studio_images/data-group.png"
  - "resources/images/studio_images/identified-problem.png"
  - "resources/images/studio_images/numeric-grouping-table.png"
  - "resources/images/studio_images/numeric-video-ss.png"
  - "resources/images/studio_images/removing-numeric.png"
  - "resources/images/studio_images/report-grouping.png"
  - "resources/images/studio_images/table-transform.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Recomendações para agrupamento numérico

A reformulação da arquitetura do cache no Q2 2026 removerá a capacidade de agrupar em uma dimensão numérica, independentemente dos critérios de cálculo. Você deve abordar as recomendações antes do próximo lançamento para evitar alterações inesperadas no comportamento dos dados.

O mecanismo de recomendação identificou configurações em seu ambiente que atualmente utilizam dimensões numéricas para agrupamento. Tome medidas para garantir uma transição tranquila em todas as fases e evitar interrupções nos seus relatórios e fluxos de dados.

ATENÇÃO:

Se você não seguir essas recomendações antes de uma versã 12.11.20, as dimensões numéricas serão automaticamente filtradas das operações de agrupamento.

## Como resolver

Use as opções abaixo para determinar o caminho de resolução adequado.

**Opção 1** : (recomendada): esta opção é usada quando o agrupamento envolve campos calculados, como valores, porcentagens ou outros valores calculados. Se uma coluna contiver um valor percentual ou decimal, você deverá removê-la do agrupamento.

Observação: resolver a recomendação antes do check-in permite verificar se a alteração de configuração satisfaz o alerta de agrupamento numérico. Se a alteração na configuração não resolver o problema de agrupamento numérico, o alerta reaparecerá após o cálculo.

**Opção 2**

**Recomendação para agrupamento numérico de tabelas**

1. Selecione **Recomendações** e, em seguida, selecione **Agrupamento numérico da tabela: dimensão numérica detectada na etapa de agrupamento** para ver a tabela afetada

   ![tabela de agrupamento numérico](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/numeric-grouping-table.png)
2. Na seção **Problemas identificados**, selecione a tabela afetada e verifique qual campo está afetado na tabela no **NumericGroupings** campo.

   ![problema identificado](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/identified-problem.png)
3. Na tabela selecionada, navegue até a guia **Importar** e altere a dimensão numérica para **Rótulo** para o campo afetado.
4. Selecione **Salvar** e **fazer check-in**
5. Verifique se a recomendação foi resolvida na lista de recomendações. Se o alerta reaparecer, siga as etapas adicionais descritas na **Opção 3**.

**Recomendação de agrupamento numérico do relatório**

1. Selecione **Recomendações** e, em seguida, selecione **Relatório de agrupamento numérico: dimensão numérica usada no agrupamento de relatórios** para ver o relatório afetado.

   ![agrupamento de relatórios](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/report-grouping.png)
2. Na seção **Problemas identificados**, selecione o relatório afetado e verifique qual campo está afetado no relatório no **NumericGroupings** campo.
3. Navegue até a guia **Dados** e selecione **Grupo**.

   ![Guia Dados e Grupo](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/data-group.png)
4. Se a dimensão numérica estiver incluída, selecione *(nenhuma)* no campo **E por** e clique no botão **Agrupar** para salvar as alterações.

   ![Remover numérico](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/removing-numeric.png)
5. Se a dimensão não foi incluída na configuração do botão da barra de faixa **de** opções Grupo, ela ainda pode ser agrupada automaticamente com base em sua posição na configuração do componente.
   1. Isso normalmente significa que a dimensão está incluída nas linhas da configuração do componente, que serão agrupadas por padrão.
   2. Nesse cenário, localize a dimensão no acordeão **Configuração do componente ad hoc**, clique com o botão direito do mouse na dimensão para abrir o menu de contexto, selecione **Desagrupar** e, em seguida, selecione **Salvar**.

      ![Configuração de Componentes Adhoc](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/adhoc-component.png)
6. Resolva as recomendações e selecione **Salvar** e **fazer check-in**.
7. Verifique se a recomendação foi resolvida na lista de recomendações. Se o alerta reaparecer, siga as etapas adicionais descritas na **Opção 3**.

**Opção 3** Se a dimensão numérica tiver que permanecer numérica para fins computacionais, siga as etapas abaixo para criar um equivalente baseado em rótulo para agrupamento.

**Pipelines de tabela**

1. Selecione **Recomendações** e vá para a tabela afetada.
2. Selecione o ícone **+** na guia **Grupo** e, em seguida, selecione **Fórmula** > **Adicionar uma nova coluna**.
3. Crie uma nova coluna com um nome descritivo (por exemplo, se estiver agrupando por department\_id, crie department\_id\_grouping\_label)
4. Defina **o Tipo** da coluna como **Etiqueta.**

   ![transformação de tabela](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/table-transform.png)
5. Defina a **fórmula** para converter o número em texto usando a fórmula NumberFormat :

   ```
   =NumberFormat(numeric_dimension_name, "#")
   ```

   Exemplo: Se a dimensão numérica for denominada DRIVE\_CAPACITY, a fórmula mais simples seria:

   ```
    =NumberFormat(DRIVE_CAPACITY, "#")
   ```
6. Navegue até a guia **Grupo** e substitua a dimensão numérica pela sua nova coluna de rótulo.
7. Selecione **Salvar** e **fazer check-in**.
8. Após o cálculo, confirme se a recomendação foi resolvida e não reapareceu.

**Para componentes do relatório:**

1. Selecione **Recomendações** e acesse o relatório afetado.
2. Verifique o relatório e selecione o componente problemático para abrir o painel de configuração do componente do relatório ad hoc.
3. Navegue até a guia **Dados**, selecione a seta suspensa **Inserir** e selecione **Inserir uma nova coluna de fórmula**.
   - Se o botão **Inserir** estiver desativado, remova/mova todas as colunas atualmente na seção Colunas do painel de configuração do componente de relatório ad hoc. Você pode adicioná-los novamente.
4. Adicione um nome de coluna, insira a coluna de fórmula fornecida acima e selecione o **rótulo** Tipo.
5. Substitua a dimensão numérica antiga pelo novo rótulo equivalente no painel de configuração do componente do relatório ad hoc e, em seguida, substitua a coluna numérica pelo novo rótulo equivalente, atualizando-o no botão da barra de faixa de opções Grupo do componente do relatório ad hoc, localizado na guia **Dados**
6. Selecione **Salvar** e **fazer check-in**
7. Após o cálculo, confirme se a recomendação foi resolvida e não reapareceu

[![Vídeo sobre agrupamento numérico](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/numeric-video-ss.png)](https://community.ibm.com/community/user/viewdocument/test-76?CommunityKey=44bcb0d2-5ce6-4504-89eb-019253d3b5d8 "(Abre em uma nova guia ou janela)")

## Validação da correção

- Depois de salvar suas alterações e fazer o check-in, se a recomendação reaparecer, a alteração de configuração não atendeu ao requisito de agrupamento numérico. Neste caso:
- - Verifique se você salvou todas as alterações de configuração
  - Certifique-se de ter removido TODAS as dimensões numéricas da operação de agrupamento
  - Verifique se a nova coluna de etiqueta está configurada corretamente (se estiver usando a solução alternativa)
