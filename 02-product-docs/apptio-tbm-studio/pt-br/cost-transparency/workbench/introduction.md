---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Workbench de cálculo de custos padrão"
breadcrumb: []
source_path: "cost-transparency/workbench/introduction.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Workbench de cálculo de custos padrão

Apptio oferece a capacidade de realizar uma variedade de atualizações de dados de referência e transacionais que são comuns na maioria das organizações e proporcionam maior valor e visibilidade da solução. Em muitos casos, os dados do sistema de origem podem não conter todas as informações necessárias para conduzir as alocações e os relatórios em sua solução Costing Standard .

O Workbench na solução Costing Standard oferece uma interface intuitiva, capacitando os usuários designados a enriquecer e manter seus dados de forma eficaz. Ele apresenta tabelas editáveis, permitindo que os usuários resolvam as lacunas de dados e refinem os mapeamentos de alocação.

O acesso ao Workbench é regido pelas permissões da sua organização, e nem todos os usuários podem ter o acesso necessário.

## Mapeamento detalhado de relatórios

Cada relatório de mapeamento específico, como o Vendor Mapping (Mapeamento de fornecedores) ou o Labor Mapping (Mapeamento de mão de obra), é estruturado em duas guias principais:

**Enriquecimento de dados**

Esta seção permite que os usuários atualizem informações ou insiram informações ausentes. Por exemplo, no Mapeamento de mão de obra, os usuários podem editar campos como Equipe, Função e Tipo de funcionário para cada ID de mão de obra. No entanto, não é permitido adicionar novas linhas nas tabelas de enriquecimento de dados e as informações ausentes devem vir do sistema de origem (por exemplo, sistema de registro de RH).

**Mapeamento de dados**

Essa seção permite que os usuários aloquem ou distribuam os custos para uma ou mais soluções, produtos ou unidades de negócios. Por exemplo, no Vendor Mapping, um usuário pode alocar o custo de um fornecedor, como o de SAP, a várias ofertas, como SAP Financial Accounting e SAP Production Planning. Isso é feito usando a coluna Weighting (Ponderação).

Exemplo:

1. Distribuir 60% do custo do fornecedor de SAP para SAP Contabilidade financeira e 40% para SAP Planejamento de produção
2. Clique com o botão direito do mouse na linha SAP Vendor e selecione 'Duplicate Row'.
3. Digite o tipo de solução, a categoria da solução e as IDs da oferta para ambas as linhas. Os nomes das ofertas devem ser preenchidos automaticamente.
4. Insira ' 0.6 ' na coluna Weighting para a oferta SAP Financial Accounting e ' 0.4 ' para a oferta SAP Production Planning.
