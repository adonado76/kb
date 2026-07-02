---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Tipos de eventos"
breadcrumb:
  - "Planning"
  - "Fluxos de trabalho e colaboração"
  - "Histórico de alterações"
source_path: "it-planning/planning/event-types.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Tipos de eventos

O Change History captura uma ampla gama de eventos do sistema no Apptio Planning, permitindo que você analise quem fez o quê, quando e como. Cada evento é categorizado por tipo, área, contêiner, tipo de item e alterações de atributo.

Observação: As funções de administrador ou de proprietário do processo orçamentário são necessárias para acessar o Change History.

Abaixo está um resumo das principais categorias de eventos.

## 1. Planejar eventos de gerenciamento.

Elas estão relacionadas às principais mudanças no ciclo de vida do plano.

- **Criar plano** - Um novo plano foi criado.
- **Rename Plan (Renomear plano** ) - O nome do plano foi alterado (nome antigo → novo nome).
- **Excluir plano** - Um plano foi removido.
- **Archive/Restore Plan (Arquivar/Restaurar Plano** ) - O plano foi arquivado ou recuperado.
- **Finalize/Reopen Plan (Finalizar/Reabrir Plano** ) - Um plano movido para o estado Final ou de volta para Open.
- **Enviar/Aprovar/Rejeitar Objeto de Custo** - Alterações de status para departamentos individuais ou objetos de custo.

## 2. Eventos de item de linha

Esses eventos rastreiam as alterações em linhas individuais do seu plano.

- **Adicionar item de linha** - Um novo item de linha foi adicionado.
- **Atualizar item de linha** - Um item de linha existente foi atualizado (mostra os valores "antes" e "depois").
- **Excluir item de linha** - Um item de linha foi removido.
- **Importar/Exportar itens de linha** - Ações de upload ou download em massa.

## 3. Eventos de gerenciamento de despesas e resultados reais

Eles capturam a importação/exportação de dados reais e operações de gerenciamento de despesas.

- **Import Actuals (Importar** dados reais) - Os dados reais foram carregados em um plano.
- **Exportar** dados reais - Os dados reais foram exportados para geração de relatórios ou integração.

## 4. Eventos de configuração e dados de referência

Elas estão relacionadas a alterações no modelo ou na configuração dos dados subjacentes.

- **Add/Update/Delete Column Configuration** - A coluna de layout ou esquema foi adicionada/modificada/removida.
- **Alterar identificador** - Uma operação de localização e substituição em um código de dimensão ou identificador entre planos.
- **Publicar/reverter/importar/exportar dados de referência** - Ações tomadas em dimensões como departamentos, contas, classes de ativos, etc.
- **Adicionar/atualizar/excluir listas ou dimensões personalizadas** - Modificações nas estruturas de dimensões personalizadas.

**Tópico pai:** [Histórico de alterações](../../it-planning/planning/change-history.html "O Change History fornece uma trilha de auditoria das principais ações executadas no ambiente de planejamento. Ele permite que as organizações mantenham a transparência, atendam aos requisitos de conformidade e solucionem problemas de planejamento, rastreando quem alterou o quê, quando e como.")
