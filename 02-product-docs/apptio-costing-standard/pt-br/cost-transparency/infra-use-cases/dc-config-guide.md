---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Custo Total de Propriedade (TCO) de Centros de Dados - Guia de Configuração"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso de infraestrutura"
  - "Datacenters"
source_path: "cost-transparency/infra-use-cases/dc-config-guide.html"
images:
  - "resources/images/ct_images/alternate-allocation-strategy.png"
  - "resources/images/ct_images/assumed-percentage-split.png"
  - "resources/images/ct_images/capacity-nx.png"
  - "resources/images/ct_images/capacity-reports.png"
  - "resources/images/ct_images/capacity-threshold-nx.png"
  - "resources/images/ct_images/capacity-threshold.png"
  - "resources/images/ct_images/cost-model-datacenter-config-guide.png"
  - "resources/images/ct_images/create-new-table.png"
  - "resources/images/ct_images/ct-apps-datacenter.png"
  - "resources/images/ct_images/data-center-enrichment-report.png"
  - "resources/images/ct_images/data-center-tco-components.png"
  - "resources/images/ct_images/datacenter-admin.png"
  - "resources/images/ct_images/datacenter-allocation-method.png"
  - "resources/images/ct_images/datacenter-analysys-nx.png"
  - "resources/images/ct_images/datacenter-enrichment-report-nx.png"
  - "resources/images/ct_images/datacenter-estimate-allocation.png"
  - "resources/images/ct_images/datacenter-feed.png"
  - "resources/images/ct_images/datacenter-review-nx.png"
  - "resources/images/ct_images/datacenter-review-report.png"
  - "resources/images/ct_images/datacenters-analysys-report.png"
  - "resources/images/ct_images/itresource=tower-datacenter.png"
  - "resources/images/ct_images/legacy-allocation-strategy.png"
  - "resources/images/ct_images/lineage-flow-diagram.png"
  - "resources/images/ct_images/mainframe-object.png"
  - "resources/images/ct_images/map-field-datacenter.png"
  - "resources/images/ct_images/project-settings-ribbon-dc-cg.png"
  - "resources/images/ct_images/server-object.png"
  - "resources/images/ct_images/steps-raw-intake-table.png"
  - "resources/images/ct_images/storage-object.png"
  - "resources/images/ct_images/table-upload-method.png"
  - "resources/images/icons/datacenters.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Custo Total de Propriedade (TCO) de Centros de Dados - Guia de Configuração

## Visão geral

**Que problema estamos resolvendo?**

A solução aborda a crescente complexidade e as pressões de custo associadas aos data centers modernos, incluindo o aumento das cargas de trabalho de IA, a maior demanda energética e as restrições de capacidade. Muitas vezes, as organizações não dispõem de uma visão unificada dos custos, do consumo e das limitações da infraestrutura, o que dificulta o planejamento de estratégias de expansão, consolidação ou migração. O TCO do Data Center oferece uma visão abrangente dos custos, da capacidade e das limitações do data center, a fim de apoiar decisões de investimento de longo prazo bem fundamentadas.

**Para quem estamos resolvendo o problema?**

Entre os principais públicos-alvo estão a liderança de TI, o departamento financeiro de TI, proprietários de instalações de data center, proprietários de infraestrutura, proprietários de aplicativos, proprietários de produtos e proprietários de serviços que precisam de visibilidade sobre custos e capacidade.

**Como estamos resolvendo isso?**

IBM Apptio O TCO de Data Center é um conjunto de conteúdos pré-definidos, desenvolvido para a Norma de Cálculo de Custos da IBM Apptio, que inclui relatórios, tabelas e elementos de modelo de dados para ajudar as organizações a compreender o custo total, a capacidade e as restrições operacionais de sua infraestrutura de data center. Ele oferece uma visão abrangente e consistente da economia por unidade e dos recursos de infraestrutura, como energia, refrigeração, espaço e densidade de rack, para apoiar melhores decisões operacionais e de investimento.

## Casos de uso

