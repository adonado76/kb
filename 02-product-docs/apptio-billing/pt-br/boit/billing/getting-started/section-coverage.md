---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "O que cada seção abrange"
breadcrumb:
  - "Billing"
  - "Como usar este guia"
source_path: "boit/billing/getting-started/section-coverage.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# O que cada seção abrange

Use isto como um mapa rápido do guia:

- [Visão geral e conceitos-chave](intro-billing-what-how.html) - Definições e ideias centrais utilizadas em todo o processo de faturamento.
- [Funções e permissões do usuário](std-custom-role.html "As funções e permissões dos usuários controlam quem pode visualizar e trabalhar com o Benchmarking. Uma função é um conjunto de permissões atribuídas a um usuário, e ninguém pode acessar um produto IBM Apptio sem ter pelo menos uma função em sua conta, que é gerenciada na Administração de Acesso. Na Administração do Access, os administradores autorizados criam e gerenciam registros de usuários, atribuem ou removem funções e controlam quais funções podem acessar cada endpoint do produto, quais endpoints estão abertos para qualquer função elegível e quais endpoints estão totalmente ocultos.") - Quais funções existem, o que elas normalmente fazem e como o acesso é concedido.
- [Edições e recursos](../edition-capabilities/es-intro.html "O faturamento está disponível em duas edições: Billing Essentials e Billing Standard.") - Diferenças entre o Billing Essentials e o Billing Standard, e quando cada um é apropriado.
- [Arquitetura da solução e dependências](../sol-arch-depend/sol-arch-intro.html "Esta seção explica como o faturamento é organizado, como ele se relaciona com o cálculo de custos e o que deve existir antes que o conteúdo do faturamento possa ser usado.") - Como o faturamento é organizado em componentes, como depende do cálculo de custos e onde os pontos finais se encaixam.
- [Ambientes e gerenciamento de lançamentos](../environ-relnmgmt/environments.html "O faturamento utiliza os mesmos ambientes do projeto de cálculo de custos no qual está instalado. As alterações de configuração no faturamento são gerenciadas por meio dos ambientes do projeto de custos: em desenvolvimento, preparação e produção.") - Como as compilações de ambiente afetam a configuração de faturamento e os relatórios.
- [Requisitos e integração de dados](../datareq-integrate/shared-data.html "O faturamento está acima do cálculo de custos. Se os dados que alimentam o Cálculo de Custos e o Faturamento forem fracos, as contas serão fracas. Esta seção explica quais dados o faturamento precisa, como ele é normalmente estruturado e onde a integração geralmente ocorre.") - Conjuntos de dados necessários, tabelas mestras e pontos de integração comuns para que o faturamento funcione
- [Executar o ciclo de faturamento](../run-bill-cycle/anual-plan.html "A maioria das implementações de faturamento segue um ritmo anual para planejamento e taxas, mesmo que ocorram ajustes durante o ano.") - Atividades anuais e mensais para definir taxas, validar cobranças e publicar contas ou diários.
- [Trabalhando com relatórios de faturamento](../work-bill-reports/where-to-find.html "Os relatórios de faturamento são onde a maioria das pessoas vê o resultado do modelo de faturamento. Esta seção enfoca como encontrar esses relatórios, como são os principais grupos de relatórios em cada edição e como eles são normalmente usados.") - Como localizar, interpretar e exportar os principais relatórios utilizados pelas unidades de TI, finanças e negócios.
- [Configurando o Billing Essentials (Implementação)](../config-be/be-overvie.html "Esta seção descreve como o Billing Essentials é configurado em um projeto do Costing Essentials, desde a instalação dos componentes até as primeiras faturas utilizáveis. Presume-se que o Costing Essentials já esteja implantado e estável.") - Etapas de configuração padrão específicas para o Billing Essentials.
- [Configuração do padrão de faturamento (implementação)](../config-bs/bs-overview.html "Esta seção descreve como o Padrão de Faturamento é configurado em um projeto Padrão de Custeio, desde a instalação dos componentes até as primeiras faturas ricas em domínios utilizáveis. Presume-se que o Padrão de Custeio já esteja implantado e estável.") - Etapas de configuração prontas para uso específicas para o padrão de faturamento e seus componentes adicionais.
- [Tópicos avançados](../advance-topic/unit-rate-analysis.html "As taxas unitárias são frequentemente o centro das conversas sobre faturamento. Esta subseção enfoca como analisá-los e ajustá-los ao longo do tempo.") - Preços de transferência, relatórios em nuvem, visualizações de projetos, previsões e otimização de taxas unitárias.
- [Administração e operações](../admin-ops/ao-admin.html "Esta seção fornece padrões concretos para estruturar o faturamento, para que você não precise inventar tudo do zero todas as vezes.") - Monitoramento contínuo, alterações de permissões e manutenção operacional.
- [Padrões de design e casos de uso](../design-uc/uc-simple.html) - Padrões de exemplo para cenários comuns de faturamento e como implementá-los com o Billing.
- [Manual de implementação](../go-live/gl-overview.html) - Listas de verificação e práticas para transferir o faturamento para a produção e estabilizar os primeiros ciclos.
- [Guia de treinamento baseado em funções](../role-based-tg/train-objectives.html "Esta seção descreve como treinar diferentes públicos para que o Billing seja realmente usado e confiável, e não apenas implantado tecnicamente. Use-o para planejar integrações, treinamentos recorrentes e transferências quando as pessoas mudarem de função.") - Como diferentes funções podem desenvolver capacidades com o Billing e em quais seções se concentrar.
- [Glossário e siglas](key-concepts-terms.html "Este apêndice define termos e siglas comuns usados em toda a Ajuda de Faturamento. Use-o como referência rápida ao ler outras seções ou ao trabalhar com o produto.") - O que cada componente acrescenta (conjuntos de dados, relatórios, métricas e dependências principais), definições para terminologia de faturamento e custos e abreviações comuns.
- [Solução de problemas e perguntas frequentes](../troubleshooting/troubleshoot.html "Este apêndice é um guia prático sobre “o que deu errado e o que verificar primeiro”. Use-o quando os números parecerem errados, os relatórios estiverem vazios ou os diários não estiverem reconciliados.") - Perguntas comuns, sintomas típicos e onde procurar mais informações no guia
