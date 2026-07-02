---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Síntese da análise de variância"
breadcrumb:
  - "Planning"
  - "Análise de variância"
source_path: "it-planning/planning/analyze-budget-variance.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Síntese da análise de variância

O recurso Variance Analysis ajuda a comparar um plano de previsão atual com uma linha de base (orçamento ou previsão anterior), identificar diferenças significativas e criar uma trilha de comentários que explique os fatores por trás das variações.

## Principais benefícios

- Analisar variações por centro de custo, conta ou departamento em escala.
- Sinalize apenas as variações significativas usando limites definidos para concentrar esforços.
- Atribua fatores de variação e comentários para criar trilhas de explicação prontas para auditoria.
- Exportar comentários para integração com ferramentas de relatório.

## Configurar análise de variância

Observação: As funções de administrador ou de proprietário do processo orçamentário são necessárias para configurar a análise de variação.

Etapa 1: Ativar o recurso

1. Vá para **Settings** (ícone de engrenagem) **→ Company Profile**
2. Ativar **o painel e os drivers de variação**

Etapa 2: Definir os fatores de variação

1. Ir para **Configuration → Reference Data → Variance Driver**
2. Fazer upload de uma lista de valores de drivers de variação (por exemplo, *tempo do projeto*, *tempo da contabilidade*, *despesas não planejadas* )
3. **Publicar** as alterações

Etapa 3: Definir categorias de contas

1. Vá para **Configuration → Reference Data → Account Category**
2. Faça o upload de uma lista de **categorias de contas** para agrupar contas GL em agrupamentos de alto nível
3. Observação: a análise de desvio é realizada no nível da categoria da conta
4. **Publicar** as alterações

Etapa 4: Mapear contas para categorias

1. Vá para **Configuration → Reference Data → Accounts**
2. Na coluna **Categoria**, mapeie cada **conta GL** para um **código de categoria de conta**
3. Importe a tabela de contas atualizada e **publique** as alterações

Etapa 5: Configurar a análise de variância para o plano

1. Abra seu plano e vá para **Análise de variação** na navegação à esquerda
2. Clique no **menu Ellipses** → **Configure Variance Analysis**
3. Na janela modal, defina as configurações:

   |  |  |
   | --- | --- |
   | **Campo** | **Descrição** |
   | Comparar com o planejado | Selecione o plano de comparação. Todos os planos não arquivados estarão disponíveis para seleção.    Observação: Os planos no estado NEW não serão visíveis para os proprietários de centros de custo. |
   | Período de comparação | Escolha o período de tempo (por exemplo, último mês, último trimestre, ano inteiro ou personalizado) |
   | Alinhamento do plano | Alinhar planos por **ano fiscal correspondente** ou **ano de início do plano** |
   | Limite de variação $ | **Diferença mínima de moeda** que requer explicação |
   | Operador | Selecione E ou OU para determinar como os limites de variação de moeda e porcentagem devem ser aplicados:    E - ambos os limites devem ser atendidos    OU - atender a qualquer um dos limites é suficiente |
   | Limite de variação % | **Variação percentual** mínima que requer explicação |

Etapa 6: Gerar a análise

- Clique em **Preview** para revisar os resultados
- Clique em **Criar** para gerar a análise de variância

Depois de criadas, as variações que excederem os limites serão sinalizadas para explicação e comentários.

## Execução de uma análise de variância

Observação: A análise de variação só está disponível para planos do tipo Forecast.

1. Abra seu **plano de previsão**.
2. Vá para **Plan → Variance Analysis** na navegação à esquerda.
3. Na tabela, procure por **sinalizadores de variação vermelhos** - eles indicam categorias de contas em que a variação excede o limite definido.
4. Selecione uma **categoria de conta** sinalizada para um departamento específico para detalhar as variações.
5. Use as guias **Summary (Resumo** ) e **Actuals (Real)** para analisar a variação como um gráfico em cascata e os detalhes das transações.
6. Atribua um ou mais **Variance Drivers** e insira uma explicação de forma livre para a variação.
7. Clique no **X** para sair da exibição de detalhes da variação.
8. Quando todas as variações tiverem drivers e explicações atribuídas, o **indicador de status ficará verde**.

## Editar configuração de análise de variância

Observação: As funções de administrador ou de proprietário do processo orçamentário são necessárias para editar as configurações de análise de desvio.

**Atualizar limites ou configurações de comparação**

1. Clique no **menu Elipses** na página Variance Analysis
2. Selecione **Configurar análise de variância**
3. Ajuste as configurações (plano, alinhamento, limites, etc.)
4. Clique em **Update** para aplicar as alterações

Importante: A atualização da configuração removerá todas as explicações de variação existentes.

**Atualizar variações para previsões ativas**

Se estiver comparando com períodos de previsão (por exemplo, comparação de ano inteiro entre dois planos), pode ser necessário atualizar os valores de desvio quando os dados planejados forem alterados.

1. Clique no **menu Elipses**
2. Selecione **Atualizar análise de desvio**
3. A caixa de diálogo exibirá os itens de linha que precisam ser atualizados, juntamente com a data da última atualização
4. Clique em **Atualizar** para recalcular a tabela de variação usando os valores de previsão mais recentes.

Importante: a atualização da análise pode remover os fatores de variação e as explicações se essas variações tiverem mudado.

## Exportação e relatórios

- No menu **Actions (Ações** ) da página Variance Analysis (Análise de variação), você pode selecionar **Export Variance Commentary (Exportar comentário de variação)** para exportar para csv. A exportação inclui todos os drivers, comentários e registros de variação.
- No **Dashboard**, navegue até *Spend Variances (Desvios de despesas* ) para visualizar um mapa em árvore e um detalhamento por drivers e departamentos.
