---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Faturamento"
breadcrumb:
  - "Billing"
source_path: "boit/billing/home.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Faturamento

## Notas sobre a liberação

- [Lançamentos recentes](release-notes/whats-new.html "Esta seção descreve apenas as alterações no conteúdo de faturamento pronto para uso, não na plataforma subjacente. Para atualizações no nível da plataforma, como o comportamento do TBM Studio e do servidor cliente, os leitores devem revisar as Notas de lançamento do TBM Studio e considerar as alterações aplicáveis juntamente com o que está documentado aqui.")

## Introdução

- Introdução ao faturamento
  - [Visão geral de faturamento](getting-started/intro-billing-what-how.html)
  - [Edições de faturamento e edições de custos](getting-started/bill-cost-editions.html "O faturamento está disponível em duas edições. Cada edição está associada a um conjunto diferente de componentes e foi concebida para diferentes níveis de complexidade e maturidade.")
  - [Conceitos fundamentais: serviços, unidades, taxas, recuperação, diários](getting-started/core-concepts.html "O restante deste guia baseia-se em um pequeno conjunto de conceitos recorrentes. Compreendê-los aqui reduz a confusão mais tarde.")
  - [Principais benefícios](getting-started/key-benefits.html "Em um nível mais abrangente, o Faturamento auxilia você a:")
- [Glossário e siglas](getting-started/key-concepts-terms.html "Este apêndice define termos e siglas comuns usados em toda a Ajuda de Faturamento. Use-o como referência rápida ao ler outras seções ou ao trabalhar com o produto.")
- Funções e permissões do usuário
  - [Visão geral e funções](getting-started/std-custom-role.html "As funções e permissões dos usuários controlam quem pode visualizar e trabalhar com o Benchmarking. Uma função é um conjunto de permissões atribuídas a um usuário, e ninguém pode acessar um produto IBM Apptio sem ter pelo menos uma função em sua conta, que é gerenciada na Administração de Acesso. Na Administração do Access, os administradores autorizados criam e gerenciam registros de usuários, atribuem ou removem funções e controlam quais funções podem acessar cada endpoint do produto, quais endpoints estão abertos a qualquer função elegível e quais endpoints estão totalmente ocultos.")
  - [Permissões e tipos de acesso para o Padrão de Faturamento](getting-started/perm-access-bs.html)
  - [Padrões de acesso para o Billing Essentials](getting-started/access-patters-be.html)
  - [Padrões de acesso para o padrão de faturamento](getting-started/access-patterns-bs.html "O Padrão de Faturamento introduz um endpoint de Faturamento separado, além do projeto de Custeio. O acesso precisa levar em conta ambos os aspectos.")
  - [Segregação de funções e práticas recomendadas](getting-started/duty-segregation.html "Ao configurar funções e permissões, considere estas práticas:")
  - [Gerenciando o acesso ao longo do tempo](getting-started/manage-access.html "O acesso raramente permanece estático. As pessoas mudam de função, novos serviços são adicionados e novos recursos de faturamento são implementados.")
- [Recursos de suporte](getting-started/support-resources.html)

## Como usar este guia

- [A quem se destina este guia](getting-started/audience.html "Esta seção explica para quem é o guia, como funcionam os avisos de edição, o que cada seção principal abrange e por onde as diferentes pessoas devem começar.")
- [Avisos sobre edição e custos](getting-started/edition-costing-notice-conventions.html "O faturamento sempre depende de um projeto de cálculo de custos, mas este guia mantém a rotulagem simples, concentrando-se nas edições de faturamento:")
- [O que cada seção abrange](getting-started/section-coverage.html "Use isto como um mapa rápido do guia:")
- [Por onde começar pela persona](getting-started/persona.html "Você não precisa ler o guia em ordem. Use as sugestões abaixo para ir para as seções mais relevantes.")
- [Lista de verificação da implementação](getting-started/checklist.html "Para quem está planejando ou alterando uma implementação de faturamento, esta lista de verificação de alto nível reúne todas as informações do guia. As seções seguintes fornecem as etapas detalhadas.")

## Requisitos e integração de dados

