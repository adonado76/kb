---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "pt-br"
doc_type: "it-benchmarking"
title: "Plataforma"
breadcrumb: []
source_path: "it-benchmarking/benchmarking-guides/it-tower-v21-v30/platform.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Plataforma

| Subtorre de recursos de TI | Definições | Exemplos | Custo unitário Unidade de medida (padrão) | Eficiência FTE Unidade de medida |
| --- | --- | --- | --- | --- |
| Banco de dados | Sistemas de gerenciamento de banco de dados (DBMS) baseados em servidor, como Oracle. | MS SQL  Oracle nos servidores | Instâncias de banco de dados | Instâncias de banco de dados por servidor FTE de banco de dados |
| Middleware | Server Middleware - software que vincula bancos de dados e servidores de diferentes arquiteturas e o esforço necessário para dar suporte a ele. | WebSphere, ColdFusion, JBoss, Apache. | Instâncias de middleware | Instâncias de middleware por servidor Middleware FTE |
| Banco de dados de mainframe | Sistemas de gerenciamento de banco de dados baseados em mainframe, como DB2 | DB2  Oracle no mainframe | Bancos de dados | Bancos de dados por FTE de banco de dados de mainframe |
| Middleware de mainframe | Mainframe Middleware - software que vincula bancos de dados e mainframes de diferentes arquiteturas e o esforço necessário para dar suporte a ele. | IBM MQ Series | Instâncias de middleware | Instâncias de middleware por FTE de middleware de mainframe |

**Composição do pool de custos da plataforma**

| Subtorre de recursos de TI | Trabalho interno/externo | Hardware | Software | Serviços externos | Instalações e energia | Telecomunicações |
| --- | --- | --- | --- | --- | --- | --- |
| Banco de dados | Pessoal para suporte operacional e de segundo nível, incluindo administração, configuração, atualizações etc. | N/A | Software de banco de dados | Serviços gerenciados para bancos de dados de servidores | N/A | N/A |
| Middleware | Pessoal para suporte operacional e de segundo nível, incluindo administração, configuração, atualizações etc. | N/A | Software de middleware | Serviços gerenciados para middleware de servidor | N/A | N/A |
| Banco de dados de mainframe | Pessoal para suporte operacional e de segundo nível, incluindo administração, configuração, atualizações etc. | N/A | Software de banco de dados | Serviços gerenciados para bancos de dados de mainframe | N/A | N/A |
| Middleware de mainframe | Pessoal para suporte operacional e de segundo nível, incluindo administração, configuração, atualizações etc. | N/A | Software de middleware | Serviços gerenciados para middleware de mainframe | N/A | N/A |

**Unidade de medida da plataforma**

| Subtorre de recursos de TI | Unidade de medida (padrão) | Diretrizes |
| --- | --- | --- |
| Banco de dados | Instâncias de banco de dados | Uma instância de banco de dados é um banco de dados lógico hospedado em uma instalação de DBMS. Observação: em alguns casos, um DBMS pode hospedar várias instâncias de banco de dados. As tabelas do sistema e outros dados mestre não são contados, e somente os dados fornecidos aos usuários finais e aos aplicativos do usuário final são contados (incluindo bancos de dados de desenvolvimento e teste). |
| Banco de dados de mainframe | Bancos de dados | Um banco de dados de mainframe é um subprocesso de banco de dados (fornecimento de sistemas de gerenciamento de banco de dados (DBMS), como DB2 e Oracle, em plataformas de mainframe). |
| Middleware  Middleware de mainframe | Instâncias de middleware | Número de instâncias do pacote de middleware. |
