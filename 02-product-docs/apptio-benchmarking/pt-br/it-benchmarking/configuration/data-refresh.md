---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "pt-br"
doc_type: "it-benchmarking"
title: "Atualização e manutenção de dados"
breadcrumb:
  - "Benchmarking"
  - "Guia de configuração"
source_path: "it-benchmarking/configuration/data-refresh.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Atualização e manutenção de dados

A configuração não é algo que se faz uma vez e pronto. Você precisa de um padrão de atualização.

**Atualize a cadência dos seus dados**  
 Padrão comum:

- **Anualmente (após a atualização dos dados de referência – final do segundo trimestre civil)**
  - Valide a configuração principal do Benchmarking para o último ano fiscal completo.
  - Valide o conjunto completo de comparações entre setores, TI OpEx, es e infraestruturas.
  - Alinhe-se com o planejamento ou o fechamento financeiro.
- **Trimestralmente**
  - Verifique aleatoriamente as principais métricas para detectar saltos incomuns.
  - Se integrado, valide se o modelo do seu projeto de Custeio não tem mapeamentos quebrados e corresponde à versão TBM no Benchmarking Interativo.

**Lidando com alterações no modelo**  
 TBM Quando você

- Adicione ou renomeie Torres de Recursos.
- Introduzir novos grupos de custos.
- Altere significativamente a lógica de alocação.

  
então

- Revise os mapeamentos de benchmarking e atualize-os quando necessário.
- Execute novamente um pequeno conjunto de visualizações de benchmark padrão para confirmar se os resultados ainda são plausíveis.
- Documente que ocorreu uma mudança estrutural para que qualquer pessoa que analise as tendências saiba onde está a ruptura.

Se você ignorar isso, verá saltos inexplicáveis e passará semanas tentando lembrar o que mudou.
