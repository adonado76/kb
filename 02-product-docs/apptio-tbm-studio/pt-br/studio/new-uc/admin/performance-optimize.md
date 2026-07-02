---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Desempenho e otimização"
breadcrumb:
  - "TBM Studio"
  - "Administração"
source_path: "studio/new-uc/admin/performance-optimize.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Desempenho e otimização

**Tipo de conteúdo:** Guia prático / Resolução de problemas

**Público-alvo:** Administradores, usuários avançados

**Pré-requisitos:** função de administrador ou usuário avançado, conhecimento da estrutura do modelo

A otimização do desempenho é fundamental para garantir relatórios ágeis e cálculos eficientes. Esta seção aborda ferramentas e práticas recomendadas para monitorar e melhorar o desempenho do TBM Studio.

## Calc Explorer

O Calc Explorer oferece informações detalhadas sobre os processos de cálculo e ajuda a identificar gargalos de desempenho. Ele exibe o esforço de cálculo para relatórios, transformações, detalhamentos e métricas.

**Para acessar o Calc Explorer:**

- Vá até **Compilação > Calc Explorer**
- Selecione uma compilação para analisar os detalhes do cálculo
- Visualizar relatórios, transformações, detalhamentos e métricas cujo cálculo demorou mais de 10 segundos

**Observação:** *O Calc Explorer captura apenas itens cujo cálculo leva mais de 10 segundos. Os componentes que forem concluídos rapidamente não aparecerão na análise.*

## Detecção de anomalias na compilação

O recurso de detecção de anomalias identifica alterações incomuns no esforço de cálculo, ajudando você a identificar precocemente possíveis problemas de desempenho. Ele compara cada compilação com as compilações anteriores e avisa sobre alterações significativas.

**Tipos de anomalias detectadas:**

- **Anomalia no cálculo** - Aumento inesperado no tempo de cálculo
- **Anomalia baseada em entidade** - Padrões incomuns na estrutura dos dados (por exemplo, contagens inesperadas de linhas)
- **Combinado** - Anomalias detectadas tanto com base em cálculos quanto em entidades

**Para ativar a detecção de anomalias:**

- Vá para **Projeto > Ativar recursos**
- Selecionar **“Mostrar painel de anomalias”**
- Visualizar anomalias em **Projeto > Anomalias**

## Mecanismo de recomendações

O mecanismo de recomendações identifica problemas de configuração que podem afetar o desempenho ou a qualidade dos dados. Ele oferece fluxos de trabalho guiados para resolver problemas comuns.

**Tipos comuns de recomendação:**

- **Alocações** com zero unidades - Alocações com zero unidades que consomem tempo de processamento sem agregar valor
- **Alocações não utilizadas** - Etapas de alocação que não são mais necessárias
- **Relatórios não utilizados** - Relatórios que não foram acessados recentemente
- **Colunas de dados da** tabela base não utilizadas - Colunas nas tabelas base que não são utilizadas por transformações ou relatórios
- **Problemas com ALL\_ROWS** - Consultas baseadas em tempo que podem exigir o tratamento de ALL\_ROWS

**Para dar seguimento às recomendações:**

- Acesse o **TBM Studio > Recomendações**
- Selecione uma recomendação e clique em **“Resolver todos os problemas identificados”**
- Siga o fluxo de trabalho guiado para revisar e corrigir os problemas
- Confirmar as alterações quando concluídas

## Componente de Avaliação de Desempenho

O componente Análise de Desempenho fornece relatórios que ajudam os administradores a compreender o impacto da configuração do projeto no desempenho. Isso inclui a análise das relações de alocação, a integridade dos identificadores e a granularidade do modelo.

**Relatórios principais no componente Avaliação de Desempenho:**

- **Informações sobre alocação** - Mostra os tamanhos das tabelas de relações de alocação para uma rápida identificação de alocações de grande porte
- **Informações sobre o Drill e o Identificador** - Analisa a granularidade da tabela e a eficiência da alocação
- **Granularidade do modelo** - Identifica áreas em que alocações de valores baixos podem afetar o tempo de cálculo
- **Índice de Saúde do Identificador** - Mede a variação do identificador ao longo do tempo (escala de 1 a 100)

## Melhores práticas para otimização de desempenho

- **Reduzir a granularidade desnecessária** - Remover colunas e detalhes que não sejam necessários para alocações ou relatórios
- **Agrupar linhas** - Agregar dados no nível da transação para reduzir o número de linhas nos casos em que os detalhes não são necessários
- **Desative relatórios não utilizados** — os relatórios aumentam o tempo de cálculo, mesmo que não sejam consultados com frequência
- **Substitua `Eval()` por ` DynamicColumn( )** ` - Permite melhorar o desempenho dos cálculos de precisão
- **Limitar a duração do projeto** - Calcular apenas os períodos necessários para atender aos requisitos de relatórios
- **Resolva as recomendações regularmente** - Trate de forma proativa as alocações de unidades nulas e as configurações não utilizadas
