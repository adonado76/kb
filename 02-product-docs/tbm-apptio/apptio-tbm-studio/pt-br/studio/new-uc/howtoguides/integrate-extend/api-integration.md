---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Integração de API"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Integrar e ampliar"
source_path: "studio/new-uc/howtoguides/integrate-extend/api-integration.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Integração de API

**Tipo de conteúdo:** Coleção de guias práticos

**Público-alvo:** Desenvolvedores, administradores técnicos

**Aplicável a:** TBM Studio 12.0 e versões posteriores

**Pré-requisitos:** credenciais da API, conhecimentos de programação, acesso à rede para o TBM Studio

## Visão geral

A API da Plataforma TBM Studio permite a automação programática de uploads e downloads de dados. Esta seção oferece guias práticos para integrar seus sistemas ao TBM Studio usando a API REST, incluindo autenticação, operações de dados e padrões de tratamento de erros prontos para produção.

A API oferece uma conexão direta entre os sistemas de dados da sua empresa e o TBM Studio por meio de comandos simples de tipo “ HTTP ”. Você pode integrar esses comandos a agendadores de tarefas, ferramentas ETL ou aplicativos personalizados com uma configuração mínima — sem necessidade de instalar nenhum software adicional.

Observação: Para a versão 12.9 e versões posteriores, inclua estes cabeçalhos em todas as chamadas de API: app-type="Flagship" e app-version="NA"

## Escolhendo o método de integração

A TBM Studio oferece diversas opções de integração. Use este guia de decisão para selecionar o método adequado para o seu caso de uso.

|  |  |  |
| --- | --- | --- |
| **Método** | **Ideal para** | **Exigências** |
| API da plataforma | Integrações personalizadas, ferramentas ETL de terceiros, ambientes nos quais não é possível instalar agentes locais | Conhecimentos de programação de scripts, credenciais de API |
| DataLink (Clássico) | Carregamento de dados com apenas alguns cliques, mesmo para usuários sem conhecimentos de programação | DataLink instalação do agente, licença do DataLink |
| Tabelas publicadas | Exportação de dados do modelo para ferramentas externas de BI ( Power BI, Tableau ) | TBM Studio 12.11.3 +, configuração de relatórios |

**Use a API da Plataforma quando:**

- Não é possível instalar um agente local do DataLink para fazer o upload de dados de fontes locais
- Você deseja usar scripts incorporados em uma ferramenta ETL de terceiros
- Você precisa automatizar o carregamento de dados por meio de agendadores de tarefas corporativos
- Você precisa de controle programático sobre as operações de dados

**Use tabelas publicadas quando:**

- Você precisa exportar os dados calculados pelo modelo para sistemas externos
- Você deseja um esquema estável para o uso por ferramentas de BI a jusante
- Você precisa de uma saída controlada de dados com governança

Consulte [Autenticação de usuários usando APIs](https://community.ibm.com/community/user/viewdocument/user-authentication-using-apis?CommunityKey=44bcb0d2-5ce6-4504-89eb-019253d3b5d8&tab=librarydocuments "(Abre em uma nova guia ou janela)") para obter mais informações.

- **[Como fazer: Autenticar-se na API](../../../../studio/new-uc/howtoguides/integrate-extend/how-to-authenticate-api.html)**
- **[Guia prático: Como enviar dados via API](../../../../studio/new-uc/howtoguides/integrate-extend/upload-data-via-api.html)**
- **[API](../../../../studio/admin/uploader-service-api.html)**  
   **do Serviço de Uploader Aplica-se a** : TBM Studio 12.0 e versões posteriores
- **[Como fazer: Baixar dados via API](../../../../studio/new-uc/howtoguides/integrate-extend/download-data-api.html)**
- **[Guia prático: Como lidar com erros de API](../../../../studio/new-uc/howtoguides/integrate-extend/handle-api-errors.html)**
- **[Referência rápida](../../../../studio/new-uc/howtoguides/integrate-extend/quick-ref.html)**
