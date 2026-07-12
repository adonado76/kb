---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Padrões comuns"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Tabelas editáveis nos relatórios"
source_path: "studio/new-uc/reference/report-studio-reference/common-patterns.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Padrões comuns

Os padrões a seguir representam implementações típicas de componentes de tabelas editáveis.

**Fluxo de trabalho de lançamento orçamentário**

Permita que os gerentes de centros de custo insiram previsões orçamentárias:

1. Crie uma tabela em branco editável no Data Studio com colunas para centro de custo, conta, período e valor
2. Configure o RLS para que cada gerente veja apenas seu próprio centro de custo
3. Adicionar o componente de tabela editável a um relatório de lançamento orçamentário
4. Inclua um validador de linha de total para garantir que os valores sejam somados corretamente
5. Configure uma programação de publicação recorrente para atualizar o modelo diariamente

**Fluxo de trabalho de enriquecimento de dados**

Permitir que os usuários adicionem classificações aos dados importados:

1. Criar uma tabela editável com informações adicionais com base na transformação de origem (por exemplo, dados contábeis)
2. Adicionar colunas editáveis para campos de classificação (por exemplo, Solução, Categoria, Subcategoria)
3. Configure menus suspensos em cascata para garantir combinações válidas
4. Defina as colunas de origem como somente leitura para preservar os dados originais
5. Os usuários enriquecem os dados sem alterar a importação original

**Integração do fluxo de trabalho de aprovação**

Acompanhar o status da aprovação e os comentários:

1. Adicionar colunas “Status” e “Aprovador” com valores em menu suspenso (Pendente, Aprovado, Rejeitado)
2. Configure a permissão de edição de linha para restringir a aprovação a funções autorizadas
3. Use o recurso “Mostrar alterações” para acompanhar quem tomou as decisões de aprovação
4. Ativar as colunas.Username e .EditDate para exibir informações de auditoria

**Tópico principal:** [Componentes de relatórios: Tabelas editáveis em relatórios](../../../../studio/new-uc/reference/report-studio-reference/report-component-editable-components.html)
