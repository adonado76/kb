---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Carga cruzada de atividade trabalhista"
breadcrumb: []
source_path: "it-planning/planning/iip/configure-cross-charge.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Carga cruzada de atividade trabalhista

Importante: *Disponível com a* *assinatura* ***do Apptio Planning Standard***

Quando o projeto usa recursos de mão de obra do Centro de custos de recursos, no lado da contabilidade do Centro de custos do projeto, a despesa da atividade de mão de obra é um valor de débito ou débito. Para evitar a contagem dupla da despesa, o proprietário do centro de custos de recursos deve receber a cobrança cruzada ou o crédito pela mesma atividade.

Você pode configurar o suporte a cobranças cruzadas em Integrated Investment Planning configurando os dados de referência da conta de atividade de trabalho.

Para obter mais informações, consulte [Gerenciar dados do tipo de atividade de trabalho](manage-labor-activity-type-data-ref.html)

Quando o tipo de atividade é definido na linha Atividade de mão de obra, os dados financeiros são gerados para alocar a cobrança (débito) na conta de cobrança e a cobrança cruzada (crédito) na conta do centro de custo de recursos.

Se estiver alocando recursos do fornecedor e, nesse caso, a despesa da atividade de mão de obra for contabilizada para o projeto que usa esses recursos, mas não houver necessidade de fazer a cobrança cruzada dessa despesa, você poderá implementar esse caso de uso configurando o tipo de atividade de modo que ele tenha uma conta de cobrança, mas nenhuma conta de cobrança cruzada.

Você pode visualizar o valor da cobrança e da cobrança cruzada gerada nos respectivos centros de custo e contas na visualização Despesas > Resumo.
