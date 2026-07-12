---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Tabelas publicadas"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Data Studio Referência"
source_path: "studio/new-uc/reference/published-tables.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tabelas publicadas

## Visão geral

As tabelas publicadas oferecem um mecanismo específico para exportar dados do TBM Studio sem utilizar relatórios.

**Vantagens:**

- Não é necessário gerenciar permissões de relatórios
- A exportação fica disponível assim que o cálculo de desenvolvimento for concluído
- Definições de exportação fáceis de localizar e manter
- Independente da interface de relatórios do TBM Studio

## Criação de tabelas publicadas

**Método 1: Criar novo**

1. Vá até a guia Início > Novo
2. Selecionar tabela publicada
3. Insira o nome e a categoria
4. Clicar em OK

**Método 2: A partir de uma tabela de relatório existente**

1. Abrir relatório com a tabela de origem
2. Clique com o botão direito do mouse na tabela do relatório
3. Selecione “Criar tabela publicada”
4. Insira o nome e a categoria

## Configurações de pré-cálculo

|  |  |
| --- | --- |
| **Configuração** | **Descrição** |
| Ativo (marcado) | O sistema pré-calcula a tabela; pronta na chamada da API (padrão) |
| Inativo (desmarcado) | O sistema realiza o cálculo na primeira solicitação de API |

**Tópico principal:** [Referência do ` Data Studio `](../../../studio/new-uc/reference/data-studio-reference.html)
