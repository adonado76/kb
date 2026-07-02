---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Fluxo do ambiente para o Billing Essentials"
breadcrumb:
  - "Billing"
  - "Administração e Operações"
  - "Ambientes e gerenciamento de versões"
source_path: "boit/billing/environ-relnmgmt/env-be.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Fluxo do ambiente para o Billing Essentials

Observação: aplica-se apenas ao Billing Essentials.

O Billing Essentials faz parte do projeto Costing Essentials e segue o seu ciclo de vida ambiental.

Implicações:

- Qualquer alteração na configuração do Billing Essentials (modelos, tabelas, relatórios) é feita **em Desenvolvimento** do projeto Costing Essentials.
- Quando os itens são registrados:
  - Uma nova versão em desenvolvimento é criada.
  - Uma compilação de preparação correspondente é criada automaticamente.
- O controle de qualidade do Billing Essentials é realizado em relação à versão **de** teste do projeto Costing Essentials:
  - Execute modelos do Billing Essentials ou processos programados.
  - Abra e valide os relatórios do Billing Essentials.
  - Verifique se as faturas, visualizações detalhadas e arquivos correspondem às expectativas.

Quando a compilação de preparação é promovida:

- O ambiente **de produção** para Costing Essentials e Billing Essentials é atualizado em conjunto.
- Os usuários finais verão o comportamento e os relatórios atualizados do Billing Essentials assim que a promoção for concluída.

<imagem: mostrar uma visualização de Builds ou Versões para um projeto do Costing Essentials, destacando uma build específica com uma nota mencionando as alterações do Billing Essentials em sua descrição>

Recomendações operacionais:

- Documento que contém alterações essenciais de faturamento para que possam ser rastreadas durante a investigação do problema.
- A Align Billing Essentials lança versões sempre que possível com a Costing Essentials para simplificar a comunicação com as partes interessadas.
