---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Linhagem"
breadcrumb: []
source_path: "studio/admin/lineage-in-tbm-studio.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Linhagem

A linhagem de dados é o processo de rastreamento do fluxo de dados ao longo do tempo, proporcionando uma compreensão clara da origem dos dados, de como eles mudaram e de seu destino final no pipeline de dados.

## Por que exigimos o Lineage em TBM Studio

Em Apptio, a linhagem mostra uma descrição do fluxo em uma rede de muitos relacionamentos complexos. Exemplos: Uma tabela que flui para outras tabelas, uma tabela que se move para objetos de modelo com muitas métricas e depois para diferentes relatórios. As diferentes áreas em TBM Studio onde a linhagem é capaz de rastrear e entender a dependência são:

- Pipeline de dados
- Modelagem
- Relatório

No **pipeline de dados**, a primeira coisa que você faz é ingerir os dados de diferentes fontes, ou seja, você pode ter uma tabela sendo originada de outra tabela ou pode estar anexando tabelas. Você também pode ter uniões de tabelas que podem identificar relações-chave entre diferentes tabelas. E, finalmente, em qualquer tabela, também pode haver fórmulas com definições que dependem de outra tabela, como a pesquisa.

Na **modelagem**, você pode ter relações de um para um, um para muitos ou muitos para muitos entre diferentes objetos de alocação e derivamos alguns algoritmos de ponderação complexos para esses objetos.

Com os **relatórios e visualizações do Analytics**, cada relatório pode ter várias guias com vários componentes. Cada componente é composto por várias métricas. Agora você pode entender que seu projeto Apptio pode se tornar um ambiente complexo.

Nosso objetivo é visualizar essa rede maciçamente interconectada de conexões entre tabelas, modelos e relatórios e mostrar interdependências potencialmente obscuras e desconhecidas. Isso permitirá que os administradores entendam o impacto das alterações feitas na configuração. Portanto, a linhagem nos fornece essa análise e insights superpoderosos que ajudam você a responder a perguntas básicas como: "O que aconteceria se eu excluísse esta coluna desta tabela?"

## Casos de uso de linhagem

Alguns dos casos de uso do Lineage são:

- Mostre imediatamente o que é "usado" por uma determinada entidade (dependências downstream) ou do que essa entidade depende (dependências upstream).
- Identifique o impacto do projeto, se você modificar ou alterar uma entidade, como uma coluna, ou se remover uma tabela.
- Limpe a complexidade do projeto que cresce com o tempo, identificando e removendo tabelas órfãs ou métricas calculadas não utilizadas.
- Corrija as informações de privacidade de dados identificando exatamente onde os dados existem e onde estão expostos.

## Como acessar o Lineage

Uma maneira de acessar a linhagem é no painel esquerdo do Project Explorer, abrindo o menu com um <clique com o botão direito do mouse> e selecionando **Trace Lineage for this document**. A outra é <clique com o botão direito do mouse> em uma guia de entidades na navegação da guia inferior. Uma janela Lineage é aberta com uma representação visual do fluxo de dados, dependendo da entidade inicial selecionada. A visualização inicial é limitada a uma profundidade de 1 e mostrará as dependências downstream, se começar a partir de uma tabela, coluna ou métrica calculada, ou as dependências upstream, se começar a partir de um relatório. Vamos começar definindo as informações mostradas na visualização da linhagem. Cada cor representa uma entidade específica:

- O cinza representa dados brutos.
- A cor verde representa tabelas e colunas padrão.
- A cor marrom representa tabelas e colunas editáveis.
- O azul representa os objetos e as métricas do modelo.
- Tan representa relatórios e componentes de relatórios.

Você pode rolar o rolo do mouse ou arrastar o touchpad do seu laptop para aumentar ou diminuir o zoom do diagrama.

Você pode explorar o gráfico Lineage alterando os seguintes dados:

|  |  |
| --- | --- |
| Profundidade | Sempre começamos com a profundidade de 1, que estende o escopo dos relacionamentos a partir da entidade selecionada. Como o projeto pode se tornar muito complexo, você terá mais profundidade para detalhar os relacionamentos. Mova o controle deslizante para aumentar a profundidade e mergulhar fundo no nível de dependências. |
| Mostre documentos que | Você também pode alternar entre dependências downstream, que é o padrão se você escolher algo como uma tabela, ou dependências upstream, que seria o padrão se você escolhesse um relatório. Selecione para ver documentos que dependem da entidade focalizada (dependência downstream) ou para A entidade focalizada depende de (dependência upstream). |
| Somente ciclos | Marque essa caixa de seleção para visualizar apenas o ciclo |
| Caixa de texto de pesquisa | Digite a(s) palavra(s)-chave que você deseja excluir (-) ou incluir (+) nos resultados da pesquisa. Para obter mais informações sobre o Lineage Search. Clique aqui. |
| Chaves adicionadas | Exibe todas as entidades que têm as palavras-chave adicionadas na caixa de texto de pesquisa |
| Chaves excluídas | Exibe todas as entidades que a palavra-chave removeu na caixa de texto de pesquisa |
| Alternar subtipos | Selecione essa opção para alternar entre marcar/desmarcar todos os subtipos de uma só vez. |
| Alternar remoção em massa | Remove todas as entidades incluídas nas chaves adicionadas ou nas chaves ocultas |
| Aplicar | Selecione esse botão para aplicar as alterações feitas nesse painel. |

Tópicos relacionados:

- [Demonstração da linhagem](lineage-demo.html "O recurso Lineage não está ativo por padrão. Um administrador pode ativá-lo navegando até a guia Projeto > Ativar recursos e, em seguida, selecionar Mostrar linhagem. Em seguida, ele pode ser acessado de diferentes entidades, como tabelas, colunas em tabelas, tabelas editáveis e relatórios de métricas.")
- [Filtro relacionado](lineage-related-filter.html "Outra maneira de utilizar o recurso de linhagem em uma experiência de usuário simplificada no Project Explorer é que agora você pode clicar em qualquer tabela para ver as tabelas relacionadas, vinculando-as ainda mais em seu relacionamento.")
- [Localizar documentos não utilizados](lineage-unused-docs.html)
- [Pesquisa de linhagem](lineage-search.html)
