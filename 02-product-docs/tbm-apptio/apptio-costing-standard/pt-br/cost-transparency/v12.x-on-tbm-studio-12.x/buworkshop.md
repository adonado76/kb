---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Workshop de unidades de negócios"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/buworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Workshop de unidades de negócios

Preparação dos dados de sua unidade de negócios

1. Se ainda não tiver feito isso, carregue os dados de sua unidade de negócios, incluindo:
   - Lista de unidades de negócios, incluindo o número de funcionários
2. Seguindo as Apptio práticas padrão, categorize cada conjunto de dados brutos na categoria de unidades de negócios.
3. Se apropriado, aplique um filtro de data aos dados de sua unidade de negócios.

## Sobre o identificador da unidade de negócios

O identificador do conjunto de dados mestre de unidades de negócios é a coluna Ident. Você pode ter até cinco níveis incorporados à hierarquia de sua unidade de negócios. Os cinco níveis definidos em Apptio são:

- Conselho de Administração
- Unidade de negócios
- Programa
- Projeto
- Local

A coluna Ident geralmente é uma concatenação dessas cinco colunas. No entanto, talvez você decida que não precisa de todos os cinco níveis como o nível de detalhe necessário em seus relatórios. Por exemplo, você pode decidir usar apenas a coluna Business Unit como a coluna Ident.

## Sobre as chaves da unidade de negócios

As chaves do conjunto de dados mestre de alocação de unidades de negócios são, em sua maioria, definidas pelo usuário. A lógica recomendada está na tabela abaixo.

| Chave | A chave de campo é baseada em | Lógica recomendada |
| --- | --- | --- |
| **Chave Direct\_BU das alocações de serviço (em 11.6 )** | Definido pelo usuário | ="Service Allocations\_BU" && Identificador da unidade de negócios |
| **Chave Project\_BU** | Unidade de negócios | ="Project\_BU"&&Unidade de Negócios&&Metacampo-chave Project\_BU |

## Colunas computadas comuns necessárias para a unidade de negócios

A única coluna computada que você talvez precise criar é a coluna Ident, se quiser concatenar dados.

## Mapear dados para os dados mestre de alocações de unidades de negócios

Mapeie os dados de sua unidade de negócios para o conjunto de dados mestre de alocações de unidades de negócios. A maior parte do mapeamento deve ser autoexplicativa neste ponto. Em 12.7, agora você pode aproveitar a função Column Map em seu conjunto de dados brutos para mapear os dados mestre de alocações de unidades de negócios ([Map Columns](https://community.apptio.com/docs/DOC-10561 "(Abre em uma nova guia ou janela)") )

## Revise o objeto de alocação de unidade de negócios nos modelos

| Modelo | Ações |
| --- | --- |
| **Custo** | Certifique-se de que os valores estejam fluindo para o objeto de alocação da unidade de negócios. Em Service Allocations Direct to Business Unit Allocation, aloque usando a Referência baseada em dados com uma ponderação uniforme (essa é a configuração padrão). As chaves que unem as alocações de serviço diretas à alocação da unidade de negócios são as colunas Service Allocations Direct\_BU Key em ambos os conjuntos de dados.  De Service Allocations Indirect a Business Unit Allocation, aloque usando Headcount ou outras opções de alocação.  Em Projetos para alocação de unidade de negócios, aloque usando a Referência baseada em dados com uma ponderação uniforme (essa é a configuração padrão). As chaves que unem os projetos às alocações de unidades de negócios são as colunas Project\_BU Key em ambos os conjuntos de dados. |
| **Orçamento** | Certifique-se de que os valores estejam fluindo para o objeto de alocação da unidade de negócios. De Serviços empresariais a Alocação de unidades de negócios, você pode alocar custos usando duas opções possíveis:   - Por número de funcionários - Por receita   Para alocar por número de funcionários, pondere a alocação pelo mestre de alocação de unidades de negócios Data.Employees. |
| **CapEx** | Certifique-se de que os valores estejam fluindo para o objeto de alocação da unidade de negócios. Em Service Allocations Direct to Business Unit Allocation, aloque usando a Referência baseada em dados com uma ponderação uniforme (essa é a configuração padrão). As chaves que unem as alocações de serviço diretas à alocação da unidade de negócios são as colunas Service Allocations Direct\_BU Key em ambos os conjuntos de dados.  De Service Allocations Indirect a Business Unit Allocation, aloque usando a alocação baseada em tabela.  Em Projetos para alocação de unidade de negócios, aloque usando a Referência baseada em dados com uma ponderação uniforme (essa é a configuração padrão). As chaves que unem os projetos às alocações de unidades de negócios são as colunas Project\_BU Key em ambos os conjuntos de dados. |

## Analisar os relatórios das unidades de negócios

Os relatórios a seguir são atualizados após a configuração do objeto Business Units:

- Revisão da unidade de negócios
- Análise da unidade de negócios - Detalhes
- Portfólio de unidades de negócios
- Lista de unidades de negócios
- Impacto da desativação de aplicativos
- Validade da alocação da unidade de negócios
- Unidade de negócios
- Unidade de negócios - Departamento
- Fatura da unidade de negócios
- Serviço - Tendência de consumo da BU
- Dimensões de dados - Unidades de negócios

Para ver detalhes desses relatórios (incluindo navegação, funções, objetivos e perguntas respondidas para cada relatório), consulte o Guia do Usuário do Costing Standard disponível na Ajuda on-line.

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
