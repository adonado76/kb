---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Lista de aplicativos"
breadcrumb:
  - "Costing Standard"
  - "Relatório detalhado"
  - "Coleta de inscrições"
source_path: "cost-transparency/reports/application-list.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Lista de aplicativos

Este relatório foi elaborado para proprietários de aplicativos. É um relatório analítico que fornece acesso rápido a todos os detalhes sobre qualquer aplicativo da organização.

Este relatório foi elaborado para:

- Liderança de TI
- Proprietários de aplicativos
- Analistas de negócios
- Arquitetos corporativos
- Gerentes de portfólio

Esse relatório permite que os proprietários de aplicativos se aprofundem nos detalhes dos aplicativos pelos quais são responsáveis. Você pode definir um fatiador global para um proprietário de aplicativo ou uma família de aplicativos específica. Por exemplo, talvez você queira definir o fatiador global Application Owner para filtrar seu próprio nome, de modo que possa ver seus aplicativos sempre que fizer logon.

Você pode adicionar e remover colunas dinamicamente usando o painel Select Additional Columns (Selecionar colunas adicionais) para ter uma visão melhor dos detalhes dos aplicativos pelos quais você é responsável. Por exemplo, depois de definir o filtro Proprietário do aplicativo como seu próprio nome, você pode optar por remover a coluna Proprietário do negócio do aplicativo da tabela, pois não precisa ver seu nome listado como proprietário em todas as linhas.

Outro caso de uso é analisar rapidamente os dados sobre os aplicativos que estão sendo eliminados. Por exemplo, você pode definir o Slice by Objective como Eliminate (Eliminar) e, em seguida, procurar números altos de desenvolvimento de aplicativos. Isso pode levá-lo a questionar por que o desenvolvimento continua para um aplicativo que está sendo descontinuado. Além disso, é de se esperar que os custos associados aos aplicativos que estão sendo eliminados sejam zero. Você pode usar esses dados para confirmar e limpar o uso do aplicativo.

Outro caso de uso pode ser a filtragem de dados históricos em um esforço para encontrar novas maneiras de armazenar aplicativos não utilizados off-line sem consumir a infraestrutura. Para obter mais informações sobre slicers, consulte a explicação do elemento 2, abaixo.

O relatório Application List contém os seguintes elementos:

![imagem](../../resources/images/ct_images/ct%20report%20collections/application%20list.jpg)

