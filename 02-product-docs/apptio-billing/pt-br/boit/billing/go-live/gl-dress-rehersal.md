---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Ensaio geral"
breadcrumb:
  - "Billing"
  - "Manual de lançamento"
source_path: "boit/billing/go-live/gl-dress-rehersal.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Ensaio geral

Um ensaio geral é uma execução completa de ponta a ponta no **Desenvolvimento** e verificada no **Staging** que imita o que será publicado na Produção.

## Âmbito do ensaio geral

No mínimo, o ensaio deve incluir:

- Atualização dos dados para o período selecionado (ou um período de teste realista) em Desenvolvimento.
- Cálculos de custo total que alimentam o faturamento em desenvolvimento.
- O faturamento completo é executado em Desenvolvimento:
  - Cálculo do núcleo PxQ.
  - Quaisquer modelos específicos do domínio em questão (por exemplo, nuvem, projetos, aplicativos).
- Validação do relatório em Desenvolvimento:
  - Visualizações de faturas/resumos.
  - Visualizações detalhadas/aprofundadas.
  - Diários e exportações.
- Verificações de controle de qualidade na fase de preparação:
  - Verificações estruturais, de volume e de taxa.
  - Reconciliação com o cálculo de custos, quando aplicável.

Se algum desses itens falhar, você não está pronto para a entrada em produção.

## Documentação dos resultados da garantia de qualidade

Registre, pelo menos:

- Qual ID de compilação de preparação foi usada.
- Quais conjuntos de dados foram carregados e quais datas eles abrangem.
- Quaisquer anomalias descobertas e como foram resolvidas.
- Aprovações de:
  - Administrador/Analista (validade técnica).
  - Finanças (se estornos/diários estiverem dentro do escopo).
  - Um ou dois proprietários de serviços ou produtos importantes.

Isso se torna sua referência quando alguém mais tarde perguntar: “O que mudou na entrada em operação?”
