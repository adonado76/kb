---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Problemas com o Model Studio"
breadcrumb:
  - "TBM Studio"
  - "Solução de problemas e suporte"
  - "Problemas comuns e soluções"
source_path: "studio/new-uc/ts-support/ms-issues.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Problemas com o Model Studio

## A alocação não está funcionando como esperado

**Sintomas:**

- Os custos não estão sendo direcionados para os destinos previstos
- Custos não alocados remanescentes após a alocação
- Valores nulos nos objetos de destino

**Soluções:**

1. **Verificar a cobertura dos dados do driver** - Abra a tabela do driver e verifique se ela contém valores para todas as entidades de destino. Considere adicionar um fundo residual para lidar com lacunas.
2. **Verifique as relações entre os dados** - Abra a etapa de alocação e confirme se a coluna de origem e a coluna de destino estão mapeadas corretamente.
3. **Resolva problemas de alocação herdados** - Se a caixa de seleção "Relação automática" estiver marcada, desmarque-a e defina manualmente as colunas de origem e destino.

Aviso: Depois de registrar as alterações para substituir uma alocação antiga, não será possível reativar a configuração antiga. Teste exaustivamente no ambiente de desenvolvimento antes de fazer o check-in.

## O cálculo do modelo está demorando muito

**Sintomas:**

- As compilações levam horas para serem concluídas
- O ambiente de teste está frequentemente desatualizado
- Os usuários enfrentam lentidão no desempenho dos relatórios

**Soluções:**

1. **Analise a complexidade do modelo** - Use o componente Análise de Desempenho para identificar áreas problemáticas. Concentre-se em reduzir as alocações nos níveis inferiores do modelo.
2. **Adicionar identificadores a objetos grandes** - Navegue até o objeto do modelo marcado. No menu suspenso “Em linhas”, selecione “Usar identificador de objeto”.
3. **Reduzir o tamanho da tabela de proporção de atribuição** - Adicionar relações entre dados para restringir o escopo da alocação. Adicione filtros "De" ou "Para".
4. **Limpar elementos não utilizados** - Exclua métricas não utilizadas pelo painel de Recomendações. Remova as alocações não utilizadas e desative os relatórios não utilizados.
