---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Tipo de atividade trabalhista"
breadcrumb:
  - "Planning"
  - "Planejamento de atividades de trabalho do projeto"
source_path: "it-planning/planning/iip/manage-labor-activity-type-data-ref.html"
images:
  - "resources/images/it_planning_images/three-dots.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Tipo de atividade trabalhista

Importante: *Disponível com a* *assinatura* ***do Apptio Planning Standard***

Lembre-se: *o recurso de Planejamento Integrado de Investimentos (IIP) está ativado.*

Os dados de referência **do Tipo de atividade de** mão de obra definem como os custos de mão de obra e os custos cruzados fluem entre o **provedor** (Centro de custos do departamento) e **o consumidor** (Centro de custos do projeto) com base no tipo de atividade de mão de obra realizada.

Cada Tipo de Atividade de Mão de Obra especifica as contas financeiras utilizadas para cobrar e creditar a mão de obra, e se a atividade é capitalizável. Esses mapeamentos são usados durante [o Planejamento de Atividades de Mão de Obra](labor-resource-planning.html) para garantir que os custos de mão de obra sejam alocados com precisão aos centros de custo corretos.

## Configurar tipo de atividade de mão de obra

***Observação:*** *as funções de administrador ou responsável pelo processo orçamentário são necessárias para realizar essas tarefas.*

1. No menu de navegação, vá para: **Dados de referência** → **Dimensões padrão** → **Tipo de atividade de trabalho**
2. Clique no ![menu de elipses](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/three-dots.jpg) menu e **em Exportar modelo**.
3. Baixe o modelo e preencha os campos obrigatórios:

   |  |  |
   | --- | --- |
   | **Campo** | **Descrição** |
   | **Nome** | O nome da atividade de trabalho (por exemplo, Desenvolvimento, Suporte, Manutenção). Este é o valor selecionado ao planejar o esforço de mão de obra na guia Atividade de mão de obra. |
   | **Conta de cobrança** | O código da conta do centro de custos do departamento (prestador) que recebe o crédito quando a mão de obra é fornecida a um projeto ou a outro centro de custos. |
   | **Conta de cobrança cruzada** | O código da conta do centro de custos do projeto (consumidor) que recebe o débito pela mão de obra consumida. |
   | **É capitalizável** | Indica se a mão de obra para este tipo de atividade pode ser capitalizada. - Verdadeiro: Os custos com mão de obra são elegíveis para capitalização. - Falso: os custos com mão de obra são contabilizados como despesas. |
   | **É Padrão** | Determina o Tipo de Atividade de Trabalho padrão aplicado quando os usuários inserem o trabalho na guia Atividade de Trabalho. - Apenas um tipo de atividade pode ser marcado como padrão. - Se um usuário não selecionar um Tipo de Atividade, o valor padrão será aplicado. |
4. Importe o CSV atualizado.
5. Clique no ![menu de elipses](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/three-dots.jpg) menu e **publique** as alterações para que elas fiquem disponíveis para os planos.
