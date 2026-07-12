---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Recomendações de configuração"
breadcrumb:
  - "TBM Studio"
  - "Solução de problemas e suporte"
  - "Explicação das mensagens de erro"
source_path: "studio/new-uc/ts-support/em-config.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Recomendações de configuração

Esta seção fornece explicações e soluções para mensagens de erro comuns no TBM Studio. Acesse as recomendações em TBM Studio > guia Recomendações.

|  |  |  |
| --- | --- | --- |
| **Mensagem de erro** | **Significado** | **Solução** |
| A tabela de índices de alocação é muito grande | A tabela de índices de atribuição excede os limites de tamanho, prejudicando o desempenho | Adicionar relação de dados, adicionar filtros De/Para, reduzir as linhas de identificador |
| Sem identificador no objeto de modelo grande | Um objeto de modelo grande não possui identificador, causando problemas de desempenho | Defina “Usar identificador de objeto” no menu suspenso “Linhas” e selecione as colunas necessárias |
| Operação de junção do modelo legado utilizada | A alocação utiliza uma configuração automática de relações d R11-era | Desmarque a caixa de seleção “Relação automática” e defina colunas explícitas |
| Limite restrito: Expansão da linha | LookupEx, SplitEx, ou o Unpivot excede os limites de linhas | Reduzir as relações um-para-muitos, limitar a expansão dos dados, reduzir o número de colunas |
| Limite de contagem métrica excedido | O projeto atingiu o número máximo de métricas | Exclua métricas não utilizadas em Explorador de Projetos > Métricas |
| Número de colunas da etapa do modelo de transformação excedido | A tabela com etapas do modelo excede o limite de colunas | Adicione a etapa “Ocultar e renomear” para ocultar colunas desnecessárias |
