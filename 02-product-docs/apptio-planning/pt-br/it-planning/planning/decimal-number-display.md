---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Exibição de números decimais"
breadcrumb:
  - "Planning"
  - "Configuração e administração"
source_path: "it-planning/planning/decimal-number-display.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Exibição de números decimais

A exibição de números decimais controla como os valores numéricos são formatados e exibidos no Apptio Planning. Essa configuração permite que os administradores definam o número de casas decimais utilizadas para todos os dados numéricos, garantindo uma exibição consistente em planos, relatórios e exportações.

Observação: Somente usuários com funções de administrador ou proprietário do processo orçamentário podem realizar essas tarefas.

## O que controla a exibição de números decimais

Quando ativada, a configuração de exibição decimal se aplica a **todas as colunas numéricas**, incluindo:

- Valores do ano fiscal e do período (valores mensais, trimestrais, anuais)
- Atributos inteiros e numéricos
- Quantidades como número de funcionários, FTE, horas e porcentagens

Essa configuração afeta **apenas a exibição** — os cálculos sempre mantêm a precisão total no sistema.

**Como ativar a exibição de números decimais**

1. Navegue até **Configurações (ícone de engrenagem)** → **Perfil da empresa**.
2. Na seção **Formato numérico**, habilite **a exibição de números decimais**.
3. Selecione o número de casas decimais a exibir (por exemplo, 0–8).
4. Selecione **Salvar e Sair** para aplicar a configuração.

## Comportamento padrão quando a exibição de números decimais está desativada

Quando **a opção “Exibição de números decimais” está desativada (padrão)**, os valores numéricos são exibidos usando as configurações padrão específicas da visualização. Essas configurações padrão variam de acordo com o módulo e o caso de uso, a fim de equilibrar legibilidade e precisão.

**Visualizações que exibem por padrão 0 casas decimais**

- Visões resumidas
- Contratos
- Ativos
- Outras abas não relacionadas ao trabalho
- Gestão de despesas
- Comparações (visualizações comparativas)

**Visualizações que exibem, por padrão, duas casas decimais**

- Mão de Obra
- Atividade laboral (valores em ETI)

**Exibição decimal na análise de variação**

- **Os valores reais** são exibidos com **0 casas decimais**
- **Os valores totais e os valores das variações** são exibidos com **duas casas decimais**
