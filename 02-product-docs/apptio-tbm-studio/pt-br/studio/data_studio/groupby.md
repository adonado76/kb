---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "GRUPO"
breadcrumb: []
source_path: "studio/data_studio/groupby.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# GRUPO

O!A função GROUPBY agrupa as entradas em uma tabela com base no valor de uma coluna específica. Você pode realizar o agrupamento de várias colunas usando a **faixa de opções**.

!GROUPBY é uma das funções de tabela mais usadas. Ele pega uma tabela e a resume com base nos valores de uma determinada coluna. Depois de agrupados, você não verá mais os detalhes de um único item de linha, embora haja links que levem a exibições detalhadas.

Observação: Há um limite de 15 colunas em uma linha GroupBy para configurações de tabela de relatório.

Há três versões da função:

- !GROUPBY[nome da coluna]
- !GROUPBY[nome da coluna,nome da coluna]
- !GROUPBY[nome da coluna|nome da coluna]

## !GROUPBY[nome da coluna]

Essa é a versão mais simples da função. Agrupa as linhas em uma tabela pelo nome da coluna fornecido.

## Exemplo

Suponha que você tenha a tabela mostrada na figura abaixo.

![Exemplo](../../resources/images/it%20planning_images/groupby-1.png)

Abaixo está o caminho de dados usado para gerar a tabela:

```
docs.org:ABC Company/
Default/
.TableTransform:Data Center Services/
.Summary
```

Suponha que você queira agrupar a tabela por data center. Você adiciona o!GROUPBY para o caminho de dados, conforme mostrado abaixo.

```
docs.org:ABC Company/
Reports/
.DateGoesHere/
CostModels/
Default/
.TableTransform:Data Center Services/
!GROUPBY[Data Center]/
.Summary
```

O resultado é mostrado na figura abaixo. Observe que as entradas na coluna Data Center agora são links que levam a exibições detalhadas de cada data center. Além disso, o site Apptio adiciona uma coluna Count indicando o número de entradas que compõem cada agrupamento.

![Serviços de data center](../../resources/images/it%20planning_images/groupby-2.png)

## !GROUPBY[nome da coluna,nome da coluna]

Esta versão do!A função GROUPBY agrupa as linhas por duas ou mais colunas. Os nomes das colunas são separados por vírgulas. A ordem em que você insere os nomes das colunas determina a ordem usada para agrupar as linhas e a ordem em que as colunas são exibidas.

## Exemplo

Suponha que você tenha a tabela mostrada na figura abaixo:

![Exemplo](../../resources/images/it%20planning_images/groupby-4.png)

Abaixo está o caminho de dados usado para gerar a tabela.

```
docs.org:ABC Company/
Reports/
.DateGoesHere/
CostModels/
Default/
.TableTransform:Data Center Services - Subservice/
.Summary
```

Suponha que você queira agrupar as linhas por serviço e, em seguida, por sub-serviço. Adicione o!GROUPBY para o caminho de dados, conforme mostrado abaixo.

```
docs.org:ABC Company/
Reports/
.DateGoesHere/
CostModels/
Default/
.TableTransform:Data Center Services - Subservice/
!GROUPBY[Service,SubService]/
.Summary
```

O resultado é mostrado na figura abaixo. Observe que as entradas na coluna Data Center agora mostram {Various}. Isso indica que há dois ou mais valores de data center para cada linha. Em nosso exemplo, seriam Seattle e Chicago. Novamente, o site Apptio adiciona uma coluna Count. Tabela após agrupamento por serviço e sub-serviço:

![agrupamento por serviço e sub-serviço](../../resources/images/it%20planning_images/groupby-5.png)

Você pode executar esse tipo de GROUPBY usando a **faixa de opções** :

1. Selecione a tabela a ser agrupada.
2. Selecione a guia **Data (Dados** ) na **faixa de opções**.
3. Selecione o ícone **Group (Grupo** ) e selecione o(s) campo(s) a ser(em) usado(s) para o agrupamento.

## !GROUPBY[nome da coluna|nome da coluna]

Inerente ao site Apptio está a capacidade de detalhar níveis sucessivos de detalhes nos relatórios clicando em links. Quando você detalha, na verdade está filtrando um relatório pelo link selecionado. Esta versão do!A função GROUPBY verifica se o caminho de dados foi filtrado por uma determinada coluna devido a uma pesquisa. Se não tiver, ele agrupa pela primeira coluna listada. Caso contrário, ele verifica a próxima coluna da lista. Se as linhas forem agrupadas pela primeira coluna, a segunda coluna será ignorada.

Isso pode ser útil quando combinado com relatórios que são salvos para serem aplicados "Mesmo se filtrados de outra forma". Observe que essa sintaxe não pode ser usada de forma prática com alguns componentes de gráfico, especificamente componentes que exigem que você especifique o nome da coluna do eixo X. Essa funcionalidade ainda não foi amplamente utilizada.

**Exemplo**

A tabela mostrada na figura abaixo foi filtrada por Data Center como resultado de um detalhamento.

![Filtrado por data center](../../resources/images/it%20planning_images/groupby-6.png)

O caminho de dados para a tabela é mostrado abaixo.

```
docs.org:ABC Company/
Reports/
.TableTransform:Data Center Service - Subservice/
!FILTER[{Data Center}="Seattle"]/
.Summary
```

Agora você modifica o caminho de dados conforme mostrado abaixo para agrupar os resultados por Data Center, se ainda não tiverem sido filtrados, ou por Serviço, se tiverem sido filtrados.

```
docs.org:ABC Company/
Reports/
.DateGoesHere/
CostModels/
Default/
.TableTransform:Data Center Services - Subservice/
!FILTER[{Data Center}="Seattle"]/
!GROUPBY[Data Center|Service]/
.Summary
```

O resultado é mostrado na figura abaixo:

![Resultado](../../resources/images/it%20planning_images/groupby-7.png)

Se pegarmos a tabela original não filtrada mostrada na Figura G abaixo e aplicarmos o mesmo caminho de dados, obteremos o resultado mostrado na figura abaixo. Tabela não filtrada:

![](../../resources/images/it%20planning_images/groupby-8.png)

Tabela não filtrada agrupada por Data Center:

![Tabela não filtrada agrupada por Data Center](../../resources/images/it%20planning_images/groupby-9.png)

**Tópico pai:** [Tabelas editáveis: Acomodando a entrada do usuário](../../studio/data_studio/editabletables.html "Aplica-se a: TBM Studio 12.6 e posterior")
