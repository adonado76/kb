---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Microsoft Azure e configuração de outros provedores"
breadcrumb: []
source_path: "cost-transparency/configuration/azure.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Microsoft Azure e configuração de outros provedores

Para configurar o aplicativo para Microsoft Azure ou outros provedores, você deve instalar o componente CTF-Cloud Service.

## Etapa 1: Instale o componente CTF - Cloud para Azure

O componente Cloud Service Provider deve ser instalado antes de você instalar esse componente.

Para instalar o componente CTF - Azure :

### Procedimento

1. Abra o projeto Costing Standard .
2. Clique na guia **Projetos**.
3. Clique em **Components (Componentes** ) na faixa de opções.
4. Clique no componente **CTF - Azure**.
5. Clique em **Install (Instalar** ).

### Resultados

Quando você instala o componente Azure, os seguintes conjuntos de dados são criados na categoria Provedor de serviços de nuvem:

- Azure Dados mestre da fatura EA
- Azure EA Dados mestre detalhados da fatura

O seguinte elemento personalizado é criado:

- Azure EA Bill Raw detalhado
