---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Conecte-se ao site Apptio Costing"
breadcrumb:
  - "Planning"
  - "Integrações"
source_path: "it-planning/planning/adm/adm_capabilities.html"
images:
  - "resources/images/it_planning_images/int-comp.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Conecte-se ao site Apptio Costing

Apptio O planejamento integra-se ao Apptio cálculo de custos usando o ADM ( Data Management Automated Design Management). O ADM é um serviço de plataforma compartilhada projetado para fornecer uma experiência de troca de dados unificada, segura e escalável entre Apptio aplicativos.

Essa integração permite que os clientes Apptio do Planning importem dados do Apptio Costing e publiquem planos de volta no Costing para relatórios e análises.

## O que é Automatizado Data Management (ADM)

O Automated Data Management Data Management ( Apptio ADM) é a estrutura padronizada de integração de dados da Microsoft que:

- Suporta trocas de dados automatizadas e repetíveis entre Apptio produtos
- Gerencia conjuntos de dados, entidades e cronogramas de integração de forma centralizada
- Garante identificadores e mapeamentos consistentes entre Planejamento e Custeio
- Reduz o esforço manual e melhora a confiabilidade dos dados

Saiba mais: [Automatizado Data Management](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=automated-data-management "(Abre em uma nova guia ou janela)").

## Integrações de custos Apptio suportadas

Usando o ADM, Apptio o Planejamento oferece suporte às seguintes integrações com Apptio o Cálculo de Custos:

**Importar do Apptio Cálculo de custos para Apptio o Planejamento**

- **Dados de referência**

  Importe as dimensões dos dados de referência do Apptio Cálculo de custos para garantir a consistência dos mestres em todas as aplicações.

  Saiba mais: [*Importar dados de referência do Cálculo de custos d Apptio*](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=costing-import-reference-data-from-apptio "(Abre em uma nova guia ou janela)")
- **Dados reais**

  Importe dados reais de gastos do Apptio Cálculo de custos para apoiar a previsão e a análise de variações.

  Saiba mais: [*Importar dados reais do cálculo de custos d Apptio*](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=costing-import-actuals-from-apptio "(Abre em uma nova guia ou janela)")
- **Planos de referência**

  Crie planos com base em dados Apptio de custos para acelerar a configuração do plano e garantir o alinhamento com as finanças atuais.

  Saiba mais: [*Importar planos de referência do cálculo de custos d Apptio*](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=costing-import-baseline-plans-from-apptio "(Abre em uma nova guia ou janela)")
- **Dados da lista de projetos**

  Importar lista de projetos em nível de plano de custos de Apptio.

  Saiba mais: [*Importar lista de projetos do Apptio Cálculo de custos*](../import-pl-acost.dita "(Abre em uma nova guia ou janela)")

**Publicar do Apptio Planejamento para Apptio o Cálculo de Custos**

- **Publicar dados do plano**

  Envie os dados do orçamento ou do plano de previsão do Apptio Planejamento para Apptio o Cálculo de custos.

  Saiba mais: [*Publicar dados do plano em um cálculo de custos d Apptio*](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=costing-publish-plan-data-apptio "(Abre em uma nova guia ou janela)")
- **Cronograma de Publicações**

  Automatize a publicação de planos recorrentes em um cronograma definido para manter Apptio os custos continuamente alinhados com as atualizações do planejamento.

  Saiba mais: [*Plano de programação publica em Apptio Cálculo de custos*](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=administration-schedule-plan-publishes "(Abre em uma nova guia ou janela)")
- **Dados da lista de projetos**

  Envie a lista de projetos em nível de plano do planejamento Apptio para o cálculo de custos Apptio.

  Saiba mais: [*Publicar lista de projetos em Apptio Cálculo de custos*](../pub-pl-ac.dita "(Abre em uma nova guia ou janela)")

## Entidades automatizadas de Data Management

