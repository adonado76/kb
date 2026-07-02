---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Ambientes de cálculo de custos: em desenvolvimento, preparação e produção"
breadcrumb:
  - "Billing"
  - "Administração e Operações"
  - "Ambientes e gerenciamento de versões"
source_path: "boit/billing/environ-relnmgmt/environments.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Ambientes de cálculo de custos: em desenvolvimento, preparação e produção

O faturamento utiliza os **mesmos ambientes** do projeto de cálculo de custos no qual está instalado. As alterações de configuração no faturamento são gerenciadas por meio dos ambientes do projeto de custos: **em desenvolvimento**, **preparação** e **produção**.

Os ambientes **não** são projetos separados. São áreas ambientais diferentes do **mesmo** projeto.

## Ambientes de cálculo de custos: em desenvolvimento, preparação e produção

Cada projeto de cálculo de custos (e, portanto, o conteúdo de faturamento dentro dele) tem três ambientes principais:

- **Em desenvolvimento**
  - Onde os administradores e analistas fazem alterações na configuração.
  - Componentes, modelos, conjuntos de dados e relatórios são editados aqui.
- **Preparação**
  - Recebe compilações concluídas do In Development.
  - Utilizado para controle de qualidade, verificações de regressão e validação antes da produção.
- **Produção**
  - O ambiente ao vivo para usuários finais.
  - Apenas compilações concluídas e testadas são promovidas aqui.

Comportamentos-chave:

- Em Desenvolvimento é o único ambiente onde os itens são verificados e editados.
- Cada check-in produz uma nova compilação para Em Desenvolvimento, e a plataforma cria automaticamente uma compilação correspondente para Staging.
- A produção recebe apenas compilações que são explicitamente promovidas.
