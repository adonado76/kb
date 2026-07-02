---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "pt-br"
doc_type: "it-benchmarking"
title: "Rede"
breadcrumb: []
source_path: "it-benchmarking/benchmarking-guides/it-tower/network.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Rede

| Subtorre de recursos de TI | Definições | Exemplos | Unidade de medida (padrão) |
| --- | --- | --- | --- |
| LAN (rede de área local) | Rede local física e sem fio que conecta equipamentos nos principais data centers e conecta os usuários finais nas áreas de trabalho dos escritórios às redes mais amplas da empresa. | - Roteadores, DNS, DHCP - Switches, pontos de acesso sem fio | Portas |
| WAN (rede de área ampla) | Equipamentos de rede de longa distância, mão de obra e serviços de suporte que conectam diretamente centros de dados, escritórios e terceiros (exclui serviços de telecomunicações e comunicação). | - Roteadores WAN - Multiplexadores (ex.: WDM, CWDM, DWDM) - Modems - Switches de pacotes - Switches Frame Relay | Dispositivos |
| Voz | VoIP, Recursos de voz que permitem ou distribuem serviços de voz por meio de equipamentos locais, incluindo PBX, correio de voz e aparelhos telefônicos (exclui serviços de telecomunicações e comunicação). | - Comutador de voz (PBX) - Fone de voz - VoIP S/Ws - Correio de voz | Aparelhos telefônicos |

**Composição do pool de custos de rede**

| Subtorre de recursos de TI | Trabalho interno/externo | Hardware | Software | Serviços externos | Instalações e energia | Telecomunicações |
| --- | --- | --- | --- | --- | --- | --- |
| LAN (rede de área local) | Analistas/engenheiros de rede que fornecem operações e suporte técnico, planejamento e gerenciamento de processos, administração (incluindo gerenciamento) | Switches, pontos de acesso sem fio (menos provável nas instalações de DC) | Gerenciamento de rede, segurança | Serviços gerenciados para infraestrutura de rede. | N/A (no nível da torre, incluído no TCO dos serviços de tecnologia) | N/A |
| WAN (rede de área ampla) | Analistas/engenheiros de rede que fornecem operações e suporte técnico, planejamento e gerenciamento de processos, administração (incluindo gerenciamento) | Roteadores, firewalls, DNS, DHCP, gerenciamento de rede. | Gerenciamento de rede, segurança | Serviços gerenciados para infraestrutura de rede. | N/A (no nível da torre, incluído no TCO dos serviços de tecnologia) | N/A |
| Voz | Analistas/engenheiros de telecomunicações que fornecem operações e suporte técnico, planejamento e gerenciamento de processos, administração (incluindo gerenciamento) | PBX, VoIP/IPT Servidores, correio de voz, telefones, suprimentos MAC | Switch de voz, VoIP/IPT software, correio de voz, gerenciamento de rede, chargeback | Serviços gerenciados para rede de PBX de voz. | N/A | N/A |

**Unidade de medida da rede**

| Subtorre de recursos de TI | Unidade de medida (padrão) | Diretrizes |
| --- | --- | --- |
| WAN | Dispositivos conectados ao usuário final | Eles são coletados separadamente por tipo de dispositivo em cada guia e são um campo calculado na Peer Selection Survey. A definição de alto nível está incluída aqui, e as definições detalhadas estão incluídas para cada tipo de dispositivo. Um dispositivo de usuário final é um dispositivo usado por um usuário. O objetivo principal de uma WAN é conectar os dispositivos dos usuários finais entre si e aos recursos centrais, como servidores e armazenamento. O número de dispositivos de usuário final (EUDs) inclui:   - Todos os PCs, terminais, thin clients, PDAs, smartphones e tablets que podem ser conectados à LAN; - Todas as impressoras conectadas à rede; - Pontos de acesso sem fio (conte cada um como um dispositivo de usuário final); - O número máximo de portas de acesso remoto simultâneas; - Outros dispositivos periféricos do usuário ou do cliente, como caixas eletrônicos, terminais POS e assim por diante.   Quando um roteador é operado pela TI em um local de terceiros, o número de EUDs para esse roteador é 1. Um exemplo típico é quando um banco instala um de seus roteadores nas instalações de uma câmara de compensação para garantir comunicações seguras.  Não inclua os seguintes itens na contagem de dispositivos de usuário final:   - Servidores - os volumes dos servidores conectados à WAN são coletados separadamente na Compute Tower - Roteadores e switches (geralmente não estão nas mãos dos usuários).   Um ponto de acesso sem fio (WAP) é um dispositivo que permite que dispositivos sem fio se conectem a uma rede com fio usando Wi-Fi ou padrões relacionados em conformidade com o IEEE 802.11. O WAP geralmente se conecta a um roteador (por meio de uma rede com fio) e pode retransmitir dados entre os dispositivos sem fio (como computadores ou impressoras) e os dispositivos com fio na rede.  As portas de acesso remoto simultâneo referem-se ao número de conexões remotas simultâneas), com suporte a VPN ou acesso semelhante |
| LAN | Portas LAN ativas | Uma porta ativa é uma porta em um switch ou roteador que foi ativada e/ou habilitada para que um dispositivo possa usá-la. Uma porta pode estar ativa mesmo que não esteja em uso no momento. Por exemplo, para organizações que usam hot-desking (ou hotelling), as portas LAN são consideradas ativas mesmo que um usuário não esteja sentado no momento na hot-desk (ou mesa de hotel). Um switch de rede ou "blade" (placa) em um chassi de switch não é considerado ativo se for necessária uma atividade MAC rígida ou flexível (por exemplo, ligar o switch), aplicar patches físicos ao switch ou aplicar políticas ( QoS ou VLAN) à rede para sua operação. |
| Voz | Fone de ouvido | Handset é o instrumento de voz de ponto final usado por um usuário para se comunicar com outra parte por meio de uma rede de voz (PSTN ou IP).  Inclui aparelhos telefônicos compatíveis com PBX, Centrex, PBX Hybrid, Centrex Hybrid, VoIP e Soft Phones (o aparelho telefônico é uma combinação de um aplicativo de software em um PC ou estação de trabalho e um fone de ouvido/telefone conectado ao PC ou à estação de trabalho).  A definição de aparelho telefônico não inclui: Máquinas de FAX, secretárias eletrônicas dedicadas, sistemas de correio de voz ou sistemas de resposta interativa de voz (IVR). |
