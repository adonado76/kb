---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "SAP LeanIX Introdução"
breadcrumb:
  - "Costing Standard"
  - "Integrações tecnológicas"
  - "SAP LeanIX"
source_path: "cost-transparency/technology-integration/sapleanix/sap-getstart.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# SAP LeanIX Introdução

## Introdução

A integração entre SAP LeanIX e IBM Apptio Costing é uma integração bidirecional. A integração básica concentra-se no fluxo de dados de SAP LeanIX para IBM Apptio Cálculo de custos. A integração avançada é construída sobre a integração básica, onde expõe métricas de TCO (custo total de propriedade) da aplicação para consumo por SAP LeanIX.

**Principais recursos**

A tabela a seguir lista os recursos incluídos na integração.

|  |  |
| --- | --- |
| **Integração da Base** | **Integração avançada** |
| - Exporte informações de SAP LeanIX para IBM Apptio através da API de integração SAP LeanIX - Agende extrações periódicas de dados de SAP LeanIX para IBM Apptio - Exportação pronta para uso dos seguintes tipos de ficha técnica com campos predefinidos e todas as relações relevantes: - Organização - Capacidade empresarial - Aplicativo - Componente de TI - Provedor - Projetos - IBM Apptio Credenciais de usuário da API - Opções de configuração para selecionar quais fichas técnicas, relações e atributos são exportados - Extensão configurável dos campos que são exportados - Acesse painéis e relatórios existentes ou crie novos em IBM Apptio | Todos os recursos incluídos na integração Base, além dos seguintes:  - Importar dados de IBM Apptio para SAP LeanIX - Dados sob demanda extraídos de IBM Apptio para SAP LeanIX - Link para a página de detalhes específicos da ficha informativa em Apptio - Sincronizar fichas técnicas - Campos de custo - Visão geral dos custos por nível da ficha informativa - Ficha informativa: custo ao longo do tempo (métrico) - Pesquisar “Filtragem por tipo de custo” - Visualização de custos para relatórios e diagramas - Execução manual ou programada da exportação de dados |

## Habilitando a integração básica

O núcleo da integração entre SAP LeanIX e IBM Apptio O cálculo de custos é configurado em SAP LeanIX.

Todas as informações relevantes sobre o site SAP LeanIX podem ser encontradas aqui:

[Apptio Integração | Portal de Ajuda do SAP](https://help.sap.com/docs/leanix/ea/apptio-integration "(Abre em uma nova guia ou janela)")

## Instalação de componentes

Uma vez que a integração básica esteja em vigor, a integração avançada torna-se possível.

Instale o seguinte componente em IBMApptio Cálculo de custos:

**Aplicativos CT - Integração com o LeanIX** - Este componente instala um relatório predefinido que a API SAP LeanIX usa para extrair métricas de TCO do aplicativo diretamente para SAP LeanIX para serem usadas em sua solução. O relatório incluído é chamado de **Relatório de Exportação do LeanIX** e e está localizado na pasta Aplicativos.

Observação: este componente atualmente está em fase beta. Entre em contato com seu administrador para instalá-lo a partir da lista de componentes disponíveis.
