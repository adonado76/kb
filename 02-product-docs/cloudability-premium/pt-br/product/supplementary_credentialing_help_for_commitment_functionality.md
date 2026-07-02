---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Ajuda complementar para credenciamento para a funcionalidade de compromisso"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Configurar a funcionalidade de otimização"
source_path: "product/supplementary_credentialing_help_for_commitment_functionality.html"
images:
  - "images/details.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Ajuda complementar para credenciamento para a funcionalidade de compromisso

Observação: Observação: A funcionalidade de gerenciamento de compromissos oferece suporte apenas a visualizações baseadas em fornecedores e contas. Ao selecionar uma visualização cuja lógica se baseia em mapeamentos comerciais e tags além do fornecedor e da conta, a página apresentará um erro. Esse comportamento se deve aos seguintes motivos: - As métricas de desempenho muitas vezes não podem ser calculadas de forma determinística em várias métricas e tags de negócios. Se mostrássemos essas telas sem esses dados, a página do portfólio ficaria sem a maioria dos dados de interesse. - É recomendável que os compromissos sejam gerenciados centralmente. Quando o compartilhamento está ativado ou quando o tipo de compromisso é sempre apenas no nível da conta do pagador, torna-se impossível determinar o desempenho em mapeamentos/tags comerciais de nível inferior em troca de uma melhor situação para a organização. - Os mapeamentos de tags e comerciais contêm regras que restringem o usuário a apenas uma parte da conta. Para proteger a privacidade dos clientes, só permitimos que usuários com permissões apropriadas visualizem as páginas de compromissos, uma vez que os compromissos dizem respeito a contas inteiras. Esta é uma limitação dos dados e da forma como interagem com a filtragem de visualizações.

Nota:

Você deve ter direitos de administrador no Cloudability para visualizar ou habilitar credenciais. Se você não tiver direitos de administrador, entre em contato com o administrador principal do Cloudability da sua organização para obter ajuda.

## Gestão do compromisso de credenciamento para AWS

**Gerar recomendações para AWS EC2**

O conjunto de produtos do Cloudability permite otimizar o uso das Instâncias Reservadas Conversíveis (CRIs) do AWS EC2, incluindo monitoramento de custos, geração de relatórios e recomendações, entre as quais recomendações para a troca de CRIs. As informações a seguir são sobre como habilitar e utilizar recomendações de troca de instâncias reservadas conversíveis.

**Verifique as permissões**

Antes de começar, certifique-se de que a permissão apropriada **ec2:GetReservedInstancesExchangeQuote** está ativada. Esta permissão é necessária para que Cloudability gere recomendações de troca conversíveis para CRIs parciais ou totais antecipadas.

Para verificar o status da permissão necessária:

1. Navegue até **Configurações > Credenciais do fornecedor**.
2. Na guia **AWS**, selecione ![ícone de detalhes da imagem](../../../../03-media/cloudability-premium/images/details.jpg) para visualizar as permissões de quaisquer contas relevantes.

   As contas que não têm as permissões necessárias ativadas são identificadas por qualquer coisa que não seja uma marca de seleção verde ao lado do item de linha “ **ec2:GetReservedInstancesExchangeQuote** ”.

   Se a permissão necessária não estiver habilitada, você pode habilitá-la gerando novamente um modelo do CloudFormation e aplicando-o às contas correspondentes. Para obter mais informações, consulte [Cloudability Gerenciar credenciais d AWS](../admin/manage-aws-credentials.html).

   Observação: após a aplicação do modelo CloudFormation e sua verificação pela plataforma Cloudability, levará aproximadamente 1 hora para que as recomendações apareçam.

Visualizando o inventário do plano de poupança próprio

Introdução

Antes de começar, certifique-se de que as permissões necessárias foram ativadas, o que fornece acesso à funcionalidade do Plano de Poupança.

A credenciação deve ser visualizada e realizada por um usuário com direitos de administrador para sua conta Cloudability. Se você não tiver acesso de administrador ou não tiver certeza se possui direitos de administrador, verifique com o administrador principal do Cloudability da sua organização.

Para verificar o status das credenciais necessárias:

1. Navegue até Configurações > Credenciais do fornecedor.

   Na visualização das contas principais das guias “ AWS ” (Contas vinculadas) e “ Azure ” (Contas de poupança), qualquer pagador principal ou conta vinculada que possua poupança (ou que você pretenda usar para comprar poupança) tem uma caixa verde com um indicador de status branco marcado em “Advanced Features” (Recursos avançados).
2. Para uma conta com qualquer indicador de status que não seja a caixa verde com uma marca de seleção branca, selecione ![ícone de status](../../../../03-media/cloudability-premium/images/details.jpg) para verificar as credenciais individuais. x
3. Na janela Detalhes da credencial, se a permissão de poupança plans:DescribeSavingsPlans na guia Reservas mostrar um x vermelho, ela precisa ser atualizada (regerando e aplicando modelos de CloudFormation ) antes que você possa ver um inventário dos seus Planos de Poupança.

## Gestão do compromisso de credenciamento para Azure

**Valide o acesso à sua conta**

As recomendações de compromisso geram recomendações de compromisso baseadas nos recursos d Azure, acessando a API em nuvem d Azure. Como o Azure Cloud limita o acesso à API para contas empresariais, você deve garantir que:

- Sua conta está coberta por um Contrato Empresarial
- Você tem acesso ao Portal Empresarial Azure

Se você não possui uma conta empresarial, acesso ao Portal Empresarial Azure ou se não tiver certeza, entre em contato com o representante da sua conta Azure para obter ajuda.

**Habilite suas credenciais do Azure**

1. Para verificar o status das suas credenciais do Azure, acesse **Configurações > Credenciais do fornecedor**.
2. Selecione a guia **AZURE**.
3. Certifique-se de que **os relatórios de faturamento** e **os recursos avançados** estejam habilitados para a conta principal (de inscrição). Você deverá ver duas caixas de seleção verdes na linha da conta principal.

Nota:

- Embora seja melhor ter **os Relatórios de Faturamento** e **os Recursos Avançados** ativados tanto para contas principais (inscrição) quanto para contas vinculadas (assinatura), você só precisa ativar essas permissões para a conta principal para usar as Recomendações de Compromisso para Azure.

- Embora seja melhor ter **os Relatórios de Faturamento** e **os Recursos Avançados** ativados tanto para contas principais (inscrição) quanto para contas vinculadas (assinatura), você só precisa ativar essas permissões para a conta principal para usar as Recomendações de Compromisso para Azure.

**Tópico pai:** [Configurar a funcionalidade de otimização](../product/configure_optimization_functionality.html)
