---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Adicionar uma tabela ao modelo"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Criar modelos de custos"
  - "Noções básicas sobre modelos"
source_path: "studio/new-uc/howtoguides/build-cost-model/add-tables.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Adicionar uma tabela ao modelo

|  |  |
| --- | --- |
| **Tipo de Conteúdo** | Guia prático |
| **Público-alvo** | Analistas de negócios, equipes de TI e finanças |
| **Tempo estimado** | 5 a 10 minutos por mesa |
| **Pré-requisitos** | Tabela de transformação criada em Data Studio com os dados carregados |

## Objetivo

Adicione uma tabela de transformação ao modelo de custos para que ela possa ser incluída nas alocações e aparecer nos relatórios do modelo.

## Quando utilizar este procedimento

Siga este procedimento quando tiver preparado uma tabela no Data Studio e e quiser incluí-la no seu modelo de custos. Entre os cenários mais comuns estão:

- Adicionar sua tabela de fontes de custo que contém dados do razão geral ou financeiros
- Adicionar tabelas de destino, como Unidades de Negócio, Aplicativos ou Serviços
- Adicionar tabelas intermediárias, como Fornecedores, Infraestrutura ou Torres de TI
- Incorporando tabelas de fatores que serão utilizadas para ponderar as alocações

## Contexto: Tabelas de transformação vs. Objetos de modelo

No TBM Studio, criar uma tabela no Data Studio e e adicioná-la ao modelo são etapas distintas. **Uma tabela de transformação** é onde você prepara, limpa e estrutura seus dados. **Um objeto de modelo** é aquele em que a tabela faz parte do modelo de custos — com fatores, alocações e fluxos de métricas.

Adicionar uma etapa de modelo ao pipeline de transformação de uma tabela converte-a em um objeto de modelo. Até que você faça isso, a tabela existe apenas em Data Studio e não pode receber nem alocar custos.

## Passos

1. **Dê uma olhada na tabela.** No Explorador de Projetos, localize a tabela que você deseja adicionar ao modelo. Clique com o botão direito do mouse e selecione “**Check Out** ”, ou selecione a tabela e clique em **“Check Out”** na guia “Página inicial”.
2. **Abra o pipeline de transformação.** Clique no nome da tabela para abri-la. Você verá o fluxo de transformação no lado esquerdo da área de trabalho, mostrando a sequência de etapas aplicadas aos seus dados (Fonte, Importação, etapas de fórmula, etc.).
3. **Adicione uma etapa de modelo.** Clique em **“Adicionar etapa”** na parte inferior do pipeline de transformação. No seletor de tipo de etapa, selecione **Modelo**. A etapa "Modelo" foi adicionada ao seu pipeline.
4. **Visualizar a área de trabalho do modelo.** Clique na nova etapa **“Modelo”** no fluxo de trabalho. A área de trabalho agora exibe uma visualização de tabela única, com a sua tabela no centro, com espaços para os motoristas à esquerda e os destinos de alocação à direita. Esta é a visualização do diagrama de Sankey.
5. **Salve suas alterações.** Clique em **“Salvar”** na guia “Página inicial” para salvar suas alterações.
6. **Confira a tabela.** Quando terminar, clique **em** “Check In” para disponibilizar suas alterações aos outros usuários e aos cálculos do modelo.

## Resultados esperados

Após concluir estas etapas:

- A tabela aparece na visualização da etapa Modelo, com seu nome exibido na coluna central
- A tabela é agora um objeto modelo que pode receber drivers e participar de alocações
- Você pode visualizar a tabela no diagrama do modelo (Exibir > Métrica modelada) junto com outros objetos do modelo
- A tabela está disponível como fonte ou destino ao criar alocações a partir de outras tabelas

## Armadilhas comuns

**A tabela não contém dados para o período atual.** Os cálculos do modelo são específicos para cada período. Se a sua tabela não tiver dados carregados para o período selecionado no momento, ela aparecerá vazia no modelo. Verifique se os dados existem consultando a tabela na etapa de Saída antes de adicionar a etapa Modelo.

**Esquecer de fazer o check-out antes de adicionar a etapa “Modelo”.** É necessário fazer o check-out de uma tabela antes de poder modificar seu pipeline de transformação. Se você tentar adicionar uma etapa sem fazer o check-out, receberá uma mensagem de erro.

**Posicionamento dos degraus do modelo.** A etapa “Model” deve, normalmente, ser a última etapa do seu pipeline (ou estar perto do final, antes de qualquer etapa de segurança no nível da linha). Adicionar etapas de transformação após a etapa Modelo pode causar um comportamento inesperado.

Dica: Se você precisar aplicar a segurança no nível da linha (RLS) a uma tabela, ao adicionar uma etapa RLS, uma etapa Modelo será adicionada automaticamente, caso ainda não exista. A segurança no nível da linha só pode ser aplicada a tabelas modeladas.

## O que vem a seguir

- Adicione [fatores](config-drivers.html) de conversão para agregar valor às suas tabelas de fontes de custo
- [Criar alocações](create-allocation.html) para transferir valores entre tabelas
- Consulte o [diagrama do modelo](view-model-diagram.html) para ver como sua tabela se encaixa no fluxo geral de custos.

## Conceitos relacionados

- [Arquitetura do modelo](../../concepts-architecture/model-architecture/model-concepts-overview.html) — Uma análise aprofundada do funcionamento do mecanismo de modelagem
- [Arquitetura de dados](../../concepts-architecture/data-architecture/data-architecture.html) — Compreendendo a relação entre o Data Studio e o Model Studio

**Tópico principal:** [Noções básicas sobre modelos](../../../../studio/new-uc/howtoguides/build-cost-model/model-basics.html)
