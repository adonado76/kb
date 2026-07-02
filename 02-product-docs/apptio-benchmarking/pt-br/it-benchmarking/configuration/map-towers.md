---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "pt-br"
doc_type: "it-benchmarking"
title: "Mapear as torres"
breadcrumb: []
source_path: "it-benchmarking/configuration/map-towers.html"
images:
  - "resources/images/it_benchmarking_images/map-towers-map.jpg"
  - "resources/images/it_benchmarking_images/map-towers.jpg"
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Mapear as torres

As torres padrão foram definidas para os dados de benchmark fornecidos pelo aplicativo Costing Standard Benchmarking Infrastructure. Para ativar os relatórios de Benchmarking, você deve mapear suas torres para as torres do aplicativo.

As torres padrão são:

Aplicativo

Comunicações

Informática

Entrega

Usuário final

Gerenciamento de TI (Gerenciamento)

Rede

Saída

Segurança e conformidade

Armazenamento

Ao criar o projeto Costing Standard , você definiu as torres em sua infraestrutura de TI. Se você aceitou as definições de torre padrão, elas corresponderão às torres padrão definidas nos dados de referência. Sempre que possível, você precisa fazer a correspondência entre as torres dos dados de referência e as torres da sua infraestrutura de TI. O mapeamento completo da torre fornece os dados de benchmarking mais completos nos relatórios. Você mapeia as torres usando as instruções do aplicativo, conforme mostrado abaixo.

![img](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/map-towers.jpg)

Na guia Torres mostrada, Remaining é uma torre que foi mapeada para Delivery, IT Mgmt e Security & Compliance. Elas não são mapeadas imediatamente, mas são regras recomendadas.

**Pré-requisitos**

Antes de poder mapear as subtorres e os reservatórios de custos, você precisa ter:

Importou o benchmarking da AIB.

Instalei o componente CTF-Benchmarking ( [https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=costing-standard-foundation-module-configuration](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=costing-standard-foundation-module-configuration "(Abre em uma nova guia ou janela)") ).

Anexou os dados de benchmarking da AIB aos dados mestre de Benchmarking.

**Para mapear as torres**

Selecione a guia Relatórios.

1. Na página inicial, selecione Benchmarking.
2. Na barra de ferramentas de navegação do Benchmarking, selecione o ícone Mapa destacado abaixo.

![img](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/map-towers-map.jpg)

1. Selecione a guia Torres.
2. Siga as instruções na página de mapeamento.

Você pode mapear uma torre de referência para uma ou mais torres de clientes, mas não pode mapear várias torres de referência para a mesma torre de cliente

1. Se você mapeou uma torre de referência para muitas torres de clientes, deverá modificar o modelo de referência.

**Para modificar o modelo de Benchmark**

Navegue até o modelo Benchmark.

1. Selecione a linha de alocação entre os objetos Fonte de custos e Torre de recursos de TI.
2. Na guia Alocação selecionada, selecione a opção Criar automaticamente uma relação de muitos para muitos.
