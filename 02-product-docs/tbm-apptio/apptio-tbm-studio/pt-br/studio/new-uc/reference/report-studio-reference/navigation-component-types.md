---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Tipos de componentes de navegação"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Navegação"
source_path: "studio/new-uc/reference/report-studio-reference/navigation-component-types.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tipos de componentes de navegação

**Componente Botão**

O componente Botão oferece controles de navegação explícitos dentro dos relatórios. Use os botões para acessar relatórios específicos, alterar o período exibido, executar scripts ou voltar à página anterior. Os botões oferecem a opção de navegação mais visível e intuitiva.

**Adicionar um botão**

1. Na guia Relatório, clique no ícone do botão
2. O componente botão é adicionado ao relatório dentro de um painel de componentes padrão
3. Posicione e redimensione o botão conforme necessário
4. Configure a aparência e as ações na caixa de diálogo Propriedades

**Propriedades de aparência do botão**

|  |  |
| --- | --- |
| **Propriedade** | **Descrição** |
| Texto do botão | Texto exibido no botão. Suporta rótulos estáticos e texto dinâmico usando a sintaxe <%=...%>. É possível incluir código HTML para referenciar imagens da biblioteca de imagens Apptio. |
|  |  |
| Dica de ferramenta do botão | Texto exibido quando os usuários passam o mouse sobre o botão. Use dicas de ferramenta para fornecer informações adicionais sobre a ação do botão. |
| Ativado | Estado do botão de controle: deixe em branco para ativar, digite "desativado" para desativar (botão cinza) ou "oculto" para ocultar. Use fórmulas para estados condicionais, por exemplo: <%=IF( Cost>5000,"ativado","desativado")%> |
| Cor do botão | Define a cor de fundo do botão |
| Cor do texto do botão | Define a cor do texto do botão |
| Tamanho do texto | Controla o tamanho do botão e do texto nele exibido. Também é possível redimensionar arrastando a borda do painel. |
| Crescimento do botão | Auto: tamanho padrão. Horizontal: alarga o botão para se ajustar ao painel ao redor. |
| Cor de fundo do painel | Define a cor do painel ao redor do botão |

**Propriedades da ação do botão**

Configure as ações dos botões na guia “Ações” da caixa de diálogo “Propriedades”:

|  |  |
| --- | --- |
| **Propriedade** | **Descrição** |
| Ação do servidor | ApptioScript código executado quando o botão é clicado. É executado antes das ações “Data de alteração” e “Navegar”. Este é um recurso avançado. |
| Alterar data | Altera o período exibido. Selecione no menu suspenso ou insira uma data personalizada no formato mês:ano (por exemplo, January:FY2012, P3:FY2012 ). |
| Navegar | Insira um link usando a sintaxe do estilo Wiki para acessar outro relatório. Consulte a seção “Links codificados” para obter detalhes sobre a sintaxe. |
| Botão Voltar | Quando selecionado, clicar no botão leva o usuário de volta ao relatório anterior. Isso oferece uma alternativa à navegação por trilha de navegação. Substitui as configurações de Ação do servidor, Alterar data e Navegar. |
| Enviar formulário | Se o botão estiver inserido em um componente de formulário, clicar nele enviará o formulário. |

**Observação sobre desempenho:** tenha cuidado ao criar botões que levam a relatórios que exigem cálculos complexos. A navegação em relatórios complexos pode afetar o desempenho do sistema.

**Links de relatórios (drill-through)**

Os links de relatório permitem que os usuários naveguem de um valor selecionado em uma tabela ou de um elemento em um gráfico para um relatório relacionado. Essa funcionalidade de detalhamento é fundamental para a criação de relatórios interativos e exploráveis. Os links nas tabelas aparecem em azul.

**Importante:** Os links de relatório se aplicam apenas a tabelas baseadas em objetos criadas na caixa de diálogo “Configuração de Componentes Ad Hoc”. Não é possível adicionar links de relatórios a tabelas de transformação, tabelas legadas ou gráficos.

**Configurando links de relatórios**

1. Selecione uma coluna em uma tabela ou selecione um gráfico inteiro
2. Selecione a guia Ad Hoc e clique em Drill na seção Navegação
3. Configure as propriedades de navegação na caixa de diálogo

**Referência de propriedades de navegação**

|  |  |
| --- | --- |
| **Propriedade** | **Descrição** |
| Ativar navegação | Ativa os links da coluna ou do gráfico selecionado. Nos gráficos, a navegação deve ser feita com base na coluna de valores, e não na coluna de rótulos. |
| Abrir como janela modal | Exibe o relatório de destino em uma janela de diálogo pop-up. Os usuários podem visualizar o relatório e clicar em “Fechar” para voltar. Ideal para relatórios simples de metas, sem filtros complexos ou seletores de colunas. |
| Ir para | Selecione o relatório de destino a partir de qualquer relatório do projeto. Clique em “Novo relatório” para criar um novo relatório de destino diretamente nesta caixa de diálogo. |
| Filtrar na linha selecionada | Filtra o relatório de destino de acordo com o valor em que o usuário clicou. Opções: Filtrar em todas as colunas das linhas, Filtrar apenas nas colunas agrupadas, Filtrar apenas na coluna selecionada no momento. |
| Filtrar com base nas seleções do segmentador aplicado | Transfere as seleções atuais do filtro para o relatório de destino, mantendo o contexto do filtro. |
| Incluir os filtros do relatório atual | Inclui os filtros definidos na seção Filtros da caixa de diálogo Configuração da consulta ad hoc. |
| Adicionar a coluna selecionada no momento | Se a coluna selecionada não existir no relatório de destino, ela será adicionada automaticamente. |
| Incluir as colunas adicionadas ao relatório atual | Mantém e aplica quaisquer colunas adicionadas do relatório atual ao relatório de destino. |

