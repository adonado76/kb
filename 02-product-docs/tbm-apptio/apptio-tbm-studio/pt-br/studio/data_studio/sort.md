---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Classificar"
breadcrumb: []
source_path: "studio/data_studio/sort.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Classificar

Classifica uma tabela em uma ou mais colunas especificadas na tabela. Você pode classificar uma tabela usando a faixa de opções. O!A função SORT pode ser aplicada usando uma, duas ou mais colunas em uma tabela.

## Sintaxe

`!SORT[Column1|asc or desc,Column2|asc or desc]`

## Argumentos

Coluna 1
:   O nome da primeira coluna que será usada para classificar a tabela.
:   asc ou desc
:   asc = ascendente
:   desc = descendente

Column2
:   O nome da segunda coluna que será usada para classificar a tabela.

## Exemplo

Suponha que você tenha a seguinte tabela.

![Exemplo](../../resources/images/it%20planning_images/sort-1.png)

Você deseja classificar a tabela por Serviço e, em seguida, por Sub-serviço. Você modifica o caminho dos dados conforme mostrado abaixo.

```
docs.org:ABC Company/
Reports/
.DateGoesHere/
.Summary/
!SORT[{Service}|asc,{SubService}|asc]
```

O resultado é mostrado abaixo.

![Resultado](../../resources/images/it%20planning_images/sort-2.png)

## Fita

Você pode classificar uma tabela usando a **faixa de opções** :

1. Selecione a tabela que você deseja classificar
2. Selecione o ícone **Classificar** na guia **Dados** da **Faixa de Opções**.
3. Preencha os campos e clique em **Sort (Classificar** ).

Para obter mais informações sobre a classificação de uma tabela na **faixa de opções**, consulte Classificação de linhas em uma tabela no Guia do Usuário do Apptio Studio.

**Tópico pai:** [Tabelas editáveis: Acomodando a entrada do usuário](../../studio/data_studio/editabletables.html "Aplica-se a: TBM Studio 12.6 e posterior")
