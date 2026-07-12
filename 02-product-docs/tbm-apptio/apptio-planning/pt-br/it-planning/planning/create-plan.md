---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Criação de planos"
breadcrumb:
  - "Planning"
  - "Criação e gerenciamento de planos"
source_path: "it-planning/planning/create-plan.html"
images:
  - "resources/images/icons/icon-add.png"
  - "resources/images/it_planning_images/settings-icon.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Criação de planos

Observação: As funções de administrador ou de proprietário do processo orçamentário são necessárias para gerenciar planos.

Apptio O Planning permite que você crie e gerencie planos financeiros que apoiam tanto o orçamento quanto a previsão. Os planos fornecem um espaço de trabalho central para a criação de orçamentos, ajuste de previsões e alinhamento de investimentos entre departamentos, projetos e recursos.

## Tipos de planos

Apptio O planejamento oferece suporte a dois tipos de planos:

- **Plano orçamentário -** Um plano sem dados reais. Todos os períodos são editáveis, o que permite criar um plano do zero ou redefinir projeções sem dados históricos.
- **Forecast Plan (Plano de previsão** ) - Um plano que inclui dados reais de períodos históricos (obtidos do Spend Management). Somente os períodos futuros são editáveis, de modo que você pode ajustar as projeções com base no desempenho passado.

## Criação de um plano

1. No menu de navegação, selecione **Planejamento** > **Planos**
2. Selecione o botão ![botão de adição](../../../../../03-media/apptio-planning/resources/images/icons/icon-add.png) .
3. Escolha um **tipo de plano** (orçamento ou previsão)
4. Insira os seguintes detalhes:

   |  |  |
   | --- | --- |
   | **Item** | **Descrição** |
   | Ano de início do plano | Selecione o ano inicial do plano. |
   | Comprimento do plano | Selecione a duração do plano (até dez anos). |
   | Período inicial da previsão  (Somente previsão) | Selecione o primeiro período editável para a previsão. Os períodos históricos serão preenchidos previamente com dados reais. Para criar um plano de previsão usando apenas dados reais para a duração do plano selecionado, selecione **Nenhum** como Período inicial da previsão. |
   | Referência de linha de base | Opcionalmente, copie dados de um plano existente para usar como linha de base. |
   | Códigos de itens de linha de cópia | Escolha copiar os códigos de item de linha da linha de base ou gerar novos códigos.  Saiba mais sobre [os códigos de itens de linha](line-item-codes.html). |
   | Dados do plano de preenchimento automático | Se a linha de base e o novo plano incluírem anos fiscais diferentes, essa opção preencherá os valores ausentes com dados do último ano da linha de base. |
   | Nome do plano | Digite um nome exclusivo para o plano. |
5. Clique no botão **Create Plan (Criar plano** ).

   Quando a criação do plano começa, o plano aparece na página Planos com o status **Pendente**. Após a conclusão, você verá uma mensagem de confirmação e o plano ficará disponível para seleção no Planning.

   Observação: a criação de um plano a partir de uma linha de base pode levar vários minutos se grandes volumes de dados estiverem sendo copiados.

## Módulos de planejamento

Os planos podem ser ampliados com módulos adicionais para cobrir uma variedade de necessidades de planejamento:

- **Planejamento financeiro** - Planeje as despesas operacionais ( OpEx ) e as despesas de capital ( CapEx ). Esse módulo é ativado por padrão em todos os planos.
- **Planejamento de mão** de obra - Planeje o número de funcionários e os custos de mão de obra.
- **Planejamento de contratos** - Planeje contratos de fornecedores com opções de amortização.
- **Planejamento de ativos** - Planeje a compra e a depreciação de ativos.
- **Planejamento do projeto** - Planeje as despesas do projeto (construção vs. execução).
- **Planejamento de atividades de mão** de obra de projetos - Capture o esforço e os custos de mão de obra para projetos.

**Para ativar os módulos** :

1. No canto superior direito, navegue até **Configurações** (![](../../../../../03-media/apptio-planning/resources/images/it_planning_images/settings-icon.jpg) ) > **Perfil da empresa**.
2. Selecione os módulos que deseja ativar:
   - Número de funcionários
   - Contratos
   - Ativos
   - Permitir o planejamento integrado de investimentos
   - Atividade trabalhista (requer planejamento integrado de investimentos)
