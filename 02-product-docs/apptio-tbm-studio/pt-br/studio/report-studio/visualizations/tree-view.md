---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Visualização em árvore"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "ApptioIBM Report Studio (Novo)"
  - "Visualizações"
  - "Tabela"
source_path: "studio/report-studio/visualizations/tree-view.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Visualização em árvore

**A Visualização em Árvore** permite visualizar dados hierárquicos diretamente dentro de uma tabela. Em vez de exibir todas as linhas em uma lista simples, a Visualização em Árvore organiza os dados em níveis que podem ser expandidos e recolhidos, facilitando a exploração de relações e a análise detalhada progressiva.

Isso é especialmente útil quando seus dados apresentam relações naturais de pai-filho, como:

- Centros de custo → Contas → Subcontas
- Unidades de Negócio → Equipes → Aplicativos
- Categorias → Subcategorias → Itens

**Use isso quando**

- Sua tabela utiliza vários campos na configuração de Linhas
- Você deseja navegar pelos dados de forma hierárquica, em vez de percorrer uma longa tabela plana
- Você quer controlar a quantidade de detalhes exibidos de cada vez

**Como usar a Visualização em Árvore**

1. Abrir uma mesa
2. Ative a opção **“Mostrar como árvore”** na tabela de propriedades de formatação
3. Certifique-se de que vários campos sejam adicionados à seção “Linhas”
4. Uma vez ativada, inicialmente são exibidas apenas as linhas do nível superior (raiz).
5. Os ícones para expandir e recolher aparecem ao lado das linhas que contêm dados secundários.
6. Expanda uma linha para visualizar o próximo nível da hierarquia.
7. Recolher uma linha para ocultar todas as suas linhas secundárias.

Nota:

- As linhas filhas aparecem diretamente abaixo da linha pai, preservando o contexto. Isso permite que você explore os dados de forma incremental sem perder de vista a relação com o elemento pai.
- A visualização em árvore funciona apenas com dimensões de um único objeto, e não com dimensões de vários objetos.

**Construção da hierarquia**

Quando a Visualização em Árvore está ativada:

- A hierarquia da tabela é criada a partir dos campos adicionados à seção “Linhas”.
- A ordem dos campos define a hierarquia:
- Primeiro campo → Nível raiz
- Segundo campo → Nível filho
- Campos seguintes → Níveis mais profundos

Cada linha pode ser expandida para mostrar seus elementos filhos diretos.

Quando a visualização em árvore está desativada:

- A tabela é exibida como uma tabela simples padrão
- Não são exibidos controles de hierarquia ou de expandir/recolher
- Todas as linhas aparecem no mesmo nível

**Configuração do número máximo de crianças**

A configuração "Max Children" permite controlar quantas linhas filhas são exibidas sob cada nó pai.

Como ela funciona

- Padrão (Mostrar tudo):

  Todas as linhas filhas de uma linha pai são exibidas quando expandidas.
- Valor definido pelo usuário (n):

  Para cada pai, são exibidas apenas as primeiras n linhas de filhos.

Isso é útil para:

- Evitar expansões de grande porte
- Melhorando a legibilidade e o desempenho
- Focando nos registros filhos principais

Observação: o valor de "Max Children" se aplica a cada nó, e não à tabela como um todo.

## Quebra automática de linha para cabeçalhos e células de tabela

As tabelas agora suportam o quebra automática de linha tanto nos cabeçalhos das colunas quanto nas células, melhorando a legibilidade e garantindo que o conteúdo fique totalmente visível sem a necessidade de redimensionamento manual.

A tabela suporta fórmulas personalizadas e dimensões de fórmula. Para mais detalhes, consulte [Fórmulas personalizadas](../create-first/custom-formula.html "As fórmulas personalizadas (também conhecidas como dimensões de fórmula) permitem definir novas dimensões calculadas utilizando campos existentes no seu modelo de dados. Isso permite uma análise mais aprofundada e insights mais detalhados, sem exigir nenhuma alteração no conjunto de dados ou no esquema subjacente.")

**Tópico principal:** [Tabela](../../../studio/report-studio/visualizations/rs-table.html "O componente de tabela exibe dados em um formato tabular estruturado. É ideal para apresentar informações detalhadas, resumir métricas e permitir a filtragem interativa dentro de um relatório.")
