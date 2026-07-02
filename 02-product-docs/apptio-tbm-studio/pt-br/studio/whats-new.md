---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Lançamentos recentes"
breadcrumb:
  - "TBM Studio"
  - "Notas sobre a liberação"
source_path: "studio/whats-new.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Lançamentos recentes

## Servidor 12.11.22 - 29 de maio de 2026

- Esta versão traz várias melhorias para o Novo Report Studio, incluindo:
  - [Mecanismo de temas](report-studio/theme-engine.html) para uma aparência de relatório mais personalizável e consistente
  - Suporte para adicionar descrições a fórmulas personalizadas, a fim de melhorar a legibilidade e a facilidade de manutenção
  - Funcionalidade de exportação para o Excel para visualizações de tabelas no Report Designer
  - Tabelas editáveis aprimoradas com limites de linhas configuráveis
  - Suporte para exibição de dados formatados em tabelas editáveis
  - Suporte à opção “Adicionar ao filtro” para fórmulas personalizadas em tabelas editáveis
  - Suporte à filtragem de valores nulos em gráficos para oferecer maior flexibilidade na análise de dados
  - Uma nova opção para desativar as interações de detalhamento na configuração do Painel de Dados
- Foi adicionado suporte para a execução de programações [de publicação recorrentes](formulas-and-functions/functions/ApptioScript-function.html "Aplicável a: TBM Studio 12.11.22 e versões posteriores") para tabelas editáveis usando o ` ApptioScript `.
- **Padrão de cálculo de custos (modelos v120 )**
  - [O TCO do Data Center](/docs/SSI71A/cost-transparency/infra-use-cases/dc-overview.html) já está disponível para todos os clientes com uma licença do Padrão de Cálculo de Custos do IBM Apptio. Este pacote de soluções ajuda as organizações a analisar o custo total de operação das instalações de data center, avaliar a capacidade e a utilização em termos de energia, refrigeração, espaço e racks, e comparar locais utilizando indicadores econômicos unitários, como custo por quilowatt, custo por rack e custo por metro quadrado. Isso também ajuda a alocar os custos do data center à infraestrutura, aos aplicativos e às soluções que eles suportam, melhorando a visibilidade sobre os fatores que geram custos, as restrições de capacidade e as decisões de investimento. [Link](https://www.youtube.com/watch?v=RT6brXfajcc "(Abre em uma nova guia ou janela)") para o vídeo com os melhores momentos
  - Melhorias [no TCO de mainframes](/docs/SSI71A/cost-transparency/infra-use-cases/mf-overview.html) :
    - A guia “Grupo de Custos” foi atualizada para permitir compreender a composição dos custos, acompanhar tendências, comparar com referências e analisar detalhes comparativos entre períodos em uma única visualização coerente.
    - Foi adicionado um novo caso de uso de armazenamento de mainframe para oferecer visibilidade sobre os custos, o consumo e a alocação de armazenamento de mainframe, como parte da análise geral do TCO do mainframe.
  - [Os relatórios prontos para uso](report-studio/ootb-report-pp.html "Este documento descreve as etapas necessárias para habilitar os relatórios OOTB modernizados (Nova Experiência (NX)) em uma instância do cliente. Esses relatórios oferecem maior visibilidade, melhores insights e uma experiência mais intuitiva, mantendo o uso dos mesmos conjuntos de dados do Classic TBM Studio.") baseados no novo Report Studio já estão disponíveis em versão geral (GA) para os componentes Financeiro, Fornecedores, Aplicativos, Mão de obra, Custo Total de Propriedade (TCO) da Nuvem Pública, Custo Total de Propriedade (TCO) do Mainframe, Custo Total de Propriedade (TCO) de IA e Serviços.
  - Os relatórios padrão do Costing Standard já estão disponíveis em polonês

**Corrigido nesta versão**

- Corrigidas vulnerabilidades de segurança

## Cliente: 2.22 - 29 de maio de 2026

- Foi adicionado suporte para a execução de agendamentos [de publicação recorrentes](formulas-and-functions/functions/ApptioScript-function.html "Aplicável a: TBM Studio 12.11.22 e versões posteriores") para tabelas editáveis usando o recurso “ ApptioScript ”.
- Todas as outras funcionalidades exigem a atualização para a versão do servidor 12.11.22. Consulte as atualizações do servidor.

## Servidor 12.11.21.1 - 8 de maio de 2026

- Atualização trimestral do Java.

## Cliente: 2.21.1 - 8 de maio de 2026

- Atualização trimestral do Java.

## Studio UI 1.21.2 - 8 de maio de 2026

**A versão 1.21.2 já está disponível para o público em geral**

Esta versão inclui o seguinte conjunto de pequenas melhorias de funcionalidades e ajustes, com foco na usabilidade e na experiência geral do produto do **Novo Report Studio.**

- Correções no preenchimento da interface do usuário para melhorar a consistência visual
- Melhorias gerais no acabamento e na apresentação em toda a experiência do Novo Report Studio

## Studio UI 1.21.1 - 17 de abril de 2026

As seguintes melhorias foram introduzidas no novo Report Studio do IBM Apptio :

- Corrigimos as violações de acessibilidade para melhorar a conformidade.
- Foi introduzido um indicador de ativo/inativo para os relatórios. O mecanismo de cálculo agora exclui relatórios inativos.
- Renderização aprimorada de dicas de ferramentas com várias linhas para melhorar a legibilidade.
- Corrigidos problemas de localização para o japonês
- Foi adicionada uma separação clara dos relatórios antigos no painel de check-in.

## Servidor 12.11.21 - 10 de abril de 2026

- O novo [IBM Apptio Report Studio](report-studio/getting-started/intro.html "O novo IBM Apptio Report Studio, desenvolvido com o Carbon, oferece uma experiência de geração de relatórios modernizada, intuitiva e mais poderosa. Foi concebido para ajudar os TBMAs e os usuários corporativos a criar relatórios mais rapidamente, com menos complexidade e uma curva de aprendizado mais curta. Em comparação com o Classic Report Studio, esta versão traz:") já está disponível para o público em geral, oferecendo uma experiência moderna para a criação, personalização e visualização de relatórios — possibilitando a adoção completa em todos os fluxos de trabalho de criação, migração e compartilhamento. Com o novo Studio de Relatórios, você pode
  - Criar relatórios do zero
  - Visualize e aprenda com os relatórios padrão pré-definidos
  - Editar e personalizar relatórios
  - Visualizar e compartilhar relatórios
- Nesta versão, as novas melhorias do IBM Apportion Report Studio incluem: componente de botão para ações, regras de visibilidade de guias, eixo compartilhado em gráficos sobrepostos, quebra automática de linha em tabelas, visualizações salvas, compartilhamento por e-mail a partir do visualizador de relatórios e um [assistente de migração](report-studio/migration-assistant.html) para transferir relatórios do TBM Studio clássico.
- Foi introduzida uma nova funcionalidade de autoatendimento no Automated Data Management (ADM) para permitir a integração entre o Cloudability e o Costing, substituindo o conector existente do Cloudability DataLink. Mais detalhes e orientações sobre a migração serão fornecidos pelo seu CSM.
- IBM A documentação de ajuda foi atualizada para o TBM Studio, o Billing e o Benchmarking.
- Costing Standard (modelos v120 )
  - Foi introduzido um novo tipo de projeto independente para o TCO de mainframe, permitindo a análise e o gerenciamento específicos dos custos de mainframe.
  - Já estão disponíveis [relatórios prontos para uso e modernizados,](report-studio/ootb-report-pp.html "Este documento descreve as etapas necessárias para habilitar os relatórios OOTB modernizados (Nova Experiência (NX)) em uma instância do cliente. Esses relatórios oferecem maior visibilidade, melhores insights e uma experiência mais intuitiva, mantendo o uso dos mesmos conjuntos de dados do Classic TBM Studio.") baseados no novo Report Studio (Pré-visualização pública).
  - Uma nova solução, o Data Center TCO (Pré-visualização Pública), já está disponível, oferecendo uma visão abrangente dos custos do data center, da utilização da capacidade e da alocação de custos.
  - O Data Advisor foi atualizado com as últimas melhorias.

**Corrigido nesta versão**

- Corrigidas vulnerabilidades de segurança

## Cliente: 2.21 - 10 de abril de 2026

- Foi adicionada uma caixa de seleção no fluxo de trabalho de Relatórios Não Utilizados para permitir a visualização dos dados de uso do Partner Admin.
- Atualizamos a biblioteca de gráficos; podem ser observadas pequenas alterações visuais nos gráficos.
- Todas as outras funcionalidades exigem a atualização para a versão do servidor 12.11.21. Consulte as atualizações do servidor.

## 12.11.20, servidor - 27 de fevereiro de 2026

- O novo [IBM Apptio Report Studio](report-studio/recent-releases.html) já está disponível para pré-visualização pública. Se você deseja participar e ainda não está registrado, entre em contato com seu Gerente de Sucesso do Cliente (Requer servidor 12.11.19/2.19 +). Novos recursos incluem
  - Exibição em árvore para tabelas
  - Exportar relatórios para PDF
  - Exportar tabelas para o Excel
  - Suporte a várias moedas
- deleteAllrows A funcionalidade da tabela editável excluirá apenas o conjunto de linhas filtradas no momento em que os filtros forem aplicados. Se nenhum filtro for aplicado, todas as linhas da tabela editável serão excluídas.
- A partir do Q2, 2026, o suporte para [agrupamento em dimensões numéricas](troubleshooting/numeric-grouping-tables-reports.html) será totalmente desativado. Recomenda-se aos clientes que identifiquem e resolvam proativamente quaisquer configurações relacionadas.
- [As assinaturas de e-mail](reports/email-subscription.html) agora oferecem suporte à segurança em nível de linha
- Costing Standard (modelos v120 )
  - **Solução TCO do produto:** Adicionadas métricas de detalhamento “ App ID ”, “ CapEx ” e “Total Spend” no [relatório detalhado do produto](/docs/SSI71A/cost-transparency/solution-uc/product-reports.html) e métricas orçamentárias no [relatório da lista de produtos](/docs/SSI71A/cost-transparency/solution-uc/product-reports.html#prorep__plist).
  - **Solução TCO para mainframe:** introduzimos um [relatório](/docs/SSI71A/cost-transparency/infra-use-cases/mf-reports.html#mfrep__mainframe-apps) dedicado a aplicativos de mainframe (anteriormente parte do TCO para mainframe).
- Fundamentos de Cálculo de Custos (modelos v200 )
  - Atualizou as alocações para atribuir primeiro a mão de obra externa aos fornecedores, antes de alocá-la à mão de obra.
  - Atualizou os seletores de colunas na [Análise](/docs/SSU3U2H/apptio-cost-management/out_of_the_box_reports/labor-review.html#LaborReview__lanalysis) de Mão de Obra.

## Cliente 2.20 - 27 de fevereiro de 2026

- O novo [IBM Apptio Report Studio](report-studio/recent-releases.html) já está disponível para pré-visualização pública. Se você deseja participar e ainda não está registrado, entre em contato com seu gerente de sucesso do cliente (é necessário um servidor 12.11.19/2.19 +).
- Corrigimos problemas de vulnerabilidade.
- Todos os novos recursos exigem a atualização para a versão do servidor 12.11.20. Consulte as atualizações do servidor.

## 12.11.19.1, servidor - 6 de fevereiro de 2026

- Atualização trimestral do Java.
- Corrigimos um problema no novo Report Designer em que o ID da dimensão da coluna Objeto incluía incorretamente o nome da tabela

## Cliente 2.19.1 - 6 de fevereiro de 2026

- Atualização trimestral do Java.

## 12.11.19, servidor - 16 de janeiro de 2026

- O novo [IBM Apptio Report Studio](report-studio/prev-releases.html) já está disponível para pré-visualização pública. Se você deseja participar e ainda não está registrado, entre em contato com seu gerente de sucesso do cliente. O acesso ao novo IBM Apptio Report Studio será habilitado na versão 12.11.19/ 2.19.
- A partir do Q2, 2026, o suporte para [agrupamento em dimensões numéricas](troubleshooting/numeric-grouping-tables-reports.html) será totalmente desativado. Recomenda-se aos clientes que identifiquem e resolvam proativamente quaisquer configurações relacionadas.
- Costing Standard (modelos v120 )
  - Adicionado um novo relatório de perfuração para se concentrar na hierarquia do produto.
  - Adicionado TCO do produto ao projeto de referência.
  - O TCO do produto está disponível em japonês.
  - Criou um novo componente para os arquivos de referência do TBM v5.
- Fundamentos de Cálculo de Custos (modelos v200 )
  - Criou um novo componente para os arquivos de referência do TBM v5.

## Cliente 2.19 - 16 de janeiro de 2026

- Corrigimos problemas de vulnerabilidade.
- Todos os novos recursos exigem a atualização para a versão do servidor 12.11.19. Consulte as atualizações do servidor.