- [Bases de dados compartilhadas](datareq-integrate/shared-data.html "O faturamento está acima do cálculo de custos. Se os dados fornecidos ao Cálculo de Custos e Faturamento forem fracos, as contas serão fracas. Esta seção explica quais dados o faturamento precisa, como eles são normalmente estruturados e onde a integração geralmente ocorre.")
- [Requisitos de dados para o Billing Essentials](datareq-integrate/data-be.html)
- [Requisitos de dados para o Padrão de Faturamento](datareq-integrate/data-bs.html "O Padrão de Faturamento utiliza um conjunto mais amplo de componentes e, portanto, um modelo de dados mais abrangente. Ainda precisa dos mesmos fundamentos básicos do Essentials, mas os distribui por vários domínios.")
- [Expectativas em relação à qualidade dos dados](datareq-integrate/data-quality.html "Dados incorretos aparecerão imediatamente nas saídas de faturamento: linhas ausentes, cobranças inexplicáveis ou taxas que parecem erradas.")
- [Calendários e períodos](datareq-integrate/calendar.html "O faturamento precisa de uma noção consistente de períodos:")
- [Moedas e câmbio](datareq-integrate/currency.html "O faturamento pode operar em ambientes com várias moedas, mas geralmente é mais simples se os resultados do faturamento forem apresentados em uma única moeda de apresentação para as partes interessadas do negócio.")
- [Mecanismos de integração e opções que não envolvem o Studio](datareq-integrate/integration.html "Os dados podem chegar ao departamento de faturamento por meio de vários mecanismos. Quais são usados depende de quem gerencia a implementação e quais ferramentas estão disponíveis.")

## Configurando os fundamentos do faturamento (implementação)

- [Âmbito e pré-requisitos](config-be/be-overvie.html "Esta seção descreve como o Billing Essentials é configurado em um projeto do Costing Essentials, desde a instalação dos componentes até as primeiras faturas utilizáveis. Presume-se que o Costing Essentials já esteja implantado e estável.")
- [Instalação dos componentes do Billing Essentials](config-be/install-be.html "O Billing Essentials é fornecido como componentes que são instalados no projeto Costing Essentials existente.")
- [Principais conjuntos de dados e tabelas](config-be/key-datasets.html)
- [Preenchimento do catálogo de ofertas](config-be/populate.html "O catálogo de ofertas determina o que aparece nas contas. Deve ser preenchido e validado antes da primeira execução de faturamento.")
- [Preparação dos dados dos consumidores](config-be/prepare.html "O modelo Billing Essentials precisa de uma visão consistente de quem está sendo cobrado.")
- [Integração de dados de consumo](config-be/integrate.html "Os dados de consumo são o que impulsionam as unidades no cálculo do PxQ.")
- [Configuração e taxas de carregamento](config-be/configure.html "As taxas convertem unidades em encargos monetários.")
- [Executando o cálculo do Billing Essentials](config-be/running.html "Com ofertas, consumidores, consumo e tarifas definidos, o cálculo do Billing Essentials pode ser executado em Desenvolvimento e Preparação.")
- [Promoção para o ambiente de produção e primeira execução de entrada em operação](config-be/prmoting.html "Quando o Billing Essentials funcionar conforme o esperado no ambiente de teste:")
- [Transferência e entrada em operação](config-be/handover.html "Após a primeira execução bem-sucedida da produção:")

## Configurando o padrão de faturamento (implementação)

