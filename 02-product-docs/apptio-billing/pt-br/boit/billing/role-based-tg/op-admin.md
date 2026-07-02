---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Caminho de integração para administradores e analistas"
breadcrumb:
  - "Billing"
  - "Guia de treinamento baseado em funções"
source_path: "boit/billing/role-based-tg/op-admin.html"
images:
  - "resources/images/boit_images/p2-admin.png"
  - "resources/images/boit_images/p3-admin.png"
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Caminho de integração para administradores e analistas

Este é o caminho de treinamento mais intensivo e deve ser estruturado, não ad hoc.

## Fase 1 - Fundamentos

**Objetivo** : Compreender o panorama antes de alterar qualquer configuração.

**Tópicos** :

- Conceitos de faturamento e relação com o cálculo de custos.
- Edições e recursos (Essentials vs Standard).
- Arquitetura e dependências (Seção 6).
- Ambientes e gerenciamento de lançamento (Seção 7).
- Visão geral do ciclo de faturamento (Seção 9).

**Atividades** :

- Visão geral do ambiente ao vivo ou de teste:
  - Mostre onde estão os relatórios de faturamento.
  - Mostrar fluxos de dados de alto nível e diagramas de modelos.

## Fase 2 - Dados e relatórios

**Objetivo** : Compreender como os dados aparecem nos relatórios antes de editar os modelos.

**Tópicos** :

- Requisitos de dados e padrões de integração (Seção 8).
- Trabalhando com relatórios de faturamento (Seção 10).
- Receitas básicas de uso (Seção 15) para:
  - PxQ showback.
  - Estorno com diários.
  - Investigação da taxa unitária.

**Atividades** :

- Exercícios práticos:
  - Filtre e exporte relatórios de faturamento importantes.
  - Compare os resultados da faturação com casos de teste conhecidos ou faturas antigas.
  - Realizar uma investigação da taxa unitária para um serviço.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/p2-admin.png)

Fig. #: Relatório detalhado de faturas no Padrão de Faturamento com o cursor sobre o botão Exportar

## Fase 3 - Configuração e alterações no modelo

**Objetivo** : Fazer alterações com segurança no In Development e compreender o seu impacto.

**Tópicos** :

- Configurando o Billing Essentials e/ou o Billing Standard (Seções 11 e 12).
- Estrutura dos componentes e tabelas principais.
- Como verificar, editar e fazer o check-in de documentos no TBM Studio.
- Como as compilações fluem do Desenvolvimento para o Staging e para a Produção.

**Atividades** :

- Exercícios guiados em desenvolvimento:
  - Adicione ou modifique uma oferta e sua tarifa.
  - Carregue o consumo da amostra e execute os modelos.
  - Valide o efeito em uma compilação de teste semelhante ao Staging.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/p3-admin.png)

Fig. #: No TBM Studio, editando fórmulas na tabela Dados mestre de alocação da unidade de negócios

## Fase 4 - Controlar o ciclo de faturamento

**Objetivo** : Os administradores e analistas podem executar o ciclo completo e lidar com problemas típicos.

**Tópicos** :

- Manual mensal detalhado com base na Seção 9 e na Seção 16.
- Padrões de controle de qualidade e tratamento de exceções.
- Comunicações aos proprietários dos serviços e ao departamento financeiro em cada ciclo de faturamento.

**Atividades** :

- Acompanhe e, em seguida, conduza um ou mais ciclos de faturamento reais:
  - Primeiro com um guia experiente, depois de forma independente com verificações pontuais.
