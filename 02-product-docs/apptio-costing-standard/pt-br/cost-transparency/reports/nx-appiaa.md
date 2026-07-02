---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Análise de infraestrutura por aplicativo"
breadcrumb:
  - "Costing Standard"
  - "Guia passo a passo do Relatório NX"
  - "Aplicativos Relatórios NX"
source_path: "cost-transparency/reports/nx-appiaa.html"
images:
  - "resources/images/ct_images/nx-appiaa.png"
  - "resources/images/ct_images/nx-appiaa1.png"
  - "resources/images/ct_images/nx-appiaa2.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Análise de infraestrutura por aplicativo

Utilize este relatório para analisar o uso de recursos de infraestrutura entre as aplicações, incluindo computação, armazenamento e distribuição do ambiente, identificando oportunidades de otimização para recursos físicos, virtuais e em nuvem.

Este relatório foi elaborado para ser utilizado pelos seguintes perfis:

- Gestores de infraestrutura
- Responsáveis pelas aplicações
- Controladores Financeiros de TI
- Arquitetos de nuvem
- Planejadores de capacidade

## Elementos-chave

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/nx-appiaa.png)

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/nx-appiaa1.png)

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/nx-appiaa2.png)

| Elemento | Descrição |
| --- | --- |
| Controles de filtro (1) | Quatro filtros permitem filtrar o relatório por nome do aplicativo, tipo de aplicativo, responsável pela TI do aplicativo e família do aplicativo. |
| Gráficos de análise do ambiente de infraestrutura (2) | Três gráficos de barras horizontais mostram as horas de funcionamento do servidor, a despesa operacional total e a despesa operacional por hora por ambiente, como produção, teste, desenvolvimento e recuperação de desastres. |
| Tabela de detalhes do ambiente (3) | Esta tabela apresenta métricas de infraestrutura por ambiente, incluindo horas de servidor, porcentagem por hora de servidor, despesas operacionais e despesas operacionais por hora de servidor. |
| Análise computacional por tabela de aplicações (4) | A tabela inclui colunas como nome do aplicativo, responsável de TI pelo aplicativo, horas de funcionamento do servidor, análise do perfil de virtualização e análise do ambiente. |
| Tabela de análise de armazenamento por aplicativos (5) | Esta tabela inclui colunas como nome do aplicativo, responsável de TI pelo aplicativo, armazenamento alocado, análise do nível de armazenamento e análise do ambiente. |
| Análise do Service Desk por aplicativo (6) | Esta seção apresenta os dados do service desk por aplicativo, quando disponíveis. |

## Perguntas e respostas

- Quais aplicativos consomem mais recursos de infraestrutura?
- Quanto custa a execução de cada aplicativo na infraestrutura?
- Qual é a porcentagem da infraestrutura que é física, virtual e em nuvem?
- Quais aplicativos utilizam mais recursos de produção, em comparação com os de teste e desenvolvimento?
- Qual é o custo por hora de servidor para cada tipo de infraestrutura?
- Quais aplicativos consomem mais espaço de armazenamento e em quais níveis de armazenamento?
- Será que estamos dimensionando excessivamente a infraestrutura para ambientes que não são de produção?

## Ações recomendadas

- Analise as solicitações com elevado número de horas de servidor na nuvem pública para garantir que sejam utilizadas Instâncias Reservadas ou Planos de Economia para otimização de custos.
- Verifique as aplicações com altas porcentagens de infraestrutura física para identificar candidatas à migração para virtualização ou nuvem.
- Consulte o gráfico “ OpEx s por hora” para identificar quais tipos de infraestrutura têm os custos mais elevados e priorizar os esforços de otimização nessas áreas.
- Filtre por Responsável de TI da Aplicação para atribuir metas de redução de custos de infraestrutura a equipes específicas.
- Analise as colunas da Análise do Ambiente para identificar aplicativos que estejam alocando recursos em excesso nos ambientes de Teste ou Desenvolvimento em comparação com o ambiente de Produção.
- Verifique a análise de camadas de armazenamento para garantir que o armazenamento de alto desempenho da Camada 1 seja utilizado apenas quando necessário, transferindo os dados para camadas mais econômicas sempre que possível.
- Clique nos nomes dos aplicativos para acessar informações detalhadas sobre o consumo de infraestrutura e identificar oportunidades específicas de otimização.
