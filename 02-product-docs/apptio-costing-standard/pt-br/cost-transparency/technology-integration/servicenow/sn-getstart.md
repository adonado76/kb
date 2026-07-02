---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "ServiceNow Introdução"
breadcrumb:
  - "Costing Standard"
  - "Integrações tecnológicas"
  - "ServiceNow"
source_path: "cost-transparency/technology-integration/servicenow/sn-getstart.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# ServiceNow Introdução

A integração entre IBM, Apptio e ServiceNow é uma integração bidirecional projetada para conectar dados operacionais e de configuração de ServiceNow com os modelos financeiros de IBM, Apptio; e para trazer as informações sobre custos e TCO de Apptio de volta para ServiceNow.

Essa abordagem permite que as organizações estabeleçam o ServiceNow como o sistema operacional de registro (CMDB, CSDM, Discovery, EA, DPM) enquanto utilizam o IBM Apptio como o sistema financeiro de registro para custos de tecnologia, TCO e lógica de alocação. O resultado é uma visão unificada e confiável dos custos, do consumo e do valor em aplicativos, serviços e portfólios digitais.

A integração é realizada por meio de duas vias complementares:

- **Ingress** : Trazendo dados do ServiceNow para o IBM Apptio usando conectores prescritivos Datalink
- **Saída** : Transferindo os insights do IBM Apptio TCO de volta para ServiceNow usando aplicativos certificados IBM Apptio da Loja ServiceNow

1. **Avaliação da prontidão**

   Antes de iniciar a integração técnica, considere entrar em contato com nossa organização de Serviços Profissionais para realizar a Avaliação de Preparação para o Apptio ServiceNow.

   Essa avaliação ajudará a validar a integridade do CMDB, o alinhamento do CSDM, a cobertura da descoberta e a qualidade dos dados antes da integração.

   Seu objetivo é identificar quais áreas estão prontas para integração, quais casos de uso importantes isso irá apoiar e, assim, quais benefícios/valor comercial podem ser esperados.
2. **Ingress: Trazendo dados d ServiceNow s para Apptio**

   A Ingress concentra-se na obtenção de dados operacionais, de configuração e de relacionamento de alta qualidade a partir de ServiceNow em IBM Apptio para alimentar modelos de custos precisos e consumíveis.
