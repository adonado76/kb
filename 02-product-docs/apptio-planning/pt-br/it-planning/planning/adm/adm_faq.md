---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "PERGUNTAS FREQUENTES: Automatizado Data Management"
breadcrumb:
  - "Planning"
  - "Solução de problemas e perguntas frequentes"
source_path: "it-planning/planning/adm/adm_faq.html"
images:
  - "resources/images/gear.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# PERGUNTAS FREQUENTES: Automatizado Data Management

- [Onde posso visualizar e editar as configurações de conexão do Costing Standard ?](adm_faq.html#FAQAutomatedDataManagement__WherecanIviewandedittheCostingStandardconnectionsettings)
- [Posso alterar o ambiente Costing Standard (desenvolvimento, produção) ao usar o Automated Data Management?](adm_faq.html#FAQAutomatedDataManagement__CanIchangetheCostingStandardenvironmentdevelopmentproductionwhenusingAutomatedDataManagement)
- [Posso me conectar à instância Costing Standard em outro ambiente Apptio?](adm_faq.html#FAQAutomatedDataManagement__CanIconnecttoCostingStandardinstanceinanotherApptioenvironment)
- [Onde posso visualizar e editar mapeamentos de conjuntos de dados para dimensões de dados de referência, dados reais e dados planejados após a ativação do Automated Data Management?](adm_faq.html#FAQAutomatedDataManagement__WherecanIviewandeditthedatasetmappingsforreferencedatadimensionsactualsandplandataafterAutomatedDataManagementisenabled)
- [E se eu não quiser ativar o Automated Data Management para determinadas funções? Por exemplo, na implementação anterior do Cost Transparency Integration , consegui habilitar apenas o compartilhamento de dados de referência, o compartilhamento de dados reais ou a publicação de dados planejados de acordo com a minha necessidade.](adm_faq.html#FAQAutomatedDataManagement__WhatifIdonotwanttoenableAutomatedDataManagementforcertainfunctionsForexampleintheearlierCostTransparencyIntegrationimplementationIwasabletoenableonlythosereferencedatasharingoractualssharingorpublishingplandataaspermyneed)
- [Como posso visualizar o status do Automated Data Management?](adm_faq.html#FAQAutomatedDataManagement__HowcanIviewtheAutomatedDataManagementstatus)
- [Como posso excluir a entidade/dimensão personalizada em Automated Data Management > Entity Mapping para a dimensão personalizada que já foi excluída em Apptio Planning?](adm_faq.html#FAQAutomatedDataManagement__HowcanIdeletethecustomentitydimensionfromAutomatedDataManagementEntityMappingforthecustomdimensionthathasalreadybeendeletedinApptioPlanning)
- [Adicionei uma nova dimensão personalizada em Apptio Planning. Quero importar dados para essa dimensão personalizada de Costing Standard. O que devo fazer?](adm_faq.html#FAQAutomatedDataManagement__IhaveaddedanewcustomdimensioninApptioPlanningIwanttoimportdataintothiscustomdimensionfromCostingStandardWhatshouldIdo)
- [Como a maioria das definições de configuração foi transferida para a interface de usuário automatizada Data Management, o que acontece com o painel Cost Transparency
  Integration na versão antiga do Planning?](adm_faq.html#FAQAutomatedDataManagement__Since)

## Onde posso visualizar e editar as configurações de conexão do Costing Standard ?

Depois de ativar o Automated Data Management, você pode verificar se as configurações de conexão são apropriadas navegando até Automated Data Management > Connections. Para ativar a integração automatizada do Data Management, consulte Ativar a integração automatizada do Data Management no ApptioOne Plan. Todas as alterações nos detalhes da conexão devem ser f **eitas na página Automated Data Management > Connections (Automático > Conexões** ). Consulte [Conexões](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=administration-connections "(Abre em uma nova guia ou janela)") para obter mais informações.

## Posso alterar o ambiente do Padrão de Cálculo de Custos (desenvolvimento, produção) ao usar o Cálculo de Custos Automatizado ( Data Management )?

O Data Management automatizado, também conhecido como Data Management automatizado, só oferece suporte a ambientes de desenvolvimento em TBM Studio. Todas as alterações serão importadas ou publicadas somente no ambiente de desenvolvimento.

## Posso conectar-me à instância do Costing Standard em outro ambiente do Apptio?

No momento, o Automated Data Management não oferece suporte à conexão da instância Costing
Standard em um ambiente Apptio diferente. Você pode definir as configurações de conexão somente para a instância Costing Standard que está usando o mesmo ambiente que a instância Planning . Para configurar as definições de conexão, consulte [Conexões](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=administration-connections "(Abre em uma nova guia ou janela)").

## Onde posso visualizar e editar os mapeamentos do conjunto de dados para dimensões de dados de referência, dados reais e dados planejados após a ativação do recurso Automated Data Management?

Qualquer alteração nos mapeamentos de conjuntos de dados pode ser feita na página Automated Data Management **> Entity Mapping (Mapeamento de entidades** ). Consulte [Gerenciamento de entidades](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=management-entity-planning "(Abre em uma nova guia ou janela)") para obter mais informações.

## E se eu não quiser ativar o Data Management automatizado para determinadas funções? Por exemplo, na implementação anterior da Integração de Transparência de Custos, eu pude habilitar apenas o compartilhamento de dados de referência ou o compartilhamento de dados reais ou a publicação de dados do plano, conforme minha necessidade.

Se você não quiser usar o Data Management automatizado para determinadas funções, certifique-se de que essas funções específicas não sejam mapeadas na página Data Management automatizado > Mapeamento de entidades. Consulte [Gerenciamento de entidades](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=management-entity-planning "(Abre em uma nova guia ou janela)") para obter mais informações.

## Como posso visualizar o status do Automated Data Management?

O status do Data Management automatizado pode ser visualizado na página Status do **Data Management automatizado**. Para mais detalhes, consulte [Status](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=management-status "(Abre em uma nova guia ou janela)").

No entanto, se quiser obter um registro de erros detalhado para solucionar problemas de compartilhamento de dados, siga as etapas abaixo:

1. No menu Apptio Planning , selecione Configurações (![imagem](../../../../../../03-media/apptio-planning/resources/images/gear.png)) e, em seguida, selecione Cost Transparency Integration.
2. Selecione a guia Status.

   Esta página mostra os detalhes dos trabalhos automatizados do Data Management e informações adicionais sobre cada um, se houver.

| Campo | Descrição |
| --- | --- |
| Início e fim | Os horários de início e término do trabalho correspondente |
| Iniciado por | O ID de e-mail do usuário que iniciou o trabalho |
| Estado | O progresso do trabalho: QUEUE, SUCCESS, SUCCESS WITH WARNINGS ou FAIL |
| Ações | Ações de acompanhamento que devem ser realizadas:  - Publicar dados quando os trabalhos de importação forem bem-sucedidos (por exemplo, publicar dados de referência após a importação).  - View, para localizar e fazer download de registros de erros de trabalhos com falha. |

## Como posso excluir a entidade/dimensão personalizada do Automated Data Management > Mapeamento de Entidades para a dimensão personalizada que já foi excluída no Apptio Planning?

A versão beta não oferece suporte à capacidade de excluir entidades/dimensões personalizadas em Automated Data Management > Entity Mapping. No entanto, você pode remover o nome do conjunto de dados na página Mapeamento de entidades para desativar as atualizações de dados. Se quiser excluir a própria entidade da página, recomendamos o registro de um tíquete de suporte para que possamos executar a ação no back-end. Esse recurso será disponibilizado com a versão geral, e os usuários finais terão a capacidade de excluir entidades personalizadas indesejadas do Mapeamento de entidades.

## Adicionei uma nova dimensão personalizada no planejamento d Apptio. Quero importar dados para esta dimensão personalizada a partir do Padrão de Custos. O que devo fazer?

Estamos trabalhando em uma solução para adicionar automaticamente a dimensão personalizada recém-criada em Automated Data Management > Entity Mapping. No entanto, nesta versão beta, recomendamos que você siga as etapas abaixo para habilitar a dimensão personalizada recém-criada para a atualização automática de dados.

1. Crie uma nova dimensão personalizada no Planning.
2. Crie um conjunto de dados em TBM Studio que você deseja usar para importar para a dimensão personalizada recém-criada.
3. Na página de planejamento, navegue até Company Profile > Settings, desative o **Automated Data Management** e salve as alterações.
4. Agora, usando as mesmas etapas acima, reative o Automated Data Management e salve as alterações. Desativar e reativar o Automated Data Management sincronizará automaticamente a dimensão personalizada recém-adicionada no Mapeamento de entidades. Consulte [Acesso automatizado ao Data Management](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=started-access-automated-data-management "(Abre em uma nova guia ou janela)") para obter mais informações sobre como ativar o recurso.

## Como a maioria das configurações foi transferida para a interface do usuário do Automated Data Management, o que acontece com o painel de integração de transparência de custos na versão antiga do Planning?

Na versão beta, após a ativação do Automated Data Management, o painel de integração Costing
Standard ainda estará disponível, no entanto, apenas para visualizar o status de vários trabalhos de compartilhamento de dados e para importar dados reais de Costing Standard para Planning.

Antes que esse recurso seja disponibilizado de forma geral, o plano é tornar a importação de dados reais totalmente automatizada, semelhante à importação de dados de referência. Quando essa alteração ocorrer, a guia Import será removida do painel Costing Standard Integration. O painel será usado apenas para relatórios de status do Automated Data Management após essa alteração.
