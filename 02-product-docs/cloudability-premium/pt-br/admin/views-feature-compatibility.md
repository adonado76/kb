---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Compatibilidade do recurso de visualizações"
breadcrumb:
  - "Cloudability Premium"
  - "Administração"
  - "Criar e gerenciar visualizações"
source_path: "admin/views-feature-compatibility.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Compatibilidade do recurso de visualizações

Embora as Visualizações ofereçam recursos avançados para organizar e controlar como os dados de custo e uso da nuvem são compartilhados entre os usuários do Cloudability, o suporte a elas varia atualmente entre os diferentes recursos do Cloudability. Algumas funcionalidades oferecem suporte total ao Views, enquanto outras têm suporte parcial ou limitações específicas.

Este documento oferece um guia de referência para ajudá-lo a entender quais recursos do Cloudability oferecem suporte ao Views, em que medida, e quaisquer limitações ou ressalvas específicas ao usar o Views com determinados recursos. Use este guia ao planejar sua estratégia de Views ou ao solucionar problemas relacionados a comportamentos inesperados em recursos específicos.

|  |  |  |
| --- | --- | --- |
| **Destaque** | **Suporte para Visualizações** | **Limitações** |
| Painel e relatórios | Suporte completo |  |
| TrueCost Explorer | Suporte completo |  |
| Contêineres  e  Otimização do tamanho dos contêineres | Suporte parcial | Só são suportadas visualizações baseadas nas dimensões ID da conta, Nome da conta, Grupos de contas e Fornecedor. |
| Contêiner avançado | Não suportado | Em breve, daremos início ao suporte parcial (semelhante ao dos contêineres). |
| Explorador de tags | Suporte completo |  |
| Detecção de anomalias | Suporte parcial | Só são suportadas visualizações baseadas no ID da conta, nome da conta, serviço, família de uso e os 5 principais BM (conforme detectado pelo algoritmo de anomalias). |
| Inventário de recurso | Suporte completo |  |
| Confirmação | Suporte parcial | Visualizações baseadas no ID da conta, nos grupos de contas e nas dimensões de fornecedores.  Além disso, se uma visualização for facilitada por meio de um mapeamento de negócios, e esse mapeamento se basear em alguma combinação de contas ou fornecedores, ela seria compatível. |
| Dimensionamento correto | Apoio total, com uma ressalva → | Observação: quando uma visualização é baseada em um mapeamento de negócios, o menu suspenso “Contas” exibe todas as contas, incluindo aquelas que deveriam ser restritas pela visualização. Como alternativa, você pode usar o filtro baseado em grupos de contas no Views. |
| Dimensionamento correto do ROI | Suporte total, com uma ressalva em relação à Política RS → | Observação: Ao criar uma política de redimensionamento (Configurações > Políticas de redimensionamento), o menu suspenso “Visualizações” contém apenas visualizações compartilhadas. |
| Orçamento | Suporte completo | Os orçamentos são vinculados às visualizações. A visualização selecionada na parte superior determina quais orçamentos são exibidos. Ao selecionar **“Mostrar todos os dados”,** são exibidos os orçamentos de todas as visualizações. |
| Previsão | Suporte completo |  |
| Planos | Suporte completo |  |
| Marcadores de desempenho | Suporte completo |  |
| Planejamento da carga de trabalho | Não suportado | As visualizações não se aplicam a este recurso. |
| Governança | Não suportado | As visualizações não se aplicam a este recurso. |

**Tópico principal:** [Criar e gerenciar visualizações](../admin/create-and-manage-views.html)
