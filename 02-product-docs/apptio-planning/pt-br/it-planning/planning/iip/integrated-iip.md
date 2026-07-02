---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Planejamento integrado de investimentos"
breadcrumb: []
source_path: "it-planning/planning/iip/integrated-iip.html"
images:
  - "resources/images/it_planning_images/itp-project-column.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Planejamento integrado de investimentos

Importante: *Disponível com a* *assinatura* ***do Apptio Planning Standard***

Integrated Investment Planning permite que os proprietários do orçamento do projeto planejem os custos relacionados ao projeto com os custos operacionais em um único plano integrado. Integrated Investment Planning introduz um atributo Project opcional em todas as exibições de despesas. Se a despesa que estiver inserindo não estiver relacionada ao projeto, deixe-a em branco. Se a despesa estiver relacionada ao custo do projeto, selecione um centro de custo que seja a fonte de financiamento do projeto e marque a despesa com o identificador do projeto

Para planejar despesas de ativos, mão de obra, contratos e outras despesas financeiras para custos relacionados a projetos e não relacionados a projetos, você pode seguir a documentação existente para Gerenciar custos diretos. Integrated Investment Planning introduz as seguintes alterações no processo.

- O centro de custos é um campo obrigatório em todos os tipos de despesas.
- O campo Objeto de custo é somente de leitura e é preenchido automaticamente ao selecionar Centro de custo, com base no mapeamento de Objeto de custo para Centro de custo definido nos dados de referência.
- O projeto é um campo opcional em todos os tipos de despesas. Você pode atribuir o identificador de projeto somente às despesas orçadas para o projeto.
- A seleção do identificador do projeto na linha de despesas filtra automaticamente os valores do menu suspenso Centro de custo para os centros de custo aplicáveis a esse projeto, conforme definido nos dados de referência do projeto.
- Cada tipo de despesa tem o atributo Cost Type, que pode ser definido como Run ou Build. Se a linha de despesas que você está inserindo estiver relacionada a manutenção, suporte ou serviços relacionados a aplicativos e/ou infraestrutura existentes, essas despesas devem ser categorizadas como custo de execução e as despesas alocadas para novos investimentos e iniciativas devem ser categorizadas como custo de construção.

  ![imagem](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/itp-project-column.jpg)

  Para obter mais detalhes sobre planejamento e alocação de mão de obra, consulte [Planejamento de recursos de mão de obra](labor-resource-planning.html).
