---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Adicionar serviços e dados orçamentários da unidade de negócios"
breadcrumb: []
source_path: "boit/services-bu-data.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Adicionar serviços e dados orçamentários da unidade de negócios

Adicione serviços e dados de orçamento da unidade de negócios somente se tiver instalado o componente**Billing Standard - Plan Variance**. Os dados serão usados para comparar o gasto planejado com o gasto real. Se você não tiver instalado o componente**Billing Standard - Plan Variance**, não execute esta etapa. Se você já tiver um modelo de orçamento configurado em seu projeto de Transparência de custos, use esse modelo de orçamento e aloque dos Torres de recursos de TI para o Feed de consumo.

**Requisitos de dados**

Os dados devem incluir as colunas descritas abaixo.

- **ID do serviço** - Deve corresponder às IDs de serviço na tabela Biblioteca de serviços.
- **Orçamento total do serviço por mês** - Se estiver carregando um ano inteiro de dados, inclua colunas separadas para cada mês do ano. Depois de fazer upload dos dados, adicione uma etapa de partição de data ao pipeline de transformação.
- **ID da unidade de negócios (opcional)** - Deve corresponder às IDs da unidade de negócios na tabela Serviços comerciais.

Ao fazer o upload da tabela, nomeie-a como `Service and Business Unit Budget Data` e coloque-a na categoria **General (Geral** ).

**Use os dados em modelos**

Para usar os serviços e os dados de orçamento da unidade de negócios nos modelos, execute as seguintes tarefas.

1. Adicione uma etapa de modelo à tabela Service and Business Unit Budget Data.
2. Nos modelos Orçamento e Orçamento empresarial, adicione um driver de unidade com base na coluna de orçamento da tabela.   
    Se você quiser comparar o custo e a cobrança com orçamentos separados, adicione dois drivers: um para o Orçamento empresarial e outro para o Orçamento.
3. Adicione uma alocação ao objeto do modelo de serviços comerciais.
