---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Visão geral dos conceitos de modelagem"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Arquitetura do modelo"
source_path: "studio/new-uc/concepts-architecture/model-architecture/model-concepts-overview.html"
images:
  - "resources/images/studio_images/cost-model.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Visão geral dos conceitos de modelagem

O modelo de custos é o elemento central do TBM Studio. Trata-se de uma representação estruturada de como os custos circulam pela sua organização — desde os lançamentos no razão geral, onde o dinheiro entra no sistema, passando por camadas intermediárias de alocação, até as unidades de negócios, aplicativos ou serviços finais que consomem esses recursos.

Pense em um modelo de custos como um mapa. Os dados financeiros brutos mostram quanto você gastou. Um modelo de custos indica em que você gastou, quem consumiu e por quê. Sem um modelo, você tem apenas números. Com um modelo, você tem uma visão clara.

## O que é um modelo de custos?

Em termos simples, um modelo de custos responde à seguinte pergunta: como distribuir de forma justa os custos compartilhados entre as pessoas e os serviços que realmente os utilizam?

Imagine um data center cuja operação custa US$ 2 milhões por ano. Os custos aparecem como uma única linha no seu razão geral, mas seis unidades de negócios diferentes utilizam servidores nesse centro de dados. Um modelo de custos permite distribuir (alocar) esses US$ 2 milhões entre essas seis unidades de negócios com base no número de servidores que cada uma utiliza, no espaço de armazenamento que consomem ou em qualquer outro fator que reflita o consumo real.

Nota:

**Conceito-chave: O modelo de custos como um mapa**

Um modelo de custos não é um conjunto de dados brutos — é um conjunto de regras que descreve como os custos devem ser distribuídos. O modelo define os caminhos; os dados fornecem os valores. Quando você executa um cálculo (denominado “compilação”), o TBM Studio aplica essas regras aos seus dados atuais e gera os resultados da alocação.

**Objetivo de um modelo de custos:**

- Transforme dados financeiros brutos em insights detalhados e úteis
- Distribuir os custos compartilhados de forma justa com base em fatores de consumo mensuráveis
- Ativar o showback e o chargeback para as unidades de negócios
- Apoiar o planejamento orçamentário por meio da modelagem de cenários hipotéticos de alocação
- Fornecer um rastro auditável desde o custo na origem até o consumidor final

## Modelo x Dados x Relatórios: Os Três Estúdios

O TBM Studio possui três áreas de trabalho principais, e é essencial compreender como elas se relacionam entre si antes de mergulhar na arquitetura do modelo.

|  |  |  |
| --- | --- | --- |
| **Studio** | **Função** | **Analogia** |
| Data Studio | Importa, limpa e transforma dados brutos em tabelas | A despensa da cozinha — ingredientes, organizados e à disposição |
| Estúdio de Modelagem | Define como os custos são transferidos das tabelas de origem para as tabelas de destino por meio de alocações | A receita — regras para combinar ingredientes e obter um produto final |
| Report Studio | Apresenta os resultados atribuídos às partes interessadas por meio de gráficos, tabelas e painéis | A mesa de jantar — a refeição pronta, em pratos e servida |

Os dados circulam por esses estúdios seguindo uma sequência específica. Primeiro, o site Data Studio prepara tabelas de transformação a partir dos arquivos enviados. Em seguida, o Model Studio utiliza essas tabelas de transformação como entradas para os objetos do modelo e aplica as regras de alocação. Por fim, o Report Studio consulta o modelo para exibir os resultados. Se seus dados forem alterados, execute novamente a compilação e o modelo será recalculado. Se a sua lógica de alocação mudar, modifique o modelo e execute-o novamente.

## Como ler um diagrama de modelo

O TBM Studio oferece uma visualização em forma de diagrama que exibe todos os objetos do modelo e suas conexões. Esta é uma das ferramentas mais úteis para compreender um modelo de custos rapidamente.

Nota:

**O que o diagrama mostra**

Cada retângulo (nó) representa um objeto do modelo — um contêiner para custos em um determinado nível. As linhas entre os nós representam alocações — regras que transferem custos de um objeto para outro. A largura de cada linha é proporcional ao valor que está sendo atribuído (visualização no estilo Sankey). O fluxo de custos segue da esquerda para a direita (ou de baixo para cima), das fontes até os consumidores finais.

Aqui está uma representação conceitual de um diagrama típico de modelo de custos:

![Modelo de Custo](../../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/cost-model.png)

Na visualização do diagrama do TBM Studio, você pode clicar em qualquer nó para abrir o Modelador de Objeto Único, que mostra em detalhes os controladores, as alocações e as conexões desse objeto. O diagrama é atualizado automaticamente quando os objetos do modelo são alterados, e não é possível modificar as alocações diretamente no diagrama — trata-se de uma visualização somente para leitura do modelo implantado.

Dica:

**Como usar o diagrama de forma eficaz**

Utilize a visualização do diagrama para integrar novos membros da equipe, depurar resultados inesperados de alocação e comunicar a estrutura do modelo às partes interessadas. Isso oferece uma visão imediata e intuitiva de como os custos se distribuem pela sua organização.
