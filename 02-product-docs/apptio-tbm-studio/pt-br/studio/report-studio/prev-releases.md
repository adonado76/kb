---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Lançamentos anteriores"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "ApptioIBM Report Studio (Novo)"
  - "Notas sobre a liberação"
source_path: "studio/report-studio/prev-releases.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Lançamentos anteriores

## 12.11.21 - Abril de 2026

Atenção: O novo Studio de Relatórios já está disponível para todos, oferecendo uma experiência moderna e intuitiva para criar, personalizar e visualizar relatórios. Esta versão permite a adoção completa, incluindo a criação, a migração e o compartilhamento de relatórios.

- **Controle administrativo para o acesso ao Visualizador de Relatórios:** os administradores agora podem controlar se os usuários finais têm acesso ao Visualizador de Relatórios. Essa configuração está ativada por padrão, garantindo que os usuários finais possam visualizar os relatórios. Os administradores podem desativar essa função nas configurações do projeto, caso queiram restringir o acesso.
- **Componente Botão:** Adiciona um componente de botão configurável no Report Studio que permite aos usuários acionar ações como navegação e execução de scripts ao clicar nele. Inclui opções de formatação flexíveis para personalizar a aparência e o comportamento dos botões nos relatórios.
- **Regras de visibilidade das guias:** Configure expressões de visibilidade para as guias dentro de um componente de grupo com guias. As guias serão exibidas ou ocultadas dinamicamente no Visualizador de Relatórios com base nas condições definidas.
- **Eixo compartilhado em gráficos sobrepostos:** Os gráficos sobrepostos agora oferecem suporte a um eixo compartilhado, permitindo que várias séries de dados sejam alinhadas em uma escala comum para facilitar a comparação e melhorar a legibilidade.
- **Quebra automática de** linha para cabeçalhos e células de tabelas: As tabelas e as tabelas editáveis agora oferecem suporte à quebra automática de linha tanto nos cabeçalhos das colunas quanto nas células, melhorando a legibilidade e garantindo que o conteúdo fique totalmente visível sem a necessidade de redimensionamento manual.
- **Visualizações salvas no Visualizador de Relatórios:** salve instantâneos personalizados de relatórios com seus filtros e interações preferidos. Alterne facilmente entre as visualizações ou defina uma visualização inicial para uma navegação mais rápida.
- **Envio de relatórios por e-mail no Visualizador de Relatórios:** Agora, os usuários podem enviar relatórios diretamente do visualizador de relatórios por e-mail. O relatório pode ser compartilhado como um anexo em PDF ou como um link para visualizar ou baixar o PDF.
- **Assistente de Migração para Relatórios:** Use o Assistente de Migração para migrar relatórios do TBM Studio clássico para o novo Report Studio.
- Lançamento das coleções de relatórios prontas para uso em pré-visualização pública.

## 12.11.20 - Fevereiro de 2026

- **Mostrar valores nas tabelas:** explore a distribuição dos dados por coluna visualizando os valores únicos e suas contagens no menu da coluna.
- **Exibição em árvore para tabelas** : as tabelas agora oferecem uma nova opção de exibição em árvore que permite visualizar dados hierárquicos com linhas que podem ser expandidas e recolhidas.
- **Exportar relatórios para PDF:** Agora é possível exportar relatórios para PDF diretamente do New Report Studio, por meio de **Arquivo -> Baixar como -> PDF**, permitindo um compartilhamento rápido sem precisar alternar para o Visualizador de Relatórios.
- **Exportar tabelas para o Excel:** Agora é possível exportar tabelas individuais de um relatório diretamente para o Excel através do menu de opções da tabela, facilitando a análise e o compartilhamento dos dados do relatório fora do aplicativo. Atualmente disponível no Novo Visualizador de Relatórios.
- **Suporte a várias moedas:** O suporte a várias moedas já está disponível no Report Studio e no Report Viewer. Os administradores podem testar relatórios utilizando diferentes moedas e tipos de taxa, e os usuários podem alternar entre moedas no visualizador – com as seleções refletidas nos relatórios em PDF e Excel.

## 12.11.19 - Janeiro de 2026

**Criação de relatórios e coleções de relatórios com configurações de visibilidade**

- Os relatórios agora incluem uma configuração **“Visível por”** durante a criação, permitindo que você controle se um relatório é visível para todos, apenas para você ou para funções específicas.
- As coleções de relatórios agora suportam uma propriedade **“Visível por”**, permitindo que a visibilidade seja restrita a todos, apenas a você ou a funções selecionadas.

**Atualização do layout do painel da tela do relatório** - Os painéis explorador de dimensões, dados e formato para componentes e visualizações foram movidos do lado direito para o lado esquerdo da tela do relatório.

**Aprimoramentos nos componentes do relatório**

- Tabela - Suporte para visualizações compatíveis
- Slicer - Adicionada uma nova propriedade Slicer Type para dividir componentes com opções de lista suspensa e vertical, permitindo uma apresentação flexível com base no layout do relatório e nas necessidades de interação do usuário.
- KPI - Os KPIs agora suportam a exibição independente de métricas primárias e secundárias, permitindo que você mostre cada métrica separadamente, em vez de apenas em uma visualização comparativa.
- Os KPIs, os seletores de colunas e os pivôs rápidos agora suportam fórmulas personalizadas.

**Visualizações**

- Gráficos de colunas + linhas
- Gráficos de colunas empilhadas + linhas
- Classificação de dados do gráfico – Os gráficos agora suportam a classificação configurável de dados, permitindo que você classifique os dados por um valor selecionado em ordem crescente ou decrescente a partir do painel de dados.

**Opções aprimoradas de depuração de widgets e atualização de dados** - Adicionadas novas ações ao cabeçalho do widget para atualizar dados, visualizar caminhos completos de dados e abrir dados de depuração em /data para facilitar o diagnóstico e a validação.

**Exportar relatórios para PDF** - O visualizador de relatórios permite exportar o relatório atualmente visualizado para um arquivo PDF, facilitando o download, o compartilhamento ou o arquivamento do relatório em um formato imprimível.

## 12.11.18 - Novembro de 2025

- **Suporte à localização** - Adicionado suporte à localização em toda a nova experiência do Report Studio, permitindo que usuários de todas as regiões tenham uma interface consistente e integrada em seu idioma e formato preferidos.
- **Novos componentes** - Componente de grupo para organizar e gerenciar vários componentes de relatório na tela como uma única unidade.
- **Aprimoramentos da tabela**
  - Capacidade de **renomear colunas** diretamente nas tabelas.
  - Suporte para **filtros zero** para incluir ou excluir explicitamente valores zero.
  - Opção para **ocultar dimensões intermediárias** para simplificar as visualizações da tabela.
  - Aprimoramentos nas **tabelas editáveis** para melhorar a entrada de dados e a usabilidade.
- **Aprimoramentos no Seletor de Colunas** - O Seletor de Colunas agora suporta a seleção baseada em data, permitindo que os usuários controlem as colunas de data dinamicamente.
- **Visualizações e interações** - Suporte para visualizações compatíveis com navegação detalhada habilitada em gráficos para uma exploração mais profunda dos dados.