1. **Entenda a estrutura de custos do seu data center**
   - **Custo total e economia por unidade:** obtenha uma visão consolidada dos gastos por local e região, com custos unitários como $/ $/kW, $/rack e $/m² para identificar ineficiências.
   - **Transparência dos fatores de custo:** veja como os custos se distribuem entre contratos de energia, mão de obra e fornecedores para justificar o custo total de propriedade (TCO) e tomar decisões mais inteligentes em matéria de preços e compras
2. **Identificar e otimizar a utilização da capacidade e as restrições**
   - **Visibilidade da utilização da capacidade e das restrições por unidade:** Identifique a utilização, as restrições e a margem de manobra por unidade para detectar antecipadamente o excesso de capacidade e os gargalos e planejar com antecedência.
   - **Visibilidade dos custos de fornecedores e contratos:** Entenda como os contratos de instalações e fornecedores influenciam os custos nas unidades, permitindo uma gestão proativa de preços, compras e otimização de contratos.
3. **Melhorar a prestação de contas sobre o consumo do data center**

   - **Alocação de custos de computação e armazenamento:** alocar os custos do data center aos servidores e ao armazenamento para estabelecer uma economia unitária justificável e dar suporte a processos de showback/chargeback.
   - **Visibilidade dos custos de infraestrutura, aplicativos, produtos e serviços:** identifique quais infraestruturas, aplicativos, produtos e serviços estão gerando gastos no data center para melhorar a prestação de contas entre as unidades de negócios.

## Pré-requisitos

São necessários os seguintes pré-requisitos para a solução de TCO do Data Center:

- IBM Apptio Norma de cálculo de custos
- Versão do servidor: Pré-visualização pública - 12.11.21, Lançamento geral -12.11.22 ou posterior
- Versão dos componentes v120

## Instalação de componentes

Observação: Antes de continuar, verifique se a versão dos componentes do seu projeto está definida como “Versão 120”.

Consulte este guia para obter mais informações — [Instalação de novas soluções de cálculo de custos IBM Apptio em projetos com modelos antigos](../configuration/config-instnew.html)

- Na faixa de opções “Projeto”, clique no botão “**Configurações do projeto** ”.
- Verifique ou defina a versão dos componentes como “Versão 120”.

  ![Configurações do projeto](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/project-settings-ribbon-dc-cg.png)
- Clique no botão **Salvar**.

**A solução de TCO** para data centers é implementada por meio de dois componentes.

- **Custo Total de Propriedade (TCO) de Centros de Dados:** Este componente instala os conjuntos de dados, tabelas editáveis, métricas, lógica de alocação e estruturas de dados essenciais necessárias para analisar as operações dos centros de dados e estabelecer uma economia de unidade justificável entre locais e instalações. Este componente é necessário antes de instalar qualquer um dos componentes de relatórios abaixo.
- **Relatórios de TCO de data centers** : instala os relatórios clássicos para a elaboração de relatórios e análises de TCO de data centers.
- **Relatórios de TCO de data centers no NX** : instala os relatórios do NX para a geração de relatórios e análise do TCO de data centers.

Os clientes podem instalar o componente de relatórios Classic ou NX, de acordo com sua preferência em termos de experiência com relatórios. No entanto, o componente de TCO dos data centers básicos deve ser instalado primeiro em todos os cenários.

![Componentes do custo total de propriedade (TCO) dos data centers](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/data-center-tco-components.png)

## Requisitos de dados

A solução de TCO para data centers requer três categorias principais de dados para permitir a análise de custos, capacidade e alocação:

1. **Dados financeiros (via IT Resource Towers)**

   Dados financeiros, como custos com fornecedores e mão de obra, são importados por meio de integrações padrão de cálculo de custos e mapeados para as Torres de Recursos de TI. Os custos devem ser classificados em uma subtorre contida na torre de Recursos de TI = Torre do Data Center, para que sejam registrados no nível do data center.