**Links codificados (sintaxe no estilo wiki)**

Para obter o máximo de flexibilidade na navegação pelos relatórios, use links codificados no estilo Wiki. Esses links podem ser inseridos em caixas de texto HTML ou no campo “Navegar” das propriedades do botão. Os links codificados permitem navegar para qualquer relatório, incluindo visualizações filtradas e relatórios em outros projetos.

**Sintaxe básica**

`[[report|display-text|tooltip-text]]`

Onde “report” é o destino, “display-text” é o texto visível do link (opcional) e “tooltip-text” é o texto que aparece ao passar o mouse (opcional).

**Opções de sintaxe de links**

|  |  |
| --- | --- |
| **Sintaxe** | **Descrição** |
| /ReportName | Acesse um relatório de nível superior (a barra inicial indica a raiz) |
| ChildReport | Navegar até um relatório filho (em relação ao atual) |
| .. | Subir um nível na hierarquia do relatório |
| ../SiblingReport | Navegue até um relatório do mesmo nível (suba um nível e, em seguida, acesse o relatório) |
| / | Acesse o relatório padrão (inicial) do projeto |
| //nome-do-projeto/relatório | Acesse um relatório em um projeto diferente |
| tab:TabName/ReportName | Acesse um relatório em uma guia específica |
| dialog:report:/ReportName | Abrir o relatório em uma caixa de diálogo modal (pop-up) |
| %MetricName | Link para um relatório de métricas; exibe o valor da métrica como texto do link |
| dataTable:TableName | Acesse uma tabela de dados específica ( v12.1+ ) |
| costModel:ModelName | Acesse um relatório de visão geral do modelo ( v12.1+ ) |
| /@Object/!FILTRO[...] | Acessar um relatório de objetos filtrado |

**Exemplos de links codificados**

**Navegue até um relatório secundário com texto personalizado e dica de ferramenta:**

`[[Applications|Click here|This report is preliminary.]]`

**Abrir um relatório de nível superior em uma janela modal:**

`[[dialog:report:/Server Group Analysis/Server Detail|Server Detail|Examine details.]]`

**Acesse um relatório filtrado:**

`[[/Software Report/@Cost Source/!FILTER[Cost Source Master Data.Cost
Pool=Software]|Software Report]]`

**Acesse um relatório em uma guia de outro projeto:**

`[[//Budget1/tab:Budgeting/2013 Budget]]`

**URL Codificação de caracteres especiais**

Se os nomes do seu relatório ou os valores dos filtros contiverem caracteres especiais, codifique-os usando a codificação padrão URL :

|  |  |  |
| --- | --- | --- |
| **Caractere** | **Valor codificado** | **Exemplo de uso** |
| / (barra) | %2F | Relatório de nomes que contêm barras |
| " (aspas) | %22 | Filtrar valores entre aspas |
| (espaço) | + ou %20 | Nomes de relatórios com várias palavras |

**Coleção de relatórios Navigator**

As coleções de relatórios agrupam relatórios relacionados, e o componente navegador de coleções de relatórios oferece aos usuários uma maneira visual de alternar entre os relatórios da mesma coleção. Quando você adiciona um relatório a uma coleção, o componente navegador é automaticamente adicionado ao relatório, aparecendo como uma barra de guias ou um menu na parte superior do relatório.

Os navegadores de coleções de relatórios são gerenciados na guia Projeto > caixa de diálogo Coleções de relatórios. Os administradores podem criar coleções personalizadas, atribuir relatórios a coleções, definir a ordem de exibição e configurar quais funções têm acesso a cada coleção.

**Caixas de texto HTML com links**

As caixas de texto HTML podem conter links de navegação utilizando sintaxe no estilo Wiki, oferecendo flexibilidade para a criação de interfaces de navegação personalizadas. Adicione imagens, texto formatado e vários links em um único componente.

**Inserir uma caixa de texto HTML**

1. Na guia Relatório, clique no ícone HTML
2. A caixa de diálogo “Editar conteúdo” é exibida, onde você pode inserir código HTML e links no estilo Wiki
3. Clique em “Aplicar” para visualizar ou em “OK” para salvar e fechar

Observação: as caixas de texto HTML não suportam o recurso " JavaScript ". Os links HTML não podem incluir manipuladores de eventos do tipo ` JavaScript `.

**Tópico principal:** [Componentes do relatório: Navegação](../../../../studio/new-uc/reference/report-studio-reference/report-component-navigation.html)