- [Âmbito e pré-requisitos](config-bs/bs-overview.html "Esta seção descreve como o Padrão de Faturamento é configurado em um projeto Padrão de Custeio, desde a instalação dos componentes até as primeiras faturas ricas em domínios utilizáveis. Presume-se que o Padrão de Custeio já esteja implantado e estável.")
- [Instalação dos componentes do Billing Standard](config-bs/bs-install.html "O Padrão de Faturamento é fornecido como um conjunto de componentes instalados no projeto Padrão de Custeio existente. O endpoint Billing Standard na interface do usuário exibe o conteúdo criado por esses componentes.")
- [Tabelas e relações do domínio principal](config-bs/bs-core.html "A força do Billing Standard vem de seu modelo rico em domínios. No mínimo, espere trabalhar com as seguintes famílias de tabelas:")
- [Configurar serviços e ofertas](config-bs/bs-setup.html "O catálogo do que é faturado é central, independentemente da edição, mas o Padrão de Faturamento frequentemente precisa de uma ligação mais rica com os domínios.")
- [Preenchimento dos dados mestre do domínio](config-bs/bs-pop-domain.html "Os mestres de domínio ativam os relatórios padrão de faturamento que dividem as cobranças por aplicativo, infraestrutura, nuvem, projeto e entidade jurídica.")
- [Alinhamento das definições de custo, consumo e unidade](config-bs/bs-align-cost.html "A norma de faturamento precisa de uma história coerente em relação a custos, unidades e preços.")
- [Configuração da lógica de preços e variações](config-bs/bs-config-price.html "O Padrão de Faturamento pode analisar custos, planos e preços. A configuração determina como isso funciona.")
- [Executando o cálculo do Padrão de Faturamento no ambiente de desenvolvimento/staging](config-bs/run-bill.html "Depois que os mestres de domínio, unidades, preços e mapeamentos estiverem definidos, o cálculo do Padrão de Faturamento poderá ser testado.")
- [Ativação do endpoint do Padrão de Faturamento e do acesso aos relatórios](config-bs/enable-bill.html "Com o conteúdo validado no Staging, o endpoint e os relatórios podem ser preparados para os usuários.")
- [Transição para a produção e primeira execução completa do Padrão de Faturamento](config-bs/promote-bill.html "Após o faturamento, o conteúdo padrão e o comportamento do ponto final são validados no Staging:")
- [Implementação da norma de faturamento](config-bs/operate-bill.html "Após a entrada em operação, o Padrão de Faturamento passa a fazer parte do ciclo de Faturamento recorrente descrito na Seção 9, com responsabilidades de domínio adicionais.")

## Executando o ciclo de faturamento

- [Planejamento anual e definição de tarifas](run-bill-cycle/anual-plan.html "A maioria das implementações de faturamento segue um ritmo anual para planejamento e taxas, mesmo que ocorram ajustes durante o ano.")
- [Processo de faturamento mensal](run-bill-cycle/monthly-bill.html "Cada período de faturamento normalmente segue um conjunto repetível de etapas.")
- [Validação das faturas do período atual](run-bill-cycle/validating.html "A validação é onde a maioria dos problemas de faturamento é detectada antes de chegar aos consumidores.")
- [Geração e distribuição de contas](run-bill-cycle/generating.html "Depois que os resultados do faturamento forem validados, a próxima etapa é gerar visualizações das faturas e distribuí-las.")
- [Exportação e lançamento de diários](run-bill-cycle/exporting.html "Para estornos, os resultados de faturamento geralmente alimentam os sistemas financeiros como diários.")
- [Lista de verificação para a administração de faturamento](run-bill-cycle/admin-checklist.html "Esta lista de verificação resume as tarefas recorrentes para cada período de faturamento. Pode ser adaptado para um manual operacional mais detalhado.")

## Trabalhando com relatórios de faturamento

- [Onde encontrar os relatórios de faturamento](work-bill-reports/where-to-find.html "Os relatórios de faturamento são onde a maioria das pessoas vê o resultado do modelo de faturamento. Esta seção enfoca como encontrar esses relatórios, como são os principais grupos de relatórios em cada edição e como eles são normalmente usados.")
- [Relatórios de faturamento no Billing Essentials](work-bill-reports/billrep-be.html "O Billing Essentials inclui um pequeno conjunto específico de relatórios instalados através do componente “Relatórios de cobrança”:")
- [Relatórios de faturamento no Billing Standard](work-bill-reports/billrep-bs.html "O Padrão de Faturamento inclui visualizações específicas do domínio, faturas e relatórios resumidos. Os relatórios são agrupados em seções exibidas na página inicial do relatório. A menos que seja indicado o contrário, os relatórios são instalados através do componente “ ““BoIT- Foundation”.")
- [Tarefas comuns de relatórios e padrões de uso](work-bill-reports/common-rep-ratasks.html "Independentemente da edição, os usuários tendem a realizar as mesmas ações principais nos relatórios de faturamento. Esta subseção concentra-se em padrões, em vez de controles específicos da interface do usuário.")

## Administração e Operações

