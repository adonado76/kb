---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Alocações não utilizadas"
breadcrumb: []
source_path: "studio/troubleshooting/unused-allocation.html"
images:
  - "resources/images/studio_images/ua-1.jpg"
  - "resources/images/studio_images/ua-2.jpg"
  - "resources/images/studio_images/ua-5.jpg"
  - "resources/images/studio_images/ua-6.jpg"
  - "resources/images/studio_images/unusd-alloc.jpg"
  - "resources/images/studio_images/za-1.jpg"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Alocações não utilizadas

Navegue até o **TBM Studio** >� guia **Recommendations (Recomendações** ) > **Zero Unit Allocations (Alocações de unidade zero** ) e, em seguida, selecione **Troubleshoot All Identified Problems (Solucionar todos os problemas identificados)**.

![Alocações não utilizadas](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/unusd-alloc.jpg)

Mude para o espaço de trabalho **Development** e selecione **Next**.

![Assistente de recomendações](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ua-1.jpg)

Você pode ver a descrição do problema e quais ações serão tomadas para resolvê-lo. As alocações não utilizadas são listadas em cada objeto do modelo. Posso ver as alocações não utilizadas por Nome da alocação, Para o objeto e Métricas marcadas para o objeto AWS Cost Allocation Bill.

![Alocações não utilizadas](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ua-2.jpg)

Selecione o botão **Excluir alocação** para corrigir individualmente.

Rolando para baixo até o objeto de modelo "Aplicativos", é possível ver as alocações com várias métricas marcadas. As métricas em "preto" são alocações ativas, enquanto as métricas em "vermelho" são alocações não utilizadas.

Marquei a caixa de seleção para *App Dev\_Budget, Budget* Business Services e selecionei o botão **Perform selected fixes for Applications**.

![Excluir alocação](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/za-1.jpg)

Da mesma forma, tome as medidas apropriadas para o restante das seções.

Depois de concluído, o status da alocação não utilizada é alterado.

![Pronto](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ua-5.jpg)

Selecione **Next** e, em seguida, selecione **Checkin** na última página.

![Check-in](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ua-6.jpg)
