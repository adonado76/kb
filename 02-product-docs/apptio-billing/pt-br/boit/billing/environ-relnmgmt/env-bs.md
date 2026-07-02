---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Fluxo ambiental para o padrão de faturamento"
breadcrumb:
  - "Billing"
  - "Administração e Operações"
  - "Ambientes e gerenciamento de versões"
source_path: "boit/billing/environ-relnmgmt/env-bs.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Fluxo ambiental para o padrão de faturamento

O Padrão de Faturamento segue o mesmo ciclo de vida do ambiente do projeto Padrão de Custeio subjacente, mas introduz um ponto final de Faturamento separado para os usuários finais.

Observação: aplica-se apenas ao padrão de faturamento.

Implicações:

- Os componentes do Padrão de Faturamento são instalados e alterados no ambiente Em Desenvolvimento do projeto **Padrão de Custeio**.
- Quando os itens relacionados ao padrão de faturamento são verificados:
  - Uma nova versão em desenvolvimento é criada para o projeto Padrão de Custos.
  - Uma compilação de preparação correspondente é criada automaticamente.

A preparação é então usada para validar:

- Modelos e processos padrão de faturamento (por exemplo, cálculos de taxa unitária, lógica de variação).
- Relatórios de faturamento específicos por domínio (nuvem, aplicativos, projetos, infraestrutura, preços de transferência).
- Cenários de faturamento de ponta a ponta:
  - Cobranças por consumidor e domínio.
  - Visões de taxa unitária e variância.
  - Diários e quaisquer exportações a jusante.

Comportamento promocional:

- Quando a compilação de preparação é promovida para produção:
  - O ambiente de produção **do Padrão de Custeio** é atualizado.
  - **O endpoint do Padrão de Faturamento** reflete a nova lógica e os novos relatórios de Faturamento, pois é respaldado pelo mesmo conteúdo do projeto.

Recomendações operacionais:

- Trate as versões padrão de faturamento como eventos coordenados:
  - Confirme as alterações no modelo padrão de cálculo de custos e as alterações no padrão de faturamento na mesma compilação.
  - Comunique às partes interessadas quais domínios de faturamento (por exemplo, nuvem, projetos, preços de transferência) são afetados em cada versão.
- Use o Staging como o local principal para testar ambos:
  - Visões focadas em tecnologia (taxas unitárias, divisões de domínio).
  - Visões focadas nos negócios (contas, diários, relatórios de variação).