|  |  |  |  |
| --- | --- | --- | --- |
| **Nome da entidade** | **Produção de aplicativos** | **Aplicativo de consumo** | **Descrição** |
| Publicar orçamento financeiro | Apptio Planejamento | Apptio Cálculo de custos | Publica itens financeiros para planos do tipo orçamento |
| Publicar previsão financeira | Apptio Planejamento | Apptio Cálculo de custos | Publica itens financeiros para planos do tipo previsão |
| **Publicar orçamento de ativos** | Apptio Planejamento | Apptio Cálculo de custos | Publica itens de linha de ativos para planos do tipo orçamento |
| Publicar previsão de ativos | Apptio Planejamento | Apptio Cálculo de custos | Publica itens de linha de ativos para planos do tipo previsão |
| Publicar orçamento do contrato | Apptio Planejamento | Apptio Cálculo de custos | Publica itens de linha de contrato para planos do tipo orçamento |
| Publicar previsão do contrato | Apptio Planejamento | Apptio Cálculo de custos | Publica itens de linha de contrato para planos do tipo previsão |
| Publicar Orçamento de Mão de Obra | Apptio Planejamento | Apptio Cálculo de custos | Publica itens de mão de obra para planos do tipo orçamento |
| Publicar previsão de mão de obra | Apptio Planejamento | Apptio Cálculo de custos | Publica itens de mão de obra para planos do tipo previsão |
| Publicar Orçamento de Atividades Trabalhistas | Apptio Planejamento | Apptio Cálculo de custos | Publica itens de linha de atividade de trabalho para planos do tipo orçamento |
| Publicar previsão de atividade laboral | Apptio Planejamento | Apptio Cálculo de custos | Publica itens de linha de atividade de trabalho para planos do tipo previsão |
| Publicar lista de projetos | Apptio Planejamento | Apptio Cálculo de custos | Publica a lista de projetos no nível do plano |
| Dados reais | Apptio Cálculo de custos | Apptio Planejamento | Importa dados financeiros reais do Cálculo de Custos para o Planejamento da Gestão de Despesas |
| Importar Plano Financeiro | Apptio Cálculo de custos | Apptio Planejamento | Importa itens financeiros |
| Importar plano de ativos | Apptio Cálculo de custos | Apptio Planejamento | Importa itens de linha de ativos |
| Contrato de plano de importação | Apptio Cálculo de custos | Apptio Planejamento | Itens da linha do contrato de importação |
| Importar plano de trabalho | Apptio Cálculo de custos | Apptio Planejamento | Importa itens de linha de mão de obra |
| Importar plano de atividades de trabalho | Apptio Cálculo de custos | Apptio Planejamento | Importa itens de linha de atividade de trabalho |
| Importar lista de projetos do plano | Apptio Cálculo de custos | Apptio Planejamento | Importar nível do plano Lista de projetos |
| Conta | Apptio Cálculo de custos | Apptio Planejamento | Importações Dados de referência da conta |
| Categoria da conta | Apptio Cálculo de custos | Apptio Planejamento | Importações Dados de referência da categoria de conta |
| Departamento | Apptio Cálculo de custos | Apptio Planejamento | Dados de referência do departamento de importações |
| Centro de Custos | Apptio Cálculo de custos | Apptio Planejamento | Importações Dados de referência do centro de custos |
| Fornecedor | Apptio Cálculo de custos | Apptio Planejamento | Importações Dados de referência do fornecedor |
| Local | Apptio Cálculo de custos | Apptio Planejamento | Importa dados de referência de localização |
| Função | Apptio Cálculo de custos | Apptio Planejamento | Importa dados de referência de funções |
| Taxas de mão de obra | Apptio Cálculo de custos | Apptio Planejamento | Importa dados de referência sobre taxas de mão de obra |
| Regras de alocação de mão de obra | Apptio Cálculo de custos | Apptio Planejamento | Importa dados de referência das regras de alocação de mão de obra |
| Padrões de classe de ativos | Apptio Cálculo de custos | Apptio Planejamento | Importa dados de referência da classe de ativos |
| Padrões do tipo de contrato | Apptio Cálculo de custos | Apptio Planejamento | Dados de referência do tipo de contrato de importação |
| Fator de variação | Apptio Cálculo de custos | Apptio Planejamento | Importa dados de referência do controlador de variação |
| Grupo do Projeto | Apptio Cálculo de custos | Apptio Planejamento | Importa dados de referência do grupo de projetos |
| Projeto | Apptio Cálculo de custos | Apptio Planejamento | Importa dados de referência do projeto |
| Função do Trabalho no Projeto | Apptio Cálculo de custos | Apptio Planejamento | Importa dados de referência sobre funções laborais do projeto |
| Tipo de atividade laboral | Apptio Cálculo de custos | Apptio Planejamento | Importa dados de referência do tipo de atividade de trabalho |

