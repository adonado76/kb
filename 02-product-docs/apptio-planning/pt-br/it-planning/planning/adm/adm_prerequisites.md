---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Configurar automatizado Data Management"
breadcrumb: []
source_path: "it-planning/planning/adm/adm_prerequisites.html"
images:
  - "resources/images/it_planning_images/adm-auto-connection.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Configurar automatizado Data Management

A seguir estão os pré-requisitos para ativar o Data Management automatizado em um Costing & Planning - Plan.

## Instale os componentes do Cost Transparency Integration para compartilhamento de dados de referência e reais

Essa etapa é necessária somente se você não tiver configurado a integração Costing Standard . Siga este procedimento somente se for a primeira vez que estiver configurando a integração com Costing Standard.

1. Em Costing Standard, instale o componente Apptio ITPF Integration. Consulte [Instalar os componentes de integração do ITPF](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=install-itpf-integration-components "(Abre em uma nova guia ou janela)") para obter mais informações.

   Essa etapa instala automaticamente todos os modelos de conjuntos de dados de referência necessários para integrar os produtos.
2. Se você usar Assets and Vendor, precisará instalar também os componentes Apptio ITPF Asset e Apptio ITPF Vendor. Para obter mais informações, consulte [Instalar os componentes](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=install-itpf-integration-components "(Abre em uma nova guia ou janela)").

## Instalar os componentes de integração do Costing Standard para o Plan Automated Data Management

1. Em Costing Standard, instale o componente ApptioOne Plan Integration.

   Essa etapa instala automaticamente todos os modelos de conjuntos de dados do Plano necessários para importar os dados do plano de Costing para Costing & Planning - Plan.

## Configurar a conexão com a instância Costing Standard no modo automatizado Data Management

Para configurar o Automated Data Management manualmente, navegue até [Connections (Conexões](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=administration-connections "(Abre em uma nova guia ou janela)") ).

Para definir automaticamente as configurações de conexão do Automated Data Management, certifique-se de que a **opção Enable Automated Data Management Integration (Ativar integração do Automated** ) esteja selecionada na página [Edit the Company Profile (Editar o perfil da empresa](../edit-company-profile.html "O Company Profile permite que os usuários Admin e Budget Process Owner definam as configurações de todo o aplicativo que personalizam a exibição, ativam ou desativam recursos e definem o comportamento do fluxo de trabalho em Apptio Planning.") ).

![imagem](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/adm-auto-connection.jpg)

**Tópico principal:** [Conectar-se a Apptio Costing](../../../it-planning/planning/adm/adm_capabilities.html)
