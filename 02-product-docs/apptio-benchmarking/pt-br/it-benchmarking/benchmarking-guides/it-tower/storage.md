---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "pt-br"
doc_type: "it-benchmarking"
title: "Armazenamento"
breadcrumb: []
source_path: "it-benchmarking/benchmarking-guides/it-tower/storage.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Armazenamento

| Subtorre de recursos de TI | Definições | Exemplos | Unidade de medida (padrão) |
| --- | --- | --- | --- |
| Camada 1 | Recursos de armazenamento que permitem aplicativos e serviços de missão crítica e exigem os mais altos níveis de disponibilidade. | - FC SAN - NAS de ponta - Switches, discos, cabeamento e SSD - SW de replicação | TB instalado |
| Camada 2 | Recursos de armazenamento que permitem aplicativos, serviços e dados essenciais, mas não essenciais à missão; requer um desempenho de nível de serviço relativamente alto. | - FC SAN - NAS de ponta - Switches, discos, cabeamento | TB instalado |
| Camada 3 | Recursos de armazenamento usados para informações não essenciais, históricas e outras em que a disponibilidade imediata não é necessária. | - SAN, NAS - Switches, discos, cabeamento - Disco para disco | TB instalado |
| Camada 4 | Recursos de armazenamento usados para arquivamento, backup e recuperação para suportar perda de dados, corrupção de dados, recuperação de desastres e requisitos de conformidade. | - Backup em fita - S/W de backup/arquivo | TB instalado |

**Composição do pool de custos de armazenamento**

| Subtorre de recursos de TI | Trabalho interno/externo | Hardware | Software | Serviços externos | Instalações e energia | Telecomunicações |
| --- | --- | --- | --- | --- | --- | --- |
| Camada 1 | Analistas/engenheiros de armazenamento que fornecem operações e suporte técnico, planejamento e gerenciamento de processos, administração (incluindo gerenciamento) | Controladores e discos de armazenamento, servidores de armazenamento, switches de fibra | Manutenção de armazenamento, replicação, relatórios, segurança, monitoramento | Serviços de armazenamento gerenciado. | N/A (no nível da torre, incluído no TCO dos serviços de tecnologia) | N/A |
| Camada 2 | Analistas/engenheiros de armazenamento que fornecem operações e suporte técnico, planejamento e gerenciamento de processos, administração (incluindo gerenciamento) | Controladores e discos de armazenamento, servidores de armazenamento, switches de fibra | Manutenção de armazenamento, replicação, relatórios, segurança, monitoramento | Serviços de armazenamento gerenciado. | N/A (no nível da torre, incluído no TCO dos serviços de tecnologia) | N/A |
| Camada 3 | Analistas/engenheiros de armazenamento que fornecem operações e suporte técnico, planejamento e gerenciamento de processos, administração (incluindo gerenciamento) | Controladores e discos de armazenamento, servidores de armazenamento, switches de fibra | Manutenção de armazenamento, replicação, relatórios, segurança, monitoramento | Serviços de armazenamento gerenciado. | N/A (no nível da torre, incluído no TCO dos serviços de tecnologia) | N/A |
| Camada 4 | Analistas/engenheiros de sistemas que fornecem operações técnicas e suporte (backup on-line e gerenciamento de fitas), planejamento e gerenciamento de processos, administração (incluindo gerenciamento) | Sistemas especializados de backup/arquivamento, subsistemas de fita, suprimentos off-line (por exemplo, fitas) | Manutenção de backup/restauração/arquivo, relatórios, segurança, monitoramento, manuseio/migração de mídia | Serviços de armazenamento gerenciado. Serviços gerenciados de arquivamento fora do local. | N/A (no nível da torre, incluído no TCO dos serviços de tecnologia) | N/A |

**Unidades de medida de armazenamento**

| Subtorre de recursos de TI | Unidade de medida (padrão) | Diretrizes |
| --- | --- | --- |
| Camada 1 | Total de armazenamento em disco instalado (bruto) em TB | A capacidade física bruta máxima de todas as unidades de disco, tecnologias (ou seja, SAN, NAS, iSCSI, CAS, DASD etc.) e locais (incluindo locais de recuperação de desastres). Por exemplo, para uma matriz de armazenamento com 64 unidades de disco classificadas pelo fabricante como unidades de 800 Gbytes, o armazenamento em disco instalado é de 51.2 Tbytes.  Para matrizes de armazenamento virtual, como RAMAC ou ICEBERG, insira a capacidade máxima declarada pelo fornecedor do dispositivo após a compactação, conforme encontrado em contratos de compra ou folhetos de produtos.  Produção e failover - FC SAN, NAS de ponta, SSD  Incluir armazenamento em mainframe  Incluir volumes de recuperação de desastres |
| Camada 2 | Total de armazenamento em disco instalado (bruto) em TB | Não crítico para a missão, desenvolvimento e teste  Incluir volumes de recuperação de desastres |
| Camada 3 | Total de armazenamento em disco instalado (bruto) em TB | Armazenamento para requisitos de baixo desempenho  Backup de disco para disco, arquivamento on-line, VTL  Incluir volumes de recuperação de desastres |
| Camada 4 | Total de armazenamento em fita instalado em TB | Reposição da fita  Incluir volumes de recuperação de desastres |