2. **Dados de uso (tabela de feed dos data centers)**

   Os dados operacionais e de capacidade devem ser fornecidos na tabela “Data Centers Feed” para permitir a geração de relatórios e a análise da rentabilidade por unidade. Verifique os dados necessários.

   [![](../../../../../03-media/apptio-costing-standard/resources/images/icons/datacenters.png)](../../resources/data-center-tco-data-advisor.xlsx "(Abre em uma nova guia ou janela)")

   Isso inclui métricas obrigatórias, tais como:
   - Uso e capacidade do rack (RU)
   - Consumo de energia e capacidade ( kW )

   As métricas opcionais, mas recomendadas, incluem:
   - Utilização e capacidade do espaço (em metros quadrados)
   - Consumo e capacidade de refrigeração

   Essas métricas são normalmente obtidas de sistemas DCIM, BMS, de gerenciamento de energia ( LogicMonitor, ) ou de instalações, e são essenciais para calcular a utilização, identificar ineficiências e possibilitar alocações baseadas em fatores determinantes.

   Use as tabelas editáveis disponíveis para aprimorar os dados de uso.
3. **Metadados (para alocação e enriquecimento)**

   Os metadados enriquecem os relatórios e apoiam a lógica de alocação. Os principais campos incluem:

   - Identificadores principais: ID do data center, nome, região, nível (obrigatórios para alocação e geração de relatórios)
   - Atributos adicionais: Localização, Tipo de instalação (própria, alugada, colocation), Centro de custo, Nome do serviço (também usado como Nome do produto)
   - Contexto operacional: Gerente, Objetivo, Nível de certificação, Status de nomeação

   Esses dados são normalmente obtidos da CMDB (por exemplo, ServiceNow ) e de sistemas de gestão de instalações.

   Use as tabelas editáveis disponíveis para enriquecer os metadados.

## Lógica de alocação

**Torre de Recursos de TI →** Custos de Alocação do Data Center atribuídos à torre do Data Center são alocados a data centers individuais por meio de uma lógica de ponderação predefinida. Por padrão, isso utiliza uma combinação de:

- Área ocupada do data center
- Porcentagem de alocação de infraestrutura

**Centro de Dados → Alocação de Infraestrutura** Os custos do centro de dados são posteriormente alocados a componentes de infraestrutura, como servidores, armazenamento e mainframe.

Essa alocação é normalmente determinada por:

- Alinhamento de localização
- Fatores baseados no uso, como horas de servidor, armazenamento (GB/TB) ou consumo de mainframe (MIPS/MSUs)

Esses métodos de alocação são configuráveis e podem ser adaptados para refletir o modelo de consumo mais preciso ou as regras específicas da sua empresa.

**LEMBRETE:** O TCO do data center concentra-se nos custos das instalações e operacionais, incluindo:

- Energia e potência
- Refrigeração
- Espaço (alugado, em colocation ou instalações próprias)
- Manutenção e operações
- Segurança
- Custos com mão de obra e outras despesas relacionadas às instalações

- Isso **exclui** os custos com hardware de infraestrutura, como servidores, armazenamento e dispositivos de rede. Esses ativos de infraestrutura estão incluídos nas seções seguintes do modelo de custos, conforme ilustrado na seção “Arquitetura” deste documento.

## Arquitetura

Modelo de custos

![Modelo de Custo](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/cost-model-datacenter-config-guide.png)

Opções para alocação de rede (Caso de uso avançado)

- **Opção 1: Estratégia de alocação tradicional**

  ![Estratégia de Alocação Tradicional](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/legacy-allocation-strategy.png)

  **Pontos importantes a considerar:**
  - É mais preciso quando se dispõe de dados detalhados sobre os dispositivos de rede localizados em cada data center e sobre o consumo de energia, espaço e refrigeração associado a eles.
  - Requisitos mais exigentes em termos de dados e configuração, uma vez que são necessários dados detalhados da infraestrutura para alocar os custos compartilhados do data center à rede.
  - Mais adequado para ambientes maduros, com dados detalhados sobre ativos e utilização.
- **Opção 2: Estratégia alternativa de alocação**

  ![Estratégia de alocação alternativa](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/alternate-allocation-strategy.png)

  **Pontos importantes a considerar:**
  - Mais simples de implementar, já que os custos de rede podem ser alocados aos data centers com base em um critério de alto nível, como a localização.
  - Requisitos de dados reduzidos, facilitando a configuração quando não há dados detalhados disponíveis no nível do dispositivo.
  - Oferece uma aproximação prática, mantendo a flexibilidade de tratar a Rede como uma torre separada.Mais adequado para ambientes maduros, com dados detalhados sobre ativos e utilização.

