---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "pt-br"
doc_type: "it-benchmarking"
title: "Mapear as unidades de medida"
breadcrumb: []
source_path: "it-benchmarking/configuration/map-uom.html"
images:
  - "resources/images/it_benchmarking_images/map-uom-map.jpg"
  - "resources/images/it_benchmarking_images/map-uom.jpg"
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Mapear as unidades de medida

Foram definidas unidades de medida padrão para os dados de benchmark fornecidos pelo aplicativo Apptio Benchmarking Infrastructure. Para ativar os relatórios de Benchmarking, você deve mapear suas unidades de medida para a unidade de medida do aplicativo.

Ao criar o projeto Costing Standard , você definiu as unidades de medida em sua infraestrutura de TI. Se você aceitou as definições de projeto padrão, elas correspondem às unidades de medida padrão definidas nos dados de referência. Sempre que possível, você precisa fazer a correspondência entre as unidades de medida dos dados de referência e a unidade de medida do seu projeto Costing Standard . O mapeamento completo da unidade de medida fornece os dados de benchmarking mais completos nos relatórios. Você mapeia as unidades de medida usando as instruções no aplicativo, conforme mostrado abaixo.

![img](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/map-uom.jpg)

**Pré-requisitos**

Antes de poder mapear as subtorres e os reservatórios de custos, você precisa ter:

Importou o benchmarking da AIB.

Instalei o componente CTF-Benchmarking ( [https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=costing-standard-foundation-module-configuration](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=costing-standard-foundation-module-configuration "(Abre em uma nova guia ou janela)") ).

Anexou os dados de benchmarking da AIB aos dados mestre de Benchmarking.

**Para mapear a coluna Unidade de medida de referência no conjunto de dados Dados mestre de origem de custos**

Abra o conjunto de dados de dados mestre da fonte de custos.

1. Na guia Data Sources (Fontes de dados ), edite a fonte de dados Benchmark Composition Master Data (Dados mestre de composição de referência ).
2. Mapeie a coluna Unidade de medida de referência para =Unidade de medida.

**Para mapear as unidades de medida**

Selecione a guia Relatórios.

1. Na página inicial, selecione Benchmarking.
2. Na barra de ferramentas de navegação do Benchmarking, selecione o ícone Mapa destacado abaixo.

![img](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/map-uom-map.jpg)

1. Selecione a guia Unit of Measure (Unidade de medida ).
2. Siga as instruções na página de mapeamento.

O mapeamento deve ser um para um.
