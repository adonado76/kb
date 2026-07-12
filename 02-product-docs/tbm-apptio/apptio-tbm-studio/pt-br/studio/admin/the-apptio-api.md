---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "API da plataforma"
breadcrumb: []
source_path: "studio/admin/the-apptio-api.html"
images:
  - "resources/images/studio_images/studioimages/studio_diagram_api.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# API da plataforma

**Aplica-se a** : TBM Studio 12.0 e posterior

Observação: na versão 12.9 e superior, inclua os seguintes valores de cabeçalho em todas as chamadas de API para a API da plataforma.

tipo de aplicativo="Flagship"

versão do aplicativo="NA"

Isso inclui chamadas de API que fazem upload ou download em Costing Standard ou em outros projetos de plataforma. Esses cabeçalhos são adicionais aos cabeçalhos de API existentes que você já pode estar usando.

Apptio pode ser usada para implementar a automação com script de uploads de dados para projetos Apptio ou download de dados de projetos Apptio. Essa API é fornecida como uma alternativa ao produto Apptio Datalink . Datalink (Classic) não exige que o usuário tenha uma habilidade especializada em scripts e tem sua própria API para ajudar na integração com ferramentas ETL de terceiros.

Alguns motivos típicos pelos quais a API da plataforma Apptio pode ser usada em vez da Datalink (Classic)são os seguintes:

- A incapacidade de instalar um agente no local Apptio Datalink (Classic) para fazer upload de dados de fontes no local
- O desejo de usar scripts incorporados em uma ferramenta de ETL de terceiros

A API do Apptio fornece um link direto entre os dados corporativos e o Apptio por meio de comandos simples. Os comandos descrevem como os dados são postados em Apptio e extraídos de Apptio, incluindo onde colocar os dados e o período de tempo apropriado.

Por exemplo, você pode fazer upload de dados mensais ou trimestrais de utilização do servidor ou de dados do razão geral para garantir que os relatórios estejam atualizados. Além disso, você pode fazer download de dados dos conjuntos de dados e componentes de relatórios do site Apptio.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_diagram_api.png)

Os comandos podem ser integrados a qualquer agendador de tarefas, adicionados a qualquer aplicativo personalizável com algumas linhas de código ou emitidos diretamente de uma linha de comando.

A simplicidade e a versatilidade da API têm muitos benefícios:

- Facilidade de implementação: não é necessário instalar nenhum software
- Compatibilidade com todos os sistemas de dados corporativos e ferramentas de extração de dados
- Automação por meio de programadores de trabalho corporativos
- Versatilidade por meio de opções de implementação: agendador de tarefas, integração de aplicativos, linha de comando

## Autenticação de API

Para executar um upload ou download, o script deve primeiro se autenticar. Consulte [https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=apis-enhanced-access-administration-api-authentication-via-api-keys](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=apis-enhanced-access-administration-api-authentication-via-api-keys "(Abre em uma nova guia ou janela)") para obter informações sobre como se autenticar usando esses métodos. Embora seja possível usar funções prontas para uso, talvez você prefira limitar o acesso das contas à ação específica que está sendo executada. Nesse caso, as funções que se autenticam devem ter os seguintes conjuntos de permissões mínimas para upload e download:

- Permissões de upload:
- AccessDev
- UploadData
- Upload de dados

  Observação: observe que as permissões “UploadData” e "Upload Data" são de fato permissões separadas. Não se esqueça de incluir ambos.
- Permissões de download:
- AccessProd
- AccessStg
- DrillDown
- Exibir o Proactive
- AllDataView
- InteractiveBenchmarksAndCostData
- ViewMetricReports
- ViewObjectReports
- ViewReportsSavedForEveryone
- ViewTransformReports
- ViewTransparencyReports
- ViewUnitReports

Observe que algumas das permissões de "Visualização" listadas acima podem não ser necessárias, dependendo dos produtos instalados e do tipo de dados que você está baixando. Em caso de dúvida, teste.

**Exemplos** :

Leia [a Licença para obter exemplos](../studio/apis/studio_license_examples.html "Aplica-se a: v12.0, v12.1, v12.2+").

- [API URL para fazer upload de uma tabela](../studio/apis/studio_api_url_table.html "♦ Aplica-se a: v11.x, v12.0, v12.1, v12.2+")
- [Exemplos de upload da API URL](../studio/apis/studio_api_url_upload_examples.html "Aplica-se a: v11.x, v12.0, v12.1, v12.2+")
- [API: Download de dados](../studio/apis/studio_api_download_data.html "Aplica-se a: TBM Studio v11.x, v12.0, v12.1, v12.2 e posterior")
- [API URL para fazer upload e editar dados de usuários em sistemas anteriores aoEnhanced Access Administration](../studio/apis/studio_api_url_upload_edit.html "Aplica-se a: v11.x, v12.0, v12.1")
- [Tutorial da API: Download e upload da tabela v.12 Costing Standard usando a ferramenta Postman](../studio/apis/studio_tutorial.html)
- [Como acessar a API R12 por meio de Enhanced Access Administration via curl](../studio/apis/studio_access_api.html)
- [Apptio Scripts de demonstração da API](../studio/apis/studio_demo_scripts.html)
