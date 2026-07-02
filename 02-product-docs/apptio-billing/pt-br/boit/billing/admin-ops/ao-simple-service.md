---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Demonstração simples do serviço"
breadcrumb:
  - "Billing"
  - "Administração e Operações"
source_path: "boit/billing/admin-ops/ao-simple-service.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Demonstração simples do serviço

**Quando usar**

- Primeira implementação de faturamento em que a prioridade é a transparência, e não a receita interna.
- As partes interessadas querem saber “quem consome o quê” e “quanto custaria” sem publicar diários.

**Orientar**

- Um catálogo disciplinado e relativamente pequeno de serviços ou produtos.
- Unidades e taxas mantidas em um pequeno número de tabelas.
- Os mapas de consumo são diretamente associados aos serviços e consumidores.
- Diários disponíveis, mas não utilizados para postagem.

**Elementos-chave**

- Tabela de ofertas: nomes e unidades de serviços claros.
- Tabela de consumo: consumidor × serviço × período × unidades.
- Tabela de taxas: uma taxa por serviço por período.
- Resultados de faturamento: usados apenas para faturas e visualizações resumidas.

**Relatórios típicos**

- Resumo do estilo de fatura por consumidor e serviço.
- Visualizações de tendências mostrando cobranças ao longo do tempo.
- Relatórios de controle de qualidade para mapeamentos ausentes e valores atípicos.

**Notas de implementação**

- Mantenha as unidades e taxas simples e explicáveis.
- Não exagere na modelagem de domínios para um padrão de showback puro; concentre-se na clareza.
