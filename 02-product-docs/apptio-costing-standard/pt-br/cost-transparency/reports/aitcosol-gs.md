---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Introdução ao TCO da IA"
breadcrumb:
  - "Costing Standard"
  - "Outras soluções"
  - "Custo total de propriedade da IA"
source_path: "cost-transparency/reports/aitcosol-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Introdução ao TCO da IA

A solução AI TCO & Usage permite que as organizações obtenham uma visibilidade clara e justificável do custo total de propriedade e uso da IA em modelos, soluções e unidades de negócios. Ele foi projetado para apoiar a adoção responsável da IA, combinando dados financeiros, operacionais e de uso em uma única estrutura analítica. Antes da implementação, as organizações devem avaliar se devem implantar essa solução em um projeto existente ou criar um projeto dedicado especificamente para TCO e uso de IA, dependendo das necessidades de governança, separação de dados e relatórios.

## Instalação de componentes

A solução AI TCO & Usage é introduzida por meio de quatro componentes, instalados em uma sequência priorizada. Dois componentes foram criados especificamente para o TCO e uso da IA, e dois são componentes existentes que devem ser atualizados (ou alterações nos dados mestres devem ser adicionadas) para habilitar a funcionalidade específica da IA.

**Custo total de propriedade e uso da IA**

O componente **AI TCO & Usage** deve ser instalado primeiro, pois ele estabelece os conjuntos de dados mestres, modelos, métricas e bancadas de trabalho específicos de IA necessários para calcular os resultados de custo e uso da IA.

**Relatórios de TCO e uso de IA**

Instale o componente **Relatórios de TCO e uso de IA**, que fornece a coleta de relatórios de IA, incluindo o relatório principal de TCO e uso de IA e o relatório do modelo de custo de IA usado para rastreabilidade de alocação.

Observação: esses componentes estão disponíveis com os modelos v120 ou superior

**Relatórios de TCO e uso de IA no NX (componente adicional)**

Oferece relatórios NX predefinidos com base em dados de custo e uso de IA para análise por serviço, carga de trabalho e período.

Use este componente quando:

- Você precisa de relatórios padrão sobre custos e uso de IA
- Você deseja analisar as tendências de custos e uso
- Você precisa de relatórios consistentes sobre IA

## Pré-requisito

**CTF – Fonte de custos**

Se este componente já estiver instalado, ele deve ser atualizado (os campos são adicionados automaticamente na atualização) ou configurado para suportar melhorias específicas de IA. Isso inclui adicionar os campos **Porcentagem de custo de IA** e **Valor de IA** aos Dados mestres da fonte de custo, permitindo a atribuição precisa dos custos de IA e a visibilidade dos gastos com IA como uma porcentagem do gasto total com TI.

**Aplicativos de TC – Serviços**

Da mesma forma, se este componente já estiver instalado, ele deve ser atualizado (os campos são adicionados automaticamente na atualização) ou configurado para suportar melhorias específicas de IA. Isso inclui **adicionar classificação de solução de IA, tipo de solução de IA e contagem de usuários de IA**, o que amplia os Serviços de Negócios com atributos específicos de IA. Esses campos são essenciais, pois os relatórios de IA são gerados a partir dos Serviços Comerciais marcados como Soluções de IA.

## Fontes comuns de dados

Os dados de TCO e uso de IA são normalmente obtidos a partir de uma combinação de plataformas de faturamento em nuvem, provedores de serviços de IA e sistemas internos da empresa. Os provedores de nuvem fornecem os custos de infraestrutura e plataforma de IA, incluindo computação, armazenamento e serviços gerenciados de IA. Os fornecedores de modelos e plataformas de IA contribuem com métricas de uso, como consumo de tokens, solicitações de inferência, licenças e taxas de assinatura. Os sistemas de mão de obra e fornecedores fornecem os custos com pessoal e serviços externos associados ao desenvolvimento, operações e governança da IA. Metadados de serviços empresariais e hierarquias organizacionais são usados para associar soluções de IA a aplicativos, serviços e unidades de negócios consumidoras, permitindo uma análise completa dos custos e do uso da IA.

**Conjuntos de dados**

A solução introduz conjuntos de dados mestres específicos para IA por meio do componente TCO e uso de IA e amplia os dados mestres existentes de fonte de custo e serviços comerciais para oferecer suporte à atribuição de custos de IA, rastreamento de uso e análise em nível de solução. A configuração depende do preenchimento das porcentagens de custo de IA, dos atributos da solução de IA e dos campos relacionados ao uso para permitir uma modelagem e relatórios precisos.

**Para obter mais detalhes sobre como configurar, acesse** [aqui.](ai-tco-configguide.html)
