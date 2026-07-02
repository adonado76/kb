---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "pt-br"
doc_type: "it-benchmarking"
title: "Aplicativo"
breadcrumb: []
source_path: "it-benchmarking/benchmarking-guides/it-tower-v2/application.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Aplicativo

| Subtorre de recursos de TI | Definições | Exemplos | Unidade de medida (padrão) |
| --- | --- | --- | --- |
| Banco de dados | Sistemas de gerenciamento de banco de dados (DBMS) baseados em servidor, como Oracle. | MS SQL  Oracle nos servidores | Instâncias de banco de dados |
| Middleware | Server Middleware - software que vincula bancos de dados e servidores de diferentes arquiteturas e o esforço necessário para dar suporte a ele. | WebSphere, ColdFusion, JBoss, Apache. | Instâncias de middleware |
| Banco de dados de mainframe | Sistemas de gerenciamento de banco de dados baseados em mainframe, como DB2 | DB2  Oracle no mainframe | Bancos de dados |
| Middleware de mainframe | Mainframe Middleware - software que conecta bancos de dados e mainframes de diferentes arquiteturas e o esforço necessário para dar suporte a ele. | IBM MQ Series | Instâncias de middleware |

**Composição do pool de custos de aplicativos**

| Subtorre de recursos de TI | Trabalho interno/externo | Hardware | Software | Serviços externos | Instalações e energia | Telecomunicações |
| --- | --- | --- | --- | --- | --- | --- |
| Banco de dados | Pessoal para suporte operacional e de segundo nível, incluindo administração, configuração, atualizações etc. | N/A | Software de banco de dados | N/A - rastreado no pool de custos de Telecom | N/A | N/A |
| Middleware | Pessoal para suporte operacional e de segundo nível, incluindo administração, configuração, atualizações etc. | N/A | Software de middleware | Serviços gerenciados para middleware de servidor | N/A | N/A |
| Banco de dados de mainframe | Pessoal para suporte operacional e de segundo nível, incluindo administração, configuração, atualizações etc. | N/A | Software de banco de dados | Serviços gerenciados para bancos de dados de mainframe | N/A | N/A |
| Middleware de mainframe | Pessoal para suporte operacional e de segundo nível, incluindo administração, configuração, atualizações etc. | N/A | Software de middleware | Serviços gerenciados para middleware de mainframe | N/A | N/A |

**Unidade de medida do aplicativo**

| Subtorre de recursos de TI | Unidade de medida (padrão) | Diretrizes |
| --- | --- | --- |
| Banco de dados  Banco de dados de mainframe | Instâncias de banco de dados | Uma instância de banco de dados é um banco de dados lógico hospedado em uma instalação de DBMS. Observação: em alguns casos, um DBMS pode hospedar várias instâncias de banco de dados. As tabelas do sistema e outros dados mestre não são contados, e somente os dados fornecidos aos usuários finais e aos aplicativos do usuário final são contados (incluindo bancos de dados de desenvolvimento e teste). |
| Banco de dados de mainframe | Bancos de dados | Número de bancos de dados |
| Middleware  Middleware de mainframe | Instâncias de middleware | Número de instâncias do pacote de middleware. |
