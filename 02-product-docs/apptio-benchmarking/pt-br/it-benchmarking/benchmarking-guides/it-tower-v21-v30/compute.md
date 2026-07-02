---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "pt-br"
doc_type: "it-benchmarking"
title: "Informática"
breadcrumb: []
source_path: "it-benchmarking/benchmarking-guides/it-tower-v21-v30/compute.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Informática

| Subtorre de recursos de TI | Definições | Exemplos | Custo unitário Unidade de medida (padrão) (consulte [a definição](#unit "(Abre em uma nova guia ou janela)") ) | Unidade de medida de eficiência FTE (consulte [a definição](#fte "(Abre em uma nova guia ou janela)") ) |
| --- | --- | --- | --- | --- |
| Servidores | Servidores físicos e virtuais que executam uma versão do sistema operacional Windows Server da Microsoft; inclui hardware, software, mão de obra e serviços de suporte. | Servidor Windows 2k  Red Hat Servidor | Servidor lógico | Número de servidores lógicos por FTE para servidor |
| Unix | Servidores que executam sistemas operacionais Unix proprietários e específicos do fornecedor; inclui hardware, software, mão de obra e serviços de suporte. | IBM AIX  Sun Solaris | Servidor lógico | Número de servidores lógicos por FTE para servidor |
| Midrange | Midrange abrange servidores proprietários que fornecem sistemas distribuídos substanciais (em plataformas como Unisys ou Tandem). O tema comum é uma arquitetura distribuída e a capacidade de oferecer suporte a vários clientes em paralelo. | iSeries (AS 400)  Servidores Tandem, DEC | MIPS LPARS CPW configurado | Número de MIPS configurados por FTE para Midrange |
| Mainframe | Computadores mainframe tradicionais e operações que executam sistemas operacionais legados. | IBM mainframes executando MVS, VM, OS/390, zOS,zLinux.Unisysmainframes | MIPS configurado | Número de MIPS configurados por FTE para mainframe |

**Calcular a composição do pool de custos**

| Subtorre de recursos de TI | Trabalho interno/externo | Hardware | Software | Serviços externos | Instalações e energia | Telecomunicações |
| --- | --- | --- | --- | --- | --- | --- |
| Servidores | Analistas/engenheiros de sistemas que fornecem operações e suporte técnico, planejamento e gestão de processos, administração (incluindo gestão) | Servidores físicos e lógicos, incluindo HW: chassi, fonte de alimentação, CPU, memória, armazenamento interno, placas de rede, adaptadores de host; SW: sistema operacional, virtualização e monitoramento | O/S, virtualização, monitoramento, segurança | Serviços gerenciados de infraestrutura de computação do Windows. | N/A (no nível da torre, incluído no TCO dos serviços de tecnologia) | N/A |
| Unix | Analistas/engenheiros de sistemas que fornecem operações e suporte técnico, planejamento e gestão de processos, administração (incluindo gestão) | Chassi, fonte de alimentação, CPU, memória, armazenamento interno, placas de rede, adaptadores de host | O/S, virtualização, segurança, gerenciamento e ferramentas | Serviços gerenciados de infraestrutura de computação Unix. | N/A (no nível da torre, incluído no TCO dos serviços de tecnologia) | N/A |
| Midrange | Analistas/engenheiros de sistemas que fornecem operações e suporte técnico, planejamento e gestão de processos, administração (incluindo gestão) | Chassi, fonte de alimentação, CPU, memória, armazenamento interno, placas de rede, adaptadores de host | O/S, virtualização, segurança, gerenciamento e ferramentas | Serviços gerenciados de infraestrutura de computação de médio porte. | N/A (no nível da torre, incluído no TCO dos serviços de tecnologia) | N/A |
| Mainframe | Analistas/engenheiros de sistemas que fornecem operações e suporte técnico, planejamento e gestão de processos, administração (incluindo gestão) | Chassi, fonte de alimentação, CPU, memória, armazenamento interno, placas de rede, adaptadores de host | O/S, virtualização, segurança, gerenciamento e ferramentas | Serviços gerenciados de infraestrutura de computação de mainframe. | N/A (no nível da torre, incluído no TCO dos serviços de tecnologia) | N/A |

**Calcular unidade de medida**

| Subtorre de recursos de TI | Unidade de medida (padrão) | Diretrizes |
| --- | --- | --- |
| Servidores  Unix | Servidores lógicos | Uma imagem de sistema operacional, partição ou servidor virtual hospedado em um servidor físico. As instâncias do sistema operacional podem ser implementadas usando firmware de particionamento (conforme fornecido em grandes servidores Unix da Sun e IBM ) ou por meio de utilitários de terceiros, como VMware ou Microsoft. O termo "VM" (Virtual Machine, máquina virtual) tornou-se linguagem comum para uma "instância de sistema operacional", exceto pelo fato de que uma máquina física sem VMs ainda conta como uma instância de sistema operacional. Não considere o firmware, os sistemas operacionais stub, o host ESX ou o software de virtualização como uma instância de sistema operacional separada. Incluir volumes de recuperação de desastres  Por exemplo, um hipervisor com 50 máquinas virtuais seria contado como 50 instâncias de sistema operacional. Não conte o hipervisor do host físico como uma instância separada do sistema operacional. |
| Mainframe  Midrange | Total de MIPs configurados | MIPS é definido como: Milhões de instruções por segundo. Uma medida da capacidade de processamento de uma CPU de mainframe ou de médio porte. A capacidade prática máxima de processamento de uma partição, levando em conta as sobrecargas de vários processadores e a maneira como o mainframe foi configurado. Os sistemas de médio porte, que são classificados por IBM em CPWs, são convertidos em MIPS. |
