---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Preferências de planejamento de carga de trabalho"
breadcrumb:
  - "Cloudability Premium"
  - "Planejar"
  - "Planejamento da carga de trabalho"
source_path: "product/workload-planning-preferences.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Preferências de planejamento de carga de trabalho

As preferências de planejamento de carga de trabalho permitem que as equipes do FinOps definam e restrinjam de forma centralizada as opções no Workload Planning. Qualquer atualização é opcional e não é necessária para usar o Workload Planning.

Por padrão, essas preferências são visíveis apenas para o administrador do Workload Planning, que pode modificá-las. “WorkloadPlanningPreferencesViewOnly” pode ser atribuída a uma função personalizada para permitir que usuários não administradores visualizem as Preferências de planejamento de carga de trabalho sem direitos de edição.

Instruções 

1. Navegue até Configurações > Trabalho. Preferências de planejamento.
2. Para cada provedor de serviços, ajuste os parâmetros com base nas preferências e políticas de sua organização e clique em Save (Salvar ). Qualquer alteração entrará em vigor imediatamente.

Detalhes da preferência

| Campo | Descrição |
| --- | --- |
| Permitir que o provedor de serviços | Ele restringe a visibilidade de um provedor de serviços específico quando os usuários criam uma carga de trabalho. Se uma carga de trabalho existente utilizar um provedor de serviços que tenha sido desativado pelos administradores, ela será bloqueada e os usuários não poderão editá-la. |
| Tipo de locação preferido | Para AWS, Azure e GCP, os administradores podem optar por exibir os “Preços Comprometidos” e os “Preços Spot” no Planejamento de Carga de Trabalho do Cloudability.  "Preço comprometido" refere-se ao preço associado a possíveis Planos de economia, Reservas ou Compromissos, dependendo da oferta do provedor de serviços e da seleção do usuário.  Para a OCI, os usuários podem optar por exibir o "Capacity Reservation Pricing" (preço de reserva de capacidade), que oferece um desconto adicional de 15% em comparação com o On-Demand e é perdido após a utilização. Eles também podem decidir exibir o "Spot Pricing". |
| Opções padrão de compromisso | Essas preferências afetarão o “Preço Comprometido” ( AWS ), Azure e GCP, quando exibidas no Planejamento de Carga de Trabalho ( Cloudability Workload Planning). Os administradores têm autoridade para desativar a seleção de opções na interface do usuário. |
| Desconto /Aumento | Para cada provedor de serviços, os administradores podem adicionar um desconto adicional ou uma % de aumento. Essa porcentagem será aplicada a todos os preços calculados pelo site Cloudability Workload Planning para um determinado provedor. Não se aplica a "Outros" custos adicionados a uma carga de trabalho. Qualquer alteração se aplicaria às cargas de trabalho novas e existentes. |
| Excluir recomendações nas quais o tipo de instância recomendado contenha os seguintes valores. | Ao usar essa opção, você pode especificar os tipos de recursos que não devem aparecer nas recomendações do Planejamento de Carga de Trabalho para a sua organização. Isso pode ser feito usando qualquer uma dessas duas opções:  - adicionando a palavra-chave para que as recomendações ignorassem os tipos de recursos que contêm essa palavra-chave. Por exemplo: definir o valor “xlarge” excluiria todos os recursos que contivessem “xlarge” em seus nomes. - adicionando um asterisco (\*) junto com a palavra-chave, para que as recomendações ignorem os tipos de recursos que começam com essa palavra-chave. Por exemplo: ao definir o valor “ t4\* ”, seriam excluídos todos os recursos que começam com “ t4 ”. |
