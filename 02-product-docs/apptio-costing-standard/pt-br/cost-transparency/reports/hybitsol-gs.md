---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Impacto do TCO da TI híbrida Introdução"
breadcrumb:
  - "Costing Standard"
  - "Outras soluções"
  - "Impacto do TCO da TI híbrida"
source_path: "cost-transparency/reports/hybitsol-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Impacto do TCO da TI híbrida Introdução

A solução Hybrid IT TCO Impact ajuda as organizações a compreender o impacto financeiro das migrações de aplicações em ambientes locais, nuvem privada e nuvem pública. Ele permite a comparação do TCO, dos custos unitários e dos volumes antes e depois da migração, além de fornecer informações sobre os pools de custos e as torres de TI que impulsionam a mudança. Esta solução oferece suporte à validação baseada em dados de casos de negócios de migração e ao acompanhamento financeiro contínuo de transformações de TI híbridas.

## Instalação de componentes

Para habilitar o impacto do TCO da TI híbrida, instale os seguintes componentes na ordem listada. Antes da instalação, certifique-se de que **a versão dos componentes** nas **configurações do projeto** esteja temporariamente definida como **versão 120**. Após a instalação, reverta a versão para evitar indicadores de atualização desnecessários.

1. **Banco de trabalho de aplicativos**

   Permite o enriquecimento dos metadados da aplicação necessários para a análise do impacto do TCO da TI híbrida.

   Os campos obrigatórios incluem:

   **Hospedado em** (local, nuvem privada, nuvem pública)

   **Objetivo do investimento da aplicação** (manter, retirar, migrar, investir)
2. **Impacto do TCO da TI híbrida**

   Instala a estrutura principal, incluindo bancadas de trabalho de migração, tabelas editáveis, métricas e modelos. Ele também utiliza relatórios intermediários para capturar e congelar métricas de aplicativos de linha de base antes da migração.
3. **Relatório sobre o impacto do TCO da TI híbrida**

   Instala os relatórios do usuário final, que vão desde visões resumidas de nível executivo até análises detalhadas em nível de aplicação dos benefícios da migração e dos fatores de custo.

   Observação: esses componentes estão disponíveis com os modelos v120 ou superior

## Pré-requisitos

Você deve ter os seguintes componentes instalados antes de configurar o Hybrid IT TCO Impact:

• CTF - Fonte de custos

• Torres CTF-IT

• Aplicativos CT - Aplicativos

## Fontes comuns de dados

**Ferramentas de gerenciamento de portfólio de aplicativos (APM)** : forneça metadados de aplicativos, incluindo IDs de aplicativos, propriedade, status do ciclo de vida e objetivos de investimento (manter, migrar, retirar, investir).

## Conjuntos de dados

A solução Hybrid IT TCO Impact instala e utiliza os seguintes conjuntos de dados principais:

• Dados mestres de aplicações

• Migração de aplicativos

• Relações de migração de aplicativos

• Aplicativos migrados (Raw, Cost Pool, IT Tower)

Esses conjuntos de dados permitem a comparação de custos antes e depois, o agrupamento de migrações e a análise de variações.

## Visão geral da configuração

Para ativar o relatório de impacto do TCO da TI híbrida, siga estas etapas gerais:

- **Estabelecer o TCO de referência**
- Certifique-se de que o TCO, os custos unitários e os volumes de uso sejam calculados para todas as aplicações atuais usando alocações padrão de ATUM. Preencha os metadados necessários no Applications Workbench.
- **Capturar metadados de migração**
- Para aplicativos marcados como **Migrar**, registre a estratégia de migração, o status da migração, os IDs dos aplicativos de destino e o tempo de migração usando o Application Migration Workbench.
- **Congelar métricas pré-migração**
- Quando o status da migração estiver definido como **Concluído**, capture um instantâneo médio dos últimos doze meses do TCO, volumes e custos unitários do aplicativo migrado usando conectores de link de dados Apptio -to- Apptio.
- **Modelar os custos pré e pós-migração**
- Configure métricas modeladas para custo pré-migração, custo pós-migração e contagem de aplicativos pós-migração para permitir uma comparação direta entre pools de custos e torres de TI.

Para obter mais detalhes sobre a configuração e o funcionamento do Hybrid IT TCO Impact, consulte [o Guia de Configuração](hybrid-it-tco-config.html) do Hybrid IT TCO Impact.
