---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Adicionar uma estrutura de árvore de subtotal a uma tabela"
breadcrumb: []
source_path: "studio/reports/tables/add-subtotal-tree.html"
images:
  - "resources/images/studio_images/studioimages/reports/rep329.png"
  - "resources/images/studio_images/studioimages/reports/rep341.png"
  - "resources/images/studio_images/studioimages/reports/rep342.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Adicionar uma estrutura de árvore de subtotal a uma tabela

**Aplica-se a** : TBM Studio 12.0 e posterior

Se estiver criando uma tabela hierárquica, é possível criar uma tabela com linhas expansíveis. Quando você expande uma linha, as linhas do próximo nível inferior na hierarquia são exibidas abaixo da linha expandida. Por exemplo, você pode querer detalhar por unidade de negócios, aplicativo e serviço. Um exemplo é mostrado na imagem a seguir.

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep329.png)

Figura A. Um exemplo de tabela com uma estrutura de árvore de subtotal.

## Diretrizes gerais

As diretrizes a seguir se aplicam às estruturas em árvore subtotais:

- Você pode aninhar linhas em vários níveis.
- Você pode exibir todas as sub-linhas ou especificar o número de sub-linhas a serem exibidas com um link **Outro** para exibir as sub-linhas restantes.
- Você pode usar campos de vários objetos se os campos estiverem bloqueados para os objetos.
- Os fatiadores ainda se aplicam à mesa.
- Funciona com tabelas baseadas em objetos.

## Criar uma estrutura em árvore de subtotais

1. Criar uma nova tabela ad-hoc.
2. Arraste dois ou mais campos para a área **Rows (Linhas** ) do painel **Component Configuration (Configuração de componentes** ).

   Se estiver adicionando campos de um ou mais objetos, os campos deverão estar bloqueados para o objeto.
3. Adicione um ou mais campos à área **Values (Valores** ) do painel **Ad Hoc Query Configuration (Configuração de consulta ad hoc** ).
4. Clique na guia **Data (Dados** ).
5. No grupo **Estrutura**, clique na opção **Como árvore**.
6. Se apropriado, especifique o número máximo de crianças que serão exibidas clicando na opção **Max Children (Máximo de crianças** ).

   Uma linha de **outro** link é adicionada à tabela para exibir as linhas restantes.

## Exportar uma tabela de visualização em árvore para o Excel

Você pode exportar uma tabela de visualização em árvore para o Excel. Quando a tabela é exportada, todas as linhas pai e filha são exportadas. A primeira coluna de cada linha filha é recuada por dois espaços para indicar o nível de hierarquia em que a linha se encontra. A exportação para o Excel não criará uma tabela de árvore correspondente. Em vez disso, ele criará uma tabela simples. Por exemplo, a tabela a seguir, quando exportada.

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep341.png)

Seria parecido com:

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep342.png)
