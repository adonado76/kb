---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Exportar o histórico de status de um plano"
breadcrumb: []
source_path: "it-planning/planning/export-plans-status.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Exportar o histórico de status de um plano

## Sobre esta tarefa

Apptio Planning os aplicativos mantêm um registro das ações tomadas em cada plano. Os administradores e proprietários de processos orçamentários podem ver o histórico completo das atividades de envio, aprovação e retorno de serviços, departamentos e projetos individuais, e os administradores podem exportar essas informações. Essas informações podem ajudar a responder às perguntas "quem, o quê e quando" sobre as ações de status de um plano.

## Procedimento

- **Para exportar todo o histórico de versões de objetos de custo:**

  1. Nos menus Plano, no canto superior direito, selecione um Plano, uma categoria de Objeto de custo e um objeto de custo ou grupo de objetos de custo.

     [Saiba mais sobre a navegação no Planejamento](navigate-apptio-planning.html#Toolbar)
  2. Navegue até Planning>Status. A página Status do plano é exibida.
  3. Selecione Ações > Exportar histórico. O aplicativo de planejamento gera um histórico de versões para todos os objetos de custo no formato `.csv` .
- **Os detalhes exportados incluem o seguinte:**

  - Código do objeto de custo.
  - Nome do objeto de custo.
  - Versão : Versão do objeto de custo na qual uma ação foi executada.
  - Ação : a ação que foi executada.
  - Usuário : nome do usuário que executou a ação.
  - Data/hora : Quando cada ação foi executada. O valor da hora está no formato GMT/UTC, salvo indicação em contrário.
  - Comentário de retorno : O comentário, se houver, que foi enviado com a ação Devolver.

  Observação: Os planos que estiverem no estado Novo ou recém-abertos (ou seja, nenhuma ação foi tomada ainda) resultarão em um.csv em branco com apenas a linha do cabeçalho.