## Visão geral da configuração

Antes de usar as integrações, o ADM deve ser configurado para o seu ambiente. A configuração normalmente inclui:

1. **Ativar automatização Data Management**
   1. Confirme se o Automated Data Management (ADM) está provisionado para o seu ambiente. Você pode verificar isso confirmando se o ADM aparece como um aplicativo no Frontdoor.
   2. Em Apptio Planejamento, acesse **Configurações (ícone de engrenagem) → Perfil da empresa** e selecione **Ativar integração Data Management automática**.
2. **Configurar as definições de exportação**

   Configure **as definições de exportação** para definir o comportamento padrão de exportação para todos os conjuntos de dados do plano.

   1. No Planejamento do Apptio, acesse **Configurações (ícone de engrenagem) → Integração de custos do Apptio → Configurações de exportação.**
   2. Configure as definições e salve as configurações.
      - **Layout de exportação:** escolha publicar o esquema completo (Exportar tudo) ou um formato reimportável.
      - **Filtros de dados confidenciais:** ative ou desative a filtragem de detalhes confidenciais sobre trabalho e finanças durante a publicação.
      - **Formato de exportação:** a opção de publicar meses como linhas ou colunas foi movida da seção Configurar para esta nova configuração de Definições de exportação.
      - **Configurações de moeda:** publique usando a moeda padrão da organização ou na moeda original.
      - **Precisão decimal:** a precisão decimal é definida por padrão nas configurações da organização definidas no Perfil da empresa. Você pode selecionar uma precisão decimal diferente e um ícone decimal (ponto ou vírgula) para exportar dados para um Cálculo de Custos d Apptio.
      - **Formato da data:** Configure o formato da data usado ao publicar no Cálculo de custos.
3. **Configurar conjuntos de dados de integração em Apptio Cálculo de custos**
   1. Instale os componentes de Apptio integração de custos com base nos recursos de planejamento que você deseja habilitar.
   2. Componentes de integração disponíveis:
      1. **Integração do planejamento**

         Instala conjuntos de dados de referência, reais, orçamentários e de previsão necessários para Apptio o planejamento.
      2. **Planejamento da integração do projeto**

         Instala conjuntos de dados adicionais necessários para o planejamento de projetos e atividades de trabalho no Apptio Planejamento.

   ![](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/int-comp.png)

## Conjuntos de dados instalados pelo Componente de Integração de Planejamento

