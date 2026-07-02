---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "pt-br"
doc_type: "it-benchmarking"
title: "Armazenamento"
breadcrumb: []
source_path: "it-benchmarking/benchmarking-guides/it-tower-v2/storage.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Armazenamento

| Subtorre de recursos de TI | Definições | Exemplos | Custo unitário Unidade de medida (padrão) (consulte [a definição](#unit "(Abre em uma nova guia ou janela)") ) |
| --- | --- | --- | --- |
| On-line | Recursos de armazenamento on-line anexados aos servidores. Ele exclui o armazenamento que é empacotado (interno) no servidor (está incluído no custo do servidor). Isso inclui o armazenamento de recuperação de desastres. | SAN, NAS, CAS ( iSCSI, ) | TB instalado |
| Off-line | Recursos de armazenamento off-line anexados aos servidores. Isso inclui o armazenamento de recuperação de desastres. | Backup de fita Backup/Arquivamento S/W | TB instalado |
| Mainframe Online | Recursos de armazenamento on-line anexados aos mainframes. Isso inclui o armazenamento de recuperação de desastres. | SAN, NAS, CAS ( iSCSI, ) | TB instalado |
| Mainframe off-line | Recursos de armazenamento off-line anexados aos mainframes. Isso inclui o armazenamento de recuperação de desastres. | Backup em fita  S/W de backup/arquivo | TB instalado |

**Composição do pool de custos de armazenamento**

| Subtorre de recursos de TI | Trabalho interno/externo | Hardware | Software | Serviços externos | Instalações e energia | Telecomunicações |
| --- | --- | --- | --- | --- | --- | --- |
| On-line  Mainframe Online | Analistas/engenheiros de armazenamento que fornecem operações e suporte técnico, planejamento e gerenciamento de processos, administração (incluindo gerenciamento) | Controladores e discos de armazenamento, servidores de armazenamento, switches de fibra | Gerenciamento de armazenamento, virtualização, replicação, relatórios, segurança e monitoramento. Drivers e software de rede para NAS. | Serviços de armazenamento gerenciado. | N/A (no nível da torre, incluído no TCO dos serviços de tecnologia) | N/A |
| Off-line  Mainframe off-line | Analistas/engenheiros de sistemas que fornecem operações técnicas e suporte (backup on-line e gerenciamento de fitas), planejamento e gerenciamento de processos, administração (incluindo gerenciamento) | Sistemas especializados de backup/arquivamento, subsistemas de fita, suprimentos off-line (por exemplo, fitas) | Manutenção de backup/restauração/arquivo, relatórios, segurança, monitoramento, manuseio/migração de mídia | Serviços de armazenamento gerenciado. Serviços gerenciados de arquivamento fora do local. | N/A (no nível da torre, incluído no TCO dos serviços de tecnologia) | N/A |

**Unidades de medida de armazenamento**

| Subtorre de recursos de TI | Unidade de medida (padrão) | Diretrizes |
| --- | --- | --- |
| On-line  Mainframe Online | Total de armazenamento em disco instalado (bruto) em TB | A capacidade física bruta máxima de todas as unidades de disco, tecnologias (ou seja, SAN, NAS, iSCSI, CAS, DASD etc.) e locais (incluindo locais de recuperação de desastres). Por exemplo, para uma matriz de armazenamento com 64 unidades de disco classificadas pelo fabricante como unidades de 800 Gbytes, o armazenamento em disco instalado é de 51.2 Tbytes.  Para matrizes de armazenamento virtual, como RAMAC ou ICEBERG, insira a capacidade máxima declarada pelo fornecedor do dispositivo após a compactação, conforme encontrado em contratos de compra ou folhetos de produtos.  Produção e failover - FC SAN, NAS de ponta, SSD  Incluir volumes de recuperação de desastres |
| Off-line  Mainframe off-line | Total de armazenamento em fita instalado em TB | Reposição da fita  Incluir volumes de recuperação de desastres |