3. **Quais dados são coletados**

   Usando conectores prescritivos IBM Apptio Datalink, IBM Apptio ingere dados de armazenamentos de dados importantes ServiceNow, incluindo:
   - Itens de configuração do CMDB (infraestrutura, aplicativos, serviços)
   - Relações entre serviços (Catálogo de Serviços) e aplicações alinhadas com o CSDM
   - Dados operacionais, como tickets, incidentes e volumes de tarefas (quando aplicável)
   - Metadados organizacionais e de propriedade (por exemplo, departamentos, centros de custo)

   Esses dados formam a base estrutural para o TCO de aplicativos, o TCO de serviços e o chargeback/showback em IBM Apptio.

   Seis conectores prontos para uso do Datalink trazem dados de 33 tabelas do ServiceNow.

   Observação: um conector 7thcustom pode ser usado para importar tabelas adicionais, conforme necessário.

   Dica: Ao configurar esses conectores Datalink, utilize a caixa de seleção Padrão. Isso selecionará automaticamente os campos mais importantes necessários para fins de alocação e relatórios em IBM Apptio; ao mesmo tempo em que oferece flexibilidade para adicionar ou remover campos conforme necessário.

   |  |  |  |
   | --- | --- | --- |
   | **Datalink Conector** | **IBM Apptio componente** | **Tabelas em ServiceNow** |
   | ServiceNow Finanças | Ativos fixos | alm\_asset |
   | Referência geral | cmn\_localização |
   | cmn\_centro de custos |
   | departamento\_cmn |
   | Projetos | pm\_projeto |
   | ServiceNow Ativos de infraestrutura - Inferior | Data center | cmdb\_ci\_datacenter |
   | cmdb\_ci\_sala\_de\_computadores |
   | cmdb\_ci\_zona |
   | cmdb\_ci\_rack |
   | Rede | cmdb\_ci\_netgear |
   | Armazenamento | cmdb\_ci\_dispositivo\_de\_armazenamento |
   | cmdb\_ci\_volume\_de\_armazenamento |
   | cmdb\_ci\_msd |
   | servidor de armazenamento cmdb\_ci |
   | Dispositivos do usuário final | cmdb\_ci\_computador |
   | ServiceNow Ativos de infraestrutura - Superior | Mainframe | cmdb\_ci\_mainframe |
   | cmdb\_ci\_mainframe\_lpar |
   | Servidores | servidor\_cmdb\_ci |
   | Banco de dados | cmdb\_ci\_banco de dados |
   |  | cmdb\_ci\_db\_instância |
   | ServiceNow Relações Infra | Relações Infra | cmdb\_rel\_ci |
   | svc\_ci\_assoc |
   | ServiceNow Central de atendimento | Chamados | incidente |
   | problema |
   | solicitação\_de\_alteração |
   | sc\_request |
   | tarefa\_ci |
   | ServiceNow Aplicativos e serviços | Middleware | cmdb\_ci\_servidor\_de\_aplicações |
   | cmdb\_ci\_app |
   | Aplicativos | cmdb\_ci\_aplicação\_empresarial |
   | Serviços | oferta de serviços |
   | cmdb\_ci\_serviço |
   | cmdb\_ci\_capacidade\_de\_negócio |
   | **6 conectores** | **15 Componentes** | **33 Tabelas** |

   Para começar a configurar os conectores de entrada do Datalink, consulte a seguinte documentação: [Conector de entrada do](https://www.ibm.com/docs/en/apptio-platform/datalink/saas?topic=connectors-datalink-servicenow-ingress-connector "(Abre em uma nova guia ou janela)") DatalinkServiceNow - Documentação do IBM
4. **Insira os dados no Modelo de Custos IBM Apptio**

   Depois que os dados forem inseridos usando os conectores de entrada do Datalink, utilize nossa organização de Serviços Profissionais para auxiliar na conexão dos novos feeds de dados do ServiceNow nos respectivos conjuntos de dados principais e objetos de modelo do IBM Apptio. Com base nos casos de uso e nos dados incluídos por meio da integração, eles podem auxiliar na desconfiguração/reconfiguração do modelo e ajudar a validar a configuração e os relatórios aprimorados.
5. **Saída: Publicação de insights sobre o TCO (custo total de propriedade) d Apptio Voltar para ServiceNow**

   A Egress concentra-se em divulgar as informações financeiras confiáveis da IBM Apptio diretamente no ServiceNow,, onde arquitetos, proprietários de serviços e líderes digitais já trabalham.

   **Aplicativos certificados para o Apptio na Loja ServiceNow**

   IBM Apptio fornece **dois aplicativos certificados** disponíveis na Loja ServiceNow para oferecer suporte a casos de uso de saída:
   - **IBM Apptio TCO da aplicação para uma arquitetura empresarial (EA) d ServiceNow**

     Aplicações de superfícies TCO, fatores de custo e tendências diretamente em uma EA ( ServiceNow ) para apoiar as decisões de racionalização e modernização de aplicações.
   - **IBM Apptio Custo total de propriedade do serviço para o Gerenciamento de Portfólio Digital (DPM) d ServiceNow**

     Incorpora informações sobre o custo total de propriedade (TCO) do serviço no DPM ( ServiceNow ), permitindo que os proprietários de produtos e serviços digitais planejem, criem, executem e calculem os custos de seus portfólios usando uma única solução.

   **Como funciona o Egress**

   1. **Instale os aplicativos certificados IBM Apptio**

      Instale os aplicativos apropriados IBM Apptio da Loja ServiceNow com base nos seus casos de uso do EA e/ou DPM.
   2. **Criar relatórios de TCO no IBM Apptio**

      Crie relatórios de TCO (custo total de propriedade) de aplicativos e serviços no IBM Apptio TBM Studio, incluindo as análises e métricas necessárias.
   3. **Configurar o conector de saída do Datalink**

      Use IBM Apptio Datalink para enviar com segurança os dados de TCO de IBM Apptio para ServiceNow.
   4. **Analise insights em painéis nativos do ServiceNow**

      IBM Apptio As métricas de TCO aparecem diretamente nos espaços de trabalho do EA e do DPM d ServiceNow, fornecendo contexto financeiro sem que os usuários precisem sair d ServiceNow.Para começar a configurar o Egress, consulte a seguinte documentação: [Configurar uma conexão Egress ( ServiceNow ) (aplicativos e serviços) - Documentação do IBM](https://www.ibm.com/docs/en/apptio-platform/datalink/saas?topic=connectors-configure-servicenow-egress-connection-apps-services "(Abre em uma nova guia ou janela)")

   Observação: além dos dois casos de uso de saída prescritivos, também é possível utilizar o conector genérico para enviar quaisquer dados IBM Apptio para ServiceNow. Para começar, consulte a seguinte documentação: [Configurar uma conexão de saída do ServiceNow (genérica) - Documentação do IBM](https://www.ibm.com/docs/en/apptio-platform/datalink/saas?topic=connectors-configure-servicenow-egress-connection-generic "(Abre em uma nova guia ou janela)")
