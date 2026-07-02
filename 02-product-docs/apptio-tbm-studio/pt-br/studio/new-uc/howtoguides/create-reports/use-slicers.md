---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Use filtros para uma filtragem interativa"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Criar relatórios"
  - "Noções básicas sobre relatórios"
source_path: "studio/new-uc/howtoguides/create-reports/use-slicers.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Use filtros para uma filtragem interativa

**Objetivo:** Adicionar filtros aos relatórios para que os usuários finais possam filtrar os dados sem precisar editar o relatório

**Quando usar:** Quando você deseja que os usuários explorem os dados selecionando diferentes categorias, períodos ou valores; quando diferentes partes interessadas precisam visualizar diferentes subconjuntos dos mesmos dados

**Tempo estimado:** 10 minutos

## Entendendo os Slicers

Os filtros são controles interativos que aparecem no seu relatório. Quando um usuário clica nos valores de um filtro, todas as tabelas e gráficos vinculados são atualizados instantaneamente para mostrar apenas os dados selecionados. Isso transforma relatórios estáticos em ferramentas exploratórias.

**Conceitos fundamentais do slicer:**

- **Valores relacionados** (destacados): Ao clicar neles, o que é exibido muda
- **Valores não relacionados** (em cinza): estes não têm nenhuma relação com as seleções atuais
- **Valores selecionados** : Filtros atualmente ativos

## Tipos de cortadores

- **Filtro de lista:** Mostrar valores de texto como itens clicáveis (mais comum)
- **Controles deslizantes:** exiba intervalos numéricos com um controle deslizante que pode ser arrastado
- **Fatiadores compactos:** combine vários fatiadores em um menu suspenso para economizar espaço
- **Filtros hierárquicos:** permitem a exploração detalhada por níveis (por exemplo, Região > País > Cidade)

## Passos: Adicionar um filtro básico

1. Abra o seu relatório e **dê uma olhada**.
2. Clique na guia **Relatório** e, em seguida, clique em **Segmentador de linhas**. Aparece um espaço reservado para o Slicer em branco e o painel de configuração do Slicer é aberto.
3. No **Explorador** de Projetos, localize o campo pelo qual você deseja que os usuários filtrem. Entre os bons candidatos a critérios de filtragem estão: Unidade de Negócios, Centro de Dados, Tipo de Despesa, Grupo de Custos e Fornecedor.
4. Arraste o campo para a área **“Filtrar por”** do painel de configuração. O filtro é preenchido com valores dos seus dados.
5. Posicione o filtro no seu relatório clicando na barra de título e arrastando-o.
6. Redimensione o filtro arrastando suas bordas.

## Resultados esperados

- O filtro exibe valores clicáveis
- Ao clicar em um valor, todas as tabelas e gráficos do relatório são filtrados
- É possível selecionar vários valores clicando com a tecla Ctrl pressionada
- O ícone de reinicialização (×) cancela todas as seleções

## Armadilhas comuns

- **Valores em excesso:** os filtros exibem no máximo 250 valores. Se você tiver mais dados, aplique um filtro ao segmentador ou use um segmentador compacto com a função de pesquisa.
- **Confusão com valores não relacionados:** os usuários podem se perguntar por que alguns valores aparecem desativados. Considere incluir uma nota explicando que valores não relacionados não têm nenhuma ligação com as seleções atuais.
- **Desempenho com muitos filtros:** os relatórios com muitos filtros podem ficar lentos. Considere usar segmentadores compactos para consolidar filtros.

**Tópico principal:** [Noções básicas sobre relatórios](../../../../studio/new-uc/howtoguides/create-reports/report-basic.html)
