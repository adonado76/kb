---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Guia de configuração de TCO do mainframe"
breadcrumb: []
source_path: "cost-transparency/configuration/mainframe-config-guide.html"
images:
  - "resources/images/ct_images/2-components-ctf.png"
  - "resources/images/ct_images/add-allocations.png"
  - "resources/images/ct_images/add-unit-driver.png"
  - "resources/images/ct_images/application-id.png"
  - "resources/images/ct_images/bi-mainframe-insights.png"
  - "resources/images/ct_images/complete-mainframe.png"
  - "resources/images/ct_images/configurations-note.png"
  - "resources/images/ct_images/cost-allocation-it-resource-tower.png"
  - "resources/images/ct_images/cost-model-architecture.png"
  - "resources/images/ct_images/ct-apps-applications.png"
  - "resources/images/ct_images/gcp-msu.png"
  - "resources/images/ct_images/lineage-flow.png"
  - "resources/images/ct_images/mainframe-analysis.png"
  - "resources/images/ct_images/mainframe-model-report.png"
  - "resources/images/ct_images/mainframe-tco-painpoints.png"
  - "resources/images/ct_images/mainframe-tco.png"
  - "resources/images/ct_images/mainframe-usage-report.png"
  - "resources/images/ct_images/map-columns.png"
  - "resources/images/ct_images/map-intellimagic-feed.png"
  - "resources/images/ct_images/map-intellomagic.png"
  - "resources/images/ct_images/map-relevant-fields.png"
  - "resources/images/ct_images/network-devices.png"
  - "resources/images/ct_images/save-gcp-msu.png"
  - "resources/images/ct_images/use-case.png"
  - "resources/images/ct_images/ziip-driver.png"
  - "resources/images/ct_images/ziip-msp-driver.png"
  - "resources/images/ct_images/ziip-msu.png"
  - "resources/images/ct_images/ziip-network-devices.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Guia de configuração de TCO do mainframe

## Visão geral

A solução de TCO de mainframe foi projetada para resolver

- Visibilidade limitada do custo total de propriedade.
- Compreensão das métricas de custo unitário real das cargas de trabalho.
- Incapacidade de alocar com precisão os custos do mainframe.

![Pontos problemáticos do TCO do mainframe](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/mainframe-tco-painpoints.png)

  

Ele oferece suporte aos seguintes casos de uso

![Caso de uso](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/use-case.png)

## Pré-requisitos

Os pré-requisitos para a solução Mainframe TCO & Usage são:

- IBM Apptio Licença padrão de cálculo de custos
- IBM Apptio Versão do servidor: R12.11.17 (ou superior), versão beta - R12.11.16 (ou superior)
- Versão dos componentes v120 em Configurações do projeto.
  - Consulte [este guia](install-apptio-ibm-costing-old-template.html) para instalar os componentes do v120 em projetos com versões mais antigas de componentes.

## Instalação do componente

O núcleo da solução Mainframe TCO & Usage é apresentado por meio do componente BI - Mainframe Insights. Para novos clientes, os componentes típicos, como fonte de custos, mão de obra, fornecedor, ativos fixos, aplicativos etc., também precisariam ser instalados, de acordo com a arquitetura geral pretendida. Os clientes existentes podem reutilizar os componentes instalados anteriormente sem changes.Before instalar os componentes, consulte a próxima seção sobre arquitetura para garantir a consideração adequada, seja para instalá-los em um projeto existente ou criar um novo projeto para a solução Mainframe TCO & Usage. A seguir, temos uma visão geral dos quatro componentes, na ordem de prioridade para considerá-los e instalá-los.

**Configure o objeto Mainframe no projeto Transparência de custos existente**. Essas alterações precisam ser feitas no TBM Studio

1. Vá para o ícone Componentes na guia Projeto e instale o componente BI-Mainframe Insights.

   ![Informações sobre o mainframe do BI](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/bi-mainframe-insights.png)
2. Instale o componente CT Apps- Aplicativos.

   ![Aplicativo CT Apps](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/ct-apps-applications.png)

   Observação: para o componente BI-Mainframe Insights, dois componentes devem ser pré-instalados e configurados.
   - CTF-Fonte de custo
   - CTF - Torre de TI

   ![Componentes do CTF](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/2-components-ctf.png)