- [Visão Geral](admin-ops/ao-admin.html "Esta seção fornece padrões concretos para estruturar o faturamento, para que você não precise inventar tudo do zero todas as vezes.")
- [Demonstração simples do serviço](admin-ops/ao-simple-service.html)
- [Estorno com diários](admin-ops/ao-chargeback-journal.html)
- [Design centrado no catálogo de serviços](admin-ops/ao-service-catalog.html)
- [Design centrado na nuvem](admin-ops/ao-cloud-centric.html)
- [Design centrado no projeto](admin-ops/ao-project-centric.html)
- [Visão da entidade jurídica e dos preços de transferência](admin-ops/ao-legal-entity.html)
- [Combinar padrões sem criar caos](admin-ops/ao-comb-patter.html)
- Edições e recursos
  - [Visão geral e resumo das edições](edition-capabilities/es-intro.html "O faturamento está disponível em duas edições: Billing Essentials e Billing Standard.")
  - [Projetar tendo a edição em mente](edition-capabilities/es-design.html "Ao trabalhar com o Billing Essentials:")
- Arquitetura da solução e dependências
  - [Relação entre faturamento e cálculo de custos](sol-arch-depend/sol-arch-intro.html "Esta seção explica como o faturamento é organizado, como ele se relaciona com o cálculo de custos e o que deve existir antes que o conteúdo do faturamento possa ser usado.")
  - [Arquitetura do Billing Essentials](sol-arch-depend/be-arch.html "O Billing Essentials é implementado dentro do mesmo projeto que executa o Costing Essentials. Não há um endpoint separado para o Billing Essentials. Todo o conteúdo é fornecido como componentes adicionais e coleções de relatórios dentro desse projeto.")
  - [Arquitetura padrão de faturamento](sol-arch-depend/bs-arch.html "O Billing Standard amplia a mesma arquitetura com um endpoint adicional e um conjunto maior de componentes.")
  - [Relações entre front-end e endpoint](sol-arch-depend/fe-endpoint-relation.html "Embora este guia não aprofunde o Frontdoor, é importante entender como os usuários acessam o Billing.")
  - [Resumo das dependências](sol-arch-depend/depend-summary.html "A tabela abaixo resume as principais dependências para cada edição.")
- Ambientes e gerenciamento de versões
  - [Ambientes de cálculo de custos: Desenvolvimento, Pré-produção, Produção](environ-relnmgmt/environments.html "O faturamento utiliza os mesmos ambientes do projeto de cálculo de custos no qual está instalado. As alterações de configuração no faturamento são gerenciadas por meio dos ambientes do projeto de custos: em desenvolvimento, preparação e produção.")
  - [Check-out, check-in e criação de build](environ-relnmgmt/checkin-checkout.html "As alterações de configuração para Faturamento seguem o mesmo padrão do Cálculo de Custos:")
  - [Bloqueio do ambiente de teste e transição para a produção](environ-relnmgmt/lock-stage-promote.html "Antes de promover alterações para a produção, o ambiente de preparação deve ser bloqueado para evitar que novos check-ins gerem compilações adicionais.")
  - [Fluxo do ambiente para o Billing Essentials](environ-relnmgmt/env-be.html)
  - [Fluxo de ambiente para o Padrão de Faturamento](environ-relnmgmt/env-bs.html "O Padrão de Faturamento segue o mesmo ciclo de vida do ambiente do projeto Padrão de Custeio subjacente, mas introduz um ponto final de Faturamento separado para os usuários finais.")

## Tópicos avançados

- [Análise e otimização de tarifas unitárias](advance-topic/unit-rate-analysis.html "As taxas unitárias são frequentemente o tema central das conversas sobre faturamento. Esta subseção enfoca como analisá-los e ajustá-los ao longo do tempo.")
- [Padrões de faturamento em nuvem](advance-topic/cloud-billing-patterns.html "O faturamento na nuvem depende muito da marcação, da estrutura da conta e do mapeamento de serviços. Os componentes da nuvem do Billing Standard foram projetados para tornar isso gerenciável.")
- [Faturamento e visualizações centrados no projeto](advance-topic/project-centric-billin.html "Os projetos geralmente representam investimentos em produtos, serviços ou iniciativas de mudança. Os componentes do projeto Padrão de Faturamento permitem o faturamento e o showback centrados no projeto.")
- [Preços de transferência e perspectivas das entidades jurídicas](advance-topic/transfer-price.html "Os preços de transferência e as visões ao nível da entidade jurídica tornam-se importantes quando os encargos tecnológicos ultrapassam as fronteiras jurídicas ou fiscais.")
- [Planejado x real x preço](advance-topic/plan-vs-actual.html "Aplica-se principalmente ao Padrão de Faturamento, mas os conceitos podem ser usados de forma simplificada com o Faturamento Básico, se os dados do plano estiverem disponíveis.")