Nota:

Para direcionar os fluxos de alocação da Rede para os Centros de Dados ou dos Centros de Dados para a Rede, certifique-se de que possui os dados necessários e personalize a alocação.

**Diagrama de fluxo de linhagem**

![Fluxo de linhagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/lineage-flow-diagram.png)

## Configuração

**Conjuntos de dados** Siga estas etapas para preencher a tabela principal “Data Centers Feed”:

1. Acesse o **TBM Studio**.
2. Carregue os dados brutos do data center de entrada em uma tabela de entrada personalizada. A seguir, apresentamos a nossa sugestão de nome para sua tabela de entrada personalizada (onde os colchetes e o texto entre colchetes devem ser substituídos pelos valores de sua escolha): Centros de Dados de [Nome do Sistema de Origem] Bruto
3. Não recomendamos adicionar etapas às tabelas de entrada de dados brutos. Idealmente, o pipeline de etapas de cada tabela bruta deve ter a aparência da captura de tela abaixo.

   ![Passos - Tabela de ingestão de alimentos crus](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/steps-raw-intake-table.png)
4. Depois de criar uma tabela de entrada bruta, transforme a tabela clicando com o botão direito do mouse na etapa “Tabela” e selecionando **“Criar nova tabela a partir desta etapa”**

   ![Criar nova tabela](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/create-new-table.png)
5. Dê à nova tabela o mesmo nome da tabela de entrada bruta, sem o sufixo “Bruta”.
6. Abra a tabela transformada e adicione uma etapa “Map Columns”, posicionando-a como a etapa anterior à etapa “Table”.
7. No menu suspenso “**Selecionar destino** ”, selecione “**Feed de data centers** ”.

   ![Feed do Data Center](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/datacenter-feed.png)
8. Mapeie os campos da sua tabela de transformação para os campos da tabela **do Feed dos Centros de Dados**.

   ![Campo do mapa](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/map-field-datacenter.png)
9. **Salve** e confirme suas alterações.

**Tabelas**  
 editáveisEsta seção de Tabelas editáveis é utilizada para o enriquecimento opcional de dados. A solução de TCO para data centers funcionará corretamente mesmo sem essa etapa. No entanto, permite que valores adicionais ou corrigidos sejam incorporados, quando necessário. A lógica aplicada garante que os valores da Tabela Editable só sejam utilizados quando os campos correspondentes no conjunto de dados principal estiverem em branco, estiverem incorretos ou incompletos, o que significa que os dados existentes não são substituídos.

**Relatório de aprimoramento de data centers** Use o relatório de aprimoramento de data centers (na coleção de relatórios do Workbench) para aprimorar ou enriquecer os dados do seu data center.

![Relatório de Aprimoramento de Centros de Dados](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/data-center-enrichment-report.png)

**Relatório de administração de centros de dados** Use este relatório para gerenciar os métodos de alocação e as ponderações de alocação para os centros de dados em questão.

Na guia "**Método de** alocação": selecione um método alterando sua seleção para **"Sim"** entre os dois métodos disponíveis para alocar os custos dos data centers aos recursos de computação e armazenamento:

- **Divisão percentual padrão** : selecione esta opção para aplicar uma divisão percentual fixa entre Compute e Storage em todos os data centers. Use esta opção quando não houver dados de alocação detalhados disponíveis.
- **Método de importação de tabela** : Selecione esta opção para alocar custos com base em dados detalhados (por exemplo, consumo de energia). Isso permite a alocação a nível de cada data center.

Clique em **“Salvar”** e, em seguida**, em “Publicar”** para aplicar a seleção.

![Administrador de Data Center](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/datacenter-admin.png)

Se a opção **“Divisão percentual presumida”** estiver definida como **“Sim”**, acesse a guia **“Estimativa de alocação”** e siga as instruções na tela para aplicar as atualizações.

![Distribuição percentual estimada](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/assumed-percentage-split.png)

Se a opção **“Método de upload da tabela”** estiver definida como **“Sim”**, acesse a guia **“Upload da tabela de alocação”** e siga as instruções na tela para aplicar as atualizações.

