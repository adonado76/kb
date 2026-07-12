---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "billing-essentials"
title: "Configuração"
breadcrumb: []
source_path: "billing-essentials/configure-billing-essentials/configuration.html"
images:
  - "resources/images/be/be-flowchrt.jpg"
  - "resources/images/be/be-s9.jpg"
  - "resources/images/be/billing-charge.jpg"
  - "resources/images/be/s7-sl.jpg"
  - "resources/images/studio_images/alloc-chrt.jpg"
  - "resources/images/studio_images/be-tu1.jpg"
  - "resources/images/studio_images/be-tu2.jpg"
  - "resources/images/studio_images/be-tu3.jpg"
  - "resources/images/studio_images/be-tu4.jpg"
  - "resources/images/studio_images/be-tu5.jpg"
  - "resources/images/studio_images/becomp-1.jpg"
  - "resources/images/studio_images/bes11.jpg"
  - "resources/images/studio_images/bes11chrg.jpg"
  - "resources/images/studio_images/bes11pc.jpg"
  - "resources/images/studio_images/bes11pu.jpg"
  - "resources/images/studio_images/bes9.jpg"
  - "resources/images/studio_images/besolution.jpg"
  - "resources/images/studio_images/cons-feed.jpg"
  - "resources/images/studio_images/df-chart.jpg"
  - "resources/images/studio_images/mc-be.jpg"
  - "resources/images/studio_images/s8.jpg"
  - "resources/images/studio_images/samp-ref.jpg"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configuração

1. (TBM Studio): Criar um projeto.
2. (TBM Studio): Billing Essentials oferece suporte a várias moedas. Consulte [aqui](multi-currency.html) os detalhes da configuração.
3. (TBM Studio): Configure as definições de horário e verifique as alterações.
4. (TBM Studio): Instalar o componente **Billing- Charge** no projeto. ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/be/billing-charge.jpg) ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/becomp-1.jpg)
5. (TBM Studio): Crie duas tabelas de entrada para garantir que os detalhes relevantes sejam carregados.
   - Nome da tabela: Feed de consumo
   - Nome da tabela de alimentação: Biblioteca de soluções

     Amostra para referência:

     O nome das tabelas pode ser específico do cliente

     ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/samp-ref.jpg)
6. (TBM Studio): Salvar e registrar as alterações.
7. (TBM Studio): Essas tabelas devem ser mapeadas para as tabelas Master/Feed, conforme mostrado abaixo

   Consumo de ração (tabela Consumo de ração)

   ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/cons-feed.jpg)

   Alimentação da biblioteca de soluções (tabela da biblioteca de soluções)

   ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/be/s7-sl.jpg)

   *\*\* Se a coluna de origem a ser mapeada estiver ausente, certifique-se de que o tipo de dados correto para a coluna esteja especificado na seção "Type Override" na transformação "Import" da tabela*
8. (TBM Studio): Salvar e registrar as alterações.

   Nota:
   - Se houver alguma alteração, carregue a tabela de entrada em uma base adhoc/mensal para garantir a precisão dos relatórios
   - Verifique se a fórmula "Billable" (Faturável) destacada abaixo está presente no Solution Master para garantir que os dados precisos sejam preenchidos nos relatórios

   ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/s8.jpg)

   Relatório de gerenciamento de tarifas (o componente "Billing Charge- Reporting" deve ser instalado)
9. (Visualização de relatório): Navegue até Faturamento > Gerenciamento de tarifas.

   Limpe o filtro de "Billable" para revelar todas as ofertas. Use essa tabela para editar a coluna "Billable" (faturável) como "Yes" (sim) ou "No" (não). Além disso, as atualizações das colunas "Base Rate" e "Rate Management" podem ser aplicadas para definir a taxa faturável, se necessário

   - Tarifa **básica** - Tarifa inicial estabelecida com base no custo unitário de Costing Essentials
   - **Ajuste de taxa** - Insira um número positivo ou negativo para calcular e ajustar a taxa faturável (taxa faturável = taxa básica + ajuste de taxa), calculada por meio do script ET
   - **Impacto do** ajuste da taxa - Usado para identificar claramente a cobrança versus a recuperação de custos como resultado do ajuste da taxa

   Selecione **Salvar** e, em seguida, **Publicar** para propagar para todos os relatórios e modelos, "Solution Library ET Transform"

   ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/be/be-s9.jpg)

   ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/bes9.jpg)

   \*\* Depois de publicado, verifique se o filtro "Faturável" está definido como "Sim" para ver o valor da cobrança no relatório.