## Padrões de Design e Casos de Uso

- [Showback simples do serviço PxQ](design-uc/uc-simple.html)
- [Estorno com exportação de diário](design-uc/uc-chargeback.html)
- [Investigue um aumento repentino na taxa unitária](design-uc/uc-investgate.html)
- [Visão geral dos custos e taxas unitárias da nuvem](design-uc/uc-cloud.html)
- [Visão do projeto de gastos com tecnologia](design-uc/uc-project.html)
- [Visão da entidade jurídica e interempresarial](design-uc/uc-legal.html)
- [Compare o plano, o real e o preço de um serviço essencial](design-uc/uc-compare.html)

## Manual de lançamento

- [O que significa “entrada em operação” para o faturamento](go-live/gl-overview.html)
- [Lista de verificação de preparação pré-lançamento](go-live/gl-checklist.html "Isso é o mínimo que você deve ter pronto antes mesmo de marcar uma data para o lançamento.")
- [Ensaio geral](go-live/gl-dress-rehersal.html "Um ensaio geral é uma execução completa de ponta a ponta no Desenvolvimento e verificada no Staging que imita o que será publicado na Produção.")
- [Abordagem de transição](go-live/gl-cutover.html "Cutover é a transição controlada de “estamos testando” para “estamos usando o Faturamento como fonte de verdade”")
- [Hipercuidados: primeiros 1–3 ciclos](go-live/gl-hypercare.html "A implementação não termina quando o primeiro período é encerrado. É nos primeiros ciclos que as fraquezas aparecem.")
- [Estratégias de contingência e correção](go-live/gl-falback.html "Às vezes, as coisas vão dar errado. Decida antecipadamente como irá corrigi-los.")
- [Responsabilidades de entrada em operação](go-live/gl-resp-runbook.html "É importante ser explícito sobre quem é o proprietário de cada elemento durante a entrada em operação.")
- [Capturando o runbook de “estado estável”](go-live/runbook.html)

## Guia de treinamento baseado em funções

- [Objetivos do treinamento](role-based-tg/train-objectives.html "Esta seção descreve como treinar diferentes públicos para que o Billing seja realmente usado e confiável, e não apenas implantado tecnicamente. Use-o para planejar integrações, treinamentos recorrentes e transferências quando as pessoas mudarem de função.")
- [Escopo do treinamento por função](role-based-tg/train-scope.html "Esta subseção resume o que cada função precisa aprender. A matriz de treinamento detalhada pode ser documentada separadamente.")
- [Caminho de integração para administradores e analistas](role-based-tg/op-admin.html "Este é o caminho de treinamento mais intensivo e deve ser estruturado, não ad hoc.")
- [Caminho de integração para proprietários de serviços e produtos](role-based-tg/op-so-po.html "Este caminho é mais curto e focado na interpretação, não na configuração.")
- [Caminho de integração para Finanças](role-based-tg/op-finance.html "O treinamento financeiro deve ser prático: como reconciliar e lançar, não como escrever ETL.")
- [Treinamento para líderes seniores e partes interessadas](role-based-tg/op-sl.html "Trata-se de apoio à tomada de decisões, não de mecânica.")
- [Treinamento, cadência e formatos](role-based-tg/cadence-format-measure.html "Depois que a integração inicial estiver concluída, o treinamento não deve parar. No mínimo:")

## Resolução de problemas

- [Resolução de problemas](troubleshooting/troubleshoot.html "Este apêndice é um guia prático sobre “o que deu errado e o que verificar primeiro”. Use-o quando os números parecerem errados, os relatórios estiverem vazios ou os diários não estiverem reconciliados.")
