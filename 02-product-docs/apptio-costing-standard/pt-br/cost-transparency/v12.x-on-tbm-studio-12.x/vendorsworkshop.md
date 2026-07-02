---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Workshop para fornecedores"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/vendorsworkshop.html"
images:
  - "resources/images/ct_images/vendors-workshop.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Workshop para fornecedores

## Preparação dos dados do fornecedor

Você pode começar e preparar os dados do seu fornecedor analisando os pontos de verificação abaixo:

1. Se você ainda não tiver feito isso, carregue todos os dados relevantes do fornecedor no arquivo Apptio.
2. Seguindo as Apptio práticas padrão, categorize cada conjunto de dados brutos na categoria de Fornecedores.
3. Se apropriado, aplique um filtro de data aos dados do fornecedor.

## Sobre o identificador do fornecedor

O identificador do objeto Fornecedor é gerado pelo sistema e não deve ser alterado. Ele inclui:

- Nome do fornecedor
- ID do Fornecedor
- Tipo de fornecedor
- Função do fornecedor
- Serviço principal do fornecedor

## Sobre as chaves do fornecedor

As chaves do conjunto de dados mestre do fornecedor são todas geradas pelo sistema e não devem ser alteradas.

| Chave | A chave de campo é baseada em | Lógica |
| --- | --- | --- |
| **Chave da fonte de custo\_fornecedor** | ID do Fornecedor  Metacampo-chave da fonte de custos | Anexar o texto CS\_Vendor com a ID do fornecedor, metacampo Chave da fonte de custos |
| **Chave Vendor\_ITRT** | Chave CSP do fornecedor  Torre de recursos de TI  Subtracção de recursos de TI | SE  Chave Vendor\_CSP = Vendor\_CSP\_null  THEN  Anexar o texto Vendor\_ITRT com IT Resource Tower e IT Resource Sub-Tower  ELSE  Definir o texto como Vendor\_ITRT\_null |
| **Chave Vendor\_CSP** | A CSP é  Nome do fornecedor | SE  É CSP = sim  THEN  Anexar o texto Vendor\_CSP ao nome do fornecedor  ELSE  Defina o texto como Vendor\_CSP\_null |

Vendor\_CSP\_Key só é necessário se você também estiver implementando o componente Public Cloud . Caso contrário, a chave (e outros campos relacionados à nuvem) pode ser deixada em branco.

## Colunas computadas comuns necessárias para fornecedores

Talvez você precise criar qualquer uma das seguintes colunas computadas:

- Declaração condicional para determinar se um fornecedor é um provedor de serviços em nuvem. Isso deve retornar uma resposta Yes/No.
- Declaração condicional para determinar se um fornecedor é um provedor de serviços gerenciados. Isso deve retornar uma resposta Yes/No.
- O tipo de fornecedor deve ser classificado como "estratégico", "preferencial" ou "transacional"

Se os dados de alocação do fornecedor estiverem em um conjunto de dados separado dos dados do fornecedor, talvez sejam necessárias colunas computadas adicionais, incluindo:

- Pesquisa de Despesas teóricas anuais de uma lista de fornecedores para uma lista de alocação de fornecedores
- Pesquisa de local de serviço de uma lista de fornecedores para uma lista de alocação de fornecedores
- Pesquisa de interação do usuário de uma lista de fornecedores para uma lista de alocação de fornecedores
- Pesquisa da função do fornecedor de uma lista de fornecedores para uma lista de alocação de fornecedores
- Pesquisa da localização do fornecedor de uma lista de fornecedores para uma lista de alocação de fornecedores
- Pesquisa do gerente de fornecedores de uma lista de fornecedores para uma lista de alocação de fornecedores
- Pesquisa de serviço de fornecedor de uma lista de fornecedores para uma lista de alocação de fornecedores
- Pesquisa de tipo de fornecedor de uma lista de fornecedores para uma lista de alocação de fornecedores

O nome do fornecedor DEVE corresponder ao nome do provedor no conjunto de dados mestre do provedor de serviços de nuvem para que exista um relacionamento. Se isso não acontecer, talvez seja necessário limpar os dados ou criar uma coluna computada.

## Mapear dados para os dados mestre dos fornecedores

