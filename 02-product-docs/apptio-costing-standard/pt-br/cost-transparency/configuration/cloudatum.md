---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Configuração da nuvem e ATUM 2.0"
breadcrumb: []
source_path: "cost-transparency/configuration/cloudatum.html"
images:
  - "resources/images/ct_images/7988_2.png"
  - "resources/images/ct_images/7988_3.png"
  - "resources/images/ct_images/7988_4.png"
  - "resources/images/ct_images/7988_5.png"
  - "resources/images/ct_images/7988_6.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Configuração da nuvem e ATUM 2.0

Este artigo explica algumas atualizações de configuração relacionadas a ATUM 2.0 e Public Cloud se forem necessárias modificações nos conjuntos de dados mestre (Cloud \ ITRT) para dar suporte à taxonomia ATUM 2.0. As alterações a seguir configuram ATUM 2.0, com uma seção adicional que mostra uma transformação de servidores que anexa os dados mestre do servidor para Public Cloud com um filtro que precisa ser removido para permitir que os dados sejam exibidos.

**AVISO**

Na lista de torres de recursos de TI que vem pronta para uso, as torres e subtorres não são identificadas como sendo Public Cloud, portanto, você precisará atualizar essa lista para incluir subtorres com Public Cloud.

Aplica-se a: Cloud for Costing Standard em TBM Studio 12.4.1 e posterior.

## Alterações de configuração

Provedor de serviços em nuvem
:   1. Anexe o AWS Cost Allocation Bill Master e, em seguida, altere a coluna Product para ProductCode.
    2. Na seção Fórmulas, atualize Instance Type, Subtower, Tower, Type, Unit da seguinte forma:
       1. Para o tipo de instância, mapeie para =Lookup(Lookup,Cloud Service Provider Lookup v2,Lookup,Instance Type).
       2. Para Subtower, mapeie para=Lookup(Lookup,Cloud Service Provider Lookup v2,Lookup, {SubTower 2.0} ).
       3. Para Tower, map to=Lookup(Lookup,Cloud Service Provider Lookup v2,Lookup, {Tower 2.0} ).
       4. Para Type,map to=Lookup(Lookup,Cloud Service Provider Lookup v2,Lookup,Type ).
       5. Para a unidade, map to=Lookup(Lookup,Cloud Service Provider Lookup v2,Lookup,Unit ).
       6. Alterar Lookup para =Product&&Item&&Procedure.
    3. Net new é Product.
    4. Somente para ATUM 1.0, utilize Item&&Procedimento.
:   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/7988_2.png)

Dados mestre de recursos de TI
:   1. Na seção Fórmulas, altere Is Cloud para Public Cloud=Yes, pois o relatório de nuvem pública abaixo tem um filtro para Is Cloud.

       Por padrão, o Is Cloud examina a subnível de recursos de TI e, em seguida, volta ao arquivo de pesquisa para determinar o valor, mas alterá-lo para examinar o arquivo v2 inflaria demais os custos nos relatórios de nuvem pública porque sinalizaria subníveis não relacionados à nuvem.

       ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/7988_3.png)
    2. Anexe o sinalizador Public Cloud ao campo de metadados no IT Resource Tower Master Data. Isso separa os custos não relacionados à nuvem dos custos relacionados à nuvem.![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/7988_4.png)

    Os relatórios de nuvem são configurados para filtrar o valor Is Cloud, definido acima.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/7988_5.png)

## Os servidores em nuvem se transformam para Public Cloud

Para ATUM 2.0 e a transformação dos servidores de nuvem, altere o filtro para Cloud Compute Linux e Windows para incluir Compute - Servers - Public Cloud, conforme mostrado.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/7988_6.png)

Para obter informações sobre o mapeamento dos serviços AWS, consulte [AWS Services Mapping](awsservices.html "Apptio os conectores CBM e AWS DataLink da TBM permitem mapear os itens de linha de faturamento dos itens de linha de faturamento do provedor de nuvem para os atributos do site ATUM, incluindo torres e subtorres de TI, a hierarquia de serviços da TBM, bem como uma unidade de medida normalizada.").

Para obter informações sobre o mapeamento dos serviços Azure, consulte [Azure Services Mapping.](azuremap.html "Apptio os conectores CBM e AWS DataLink da TBM permitem mapear os itens de linha de faturamento dos itens de linha de faturamento do provedor de nuvem para os atributos do site ATUM, incluindo torres e subtorres de TI, a hierarquia de serviços da TBM, bem como uma unidade de medida normalizada.")

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