|  |  |  |  |
| --- | --- | --- | --- |
| **Categoria** | **Conjunto de dados** | **Grupo de tabelas** | **Descrição** |
| Conta e estrutura financeira | Planejamento Mestre de Contas | Dados de referência de planejamento da Z\_Apptio | Lista principal de contas financeiras utilizadas para planejamento, incluindo os atributos de conta exigidos pelo Apptio Planejamento. |
| Planejamento da categoria de conta mestre | Dados de referência de planejamento da Z\_Apptio | Define categorias financeiras de alto nível usadas para agrupar e analisar contas no Planejamento. |
| Hierarquia de contas de planejamento | Dados de referência de planejamento da Z\_Apptio | Estrutura hierárquica que organiza contas em relações pai/filho para rollups e relatórios. |
| Planejamento de conta nível 1–5 | Dados de referência de planejamento da Z\_Apptio | Visualizações simplificadas da hierarquia da conta em cada nível para dar suporte a integrações e relatórios. |
| Centros de custo e departamentos | Planejamento do Mestre do Centro de Custos | Dados de referência de planejamento da Z\_Apptio | Lista oficial de centros de custo disponíveis para orçamentação e previsão. |
| Planejamento da hierarquia do centro de custos | Dados de referência de planejamento da Z\_Apptio | Estrutura hierárquica que organiza centros de custo em relações pai/filho para rollups e relatórios. |
| Planejamento do Centro de Custos Nível 1–5 | Dados de referência de planejamento da Z\_Apptio | Visualizações simplificadas da hierarquia do centro de custos em cada nível para apoiar integrações e relatórios. |
| Departamento de Planejamento Mestre | Dados de referência de planejamento da Z\_Apptio | Conjunto de dados mestre que define os departamentos utilizados no Apptio Planejamento. |
| Hierarquia do Departamento de Planejamento | Dados de referência de planejamento da Z\_Apptio | Estrutura hierárquica que organiza os departamentos em relações pai/filho para rollups e relatórios. |
| Departamento de Planejamento Nível 1–5 | Dados de referência de planejamento da Z\_Apptio | Visões simplificadas da hierarquia do departamento em cada nível para apoiar integrações e relatórios. |
| Dados reais | Planejamento Real Master | Dados de planejamento da Z\_Apptio | Conjunto de dados mestre das finanças reais utilizadas pelo Apptio Planejamento. O conjunto de dados Realizações do planejamento é mapeado para esta tabela para o consumo do planejamento. |
| Planejamento Real | Dados de planejamento da Z\_Apptio | Conjunto de dados transformado derivado dos dados mestre de custos, filtrado para incluir apenas valores reais para importação para Apptio o Planejamento. |
| Planos financeiros | Orçamento de planejamento | Dados de planejamento da Z\_Apptio | Itens financeiros orçamentados publicados a partir Apptio do Planejamento. |
| Previsão de planejamento | Dados de planejamento da Z\_Apptio | Itens financeiros previstos publicados a partir do Apptio Planejamento. |
| Planos de ativos | Planejamento do Orçamento de Ativos | Dados de planejamento da Z\_Apptio | Itens financeiros de ativos publicados a partir dos planos Apptio orçamentários de planejamento. |
| Planejamento de previsão de ativos | Dados de planejamento da Z\_Apptio | Itens financeiros de ativos publicados a partir de Apptio planos de previsão de planejamento. |
| Planejamento da Classe de Ativos Mestre | Dados de referência de planejamento da Z\_Apptio | Dados de referência que definem as classes de ativos e o comportamento de capitalização utilizados no planejamento. |
| Planos de Contrato | Planejamento do orçamento do contrato | Dados de planejamento da Z\_Apptio | Itens de linha de contrato orçados publicados a partir Apptio do Planejamento. |
| Previsão do contrato de planejamento | Dados de planejamento da Z\_Apptio | Itens de contrato previstos publicados a partir do Apptio Planejamento. |
| Planejamento Tipo de contrato mestre | Dados de referência de planejamento da Z\_Apptio | Dados de referência que definem os tipos de contrato utilizados no planejamento. |
| Planos de trabalho | Planejamento do orçamento de mão de obra | Dados de planejamento da Z\_Apptio | Itens de mão de obra orçados publicados a partir Apptio do Planejamento. |
| Planejamento da previsão de mão de obra | Dados de planejamento da Z\_Apptio | Itens de mão de obra previstos publicados a partir Apptio do Planejamento. |
| Planejamento das taxas de mão de obra | Dados de referência de planejamento da Z\_Apptio |  |
| Planejamento do Mestre de Funções de Trabalho | Dados de referência de planejamento da Z\_Apptio | Definições de taxas de mão de obra por função, localização ou fornecedor utilizadas para calcular os custos de mão de obra no Apptio Planejamento. |
| Dados de referência | Planejamento Localização Mestre | Dados de referência de planejamento da Z\_Apptio | Dados de referência de localização utilizados para taxas de mão-de-obra, relatórios e análises no Apptio Planejamento. |
| Planejamento de taxas de IVA | Dados de referência de planejamento da Z\_Apptio | Conjunto de dados de referência que define as taxas de IVA utilizadas para calcular os itens de linha do contrato com impostos incluídos no Apptio Planejamento. |
| Fator de variação do planejamento | Dados de referência de planejamento da Z\_Apptio | Conjunto de dados de referência que define as categorias de variação utilizadas na análise de variação e comentários em Apptio Planejamento. |
| Planejamento do mestre de fornecedores | Dados de referência de planejamento da Z\_Apptio | Lista principal de fornecedores utilizados no Apptio Planejamento. |