Mapear os dados do fornecedor do cliente para o conjunto de dados mestre de fornecedores. A maior parte do mapeamento é autoexplicativa. Em 12.7, agora você pode aproveitar a função Column Map em seu conjunto de dados brutos para mapear os dados mestre dos fornecedores ([Map Columns](https://community.apptio.com/docs/DOC-10561 "(Abre em uma nova guia ou janela)") ).

Para usar a porcentagem de alocação (para fornecedores mapeados para mais de uma torre), use a opção Selecionar colunas de origem adicionais ao mapear seus dados. Você usará isso para a alocação de fornecedores para torres de recursos de TI nos modelos.

## Revisar o objeto Vendors nos modelos

Depois de mapear seus dados para os dados mestre dos fornecedores, você pode ir em frente e revisar os objetos nos modelos. Analise os modelos a seguir e verifique se os valores estão fluindo para os objetos adequadamente.

| Modelo | Ações |
| --- | --- |
| **Custo** | Certifique-se de que os valores estejam fluindo do objeto Fonte de custos para o objeto Fornecedores.  Da fonte de custos para os fornecedores, aloque usando a referência baseada em dados (essa é a configuração padrão). As chaves que unem os dois conjuntos de dados incluem o ID do fornecedor e o metacampo da chave da fonte de custos. |
| **Orçamento** | Certifique-se de que os valores estejam fluindo do objeto Fonte de custos para o objeto Fornecedores.  Da fonte de custos para os fornecedores, aloque usando a referência baseada em dados (essa é a configuração padrão). As chaves que unem os dois conjuntos de dados incluem o ID do fornecedor e o metacampo da chave da fonte de custos. |
| **Previsão** | Certifique-se de que os valores estejam fluindo do objeto Fonte de custos para o objeto Fornecedores.  Da fonte de custos para os fornecedores, aloque usando a referência baseada em dados (essa é a configuração padrão). As chaves que unem os dois conjuntos de dados incluem o ID do fornecedor e o metacampo da chave da fonte de custos. |
| **CapEx** | Certifique-se de que os valores estejam fluindo do objeto Fonte de custos para o objeto Fornecedores.  Da fonte de custos para os fornecedores, aloque usando a referência baseada em dados (essa é a configuração padrão). As chaves que unem os dois conjuntos de dados incluem o ID do fornecedor e o metacampo da chave da fonte de custos. |
| **Orçamento CapEx** | Certifique-se de que os valores estejam fluindo do objeto Fonte de custos para o objeto Fornecedores.  Da fonte de custos para os fornecedores, aloque usando a referência baseada em dados (essa é a configuração padrão). As chaves que unem os dois conjuntos de dados incluem o ID do fornecedor e o metacampo da chave da fonte de custos. |
| **CapEx Previsão** | Certifique-se de que os valores estejam fluindo do objeto Fonte de custos para o objeto Fornecedores.  Da fonte de custos para os fornecedores, aloque usando a referência baseada em dados (essa é a configuração padrão). As chaves que unem os dois conjuntos de dados incluem o ID do fornecedor e o metacampo da chave da fonte de custos. |

## Revisar os relatórios do fornecedor

Os relatórios a seguir são atualizados após a configuração do objeto Vendors:

- Avaliação do fornecedor
- Portfólio de fornecedores
- Lista de fornecedores
- Gastos do fornecedor por projeto
- Validade dos fornecedores
- Dimensões de dados - Fornecedores
- Fornecedor - tendência do centro de custos
- Fornecedor - Tendência da torre de TI
- Fornecedor - Tendência do projeto
- Fornecedor - tendência do tipo de fornecedor
- Detalhes do fornecedor
- Detalhes do tipo de fornecedor

Para ver os detalhes desses relatórios (incluindo navegação, funções, objetivos e perguntas respondidas para cada relatório), consulte o Guia do Usuário Costing Standard na Ajuda on-line.

## Acompanhar e gerenciar as despesas com fornecedores

A empresa típica habilitada para TBM utilizará Apptio para obter mais informações sobre o custo e o valor de seus relacionamentos com fornecedores, monitorando a utilização de vários produtos e serviços fornecidos pelos fornecedores, juntamente com métricas relacionadas ao desempenho de custo-volume.

Apptio permite que as áreas de compras, jurídica, financeira e de TI alinhem os pontos de vista do desempenho financeiro do fornecedor e esclareçam a natureza da contribuição do fornecedor para o valor de TI. Além disso, Apptio faz a ponte entre o antigo e o novo, fornecendo insights padrão sobre o faturamento do fornecedor de nuvem e comparações de tendências de custo unitário. Agora, o setor financeiro e a TI podem ver os detalhes significativos do que os fornecedores estão fazendo, que tipos de fornecedores estão envolvidos e como esses fornecedores se comparam às alternativas baseadas na nuvem.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/vendors-workshop.png)

Esse procedimento abrange a análise de fornecedores estratégicos, preferenciais e transacionais com base no custo total, no orçamento, na meta, no centro de custos CapEx/OpEx,, no projeto, na torre, na subtorre e na função do fornecedor. Isso inclui o monitoramento de fornecedores por tipo e por meta de gastos com análise de séries temporais e métricas importantes.

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