10. (TBM Studio): Navegue até Tables > Solution Library ET Transform e revise os dados após a publicação na Etapa 10. Além disso, uma publicação recorrente pode ser definida para essa tabela. Para obter mais informações, consulte [Publicação recorrente da tabela de transformação](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=administration-recurring-publish-transform-table "(Abre em uma nova guia ou janela)").
11. (TBM Studio): Abra o Modelo de Consumo e verifique as alocações

    Unidades faturáveis

    ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/bes11.jpg)

    *\*\* Esta captura de tela serve como referência, pois as alocações de custo variam de acordo com os dados.*

    **Carga**

    ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/bes11chrg.jpg)

    *\*\* Esta captura de tela serve como referência, pois as alocações de custo variam de acordo com os dados.*

    Cobrança de plano

    ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/bes11pc.jpg)

    *\*\* Esta captura de tela serve como referência, pois as alocações de custo variam de acordo com os dados.*

    Unidades planejadas

    ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/bes11pu.jpg)

    *\*\* Esta captura de tela serve como referência, pois as alocações de custo variam de acordo com os dados.*

    Além disso, verifique as alocações no modelo **Solutions** para as métricas mencionadas acima

    ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/besolution.jpg)

    *\*\* Esta captura de tela serve como referência, pois as alocações de custo variam de acordo com os dados.*

    Fluxograma de dados

    ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/df-chart.jpg)

    Gráfico de alocação

    ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/alloc-chrt.jpg)

    ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/be/be-flowchrt.jpg)

**Multi-moeda**

Se o cliente usa várias moedas, esse seria um bom momento para configurar isso. A multimoeda é a mesma em Costing Essentials e em projetos de CT. Você pode consultar a configuração de várias moedas na Central de Ajuda.

No entanto, se o seu cliente usar um calendário não gregoriano, a versão mais recente do MCC não é compatível com o calendário não gregoriano. Se o seu cliente precisar de um calendário não gregoriano, siga a configuração de várias moedas legadas aqui.

Selecione a **moeda base** preferida.

![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/mc-be.jpg)

**Upload de tabelas**

O componente **Table Upload** permite que os usuários finais com as permissões adequadas **carreguem** diretamente os dados das planilhas para as tabelas sem a necessidade de acesso ao site TBM Studio . O relatório Uploads de tabela consiste em duas guias: Upload de tabela e Acesso ao upload de tabela.

**Guia Uploads de tabelas**

A guia Table Uploads ajudará os usuários a fazer upload de dados diretamente para o Consumption/General Ledger, Budget e Labor sem a necessidade de acesso ao site TBM Studio .

Navegue até Workbench > Uploads de tabela > Upload de tabela, conforme mostrado:

![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/be-tu1.jpg)

O componente de upload de tabela oferece duas opções de configuração: [Configuração simples](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=reports-table-upload-component#TableUploadcomponent__Simpleconfiguration__title__1 "(Abre em uma nova guia ou janela)") e [Configuração avançada](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=reports-table-upload-component#TableUploadcomponent__Advancedconfiguration__title__1 "(Abre em uma nova guia ou janela)"). Neste exemplo, ele está equipado com Advanced Configuration, permitindo a correspondência de usuários na guia Table Upload Access.

![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/be-tu2.jpg)

**Guia Acesso ao upload de tabelas**

A guia Table Uploads Access ajudará os administradores a gerenciar o acesso a quem pode fazer o upload direto de dados para o Consumption/General Ledger, Budget e Labor sem a necessidade de acesso a TBM Studio .

Navegue até Workbench > Uploads de tabela > Upload de tabela > Acesso ao upload de tabela, conforme mostrado:

![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/be-tu3.jpg)

Conceda acesso de upload de tabela especificando o nome da tabela e os detalhes do usuário correspondente para permitir que eles façam upload de dados na tabela designada, conforme mostrado abaixo.

![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/be-tu4.jpg)

![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/be-tu5.jpg)

*\*\* A visibilidade da guia pode ser personalizada com base nos requisitos do cliente para controlar quais funções de usuário têm acesso à guia "Table Upload Access" no relatório Table Upload.*

Para obter mais informações, consulte [Tabela Upload](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=reports-table-upload-component "(Abre em uma nova guia ou janela)").
