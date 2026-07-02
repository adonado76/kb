---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Estrutura da conta por fornecedor"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Noções básicas sobre gerenciamento de compromissos no Cloudability"
source_path: "product/commitments_vendor_account_structure.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Estrutura da conta por fornecedor

## Propósito

O objetivo deste documento é levar a hierarquia de contas na nuvem para o nível prático. É fundamental entender como a estrutura da conta afeta o compartilhamento de compromissos, a visibilidade e os relatórios em Cloudability Commitments. Se ainda não o fez, revise as definições formais de conta em [Como o gerenciamento de compromissos difere entre os provedores de serviços de nuvem](commitment_management_across_providers.html).

## Por que a estrutura da conta é importante para os compromissos

Os benefícios do compromisso fluem de acordo com os escopos específicos do provedor (organização, perfil de faturamento, projeto, região/AZ). Cloudability mapeia essas hierarquias para:

- Calcule os KPIs corretamente nos diferentes níveis de relevância.
- Recomendar compras no limite de compartilhamento correto com base nas preferências.
- Fornecer aos nossos usuários a capacidade de credenciar adequadamente suas contas para obter sistematicamente os dados apropriados necessários.

A falha em credenciar e configurar preferências adequadamente pode resultar em suposições e recomendações incorretas que podem levar a relatórios incorretos ou, pior ainda, a uma compra errônea. Além disso, as APIs públicas raramente fornecem preferências de compartilhamento de forma sistemática. Isso requer uma entrada manual para garantir que o portfólio e as recomendações estejam alinhados com a forma como os descontos são realmente aplicados.

## Como o Cloudability mapeia as hierarquias de sua conta

Cloudability ingere os metadados do provedor e os normaliza para algumas ideias centrais usadas em todo o aplicativo.

**Conta do pagador** - O proprietário da fatura e o local comum onde os compromissos são geralmente cobrados formalmente. Observe que, muitas vezes, o compromisso pode ser adquirido no nível do pagador ou da conta vinculada. Se o compartilhamento estiver ativado, o compromisso será normalmente compartilhado entre contas vinculadas no pagador.

**Conta vinculada -** onde os recursos são executados e o uso ocorre.

No produto, nosso objetivo é fornecer uma seleção de conta hierárquica e múltipla em todas as páginas. Embora, no momento em que escrevemos este artigo, ainda não tenhamos oferecido suporte total a essa funcionalidade, nossos planos são cumprir esse compromisso. Por enquanto, o endereço das páginas é o seguinte:

**Commitment Manager** - Agrega dados em contas de fornecedores. Permite a seleção múltipla. Para os dados reais (históricos) e previstos (futuros), a seleção de conta funciona como um seletor de uso.

**Portfólio de compromissos** - Mostra resumos por tipo e detalhes por conta/assinatura/projeto.

**Recomendações de comprometimento** - Respeita sua intenção de compartilhamento (em toda a organização ou com escopo) e os filtros da conta.

## AWS

*Estrutura da conta*

**Conta de gerenciamento (pagador)** - Recebe a fatura consolidada; geralmente é a conta de compras para RIs/Planos de Poupança.

**Contas de membros (vinculadas)** - Onde os recursos são executados e os custos são gerados.

**Unidades organizacionais (OUs)** - "Pastas" hierárquicas para política e governança (não contêineres de faturamento). Não é de interesse particular para compromissos.

*Comportamento de compartilhamento*

O compartilhamento de compromisso é uma configuração no nível da organização. Quando ativado, os descontos podem ser aplicados automaticamente às contas dos membros, independentemente do posicionamento da UO.

O compartilhamento de região é relevante para os compromissos em que as cargas de trabalho são implantadas e o compromisso é adquirido na região ou na zona de disponibilidade

## Azure

*Estrutura da conta*

**Conta de faturamento** (EA/MCA) - Construção de contrato de nível superior.

**Perfil de faturamento** (MCA) - Proprietário da fatura; geralmente seu limite de compartilhamento principal.

**Seção de faturas** (MCA) - Compartimentos de subfaturas usados para alocações/resultados.

**Assinatura** - Contêiner de recursos e unidade de cobrança.

*Comportamento de compartilhamento*

O escopo compartilhado aplica benefícios em um contexto de faturamento (por exemplo, inscrição no EA ou perfil de faturamento MCA / seção de fatura)

Single Subscription ou Single Resource Group limita os benefícios a esse escopo

## GCP

*Estrutura da conta*

**Conta de faturamento** - Onde os compromissos e créditos são gerenciados; proprietário da fatura.

**Projeto** - contêiner de recursos onde as cargas de trabalho são executadas e os custos são gerados.

*Comportamento de compartilhamento*

O compartilhamento deve estar ativado no console do GCP. Ele é gerenciado no nível da conta de cobrança.

A região é relevante para os CUDs de recursos do GCE e alguns CUDs de gastos, como os CUDs do Cloud SQL.

## Dicas

1. Credencie primeiro as contas de pagadores corretas, confirme as contas vinculadas e analise todas as permissões especiais por serviço.
2. Defina suas configurações de compartilhamento de conta por pagador nas preferências de compromisso para garantir que as configurações de compartilhamento corretas sejam usadas como padrão nas recomendações.
3. Verifique se o compartilhamento está ativado no nível do pagador antes de confiar na cobertura de toda a organização no portfólio.
4. Confirme as configurações de compartilhamento e defina-as nas preferências de compromisso.
5. Verifique periodicamente essas configurações.

## Conclusões

A estrutura da conta é fundamental para o funcionamento adequado do site Cloudability Commitments. Verifique se as contas estão credenciadas corretamente e se as preferências de compartilhamento estão definidas de forma que a funcionalidade de compromisso funcione corretamente.

**Tópico dos pais:** [Entendendo os fundamentos do gerenciamento de compromissos em Cloudability](../product/commitment_management_basics.html)