![Método de envio de tabelas](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/table-upload-method.png)

Guia “**Limite de capacidade** ”: use esta guia para definir os valores do “Limite de baixa utilização (%)” e do “Limite de alta utilização (%)” para diferentes tipos de capacidade.

- **O “Limite de baixa utilização (%)”** identifica recursos subutilizados que podem indicar excesso de capacidade ou oportunidades de otimização.
- **O “Limite de alta utilização (%)”** identifica recursos que estão se aproximando dos limites de capacidade e riscos operacionais potenciais.

Cada tipo de capacidade pode ter um limite diferente, com base em considerações operacionais.   
Por exemplo:

- **Área útil (m²):** Ajuda a identificar restrições de espaço ou oportunidades de consolidação.
- **Unidades de rack:** Os limites podem ser configurados com base na capacidade instalada do rack e nas necessidades de expansão.
- **Potência ( kW ):** Limites altos indicam que a infraestrutura de energia está se aproximando dos limites, enquanto limites baixos podem indicar excesso de capacidade ociosa.
- **Refrigeração ( kW ):** Limites altos ajudam a identificar riscos de saturação do sistema de refrigeração, enquanto limites baixos podem indicar um excesso de capacidade de refrigeração

Esses limites facilitam o planejamento proativo da capacidade e o monitoramento da utilização em todo o data center.

Os valores-limite atuais são fornecidos como orientações gerais e podem ser atualizados de acordo com os requisitos da organização e as necessidades operacionais.

Siga as instruções na tela para atualizar os valores limite.

![Limite de capacidade](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/capacity-threshold.png)

**Alocações** Siga estas etapas para concluir a configuração da alocação:

1. Abra o TBM Studio.
2. Acesse o objeto **“Centros de Dados”** e dê uma olhada.
3. Se o componente “CT Apps - Data Centers” tiver sido instalado, adicione o campo **Infraestrutura** ao identificador do objeto **Data Centers**. Se o componente **TCO do** Data Centers tiver sido instalado pela primeira vez, siga as etapas a seguir.

   ![Centros de dados da CT Apps](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/ct-apps-datacenter.png)
4. Acesse o objeto **“IT Resource Towers”** e dê uma olhada.
5. Defina a métrica como **"Custo"**.
6. Abra a estratégia de alocação associada ao objeto Data Centers.
7. Na seção "Distribuição", defina as seguintes opções:
   - Ativar “Peso por”
   - Selecione a opção “Coluna da tabela” e defina a coluna como “Ponderação” da tabela **Dados Mestres dos Centros de Dados**.

   ![Da Torre de Recursos de TI ao Data Center](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/itresource=tower-datacenter.png)
8. Acesse a página “Data Centers” em object.\
9. Abra a estratégia de alocação associada ao objeto **Servidores** e defina as seguintes opções, conforme mostrado na captura de tela abaixo:
   - Na seção “De”, defina o filtro de forma que o campo **“Data Centers Master” Data.Infrastructure** seja igual a “Compute”.
   - Na seção "Distribuição", defina as seguintes opções:
     - Ativar “Peso por”
     - Selecione a opção “Coluna da tabela” e defina a coluna como “Horário do servidor” da tabela **Servidores**.
     - Ative a opção “Relação de dados” e faça a correspondência com base no seguinte:
     - Localização = LocalizaçãoFeche a estratégia de alocação associada ao objeto Servidores.

   ![Objeto Servidor](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/server-object.png)
10. Com o objeto **"Data Centers"** ainda aberto, prossiga para a próxima etapa.
11. Abra a estratégia de alocação associada ao objeto **de armazenamento** e defina as seguintes opções, conforme mostrado na captura de tela abaixo:
    - Na seção “De”, defina o filtro de forma que o campo **“Data Centers Master” Data.Infrastructure** seja igual a “Armazenamento”.
    - Na seção "Distribuição", defina as seguintes opções:
      - Ativar “Peso por”
      - Selecione a opção “Coluna da tabela” e defina a coluna como “Espaço utilizado” da tabela **Dados Mestres de Armazenamento**.
      - Ative a opção “Relação de dados” e faça a correspondência com base no seguinte:
      - Localização = Localização

    ![Objeto de armazenamento](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/storage-object.png)
