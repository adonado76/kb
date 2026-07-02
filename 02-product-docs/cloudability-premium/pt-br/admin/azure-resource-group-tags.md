---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Azure Tags"
breadcrumb:
  - "Cloudability Premium"
  - "Obtendo dados em Cloudability"
  - "Conectar Microsoft Azure"
source_path: "admin/azure-resource-group-tags.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Azure Tags

Cloudability suporta os tipos de tags mencionados abaixo para Azure

- **Tags de nível de recurso**
  - - Eles fazem parte dos arquivos de exportação do Azure e não são necessárias permissões adicionais no Cloudability para habilitá-los
      - Formato das tags - cldy:Azure:ResourceTag:<resource tag key>
- **Tags de grupos de recursos**
  - Para obter tags de grupos de recursos de Azure, Cloudability precisa de permissões adicionais
    - gerenciamento: Leitor ou Microsoft.Resources/subscriptions/resourceGroups/read nas assinaturas
      - Formato das tags - cldy:Azure:ResourceGroupTag:<resource group tag key>
- **Tags de nível de assinatura**
  - Para obter tags de nível de assinatura de Azure, Cloudability precisa de uma permissão adicional
    - subscription:ReadSubscription
      - Formato das tags - cldy:Azure:SubscriptionLevelTag:<subscription tag key>

Tarefa : permitir o acesso às informações de tag do grupo de recursos para apoiar as atividades de alocação de custos.

O uso de [tags de grupos de recursos do Azure](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/tag-resources "(Abre em uma nova guia ou janela)") tornou-se um mecanismo popular de alocação primária com um grande número de usuários do Azure. Ele supera os problemas duplos de baixa cobertura de tags e o fato de que o site Azure não reporta informações de tags para todos os tipos de recursos. As tags de grupos de recursos não aparecem nativamente nas informações detalhadas de faturamento e, portanto, é necessário conceder acesso adicional, conforme especificado nesta página.

Cloudability tem um modelo de herança de tag para Azure : se um recurso individual tiver uma tag específica nos dados detalhados de faturamento, usaremos essa tag primeiro para preencher nossa plataforma de análise. Se essa tag não aparecer nos dados de faturamento desse recurso, o site Cloudability consultará o grupo de recursos ao qual ele pertence e extrairá as informações da tag de lá. Se a tag não existir no grupo de recursos, nós a consideraremos como "(não definida)"

Para habilitar a coleta e o processamento de tags de grupos de recursos, siga as etapas [aqui](azure-advanced-rightsizing.html) para configurar as credenciais de suas assinaturas.

**Tópico principal:** [Conectar Microsoft Azure](../admin/azure-cm-setup-premium.html)
