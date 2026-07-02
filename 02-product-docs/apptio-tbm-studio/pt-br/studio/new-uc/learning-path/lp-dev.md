---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Cursos de aprendizagem para desenvolvedores"
breadcrumb:
  - "TBM Studio"
  - "Percursos de aprendizagem (baseados em funções)"
source_path: "studio/new-uc/learning-path/lp-dev.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Cursos de aprendizagem para desenvolvedores

**Objetivo:** Integrar o TBM Studio aos sistemas corporativos e ampliar os recursos da plataforma

**A quem se destina:** Desenvolvedores de software, especialistas em integração, desenvolvedores de ETL e qualquer pessoa que esteja criando pipelines de dados automatizados ou integrações personalizadas com o TBM Studio

## Introdução (30 minutos)

**O que você** aprenderá: Arquitetura de integração e quando utilizar diferentes métodos de integração

**Objetivos de aprendizagem:**

- Compreender a arquitetura de integração do TBM Studio
- Conheça os métodos de autenticação e segurança
- Decida quando usar a API, as tabelas publicadas ou o ` DataLink `
- Compreender os padrões de entrada e saída de dados
- Verificar os pontos de integração disponíveis

**Tópicos a serem concluídos:**

1. **Arquitetura de integração** (10 min) *→ Seção 4.1, 4.2*
2. **Métodos de autenticação** (10 min) *→ Seção 5.5*
3. [Integração de API](../howtoguides/integrate-extend/api-integration.html) (10 min)

**Pré-requisitos:** Conhecimentos de programação em qualquer linguagem, compreensão das APIs REST

## Competências essenciais (3 horas)

**O que você** aprenderá: Implementar a autenticação da API, fazer upload e download de dados, configurar tabelas publicadas

**Objetivos de aprendizagem:**

- A autenticação da API foi configurada com sucesso
- Carregar dados de custos via API (automatizar o carregamento de dados)
- Baixar dados via API ou tabelas publicadas
- Tratar erros e implementar a lógica de repetição
- Configurar tabelas publicadas para integração com relatórios
- Testar e validar integrações

**Tópicos a serem concluídos:**

1. Configuração da autenticação da API (30 min) *→ Seção 5.5*
2. [Carregar dados via API](../howtoguides/integrate-extend/upload-data-via-api.html) (60 min)
3. [Baixar dados via API](../howtoguides/integrate-extend/download-data-api.html) (45 min)
4. Configurar tabelas publicadas (45 min) *→ Seção 3.5.2*

**Pré-requisitos:** Conclusão do curso básico, configuração do ambiente de desenvolvimento

**Tempo estimado para a prática:** reserve de 2 a 3 horas para criar e testar integrações

## Avançado (5 horas)

**O que você** aprenderá: Dominar o ApptioScript, implementar integrações complexas, lidar com casos extremos e criar soluções prontas para produção

**Objetivos de aprendizagem:**

- Envie um e-mail para ApptioScript para solicitar cálculos e lógica personalizados
- Implementar padrões de fórmulas complexas
- Crie integrações com o ServiceNow ou outras plataformas corporativas
- Lide com erros de maneira adequada usando uma lógica de repetição
- Otimizar o desempenho da API
- Implementar o monitoramento e os alertas de produção
- Criar soluções de integração robustas e fáceis de manter

**Tópicos a serem concluídos:**

1. ApptioScript Fundamentos (90 min) *→ Seção 5.6*
2. Padrões de fórmulas complexas (60 min) *→ Seção 5.4, 5.6*
3. [Integração de Sistemas Empresariais](../howtoguides/integrate-extend/api-integration.html) (90 min)
4. [Tratamento de erros e lógica de repetição (45 min)](../howtoguides/integrate-extend/handle-api-errors.html)
5. [Otimização de desempenho](../admin/performance-optimize.html) (30 min)
6. [Padrões de integração de produção (45 min)](../howtoguides/integrate-extend/htg-use-common-pattern.html)

**Pré-requisitos:** Conclusão do curso de Competências Essenciais, experiência com sistemas de produção

## Desafios comuns

- **Falhas de autenticação:** verifique a validade da chave da API e as permissões
- **Erros de validação no upload:** verifique o formato dos dados e os mapeamentos das colunas
- **Limitação de taxa:** Implementar backoff e operações em lote
- **Inconsistências nos dados:** Adicionar lógica de reconciliação e validar antes do envio
- **Problemas de desempenho:** operações em lote, otimização do tamanho dos dados
