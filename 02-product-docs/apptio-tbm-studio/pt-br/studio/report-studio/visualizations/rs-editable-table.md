---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Tabela editável"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "ApptioIBM Report Studio (Novo)"
  - "Visualizações"
source_path: "studio/report-studio/visualizations/rs-editable-table.html"
images:
  - "resources/images/studio_images/apptio-script.png"
  - "resources/images/studio_images/cust-form-et.png"
  - "resources/images/studio_images/dd-1.png"
  - "resources/images/studio_images/et-sh-1.png"
  - "resources/images/studio_images/et-sh-2.png"
  - "resources/images/studio_images/et-uploaddata.png"
  - "resources/images/studio_images/etcf.png"
  - "resources/images/studio_images/etrefdate.png"
  - "resources/images/studio_images/etspacer.png"
  - "resources/images/studio_images/row-limit-et.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tabela editável

Uma tabela editável permite que você edite os dados diretamente na tabela, como atualizar valores, adicionar novas linhas ou excluir linhas existentes, sem precisar sair da tabela ou navegar para uma interface de edição separada.

## Quando usar uma tabela editável

Use tabelas editáveis quando desejar:

- Atualizar valores em linha
- Colabore em dados estruturados

## Adicionar uma tabela editável ao relatório

1. Adicione uma tabela editável a partir do painel Visualizações na barra de ferramentas
2. Clique na tabela editável para ativar os painéis Data e Format.
3. Painel de dados
   1. Arraste um ou mais campos para **a** área Colunas a partir do Explorador de dimensões.
