---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Ajustes de remuneração de mão de obra"
breadcrumb:
  - "Planning"
  - "Planejamento trabalhista"
source_path: "it-planning/planning/plan-labor-compensation.html"
images:
  - "resources/images/it_planning_images/comp3.png"
  - "resources/images/it_planning_images/comp4.png"
  - "resources/images/it_planning_images/comp5.png"
  - "resources/images/it_planning_images/newview.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Ajustes de remuneração de mão de obra

Os ajustes de remuneração de mão de obra permitem que as organizações modelem aumentos (ou reduções) de remuneração ao longo do tempo no site Apptio Planning. Esse recurso oferece uma forma estruturada de contabilizar os ajustes salariais planejados, como aumentos por mérito, ajustes de mercado, promoções ou mudanças no custo de vida.

Quando ativados, os usuários podem definir porcentagens de ajuste e datas efetivas que atualizam automaticamente os valores de remuneração base para o número de funcionários existentes ou planejados. Os ajustes são aplicados a partir da data de vigência e fluem para os cálculos financeiros, incluindo custos de mão de obra totalmente onerados e alocações departamentais.

## Pré-requisitos

Antes de poder usar esse recurso:

- O planejamento do **número de funcionários** deve ser ativado em **Settings → Company Profile**.
- Os proprietários de orçamento precisam das permissões **View Sensitive Financials** e **View Sensitive Columns** para ver os campos de ajuste.

## Configurar ajustes de compensação

1. Vá para **Configurações → Perfil da empresa → Planejamento de mão de obra**
2. Ative **os ajustes de remuneração variável**.
3. **Definir ciclos de compensação padrão**
   1. Especifique os **ciclos de remuneração** padrão de sua organização, normalmente alinhados com os cronogramas de aumento por mérito ou de mercado.
   2. Selecione os períodos em que os ajustes de remuneração são permitidos.
   3. Esses padrões podem ser modificados posteriormente no nível do plano.

   ![imagem do ciclo de ajuste da compensação variável](../../../../../03-media/apptio-planning/resources/images/it_planning_images/comp3.png)
4. **Configurar por plano**
   - Navegue até **Plan → Settings → Labor Compensation Adjustment**.
   - Selecione o botão **Compensation Cycle (Ciclo de remuneração** ) e revise ou ajuste os ciclos do plano atual.

   ![imagem do plano de configuração](../../../../../03-media/apptio-planning/resources/images/it_planning_images/comp4.png)
5. **Definir taxas de ajuste padrão**
   - A tabela **Ajuste de remuneração de mão de obra** obtém taxas padrão da tabela de dados de referência de **taxas de mão de obra**.
   - Para cada combinação de função (função, fornecedor, local, tipo de funcionário), especifique uma porcentagem de ajuste padrão para cada ciclo de remuneração definido (por exemplo, 2% em março, 1% em setembro).
   - Opcionalmente, exporte um modelo, atualize as porcentagens de ajuste e importe-o novamente.

   ![imagem das taxas de ajuste de inadimplência](../../../../../03-media/apptio-planning/resources/images/it_planning_images/comp5.png)
6. **Revisão das tarifas ajustadas**
   1. O campo **Adjusted Base Rate (Taxa básica ajustada** ) exibe o novo valor da remuneração após o ajuste entrar em vigor.
   2. Na **Nova visualização**, o campo **Ajuste** aparecerá para cada item de linha de mão de obra, permitindo que você aplique ou substitua as taxas diretamente na guia Mão de obra.
   3. As alterações são salvas automaticamente e refletidas nos cálculos do plano.

## Permissões

É possível controlar quem pode visualizar ou editar ajustes de remuneração:

