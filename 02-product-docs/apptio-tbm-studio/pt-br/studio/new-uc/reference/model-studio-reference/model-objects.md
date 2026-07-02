---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Objetos modelo"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Model Studio"
source_path: "studio/new-uc/reference/model-studio-reference/model-objects.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Objetos modelo

Os objetos de modelo são os elementos básicos de um modelo de custos do TBM Studio. Cada objeto do modelo representa uma camada ou entidade distinta na estrutura de custos da sua organização, como fontes de custo, fornecedores, aplicativos ou unidades de negócios.

## Tipos de objetos de modelo e suas finalidades

O TBM Studio oferece suporte a um tipo de objeto de modelo unificado que pode servir a diferentes finalidades, dependendo de sua posição na hierarquia do modelo e de sua configuração.

**Objeto Modelo**

**Descrição:** Um objeto de modelo é criado ao adicionar uma etapa de modelo ao pipeline de transformação de uma tabela. Isso converte a tabela em uma entidade modelada que pode participar de alocações, receber fatores de ponderação e processar métricas por meio do modelo de custos.

**Objetivo:** Os objetos de modelo agrupam dados para análise e definem relações de alocação. Eles podem atuar como objetos de origem (fornecendo valor), objetos de destino (recebendo valor) ou ambos.

**Funções comuns dos objetos do modelo**

|  |  |  |
| --- | --- | --- |
| **Função** | **Descrição** | **Exemplos** |
| Origem do custo | Ponto de entrada para dados financeiros. Geralmente contém dados do Razão ou de faturas com os responsáveis pelas unidades. | Dados reais de origem de custo, Razão, Livro de ativos fixos |
| Pool de custos | Camada de agrupamento intermediária. Recebe alocações de fontes de custo e as distribui para infraestrutura ou serviços. | Mão de obra, Instalações, Ativos fixos, Licenças de software |
| da nuvem e híbrida | Camada de recursos tecnológicos. Representa ativos físicos ou virtuais. | Servidores, Armazenamento, Rede, Centros de Dados |
| Serviço | Camada de serviços de TI. Representa os serviços utilizados pela empresa. | Serviços de Tecnologia, Aplicativos, Soluções |
| Consumidor | Destino final da alocação de custos. Representa consumidores empresariais. | Unidades de Negócios, Departamentos, Projetos, Clientes |

*→ Consulte [as camadas da estrutura TBM para obter uma visão geral conceitual](../../concepts-architecture/model-architecture/model-concepts-overview.html)*

*→ Consulte [“Criar um objeto modelo” para obter instruções passo a passo](../../howtoguides/build-cost-model/create-model-rep.html)*

- **[Propriedades do objeto modelo](../../../../studio/new-uc/reference/model-studio-reference/model-objects-properties.html)**
- **[Relações e dependências entre objetos](../../../../studio/new-uc/reference/model-studio-reference/objects-relationships.html)**
- **[Convenções de nomenclatura de objetos](../../../../studio/new-uc/reference/model-studio-reference/object-naming-convention.html)**
