---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Adicionar tabelas aos relatórios"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Criar relatórios"
  - "Noções básicas sobre relatórios"
source_path: "studio/new-uc/howtoguides/create-reports/add-tables-report.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Adicionar tabelas aos relatórios

**Objetivo:** Adicionar uma tabela de dados para exibir os dados do modelo em um formato estruturado, com linhas e colunas

**Quando usar:** Quando for necessário mostrar dados detalhados, permitir análises detalhadas ou apresentar informações que os usuários queiram classificar, filtrar ou exportar

**Tempo estimado:** 10 a 15 minutos

## Entendendo o Painel de Configuração de Componentes

Ao adicionar uma tabela, o painel Configuração do Componente é exibido. Este painel possui quatro áreas para as quais você pode arrastar campos para criar sua tabela:

|  |  |  |
| --- | --- | --- |
| **Área** | **Propósito** | **O que arrastar para cá** |
| **Linhas** | Define os dados da primeira coluna | Campos de dimensão (rótulos, categorias) |
| **Colunas** | Fornece cabeçalhos de coluna | Períodos de tempo ou uma única dimensão |
| **Valores** | Exibe os dados nas células da tabela | Métricas (Custo, Orçamento, Contagem) |
| **Filtros** | Limita quais dados são exibidos | Qualquer campo para filtrar os resultados |

**Passos**

1. Abra seu relatório e **dê uma olhada,** caso ainda não tenha feito isso.
2. Clique na guia **Relatório** e, em seguida, clique em **Tabela**. Uma tabela provisória é exibida no relatório, e o painel de configuração do componente ad hoc é aberto.
3. Na parte superior do painel de configuração, selecione um **objeto de modelo** na lista suspensa. Isso determina quais tabelas e métricas estão disponíveis.
4. No **Explorador** de Projetos (painel esquerdo), expanda a seção **Tabelas** para localizar os campos de dimensão.
5. Arraste um campo de dimensão para a área **Linhas**. Por exemplo, arraste “Data Center” para criar uma tabela que mostre uma linha por data center.
6. Expanda a seção **Métricas** no Explorador de Projetos.
7. Arraste uma ou mais métricas para a área **Valores**. Por exemplo, arraste “Custo” e “Orçamento” para exibir ambos os valores em cada linha.
8. (Opcional) Adicione colunas baseadas em tempo expandindo a seção **Tempo** e arrastando um campo de tempo para a área **Colunas**.
9. (Opcional) Aplique filtros arrastando qualquer campo para a área **Filtros** e clicando com o botão direito do mouse para selecionar **Editar filtro**.

## Exemplo: Como criar uma tabela de custos simples

Para criar uma tabela que mostre o custo e o custo acumulado no ano por centro de dados:

- Selecione **“Data Centers”** como objeto modelo
- Em Tabelas > Informações sobre centros de dados, arraste **“Centro de dados”** para **“Linhas”**
- Na seção Métricas, arraste **“Custo”** para **a seção Valores**
- Na seção Métricas, arraste **“Custo acumulado no ano”** para **a seção Valores**

## Resultados esperados

- A tabela é preenchida com os dados do seu modelo
- Aparecem colunas para cada métrica que você adicionou
- São exibidas linhas para cada valor único no campo “Linhas”
- Por padrão, uma linha de total aparece na parte inferior

## Armadilhas comuns

- **Excesso de dados:** tabelas com milhares de linhas ficam lentas e difíceis de usar. Aplique filtros ou considere usar gráficos para obter uma visão geral.
- **Objeto de modelo incorreto:** Se você não estiver vendo os campos necessários, verifique se selecionou o objeto de modelo correto na parte superior do painel de configuração.
- **Esquecimento de atualizar:** Se você desmarcar a opção “Atualizar resultados imediatamente”, clique em “Atualizar” após fazer as alterações para visualizar seus dados.

**Tópico principal:** [Noções básicas sobre relatórios](../../../../studio/new-uc/howtoguides/create-reports/report-basic.html)
