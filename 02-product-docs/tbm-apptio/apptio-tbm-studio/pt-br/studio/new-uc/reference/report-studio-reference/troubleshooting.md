---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Resolução de problemas"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Filtros e segmentadores"
source_path: "studio/new-uc/reference/report-studio-reference/troubleshooting.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Resolução de problemas

**O Slicer não exibe valores**

**Possíveis causas:**

- Campo incompatível com os dados atuais
- Todos os valores filtrados por filtros no nível dos componentes
- !ALL\_ROWS desativado e sem dados no período atual
- Campo sob uma perspectiva incompatível

**Solução:** Verifique a origem do campo na perspectiva, verifique os filtros no nível do componente, teste com diferentes intervalos de tempo e verifique!Configuração do projeto ALL\_ROWS.

**A seleção do cortador não tem efeito**

**Possíveis causas:**

- Seleção de valores não relacionados (desativados)
- Slicer na caixa de grupo, componentes fora do grupo
- O Slicer está em uma guia diferente da dos componentes de destino
- Tabela/gráfico antigo não compatível com filtros

**Solução:** Verifique o escopo do filtro (nível de grupo ou de relatório), certifique-se de que os componentes utilizam o formato de consulta ad hoc, garanta que o filtro e os componentes estejam na mesma guia e verifique se há filtros conflitantes em outros filtros.

**Tópico principal:** [Componentes do relatório: Filtros e segmentadores](../../../../studio/new-uc/reference/report-studio-reference/report-component-filters-slicers.html)
