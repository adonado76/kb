---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Atualização dos dados de referência nos planos"
breadcrumb:
  - "Planning"
  - "Trabalhando com planos"
source_path: "it-planning/planning/update-refdata-plan.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Atualização dos dados de referência nos planos

Observação: Somente usuários com funções de administrador ou proprietário do processo orçamentário podem realizar essas tarefas.

## O que são dados de referência?

Os dados de referência definem os valores de pesquisa padronizados para dimensões como Centro de Custos, Conta, Departamento, Fornecedor, Projeto, etc. Esses valores determinam como os itens do plano são classificados, agregados e relatados.

Saiba mais: [Visão geral dos dados de referência](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=administration-reference-data-overview "(Abre em uma nova guia ou janela)")

## Atualização dos dados de referência em um plano

Quando um plano é criado, ele usa automaticamente a versão mais recente dos dados de referência disponíveis naquele momento. Se os dados de referência forem atualizados posteriormente, os planos existentes não herdam automaticamente essas alterações. Você deve atualizar explicitamente o plano para aplicar os dados de referência mais recentes.

**Como atualizar dados de referência**

1. Abra o plano que deseja atualizar.
2. Certifique-se de que está visualizando **Todos os Departamentos**.
3. Abra os **pontos de suspensão (...) menu** e selecione **Atualizar dados de referência**.
4. Analise o **resumo do impacto** apresentado na janela modal de confirmação, que inclui:
   1. Itens a serem atualizados
   2. Itens a serem excluídos
   3. Novos itens
   4. Itens removidos
   5. Códigos pai alterados
5. Se o impacto parecer correto, selecione **Atualizar** para aplicar as alterações.

**Observações importantes**

- Por padrão, as atualizações que excluiriam itens de linha existentes são bloqueadas para evitar a perda acidental de dados.
- Para permitir atualizações destrutivas, um administrador deve habilitar **a opção Desativar restrições de dados de referência de atualização** no perfil da empresa.
- Quando atualizações destrutivas são permitidas, um **plano de backup é criado automaticamente** antes da aplicação da atualização dos dados de referência.