3. Verifique as alterações.

## Arquitetura

![Arquitetura](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/cost-model-architecture.png)

A linha de alocação do modelo de custo descreve o custo das soluções de mainframe que flui da origem do custo para mão de obra/fornecedor/ativos fixos/outros pools de custo para torres de recursos de TI para mainframes para aplicativos para serviços de negócios para unidade de negócios. Todas as linhas em cinza e pontilhadas mostram que esses objetos não fazem parte da solução Mainframe TCO.

Fluxo de linhagem

![Fluxo de linhagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/lineage-flow.png)

## Configurações

Essas alterações precisam ser feitas no TBM Studio

**Conjuntos de dados**

1. Carregue os dados recebidos da ferramenta Intellimagic como arquivo de entrada na categoria " **Mainframes** ". Crie uma coluna ' **Ponderação** ' usando uma fórmula personalizada.

   Nota:
   - Em Apptio, a ponderação distribui os custos entre dimensões como aplicativos, mão de obra e fornecedor. Ele se baseia em: MSU + ( zIIP \* 0.3 ), garantindo a alocação justa de custos com base no uso.
   - Você tem a flexibilidade de alterar a fórmula com base na preferência de peso da MSU. Aqui, a ponderação é baseada na soma de 100% do consumo de MSU do GCP e 30% do consumo de MSU do zIIP.

   ![Configurações](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/configurations-note.png)
2. Selecione **Salvar** e verifique as alterações.
3. Mapear o conjunto de dados do Intellimagic para o Mainframe Intellimagic Feed.

   ![Mapa de alimentação do Intellimagic](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/map-intellimagic-feed.png)
4. Mapeie os campos relevantes do arquivo de entrada para a tabela de alimentação do Mainframe Intellimagic, conforme mostrado abaixo.

   ![Mapear campos relevantes](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/map-relevant-fields.png)
5. Selecione **Salvar** e verifique as alterações.

   Observação: a tabela de alimentação do Mainframe Intellimagic deve ser revisada para garantir que seja mapeada corretamente para a tabela mestre do Mainframe, com todas as transformações necessárias criadas por meio do site formulas.Additionally personalizado; se forem adicionados novos campos personalizados, eles também deverão ser incluídos no mapeamento de acordo.

   ![Intellimagic](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/map-intellomagic.png)

     

   ![Colunas do mapa](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/map-columns.png)
6. Alocação de custos da torre de recursos de TI para o mainframe.
   - Selecione Metric Cost (Custo métrico) no menu suspenso Select a metric (Selecionar uma métrica).
   - No modelo, selecione a seção **Distribuição** > **Por ponderação** e escolha a coluna **Ponderação** nos dados mestre do mainframe.

     ![Torre de recursos de TI](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/cost-allocation-it-resource-tower.png)
   - Alocação de custos de torres de recursos de TI para mainframes concluída.

     ![Mainframe completo](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/complete-mainframe.png)
7. Selecione Salvar e verifique as alterações.
8. Alocação de MSU do GCP para o mainframe.
   - Em Modelo, selecione a métrica como GCP MSU e, em seguida, clique em **Adicionar driver de unidade**

     ![Adicionar driver de unidade](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/add-unit-driver.png)
   - Use a coluna **GCP CPU (MSU Consumption)** para preencher o driver e nomeie-o como **GCP MSU Unit Driver**.

     ![MSU GCP](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/gcp-msu.png)
   - Selecione **Save (Salvar** ) e Check in (Verificar) nas alterações para preencher os dados do GCP MSU no objeto Mainframes.

     ![Salvar alterações](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/save-gcp-msu.png)

   Observação: as MSUs do GCP são drivers de unidade específicos do objeto Mainframes e devem ser alocadas somente a partir do Mainframe. Essa alocação deve ser removida manualmente se houver alocação de qualquer outro objeto.

   ![Dispositivos de rede](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/network-devices.png)