## Conjuntos de dados instalados pelo Componente de Integração do Projeto de Planejamento

|  |  |  |  |
| --- | --- | --- | --- |
| **Categoria** | **Conjunto de dados** | **Grupo de tabelas** | **Descrição** |
| Projetos | Planejamento do Projeto Mestre | Dados de referência de planejamento da Z\_Apptio | Lista principal de projetos disponíveis para planejamento de projetos e investimentos em Apptio Planejamento. |
| Planejamento Grupo de Projeto Mestre | Dados de referência de planejamento da Z\_Apptio | Agrupamento hierárquico de projetos utilizado para gestão de portfólio e relatórios. |
| Atividade Laboral | Planejamento do projeto Função do mestre de trabalho | Dados de referência de planejamento da Z\_Apptio | Funções de trabalho específicas do projeto e taxas associadas utilizadas para a atividade de trabalho do projeto no Apptio Planejamento. |
| Planejamento do mestre de tipos de atividade de mão de obra | Dados de referência de planejamento da Z\_Apptio | Define os tipos de atividade de trabalho e os mapeamentos para a contabilidade de cobranças e cobranças cruzadas no Apptio Planejamento. |
| Planos do projeto | Planejamento do orçamento para atividades trabalhistas | Dados de planejamento da Z\_Apptio | Itens de linha de atividade de mão de obra orçados publicados a partir Apptio do Planejamento. |
| Planejamento da previsão de atividades de trabalho | Dados de planejamento da Z\_Apptio | Itens de atividade de trabalho previstos publicados a partir Apptio do Planejamento. |
| Integração do Targetprocess | Atividade de mão de obra do processo alvo - Dados reais | Dados de planejamento da Z\_Apptio | Atividade real da mão de obra do projeto importada do Targetprocess. |
| Plano de Atividades Trabalhistas do Processo Alvo | Dados de planejamento da Z\_Apptio | Atividade de trabalho planejada do projeto obtida do Targetprocess para comparação e alinhamento com o Planejamento. |

## Melhores práticas para Data Management

A abordagem recomendada é importar e publicar conjuntos de dados principais a partir Apptio do Costing, em vez de sobrescrever ou integrar diretamente com arquivos de dados brutos de origem.

Os feeds de origem brutos devem primeiro ser transformados, normalizados e mapeados no Apptio Costing em conjuntos de dados mestres padronizados. Esses conjuntos de dados principais representam dados financeiros limpos, categorizados e alinhados aos negócios, e são projetados para serem reutilizados de forma consistente em Apptio aplicativos, incluindo Apptio o Planning.

Embora você possa criar suas próprias tabelas de integração personalizadas em vez de usar os conjuntos de dados prontos para uso (OOTB), lembre-se de que a mantém e Apptio aprimora continuamente os esquemas OOTB. Quando atualizações do modelo de dados ou do esquema forem lançadas, os conjuntos de dados e componentes Apptio de integração OOTB serão atualizados, e você poderá atualizar esses componentes para aproveitar automaticamente as melhorias e correções mais recentes. As tabelas personalizadas, por outro lado, devem ser mantidas e atualizadas manualmente.