| Elemento-chave | Descrição |
| --- | --- |
| (1) Coleta de relatórios | Essa coleção de relatórios fornece os detalhes de que você precisa para analisar os gastos, as tendências e o uso de seus aplicativos:  - [Relatório de revisão de aplicativos](application_review.html) (aberto por padrão) - [Relatório do portfólio de aplicativos](application_portfolio.html) - Lista de aplicativos (descrita nesta página) - [Relatório de análise de infraestrutura por aplicativo](infrastructure_analysis_by.html) - [Relatório de aplicativos novos e desativados](new_retired_apps.html) |
| (2) Cortadores | Os seguintes filtros globais estão disponíveis neste relatório:   - Tipo de aplicativo: - COTS: Aplicativos de consumo prontos para uso, empacotados - Personalizados: Aplicativos desenvolvidos internamente, criados internamente - SaaS: Aplicativos sob demanda e baseados na Web - Proprietário de TI do aplicativo: semelhante ao proprietário do pool de custos, o proprietário do aplicativo é a pessoa responsável por entender e fornecer um aplicativo. - Família de aplicativos: As famílias são grupos de aplicativos relacionados, conforme definido por sua organização.  As funções a seguir podem usar as segmentações neste relatório para obter uma visualização mais personalizada:  - Gerente de portfólio de aplicativos ou CIO: Sem definir nenhuma segmentação, você pode ter uma visão geral dos gastos com aplicativos em toda a organização. Use as segmentações para restringir o que você vê em todos os relatórios de Aplicativos. Você pode selecionar um nome no divisor Proprietário de TI do aplicativo para entender as responsabilidades dessa pessoa relacionadas aos aplicativos. Você pode selecionar um grupo de aplicativos da família de aplicativos para entender o desempenho geral desse grupo. - Proprietário do aplicativo: selecione seu nome para restringir os aplicativos àqueles pelos quais você é responsável e para ver o desempenho desses aplicativos em alto nível. - Analista financeiro: Defina os slicers para as áreas às quais você dá suporte para permitir uma análise de despesas detalhada e interorganizacional.   Observação: Lembre-se de que os filtros definidos em outros relatórios de aplicativos podem afetar o que você vê no relatório Revisão de aplicativos. Por exemplo, é possível definir um filtro no relatório Lista de aplicativos que acidentalmente impede ou limita os aplicativos que você pode ver no relatório Revisão de aplicativos. |
| (3) Detalhes do aplicativo | Use esta tabela para ver detalhes específicos sobre todos os seus aplicativos. A tabela lista os proprietários comerciais e de TI de cada aplicativo, os gastos com execução e desenvolvimento de aplicativos, o número de servidores, o espaço de armazenamento, os gastos por usuário e muito mais. Selecione qualquer item na coluna Nome do aplicativo para abrir o [relatório detalhado de aplicativos](https://tbmcouncil.jiveon.com/docs/DOC-9217 "(Abre em uma nova guia ou janela)") de página inteira, que fornece todos os dados padrão no sistema para o aplicativo específico em que você clicou.  A tabela Detalhes do aplicativo inclui os seguintes fatiadores adicionais, que são específicos para este relatório. Esses slicers não persistem em outros relatórios da coleção de relatórios Aplicativo:   - Fatiar por objetivo: Esse fatiador permite filtrar de acordo com os objetivos de investimento que você pode atribuir a aplicações individuais. Você também pode ver esses objetivos para os aplicativos com as despesas mais altas na guia Despesas de aplicativos do relatório Revisão de aplicativos. - Tolerar: Esses são aplicativos que você deseja manter no portfólio por um longo tempo. Você precisa delas, mas não quer necessariamente investir nelas. Idealmente, esses aplicativos não terão muito desenvolvimento contínuo, conforme evidenciado pelos baixos números na coluna App Dev. - Investir: Esses são aplicativos que a empresa deseja aprimorar ou alterar. Como resultado, espere ver números mais altos na coluna App Dev para esses aplicativos.   Se você observar números baixos de aplicativos marcados como Invest, deve questionar se o desenvolvimento foi iniciado.   - Migrar: Esses são aplicativos que estão sendo migrados. Espere ver pouco ou nenhum desenvolvimento contínuo (evidenciado na coluna App Dev) para esses aplicativos. - Eliminar: Esses são aplicativos que precisam ser eliminados. Espere ver números baixos na coluna App Dev para esses aplicativos. Se você vir números altos na coluna Desenvolvimento de aplicativos para aplicativos que estão sendo migrados ou eliminados, é bom questionar isso, pois o desenvolvimento contínuo desses aplicativos iria contra a meta do seu portfólio de aplicativos. - Fatia por criticidade: Esse fatiador permite que você filtre de acordo com o nível de necessidade comercial. - Essencial para os negócios: Sem esses aplicativos, a empresa sofreria perdas ou penalidades financeiras, legais ou de outra forma. A perda desses aplicativos teria um sério impacto nos negócios. - Histórico: esses aplicativos não são mais usados. - Missão crítica: sem esses aplicativos, a empresa sofreria graves perdas ou penalidades financeiras, legais ou de outra forma. A perda desses aplicativos interromperia completamente os negócios. - Produtividade do usuário: Esses aplicativos ajudam a organização a alcançar os resultados finais desejados, reduzir falhas, melhorar o desempenho no trabalho e simplificar o gerenciamento de dados. A perda desses aplicativos teria um efeito baixo a moderado sobre os negócios. - Fatiar por categoria: Esse fatiador permite que você filtre de acordo com o tipo de aplicativo. |
| (4) Selecione Colunas adicionais | Controle a visibilidade das colunas na tabela Detalhes de aplicativos selecionando e desmarcando os nomes de coluna listados no painel Selecionar colunas adicionais. |

Perguntas respondidas

- Você pode usar esse relatório para responder às seguintes perguntas:
- Quem são nossos provedores de SaaS e quanto gastamos com cada um deles?
- Qual é o nosso gasto total por usuário e por aplicativo?
- Qual é o nosso total de execução de aplicativos e desenvolvimento de aplicativos por aplicativo?
