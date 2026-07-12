---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Integração com outros fluxos de trabalho"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Ciclo de vida de compilação e implantação"
source_path: "studio/new-uc/concepts-architecture/integration-other-wf.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Integração com outros fluxos de trabalho

O ciclo de vida da compilação se integra a vários outros fluxos de trabalho do TBM Studio. Compreender essas conexões ajuda você a planejar seu trabalho de forma eficaz.

**Tabelas editáveis e promoção automática**

As tabelas editáveis permitem que os usuários finais insiram dados por meio de relatórios. Quando publicados, esses dados percorrem o ciclo de vida da compilação:

1. O usuário edita os dados em um relatório que exibe uma tabela editável
2. A função Publish grava os dados editáveis da tabela na tabela de transformação associada
3. Transformar as atualizações da tabela em objetos do modelo
4. O modelo é recalculado durante a próxima compilação de teste ou de produção
5. Os relatórios refletem as alocações atualizadas

As tabelas programadas editáveis podem acionar cálculos de teste automaticamente e, se configuradas, promover automaticamente para a produção. Isso cria um fluxo de trabalho totalmente automatizado, desde os dados até a produção.

**Regras de atualização dos dados**

As regras de atualização de dados monitoram as atualizações das tabelas e se integram ao ciclo de vida da compilação:

- As regras detectam quando faltam dados esperados ou quando estes estão desatualizados
- O sistema envia notificações aos administradores
- Os administradores atualizam as tabelas e fazem o check-in
- O próximo cálculo do modelo incorpora dados atualizados

Os indicadores de atualização são particularmente importantes durante os processos de fechamento de mês, ajudando a identificar se os resultados desatualizados do modelo se devem à falta de atualizações nos dados.

**Períodos e controle de versões**

A configuração do período de validade afeta as compilações em todas as camadas:

- **Data Studio :** A filtragem por partição de data determina quais dados de cada mês são incluídos nas transformações
- **Model Studio:** Os cálculos utilizam a versão correspondente ao período ativo
- **Relatórios:** os valores exibidos refletem os dados do período atual
- **Períodos fechados:** impedem atualizações, mas ainda podem ser incluídos nos relatórios