4. Painel de formatação
   1. Propriedades gerais – Veja [Propriedades do componente](../components/components.html#abt-comp__comprop)
   2. Propriedades específicas da tabela editável
      1. Colunas não editáveis - Selecione/desmarque colunas específicas nas Tabelas Editáveis como não editáveis.
      2. Permissões - Conceda/remova permissões para propriedades da tabela (como adicionar linha, excluir linha, alterar histórico, etc.) para funções selecionadas ou para toda a organização.
      3. Script - Edite os scripts para habilitar ações como edições de tabelas, e-mails, fluxos de trabalho e lógica de botões.
      4. Totais - Exibe o total dos valores numéricos nas linhas e/ou colunas.
      5. Desativar edições - Insira as condições para desativar as edições na tabela.

A Tabela editável suporta fórmulas personalizadas e dimensões de fórmulas. Para obter mais detalhes, consulte [Fórmulas personalizadas.](../create-first/custom-formula.html "As fórmulas personalizadas (também conhecidas como dimensões de fórmula) permitem definir novas dimensões calculadas utilizando campos existentes no seu modelo de dados. Isso permite uma análise mais profunda e insights mais ricos, sem a necessidade de alterações no conjunto de dados ou esquema subjacente.")

## Carregar dados em uma tabela editável

O recurso **Upload Data** permite preencher rapidamente as tabelas editáveis com dados de arquivos. Isso facilita a adição ou atualização de informações em massa sem a necessidade de inserir manualmente cada valor.

**Etapas para uso**

1. Navegue até a seção **Editable Table (Tabela editável** ) no aplicativo.
2. Clique no botão **Upload** localizado no canto superior direito da interface da tabela.
3. Na **caixa de diálogo de seleção de arquivos**, escolha o arquivo que deseja carregar
   1. Formatos compatíveis:.csv,.xlsx
4. Clique em **Open (Abrir** ) para iniciar o upload.
5. Após a conclusão do upload, a tabela será **atualizada** e exibirá os **dados recém-adicionados.**

![imagem de upload de dados](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/et-uploaddata.png)

## Mostrar/ocultar colunas em uma tabela editável

O recurso **Show/Hide Columns** aprimora a rastreabilidade e a usabilidade dos dados, permitindo que os usuários personalizem as colunas exibidas em uma tabela editável. Ele também ajuda a simplificar sua visualização por meio de auditoria e análise, mantendo os valores confidenciais ou gerados pelo sistema (.pk,.Username e .EditDate ) ocultos por padrão.

**Etapas para uso**

1. Abra **as Configurações da coluna** (geralmente representadas por um ícone de engrenagem ou de coluna).
2. Será exibida uma lista de colunas disponíveis com caixas de seleção.
3. Marque as caixas das colunas que deseja exibir e desmarque aquelas que deseja ocultar.
4. A exibição da tabela será atualizada instantaneamente para refletir suas seleções.

![imagem de mostrar ocultar coluna](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/et-sh-1.png)

![imagem da coluna oculta](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/et-sh-2.png)

## Apptio Roteiro

O recurso de script Apptio permite **interações e validações dinâmicas** em tabelas editáveis por meio de scripts de backend.

**Etapas para uso**

1. O script é executado automaticamente em segundo plano - não é necessária nenhuma ação do usuário.
2. Ele garante que os comportamentos da tabela, como formatação condicional, validação de dados ou cálculos automáticos, sejam executados corretamente à medida que os usuários interagem com a tabela.

![imagem do script apptio](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/apptio-script.png)

## Publicar para transformar tabela

O recurso Publicar para transformar tabela permite que os usuários publiquem as alterações feitas em uma tabela editável em uma tabela de transformação vinculada. Isso garante que todas as atualizações ou edições feitas no nível de entrada de data sejam refletidas no downstream para processamento e análise adicionais.

**Etapas para uso**

1. Depois de fazer as edições na tabela editável, clique no botão **Publish (Publicar** ).
2. Será exibida uma janela modal mostrando a tabela de transformação associada.
3. Revise os detalhes e clique em **Confirm (Confirmar** ) para continuar.
4. Será exibida uma notificação confirmando que as alterações foram anexadas à tabela de transformação.
5. O modal **Check-In** será aberto, permitindo que você finalize e envie as alterações.

   Observação: no momento, essa funcionalidade está disponível apenas para **usuários administradores**.

## Desativar edições

Este campo aceita uma expressão de texto dinâmica. Se a expressão for avaliada como verdadeira, a edição será desativada para a tabela. No exemplo abaixo, o usuário ddavis não poderá editar a tabela.

```
“ {$CurrentUser:Users.ID}=ddavis@ABCCompany.com ”
```

## Coluna espaçadora

A coluna espaçadora adiciona separação visual entre as colunas para melhorar a legibilidade. Para adicionar uma coluna espaçadora a uma tabela editável, clique com o botão direito do mouse na tabela e selecione **Inserir coluna à direita** > **Coluna espaçadora**. Uma nova coluna aparece na parte superior da tabela editável.

![imagem da coluna espaçadora](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/etspacer.png)

## Ativar/Desativar Transferência

Esta função permite transportar os valores numéricos em um relatório de tabela editável (ET). Na tabela editável, selecione **Mais opções** e, em seguida, selecione a opção **Ativar transporte**.

![imagem de ativação e desativação de colunas](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/etcf.png)

Observação: o transporte só é aplicável a valores numéricos e colunas consecutivas. Se houver uma coluna não numérica entre elas, o transporte não será aplicado posteriormente.

Não é possível mover as colunas se a opção Ativar transferência estiver selecionada. Se o usuário selecionar **Desativar transporte**, o transporte será desativado e o botão aparecerá como **Ativar transporte**, e vice-versa.

O comportamento de transporte é aplicável apenas para a sessão local e não persiste. Portanto, sempre que o usuário retornar, ele estará no estado padrão de transporte ativado.

## Atualizar dados

A atualização de dados atualiza o conteúdo da tabela globalmente. Ele aparece na parte superior ou inferior direita da tabela editável.

![imagem da opção de atualizar dados](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/etrefdate.png)

## Diagnóstico de dados

Esse recurso permite que você abra (/data) para depuração adicional. Para ver e abrir o caminho completo dos dados, selecione a tabela editável e clique nos três pontos.

![imagem de diagnóstico de dados](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/dd-1.png)

## Quebra automática de linha para cabeçalhos e células editáveis da tabela

As tabelas editáveis agora oferecem suporte ao quebra automática de linha tanto nos cabeçalhos das colunas quanto nas células, melhorando a legibilidade e garantindo que o conteúdo fique totalmente visível sem a necessidade de redimensionamento manual.

## Configurando limites de linhas em tabelas editáveis

As tabelas editáveis agora oferecem suporte a limites de linhas configuráveis, permitindo que os usuários controlem o número máximo de linhas que podem ser adicionadas ou editadas em uma tabela. Isso ajuda a gerenciar os fluxos de trabalho de entrada de dados de forma mais eficaz e garante um melhor controle sobre o tamanho das tabelas e sua usabilidade.

![imagem para definir o limite de linhas na tabela editável](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/row-limit-et.png)

## Exibição de dados formatados em tabelas editáveis

As tabelas editáveis agora oferecem suporte à exibição de dados formatados, garantindo que os valores sejam exibidos de acordo com as regras de formatação configuradas na tabela. Isso melhora a legibilidade e proporciona uma experiência mais consistente na geração de relatórios e na entrada de dados.

## Como usar fórmulas personalizadas com a opção “Adicionar ao filtro” em tabelas editáveis

Agora é possível usar fórmulas personalizadas com o recurso “Adicionar ao filtro” nas tabelas editáveis. Essa melhoria permite que os usuários criem filtros mais flexíveis e dinâmicos com base em valores calculados dentro da tabela.

![imagem para usar uma fórmula personalizada na opção “Adicionar ao filtro”](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/cust-form-et.png)