9. zIIP Alocação de MSU para mainframe
   - Em Model (Modelo), selecione a métrica como zIIP MSU e, em seguida, clique em **Add Unit Driver (Adicionar driver de unidade)**

     ![Ziip MSU](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/ziip-msu.png)
   - Use a coluna **zIIP CPU (MSU Consumption)** para preencher o driver e nomeie-o como zIIP MSU Unit Driver.

     ![Driver Ziip MSU](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/ziip-msp-driver.png)
   - Selecione **Salvar** e verifique as alterações para preencher os dados do zIIP MSU no objeto Mainframes.

     ![Salvar](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/ziip-driver.png)

     Observação: zIIP MSUs são drivers de unidade específicos para objetos de Mainframes e devem ser alocados somente a partir do Mainframe. Essa alocação deve ser removida manualmente se houver alocação de qualquer outro objeto.

     ![Dispositivos de rede Ziip](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/ziip-network-devices.png)
10. Alocação de custos do mainframe para o aplicativo.
    - Selecione Metric Cost e, em seguida, selecione as métricas GCP MSU e zIIP MSU.
    - Clique na opção **Adicionar alocação** e escolha o objeto **Aplicativos** como destino.

      ![Adicionar alocações](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/add-allocations.png)
    - Na seção Distribuição, marque a caixa de seleção Relacionamento de dados e mapeie a origem e o destino pelo ID do aplicativo.

      ![ID do aplicativo](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/application-id.png)
    - Selecione **Salvar** e verifique as alterações.

## Relatório

O componente Mainframe tem quatro relatórios prontos para uso.

- **TCO do mainframe**
  - Visão abrangente do custo total e do consumo, combinando custos e GCP/zIIP MSUs em uma única tela.
  - Entenda as tendências de custo e uso ao longo do tempo e compare com os volumes de negócios e os custos unitários transacionais para identificar ineficiências e anomalias.
  - Divida os principais geradores de custos entre mão de obra, fornecedores e aplicativos, incluindo gastos por função, tipo de fornecedor e objetivo de investimento em aplicativos.
  - Um relatório de pesquisa está disponível na guia "Aplicativo" para obter mais detalhes sobre o aplicativo selecionado.
  - O relatório de pesquisa tem duas guias
    - **Custo** : Comparação entre custo e consumo com base na categoria selecionada, os valores mensais são mostrados em detalhes para o aplicativo selecionado.
    - **Métrica da unidade:** mostra o histórico detalhado do aplicativo selecionado, como "Família do aplicativo", "Objetivo do investimento" etc., juntamente com a comparação de duas métricas de negócios ao longo dos meses.

    ![Relatório de TCO do mainframe](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/mainframe-tco.png)
- **Análise de mainframe**
  - Visualize os custos e o consumo do mainframe em um formato de tabela flexível usando filtros e dimensões, métricas e tempo opcionais.
  - Veja o consumo do GCP e do zIIP MSU e compare diferentes tipos de processamento de carga de trabalho.
  - Analisar tendências em vários períodos de tempo - mensal, trimestral ou conforme necessário para relatórios.

  ![Análise de mainframe](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/mainframe-analysis.png)
- **Uso do mainframe**
  - Veja as tendências de consumo da MSU por categoria de carga de trabalho, ajudando os usuários a rastrear o uso em diferentes tipos de processamento.
  - Rastreie o uso por tipo de carga de trabalho, nome da linha de produtos, nome do produto e nome do aplicativo.
  - Monitore o consumo de MSU mês a mês com destaques condicionais que identificam mudanças significativas mês a mês.
  - As visualizações trimestre a trimestre e ano a ano ajudam a entender as tendências de consumo de longo prazo.

  ![Relatório de uso do mainframe](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/mainframe-usage-report.png)
- **Modelo de mainframe**
  - Visualize o fluxo de custos do início ao fim no modelo de custos.
  - Rastreie os geradores de custos subjacentes que alimentam o processador do mainframe, incluindo custos diretos do Razão (por exemplo, depreciação), bem como custos de mão de obra e de fornecedores.
  - Visualize como os dados de uso impulsionam a alocação do TCO do mainframe para os aplicativos de negócios.

  ![Modelo de mainframe](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/mainframe-model-report.png)