- **[Importar dados de referência de](../../../it-planning/planning/adm/adm_import_reference_data.html)** Dados de   
   referência Apptio de custos em Apptio Planejamento define as dimensões principais utilizadas para planejamento, previsão e relatórios, tais como Contas, Centros de custos, Departamentos, Fornecedores, Projetos e Funções de mão de obra. Usando o Automated Data Management Data Management (ADM), você pode importar dados de referência confiáveis e controlados diretamente do Apptio Cálculo de Custos para garantir a consistência em todos os fluxos de trabalho financeiros.
- **[Importar dados reais do Apptio Cálculo de custos](../../../it-planning/planning/adm/adm_import_actuals.html)**  
   A importação de dados reais traz dados históricos de gastos do Apptio Cálculo de custos para Apptio o Planejamento, onde podem ser usados para previsões, análises de variação e comparações de planos.
- **[Importar planos de referência do Apptio Cálculo de custos](../../../it-planning/planning/adm/adm-import-baseline-data.html)**  
   Esse recurso permite importar dados do plano de referência do Apptio Cálculo de custos para Apptio o Planejamento. Isso é útil quando você deseja trazer um conjunto de dados existente do Apptio Cálculo de custos como ponto de partida para o orçamento ou a previsão.
- **[Importar lista de projetos do Cálculo de custos do Apptio](../../../it-planning/planning/import-pl-acost.html)**
- **[Publicar dados do plano para Apptio Cálculo de custos](../../../it-planning/planning/adm/adm_publish_import_plan_data.html)**  
   A publicação dos dados do plano do Apptio Planejamento para Apptio o Cálculo de custos permite compartilhar dados finalizados do orçamento e da previsão com seu ambiente de alocação e transparência de custos. Por meio dos recursos integrados de integração e programação do Automated Data Management (ADM), você pode exportar itens financeiros (finanças, mão de obra, atividade de mão de obra, contratos, ativos) do Planejamento e enviá-los diretamente para Apptio o Cálculo de Custos.
- **[Publicar lista de projetos em Apptio Cálculo de custos](../../../it-planning/planning/pub-pl-ac.html)**
- **[Status da](../../../it-planning/planning/adm/adm-status.html)**   
   integração A página Status da integração fornece visibilidade do progresso das trocas de dados entre Apptio o Planejamento e Apptio o Custeio usando o ADM ( Data Management Automated Data Management). Essa visualização ajuda os administradores a monitorar importações, publicações e solucionar problemas de integração.
- **[Integração de transparência de custos (legado)](../../../it-planning/planning/integrate-ct.html)**  
   Se a sua organização executa tanto o aplicativo Apptio Costing Standard quanto um Apptio Planning , é possível integrá-los para compartilhar dados.
- **[Conecte-se a Cloudability Financial Planning](../../../it-planning/planning/connect-cfp.html)**
- **[Gerencie despesas com nuvem (sem integração com CFP)](../../../it-planning/planning/manage-cfp-wo-int.html)**  
   A guia **Nuvem** na visualização **Despesas** pode ser usada independentemente, sem a integração com CFP, para gerenciar e acompanhar os gastos com nuvem dentro dos orçamentos e previsões.
- **[Configurar e gerenciar a integração do Cloud Financial Planning](../../../it-planning/planning/cfp-integration.html)** As  
   configurações de integração do Cloud Financial Planning (CFP) são definidas **por plano** nas Configurações do plano. Essas configurações estabelecem a conexão entre o Planejamento do Apptio e o **Plano CFP** específico e **a Visualização de Propriedade de Custos**, e definem como as dimensões do Planejamento (Departamento, Centro de Custos, Conta, etc.) mapa das estruturas de propriedade de custos da CFP.
