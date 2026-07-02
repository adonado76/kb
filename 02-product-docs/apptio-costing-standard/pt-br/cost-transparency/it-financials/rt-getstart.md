---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Torre de Recursos Introdução"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso financeiro"
  - "Torres de Recursos"
source_path: "cost-transparency/it-financials/rt-getstart.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Torre de Recursos Introdução

Use as Torres de Recursos de TI para analisar os gastos com TI por torres funcionais e subtorres, permitindo uma revisão consistente da distribuição de custos, tendências e alinhamento com o orçamento. O componente **CTF – IT Towers** faz parte do Padrão de Custeio e fornece a estrutura de dados mestre necessária para dar suporte a relatórios e análises em nível de torre.

Antes de utilizar os relatórios IT Towers, instale os componentes necessários e certifique-se de que os dados de custos estão mapeados para a taxonomia IT Resource Towers.

## Instalação de componentes

- **CTF- IT Tower** - O componente **CTF – IT Towers** fornece informações sobre os custos das torres e subtorres de recursos de TI e permite comparar os gastos com o orçamento para análises operacionais e estratégicas. A instalação deste componente cria os **dados mestre das torres de recursos de TI**, necessários para todos os relatórios das torres de TI.

Este componente permite que você:

- Identifique as mudanças mensais e trimestrais nos gastos com a torre de TI
- Identifique torres de TI com variação significativa em relação ao orçamento
- Gerencie os gastos com TI em um nível funcional
- Analise as principais fontes de custo que contribuem para cada torre

**Pré-requisitos:**

- **CTF – Fonte de custo** *(obrigatório)*
- Fornece os dados básicos de custos utilizados para alocar gastos às torres de recursos de TI.
- **CTF – Trabalho** *(Opcional)*
- Permite o mapeamento dos custos de mão de obra para torres e subtorres de recursos de TI.
- **CTF – Fornecedor** *(opcional)*
- Permite mapear os gastos com fornecedores para torres e subtorres de recursos de TI.
- **CTF – Ativos fixos** *(opcional)*
- Permite o mapeamento dos custos dos ativos fixos para torres e subtorres de recursos de TI.

## Fontes comuns de dados

A taxonomia da torre e subtorre de recursos de TI é definida pelo **Modelo Unificado TBM ( Apptio )** ( ATUM ) e é carregada automaticamente com o projeto Padrão de Custeio na **Lista de Recursos** das Torres de Recursos de TI.

Nem todos os custos são automaticamente alocados às torres por meio de outros componentes. Para garantir relatórios precisos sobre as torres, as organizações normalmente:

- Mapeie os centros de custo para torres e subtorres de recursos de TI
- Defina porcentagens de alocação quando um centro de custos estiver mapeado para várias torres
- Defina uma lógica de alocação separada para dados reais e orçamentários

Apptio As automações podem ajudar a simplificar e acelerar o processo de mapeamento. Entre em contato com seu gerente de sucesso do cliente para saber mais sobre as opções disponíveis.

**Exemplos de cenários de mapeamento**

Os exemplos a seguir ilustram abordagens comuns para mapear dados de custos para as Torres e Subtorres de Recursos Tecnológicos do TBM:

- Um centro de custos responsável pelas operações do centro de dados pode ser mapeado para Centro de dados → Centro de dados empresarial.
- Funções como engenheiros de rede ou administradores de LAN podem ser mapeadas para Rede → LAN, enquanto administradores de armazenamento podem ser mapeados para Armazenamento → Armazenamento online.
- Os custos dos fornecedores de serviços de segurança gerenciados podem ser mapeados para Segurança → Segurança digital, enquanto os fornecedores de ITSM ou service desk podem ser mapeados para Entrega → Gerenciamento de serviços.

## Conjuntos de dados principais

**Dados Mestres das Torres de Recursos de TI**

Os dados mestre das torres de recursos de TI definem a estrutura utilizada para classificar os custos por torre e subtorre. Esses dados mestres são instalados com o componente **CTF – IT Towers**.

Para apoiar a alocação e a comunicação completas, outros conjuntos de dados devem incluir os seguintes campos, quando aplicável:

- Dados mestre da fonte de custo
  - Centro de Custos
  - Torre de Recursos de TI
  - Subtorre de Recursos de TI
- Dados mestre de mão de obra *(se instalado)*
  - Torre de Recursos de TI
  - Subtorre de Recursos de TI
- Dados mestre de ativos fixos *(se instalado)*
  - Torre de Recursos de TI
  - Subtorre de Recursos de TI
- Dados mestre do fornecedor *(se instalado)*
  - Torre de Recursos de TI
  - Subtorre de Recursos de TI

Se não houver dados suficientes para alocar os custos com precisão, deixe esses custos no objeto Origem do custo, em vez de aplicar alocações incompletas ou incorretas.
