---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Carga útil de dados"
breadcrumb: []
source_path: "cost-transparency/technology-integration/data-uploaded.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Carga útil de dados

Conforme descrito nos pré-requisitos, o fluxo de dados é iniciado em IBM Turbonomic. Depois que o IBM Apptio Target Type é configurado, os dados, incluindo Turbo Pending e Turbo Executed Actions, são transferidos para o Datadrop do IBM Apptio. A partir daí, os conectores Datalink transmitem os dados para IBM Apptio 's TBM Studio para processamento posterior.

Os quatro arquivos a seguir serão carregados

- Ações pendentes do Turbo On Prem
- Turbo On Prem Executed Actions
- Ações pendentes do Turbo Cloud
- Ações executadas no Turbo Cloud

Os arquivos são diferenciados por duas dimensões principais:

- **Estado da ação** : PENDENTE ou EXECUTADO.
- **Entrega** : CLOUD ou ON-PREM.

A principal distinção está nos dados que estão sendo transmitidos. Para a CLOUD, somente os dados agregados são enviados, o que inclui 14 colunas, em contraste com as 25 colunas enviadas para os dados On-Prem. Os principais motivos para essa diferença de granularidade são os seguintes:

- Os dados no local são quantificados usando o modelo e os dados do IBM Apptio, pois o IBM Turbonomic não fornece detalhes financeiros para ambientes no local. Para realizar esses cálculos, é necessário um nível mais alto de granularidade, e é por isso que colunas detalhadas, como Entity Id e Action Id, estão incluídas. Por outro lado, os dados da nuvem já vêm com $ Savings pré-calculados, conforme determinado pelo IBM Turbonomic, eliminando a necessidade de detalhes tão granulares.
- IBM Apptio não foi projetado para armazenar dados granulares da nuvem - esse é o objetivo do produto Cloudability. Da mesma forma que as faturas de nuvem do CSP são ingeridas sem incluir as informações mais detalhadas (por exemplo, ID do recurso), essa integração também evita o envio de dados granulares de otimização da nuvem.

Os conjuntos de 25 colunas para dados no local e 14 colunas para dados na nuvem foram cuidadosamente selecionados por meio de um esforço de colaboração entre IBM Apptio e IBM Turbonomic. Esse exercício se concentrou na identificação das colunas mais importantes que seriam valiosas tanto para a modelagem quanto para a geração de relatórios na integração.