- **ITPCompensationAdjustmentEdit** - Permite substituir as porcentagens padrão para ciclos de compensação definidos.
- **ITPCompensationAdjustmentAllPeriodsEdit** - Permite a edição de porcentagens em todos os períodos.
- **canEditPlanSettings** - Necessário para modificar a página **Plan Settings (Configurações do plano** ).
- **canViewPlanSettings** - Necessário para visualizar a página **Plan Settings (Configurações do plano** ).
- Por padrão, essas permissões são concedidas às funções de **Administrador** e **Proprietário do Processo Orçamentário**.
- Se você quiser que **os proprietários do orçamento** gerenciem os ajustes de remuneração, conceda a eles as permissões apropriadas com base em seu modelo de governança.

## Como planejar um ajuste de remuneração

É possível modelar as alterações de remuneração diretamente no plano de mão de obra - usando a **New View** para ajustes interativos e baseados em períodos ou a **Legacy View** para um modelo de ajuste anual mais simples.

***Em New View***

1. **Abrir o plano**
   1. Selecione seu plano e escolha o **departamento** apropriado.
   2. Navegue até **Planning → Expenses → Labor**.
2. **Abra a gaveta de ajustes**
   1. Na tabela Trabalho, selecione o botão **Ajuste** na coluna **Ajustes** da linha de trabalho que você deseja atualizar.
   2. O **gaveteiro Ajustes** exibe as porcentagens padrão se elas tiverem sido configuradas na tabela **Configurações do plano → Ajuste da remuneração do trabalho**.
3. **Revisão e modificação de ajustes**
   1. Você pode substituir as porcentagens padrão para períodos específicos se tiver as permissões necessárias.
   2. A gaveta mostra o **custo de mão de obra totalmente onerado por Conta** para a linha de mão de obra selecionada - essas contas se alinham com suas **Regras de alocação de mão de obra** configuradas.
   3. Os ajustes atualizam automaticamente o custo total da mão de obra, permitindo que você veja o impacto financeiro em tempo real.

![revisão do ajuste de imagem](../../../../../03-media/apptio-planning/resources/images/it_planning_images/newview.png)

Observação: Se os Ajustes de remuneração variável de mão de obra estiverem ativados, os ajustes de mão de obra não poderão ser modificados na visualização herdada. Se esse recurso estiver ativado, a única maneira de restaurar os ajustes de mão de obra na visualização antiga é desativar o recurso no Perfil da Empresa e recriar manualmente o plano (isso removerá os códigos dos itens).

***Em Legacy View***

1. **Abrir o plano**
   1. Selecione seu plano e escolha o **departamento** apropriado.
   2. Navegue até **Planning → Expenses → Labor.**
2. **Inserir detalhes de ajuste**
   1. **Data efetiva do** ajuste - A data em que o ajuste começa.
      1. Se o plano abranger vários anos, o ajuste será composto ano a ano a partir dessa data.
   2. **Ajuste %** - A taxa de aumento (positiva) ou diminuição (negativa).
3. **Revisar resultados**
   1. O sistema aplica o ajuste a jusante para o restante do período do plano.
   2. Você pode revisar o impacto do custo atualizado na guia **Resumo**, onde os itens de linha financeira ajustados são refletidos com base nas **Regras de alocação de mão de obra** configuradas.

**Interação com regras de alocação com efeito temporal no nível do plano**

Quando são configuradas **regras de alocação de mão de obra** com validade temporal no nível do plano, os ajustes de remuneração utilizam a taxa de alocação válida para o período correspondente no plano.

**O custo total** apresentado na aba “**Ajustes** ” reflete a taxa de alocação baseada no tempo aplicável a cada período, em vez da taxa padrão global. Isso garante que os ajustes de remuneração permaneçam alinhados com os pressupostos de alocação definidos no plano.

Por exemplo, se um plano definir uma taxa de benefício de **7% no Ano 1** e **de 8% no Ano 2**, um reajuste salarial aplicado no Ano 2 será calculado com base na **taxa de benefício de** 8%. Como as taxas de alocação variam ao longo do tempo, os ajustes de remuneração utilizam automaticamente a taxa vigente no período em que o ajuste é aplicado.
