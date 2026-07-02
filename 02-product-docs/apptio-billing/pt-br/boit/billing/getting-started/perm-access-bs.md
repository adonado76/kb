---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Permissões e tipos de acesso para o Padrão de Faturamento"
breadcrumb:
  - "Billing"
  - "Introdução"
  - "Funções e permissões do usuário"
source_path: "boit/billing/getting-started/perm-access-bs.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Permissões e tipos de acesso para o Padrão de Faturamento

A tabela a seguir lista as permissões disponíveis específicas para o Padrão de Faturamento e suas descrições:

|  |  |
| --- | --- |
| **Nome da permissão** | **Descrição** |
| ViewDataQualityAndMonthlyProcessReports | Permite ao usuário acessar a Coleção de Qualidade de Faturamento. |
| ViewBusinessRelationshipReports | Permite que o usuário acesse tudo, EXCETO a coleção de Qualidade de Faturamento. |
| ManageAndSendInvoices | Permite ao usuário configurar e enviar contas por e-mail. |
| ViewServiceProviderReports | Permite ao usuário acessar a coleção de Relatórios do Provedor de Serviços de TI. |
| ViewBusinessUserReports | Permite que o usuário acesse a coleção de relatórios de Taxas de Serviço. |

O faturamento depende de uma combinação de acesso front-end e acesso back-end (via TBM Studio). Nem todos precisam dos dois.

## Acesso front-end

**O acesso front-end é usado para:**

- Visualize e interaja com relatórios de faturamento (faturas, visualizações detalhadas, análise de taxa unitária, visualizações de variação).
- Exporte dados para análise offline ou preparação de diários.
- Para algumas implementações, ajuste as taxas ou outros valores de configuração que são intencionalmente expostos por meio de tabelas editáveis e mecanismos de upload.

**Padrões de acesso comuns:**

- Os administradores e analistas têm amplo acesso às coleções de relatórios de faturamento.
- Os proprietários de serviços ou produtos visualizam as visualizações de seus serviços ou produtos.
- Os consumidores e as partes interessadas visualizam as partes do catálogo de faturamento relacionadas às suas unidades de negócios ou centros de custo.

## Acesso ao TBM Studio

**O acesso ao TBM Studio é usado para:**

- Instale e atualize os componentes de faturamento.
- Ajuste modelos, métricas, conjuntos de dados e definições de tabelas dos quais o Faturamento depende.
- Diagnostique problemas de dados que exigem a análise da lógica upstream no Cálculo de Custos.

**Padrões típicos:**

- Administradores, analistas, TAS e parceiros que projetam ou mantêm a lógica de faturamento trabalham no TBM Studio.
- Os proprietários de serviços ou produtos, líderes seniores e consumidores geralmente não precisam de acesso ao TBM Studio.
