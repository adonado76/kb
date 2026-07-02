---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "pt-br"
doc_type: "it-benchmarking"
title: "Alinhamento de taxonomia e versão"
breadcrumb:
  - "Benchmarking"
  - "Guia de configuração"
source_path: "it-benchmarking/configuration/taxanomy-alignment.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Alinhamento de taxonomia e versão

A análise comparativa utiliza estruturas TBM para interpretar seus dados. Se o modelo do seu projeto de Custeio não estiver alinhado com a versão ATUM do seu Benchmarking Interativo, as métricas serão imprecisas e incompletas.

**Selecione a versão do TBM ( ATUM**  
) Na configuração do Interactive Benchmarking, é possível escolher a versão do TBM ( ATUM ).

![Configuração do Benchmarking Interativo – Seleção da versão do ATUM](../../resources/images/it%20benchmarking_images/benchmarking-atum.png)

  
Diretrizes

- Corresponda à versão utilizada no seu projeto de cálculo de custos.
- Se você estiver no meio da migração, escolha a versão de destino e conclua primeiro a parte de cálculo de custos
- Evite alternar entre versões de forma casual. Trate isso como uma mudança estrutural com um ano efetivo claro.

  
A versão selecionada controla:

- Quais são os pools de custos, torres de recursos e subtorres existentes.
- Como as métricas de infraestrutura são agrupadas e rotuladas
- Quais definições de referência estão disponíveis.

**Valide o alinhamento do seu**   
modelo TBM Depois de selecionar uma versão no Benchmarking Interativo:

- Confirme se o seu modelo de cálculo de custos utiliza a mesma versão com os mesmos pools de custos e torres de recursos.
- Identifique estruturas personalizadas ou mescladas, por exemplo:
  - Categoria local “Centro de dados” que combina várias torres de recursos padrão.
  - Grupos de custos personalizados que combinam mão de obra e serviços externos.
  - Subtorres extras não presentes na taxonomia padrão da TBM.

  
Documente como você irá mapear essas estruturas locais para estruturas de referência padrão.   
Abordagens típicas:

- Crie tabelas de mapeamento no Costing que mapeiem códigos locais para pools de custos e torres de recursos padrão.
- Quando não for possível mapear 1-to-1, decida se deseja:
  - Mapa para a torre padrão mais próxima e anotação.
  - Excluir do escopo da análise comparativa.  
  Se você pular esta etapa, passará meses discutindo por que sua estrutura não se parece com a dos colegas.
