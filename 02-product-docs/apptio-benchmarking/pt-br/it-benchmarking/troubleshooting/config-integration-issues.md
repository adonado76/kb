---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "pt-br"
doc_type: "it-benchmarking"
title: "Problemas de configuração e integração"
breadcrumb:
  - "Benchmarking"
  - "Relatórios de benchmarking"
  - "Solução de problemas e perguntas frequentes"
source_path: "it-benchmarking/troubleshooting/config-integration-issues.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Problemas de configuração e integração

**A análise comparativa não reflete as mudanças recentes nos custos.**

Sintoma  
: você atualizou os mapeamentos ou alocações no Cálculo de custos, mas o Benchmarking ainda mostra a estrutura antiga. Causas   
prováveis:

- A comparação é direcionada a um projeto de cálculo de custos diferente daquele que você atualizou
- Os dados de referência não foram atualizados desde a alteração
- Você alterou um modelo ou módulo que não está no feed de benchmarking

O que verificar

1. Verifique a configuração de benchmarking para saber qual projeto de cálculo de custos está em uso.
2. Confirme quando foi executada a última atualização de dados.
3. Verifique se o modelo de cálculo de custos que você alterou está realmente alimentando o conjunto de dados de benchmarking.

Resposta curta que você pode enviar  
: O Benchmarking ainda está usando a visualização anterior do Custeio porque não foi atualizado a partir do projeto atualizado. Depois de atualizarmos a partir do projeto correto, as visualizações de benchmark refletirão os novos mapeamentos.

**Após alterar a versão do TBM, as métricas parecem inconsistentes**

Sintoma  
: Você altera a versão da taxonomia no Benchmarking e, de repente, os relatórios não correspondem aos anos anteriores.   
Causas prováveis:

- As Torres de Recursos e as Subtorres de Recursos diferem entre as versões antigas e novas
- Nem todos os custos foram mapeados para as novas estruturas ainda
- Algumas métricas utilizam novos agrupamentos que não correspondem aos agrupamentos históricos
- A análise comparativa e o cálculo de custos utilizam versões diferentes do TBM.

O que verificar

1. Compare as definições antigas e novas de Torre de Recursos/Subtorre.
2. Verifique se há custos não mapeados ou parcialmente mapeados na nova versão.
3. Trate o ano da mudança de versão como uma nova linha de base, não como uma continuação.
4. No Benchmarking Interativo, verifique se as suas Configurações refletem a mesma versão do TBM que o seu projeto de Custeio.

Resposta curta que você pode enviar  
: Mudamos para uma taxonomia mais recente, que altera a forma como as torres e subtorres são agrupadas. Isso faz com que os novos resultados não sejam diretamente comparáveis aos anos anteriores. Trataremos o ano da mudança como uma reinicialização da linha de base e, quando necessário, reapresentaremos os períodos anteriores na nova estrutura.
