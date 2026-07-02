---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "pt-br"
doc_type: "it-benchmarking"
title: "Rede"
breadcrumb: []
source_path: "it-benchmarking/benchmarking-guides/it-tower-v21-v30/network.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Rede

| Subtorre de recursos de TI | Definições | Exemplos | Custo unitário Unidade de medida (padrão) (consulte [a definição](#unit "(Abre em uma nova guia ou janela)") ) | Unidade de medida de eficiência FTE (consulte [a definição](#fte "(Abre em uma nova guia ou janela)") ) |
| --- | --- | --- | --- | --- |
| LAN/WAN | Rede local física e sem fio que conecta equipamentos nos principais data centers e conecta os usuários finais nas áreas de trabalho dos escritórios às redes mais amplas da empresa.  Equipamentos de rede de longa distância, mão de obra e serviços de suporte que conectam diretamente centros de dados, escritórios e terceiros (exclui serviços de telecomunicações e comunicação). | Roteadores, DNS, DHCP  Switches, pontos de acesso sem fio  Multiplexadores (ex.: WDM, CWDM, DWDM)  Modems  Switches de pacotes  Switches Frame Relay | Usuários | Milhares de dispositivos de dados (LAN, WAN) por FTE de dados |
| Voz | VoIP, Recursos de voz que habilitam ou distribuem serviços de voz por meio de equipamentos locais, incluindo PBX, correio de voz e aparelhos telefônicos (exclui serviços de telecomunicações e comunicação). | Switch de voz (PBX), fone de voz, VoIP S/Ws, correio de voz | Aparelhos telefônicos | Milhares de aparelhos por FTE de voz |
| Transporte | Circuitos de rede de voz e dados e instalações e serviços de acesso associados; inclui redes de dados dedicadas e virtuais, acesso à Internet e circuitos de voz. Uso de voz e dados associado a chamadas telefônicas padrão, serviço de número 800, mobilidade e outros dados em trânsito com base no faturamento de uso. | Circuitos: Linhas alugadas  MPLS/ATM  Anéis SONET  Acesso à Internet  Instalações de transmissão de propriedade e mantidas pelo cliente  Troncos dedicados  Fibra dedicada/propriedade  Gerenciamento de despesas S/W  Ferramentas de gerenciamento  Uso de voz e dados (Internet) | Usuários | Não suportado |

**Composição do pool de custos de rede**

| Subtorre de recursos de TI | Trabalho interno/externo | Hardware | Software | Serviços externos | Instalações e energia | Telecomunicações |
| --- | --- | --- | --- | --- | --- | --- |
| LAN/WAN | Analistas/engenheiros de rede que fornecem operações e suporte técnico, planejamento e gerenciamento de processos, administração (incluindo gerenciamento) | Switches, pontos de acesso sem fio (menos provável nas instalações de DC)  Roteadores, firewalls, DNS, DHCP, gerenciamento de rede. | Gerenciamento de rede, segurança | Serviços gerenciados para infraestrutura de rede. | N/A (no nível da torre, incluído no TCO dos serviços de tecnologia) | N/A |
| Voz | Analistas/engenheiros de telecomunicações que fornecem operações e suporte técnico, planejamento e gestão de processos, administração (incluindo gestão) | PBX, VoIP/IPT Servidores, correio de voz, telefones, suprimentos MAC | Switch de voz, VoIP/IPT software, correio de voz, gerenciamento de rede, chargeback | Serviços gerenciados para rede de PBX de voz. | N/A | N/A |
| Transporte | Analistas/engenheiros de telecomunicações que fornecem operações e suporte técnico, planejamento e gestão de processos, administração (incluindo gestão)  Analistas/engenheiros de sistemas que fornecem operações e suporte técnico | N/A | Software de gerenciamento de despesas de telecomunicações, Ferramentas de gerenciamento | N/A | N/A - rastreado no pool de custos de Telecom | Circuitos: Linhas de acesso, linhas alugadas, instalações de transmissão mantidas e de propriedade do cliente, troncos dedicados, acesso à Internet Fibra dedicada/de propriedade do cliente, anéis SONET, MPLS, uso de ATM: Saída e entrada, uso de voz e dados Entrada 800, saída de longa distância, serviços de roteamento de chamadas, serviços avançados de chamadas, uso da Internet |

**Unidades de medida de rede**

| Subtorre de recursos de TI | Unidade de medida (padrão) | Diretrizes |
| --- | --- | --- |
| LAN/WAN | Usuários | O número de usuários que consomem serviços de TI (incluindo funcionários em tempo integral, prestadores de serviços, consultores, fornecedores) e é usado para calcular o custo de LAN/WAN por usuário. A maioria dos clientes coleta essa contagem reunindo uma contagem de IDs de usuário para logon na rede, mas outras estimativas também são aceitáveis. |
| Voz | Fone de ouvido | Handset é o instrumento de voz de ponto final usado por um usuário para se comunicar com outra parte por meio de uma rede de voz (PSTN ou IP).  Inclui aparelhos telefônicos compatíveis com PBX, Centrex, PBX Hybrid, Centrex Hybrid, VoIP e Soft Phones (o aparelho telefônico é uma combinação de um aplicativo de software em um PC ou estação de trabalho e um fone de ouvido/telefone conectado ao PC ou à estação de trabalho).  A definição de aparelho telefônico não inclui: Máquinas de FAX, secretárias eletrônicas dedicadas, sistemas de correio de voz ou sistemas de resposta interativa de voz (IVR). |
| Transporte | Usuários | O número de usuários que consomem serviços de TI (incluindo funcionários em tempo integral, prestadores de serviços, consultores, fornecedores) e é usado para calcular o custo de comunicação por usuário. A maioria dos clientes coleta essa contagem reunindo uma contagem de IDs de usuário para logon na rede, mas outras estimativas também são aceitáveis. |
