---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Nuvem pública"
breadcrumb:
  - "Costing Standard"
  - "Guia passo a passo do Relatório NX"
  - "Relatórios do Public Cloud NX"
source_path: "cost-transparency/reports/pc-nx-report.html"
images:
  - "resources/images/ct_images/nx-pctco.png"
  - "resources/images/ct_images/nx-pctco1.png"
  - "resources/images/ct_images/nx-pctco2.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Nuvem pública

Use este relatório para analisar os gastos com nuvem entre os diferentes provedores, acompanhar a eficiência dos recursos por meio da utilização e cobertura das instâncias reservadas e identificar oportunidades de otimização de custos.

Este relatório foi elaborado para ser utilizado pelos seguintes perfis:

- Arquitetos de nuvem
- FinOps Equipes
- Controladores Financeiros de TI
- Operações em nuvem
- CIO

## Elementos-chave

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/nx-pctco.png)

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/nx-pctco1.png)

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/nx-pctco2.png)

| Elemento | Descrição |
| --- | --- |
| Fichas de resumo (1) | Cinco cartões de resumo mostram o custo, a taxa de cobertura das instâncias reservadas, a utilização das instâncias reservadas, o desperdício das instâncias reservadas e os créditos de nuvem. |
| Opções de filtro - Linha superior (2) | Cinco filtros permitem filtrar o relatório por prestador, categoria, unidade de negócios, divisão e centro de custo. |
| Opções de filtro - Linha inferior (2) | Filtros adicionais permitem refinar o relatório por nome da conta, aplicativo, família de uso, nome do serviço, categoria do serviço, produto, tipo de contrato de locação e localização. |
| Navegação por abas (3) | As guias alternam entre as visualizações Visão geral, Definições de KPIs, Definições de filtros, Detalhes de crédito na nuvem, Mapeamento da Cloud Tower e Definições. |
| Tabela de Custos dos Prestadores (4) | Esta tabela mostra o provedor, o custo, a quantidade de uso de computação e o custo de computação por 100 unidades, por mês. |
| Gráfico da taxa de cobertura do RI por mês (5) | Um gráfico de linhas mostra a taxa de cobertura das instâncias reservadas ao longo do tempo, com intervalos de referência. |
| Gráfico da taxa de utilização do RI por mês (5) | Um gráfico de linhas mostra a utilização das instâncias reservadas ao longo do tempo em comparação com o valor de referência. |
| Gráfico de comparação entre uso e custo de computação (5) | Um gráfico combinado de barras e linhas mostra a quantidade de uso de computação e o custo de computação por 100 unidades ao longo do tempo. |
| Gráfico: Custo da nuvem de computação vs. custo por 100 unidades (5) | Um gráfico combinado de barras e linhas mostra o custo da computação em nuvem e o custo de computação por 100 unidades ao longo do tempo. |
| Gráfico do número de instâncias reservadas (5) | Um gráfico de linhas mostra o número de instâncias reservadas ao longo do tempo. |
| Custo total da nuvem por gráfico de barras (5) | Um gráfico de barras mostra o custo total da nuvem por torre de nuvem. |
| Guias da Cloud Tower (6) | As guias alternam entre as visualizações “Visão geral de computação e RI” e “Visão geral de armazenamento”. |
| Caixas de seleção do seletor de dimensões (7) | Use essas caixas de seleção para mostrar ou ocultar as colunas disponíveis na tabela de análise. |

## Perguntas e respostas

- Quanto estou gastando em serviços de nuvem pública por mês?
- Qual é a minha taxa de cobertura de Instâncias Reservadas e como ela se compara às melhores práticas?
- Estou aproveitando ao máximo minhas Instâncias Reservadas ou estou desperdiçando dinheiro?
- Qual provedor de nuvem ( Azure, AWS ) é mais caro?
- Qual é o meu custo por 100 unidades de computação e ele está aumentando ou diminuindo?
- Qual torre de nuvem (Computação, Armazenamento, Rede) consome mais do orçamento?
- Quantos créditos de nuvem tenho disponíveis?
- O número de minhas Instâncias Reservadas está aumentando ou diminuindo?
- Qual é o meu desperdício total na nuvem e de onde ele vem?

## Ações recomendadas

- Analise a taxa de cobertura de RI ( 22.69 %) — ela está bem abaixo da faixa de referência de 75% a 85%, o que indica uma oportunidade significativa de economizar dinheiro com a aquisição de mais Instâncias Reservadas.
- Verifique a taxa de utilização das RI (100%) — isso é excelente e indica que você está utilizando plenamente suas Instâncias Reservadas, mas, com baixa cobertura, você está pagando tarifas sob demanda pela maioria dos recursos.
- Observe o gráfico do número de instâncias reservadas, que mostra uma queda de 13.000 para 5.000 — analise por que o número de instâncias reservadas está diminuindo e se isso está alinhado com sua estratégia de nuvem.
- Analise o gráfico “Custo Total da Nuvem” da Cloud Tower para identificar quais serviços (Computação, Armazenamento, Marketplace) oferecem as melhores oportunidades de otimização.
- Filtre por provedor para comparar os gastos com Azure e AWS e determinar se você está obtendo um melhor custo-benefício com um deles.
- Use a tendência “Custo de computação por 100 unidades” para acompanhar se seus custos unitários estão melhorando ao longo do tempo ou se você precisa renegociar tarifas ou otimizar o uso.
- Clique na guia “Detalhes de créditos na nuvem” para entender seus créditos do programa “ $1.5M ” e garantir que eles estejam sendo aplicados corretamente para reduzir custos.