12. Abra a estratégia de alocação direcionada ao objeto Mainframes e defina as seguintes opções, conforme mostrado na captura de tela abaixo:
    - Na seção “De”, configure o filtro para que o campo **“Data Centers Master” Data.Infrastructure** seja igual a “Mainframe”.
    - Na seção "Distribuição", defina as seguintes opções:
      - Ative a opção “Relação de dados” e faça a correspondência com base no seguinte:
      - Localização = Localização

    ![Objeto de mainframe](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/mainframe-object.png)
13. **Salve** e confirme as alterações.
14. Selecione a métric **CapEx** e e configure as alocações da mesma forma que as alocações da métrica de Custo.

## Relatório

Além do relatório de administração de data centers, a solução de TCO para data centers inclui três relatórios principais:

1. **Relatório de análise de data centers**

   **Destinado a:** Proprietários de data centers/instalações, executivos, profissionais de TI e finanças

   **Principais benefícios:**

   - Identifique os principais data centers por custo e área ocupada e compare por região, gestor, tipo de instalação (colocação / alugado) e nível
   - Compreender os fatores que influenciam o custo total de propriedade (TCO), incluindo energia, refrigeração, mão de obra e gastos com fornecedores
   - Veja os custos unitários para comparar locais de data centers, incluindo $/kW, $/rack e $/m²

   Compare locais de data centers, identifique ineficiências e oriente as decisões relativas a investimentos, consolidação e planejamento de capacidade.

   ![Relatório de Avaliação de Centros de Dados](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/datacenter-review-report.png)
2. **Relatório de análise de centros de dados**

   **Destinatários:** Analistas de TI, Finanças e Infraestrutura

   **Principais benefícios:**

   - Visualize os custos e o consumo do Data Center em um formato de tabela flexível, utilizando filtros e dimensões, métricas e intervalos de tempo opcionais.
   - Visualizar o consumo de energia, a área útil, as unidades de rack e o resfriamento, e comparar com a capacidade
   - Analise tendências em diferentes períodos — mensais, trimestrais ou conforme necessário para a elaboração de relatórios.

   ![Relatório de análise de centros de dados](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/datacenters-analysys-report.png)
3. **Relatório de capacidade**

   **Para:** Proprietários de data centers / instalações

   **Principais benefícios:**

   - Compreender a capacidade total das instalações do data center em termos de energia, refrigeração e espaço
   - Monitorar a utilização da capacidade para identificar áreas de restrição
   - Melhore a utilização das instalações e identifique a capacidade disponível antes de investir em expansão

   Identifique a capacidade potencial e as limitações dos seus data centers para otimizar de forma proativa e planejar expansões com confiança

   Nota:

   Os destaques do relatório indicam a utilização da capacidade total com base na porcentagem limite.

   - Se a utilização for superior ao limite de alta utilização (%): Rosa
   - Utilização < Limite inferior de utilização (%): Amarelo
   - A utilização está entre o % do limite superior de utilização e o % do limite inferior de utilização: Branco

   ![Relatório de capacidade](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/capacity-reports.png)

**Relatórios sobre a modernização da interface do usuário:**

1. **Relatório de aprimoramento de data centers**

   ![Relatório de aprimoramento de data centers](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/datacenter-enrichment-report-nx.png)
2. **Relatório do administrador do data center**
   - **Método de alocação:**

     ![Método de alocação](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/datacenter-allocation-method.png)
   - **Alocação de orçamento:**

     ![Alocação de orçamento](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/datacenter-estimate-allocation.png)
   - **• Limite de capacidade:**

     ![Limite de capacidade](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/capacity-threshold-nx.png)
3. **Relatório de análise de data centers**

   ![Relatório de análise de data centers](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/datacenter-review-nx.png)
4. **Relatório de análise de centros de dados**

   ![Relatório de análise de centros de dados](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/datacenter-analysys-nx.png)
5. **Relatório de capacidade**

   ![Relatório de capacidade](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/capacity-nx.png)
