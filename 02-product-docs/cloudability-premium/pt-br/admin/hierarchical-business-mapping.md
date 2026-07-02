---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Organizar dados usando mapeamentos hierárquicos de negócios"
breadcrumb:
  - "Cloudability Premium"
  - "Configuração"
  - "Organize seus gastos com a nuvem"
  - "Mapeamento de negócios"
source_path: "admin/hierarchical-business-mapping.html"
images:
  - "images/hier-business-mapping-create-add-layer.png"
  - "images/hier-business-mapping-create-add-layer2.png"
  - "images/hier-business-mapping-create-add-name-layer.png"
  - "images/hier-business-mapping-create-name.png"
  - "images/hier-business-mapping-create-start.png"
  - "images/hier-business-mapping-create-upload-mapping.png"
  - "images/hier-business-mapping-listing.png"
  - "images/hier-business-mapping-upload-rev.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Organizar dados usando mapeamentos hierárquicos de negócios

Nota:

Os mapeamentos hierárquicos de negócios têm atualmente um limite de 1000 linhas de mapeamentos de negócios.

Um mapeamento hierárquico de negócios é uma forma especializada de mapeamento de negócios projetada para criar e manter relacionamentos de dados hierárquicos entre dimensões de negócios (até cinco). As dimensões de negócios são dimensões sintéticas geradas usando lógica de negócios (instruções de mapeamento de negócios) para mapear tags específicas da nuvem e do fornecedor para conceitos de negócios significativos.

Um mapeamento hierárquico de negócios (HBM) permite que você crie um conjunto relacionado de dimensões de negócios que pode suportar rollups de custos em Cloudability Reporting, View Filters e Plans. Essa abordagem simplifica a criação e a manutenção da lógica comercial necessária para manter as Business Dimensions relacionadas sincronizadas.

## Como funciona?

Imagine que você precise gerar relatórios sobre custos em diferentes níveis de propriedade de custos em sua organização: Equipe, Departamento e Grupo. Você deseja uma dimensão de negócios para cada nível e, normalmente, precisaria criar mapeamentos de negócios separados para cada um deles. No entanto, essas dimensões seguem uma estrutura hierárquica: as equipes se estendem até os departamentos, que, por sua vez, se estendem até os grupos.

Para definir esses relacionamentos usando mapeamentos de negócios padrão, você precisaria criar declarações especificando como cada equipe é mapeada para um departamento e como cada departamento é mapeado para um grupo. Embora essa abordagem possa funcionar para um pequeno número de equipes, departamentos e grupos, ela se torna difícil de gerenciar em escala - especialmente quando os relacionamentos de rollup mudam com o tempo (por exemplo, novas equipes ou departamentos são adicionados ou as estruturas de relatórios são reorganizadas).

Um mapeamento hierárquico de negócios (HBM) simplifica esse processo, permitindo que você defina um único mapeamento de negócios que se aplica a várias dimensões de negócios em uma hierarquia de rollup estruturada. Em vez de definir manualmente mapeamentos de negócios individuais usando uma lógica complexa e interdependente no estilo IF-THEN, você pode criar toda a hierarquia usando uma abordagem declarativa simples:

1. Selecione uma dimensão de negócios para usar como base da hierarquia (por exemplo, equipe).
2. Especifique os níveis hierárquicos adicionais desejados (por exemplo, Departamento e Grupo).
3. Faça upload de um arquivo de mapeamento que especifique como os valores em cada camada se relacionam com a camada principal.

Cloudability gera automaticamente novas Business Dimensions e instruções de mapeamento de negócios para cada nível hierárquico. Se os relacionamentos de rollup forem alterados - como a adição ou remoção de Departamentos ou Grupos - basta fazer o upload de um novo arquivo de mapeamento e o sistema atualizará todas as declarações de Mapeamento de Negócios de acordo. Isso garante que os valores corretos de Equipe, Departamento e Grupo sejam atribuídos de forma consistente para garantir rollups de custos precisos.

Além disso, o Hierarchical Business Mapping pode ser usado para criar visualizações que se alinham com a estrutura de rollup de custos do HBM. Consulte [Organizar visualizações usando visualizações hierárquicas](hierarchical-views.html) para saber mais.

## O que é um arquivo de mapeamento?

Um arquivo de mapeamento é uma forma estruturada de definir como os valores em cada camada do Hierarchical Business Mapping (HBM) são transferidos para a camada principal. Trata-se de uma tabela (arquivo CSV ), na qual:

- A coluna mais à esquerda representa a dimensão básica.
- Cada coluna subsequente representa um nível superior na hierarquia.
- Cada linha define como um valor na dimensão básica é mapeado para suas camadas principais.

Por exemplo, a tabela abaixo mostra um arquivo de mapeamento para um HBM em que Team (Equipe) é a dimensão básica, que se desdobra em Department (Departamento) e Group (Grupo). Há 10 equipes (Equipe 1 a Equipe 10), e cada linha especifica como uma equipe é mapeada para seu departamento e grupo correspondentes.

| Equipe | Departamento | Grupo |
| --- | --- | --- |
| Equipe 1 | Departamento A | Grupo X |
| Equipe 2 | Departamento D | Grupo Y |
| Equipe 3 | Departamento B | Grupo X |
| Equipe 4 | Departamento A | Grupo X |
| Equipe 5 | Departamento C | Grupo Y |
| Equipe 6 | Departamento B | Grupo X |
| Equipe 7 | Departamento C | Grupo Y |
| Equipe 8 | Departamento D | Grupo Y |
| Equipe 9 | Departamento B | Grupo X |
| Equipe 10 | Departamento C | Grupo Y |

Para fins ilustrativos, aqui está a mesma tabela, mas reformatada para destacar as relações hierárquicas entre equipes, departamentos e grupos. Esse formato facilita a visualização de como os Grupos são compostos por vários Departamentos e, por sua vez, como cada Departamento contém Equipes específicas.

| Equipe | Departamento | Grupo |
| --- | --- | --- |
| Equipe 1 | Departamento A | Grupo X |
| Equipe 4 |
| Equipe 3 | Departamento B |
| Equipe 6 |
| Equipe 9 |
| Equipe 5 | Departamento C | Grupo Y |
| Equipe 7 |
| Equipe 10 |
| Equipe 2 | Departamento D |
| Equipe 8 |

Neste exemplo de arquivo de mapeamento:

- O Grupo X inclui o Depto. A e o Depto. B :
  - O Departamento A consiste na Equipe 1 e na Equipe 4.
  - O Departamento B consiste na Equipe 3, na Equipe 6 e na Equipe 9.
- O Grupo Y inclui o Depto. C e o Depto. D :
  - O Departamento C consiste na Equipe 5, na Equipe 7 e na Equipe 10.
  - O Departamento D consiste na Equipe 2 e na Equipe 8.

## Conceitos de dimensão empresarial hierárquica (HBM)

Nome

O nome da hierarquia geral. Esse é um atributo obrigatório. Escolha um nome que transmita claramente sua estrutura ou propósito geral, pois ele aparecerá como o nó raiz da hierarquia - ou seja, o nome da visualização de nível superior se você criar uma estrutura de visualização hierárquica para o HBM.

Dimensão da base

Toda hierarquia é construída sobre uma dimensão de negócios básica. Essa deve ser uma dimensão de negócios existente e não pode ser uma dimensão usada em outro HBM.

Camadas de hierarquia

Camadas adicionais de hierarquia (roll up). Cada camada deve ter um nome, e esse nome deve ser exclusivo (não pode ser o nome de uma dimensão de negócios existente). Eles serão gerados como novas dimensões de negócios após a conclusão da configuração do HBM.

## Como configurar mapeamentos hierárquicos de negócios

Listagem e revisão de dimensões hierárquicas de negócios

Na página inicial de Mapeamentos de negócios, na guia Dimensões hierárquicas, é possível ver uma lista de todas as dimensões hierárquicas de negócios que você configurou.

![captura de tela da dimensão de novos negócios](../../../../03-media/cloudability-premium/images/hier-business-mapping-listing.png)

Criação de dimensões hierárquicas de negócios

Para criar uma nova dimensão de negócios hierárquica:

1. Na guia Hierarchical Dimensions (Dimensões hierárquicas ), selecione New Business Dimension Hierarchy (Nova hierarquia de dimensão de negócios ) no menu Add (Adicionar).
2. A gaveta Criar hierarquia de dimensão será aberta na etapa Visão geral > Selecione Avançar para avançar para a próxima etapa (Definir camadas ).

   ![criar captura de tela da hierarquia de dimensões](../../../../03-media/cloudability-premium/images/hier-business-mapping-create-start.png)
3. Dê um nome à hierarquia > digite o nome desejado (por exemplo, Cost Org ) no campo Hierarchy Name (Nome da hierarquia ).

   ![captura de tela do cost org BD](../../../../03-media/cloudability-premium/images/hier-business-mapping-create-name.png)

   Nota:

   O nome da hierarquia é usado como o nome da visualização raiz da visualização hierárquica correspondente. Consulte [Organizar visualizações usando visualizações hierárquicas](hierarchical-views.html) para saber mais.
4. Selecione uma dimensão de negócios existente como a base da hierarquia > Clique no menu suspenso Selecionar a dimensão de base e escolha uma dimensão da lista (por exemplo, Equipe ).

   ![captura de tela da dimensão básica](../../../../03-media/cloudability-premium/images/hier-business-mapping-create-add-layer.png)

   Nota:

   Você deve selecionar uma dimensão de base antes de poder adicionar camadas de hierarquia.
5. Adicione camadas adicionais à hierarquia > clique no botão Adicionar camada de hierarquia e digite o nome da dimensão desejada (por exemplo, Departamento ) no modal exibido. Clique em Add.

   ![adicionar captura de tela da camada hierárquica](../../../../03-media/cloudability-premium/images/hier-business-mapping-create-add-name-layer.png)

   Nota:

   O valor padrão não é usado e pode ser ignorado.
6. Repita a Etapa 5 para adicionar outras camadas de hierarquia. Você pode adicionar até um total de quatro (4) camadas sobre a dimensão de base. Clique em Next (Avançar) para terminar de adicionar camadas e avançar para a próxima etapa (Importar valores ).

   ![criar captura de tela DH](../../../../03-media/cloudability-premium/images/hier-business-mapping-create-add-layer2.png)
7. Carregue um arquivo de mapeamento que descreva como os valores da dimensão base se mapeiam para os valores do nível superior > clique em “Procurar” para selecionar um arquivo ou arraste e solte um arquivo. CSV na caixa de importação. Clique em Importar para importar o arquivo de mapeamento e criar o HBM.

   ![navegar na captura de tela da dimensão](../../../../03-media/cloudability-premium/images/hier-business-mapping-create-upload-mapping.png)

   Nota:

   Ao clicar no link “Exportar o modelo de dimensão base” ( CSV ), será baixado um arquivo de modelo de dimensão base ( CSV ) já preenchido com os valores atuais da dimensão base, pronto para ser preenchido com os valores da dimensão pai.

Edição de dimensões de negócios hierárquicas

Para modificar um mapeamento hierárquico de negócios existente:

1. Selecione a opção Editar mapeamento de negócios no menu Opções (engrenagem). Isso abrirá a gaveta Edit Dimension Hierarchy (Editar hierarquia de dimensões ) na etapa Import Values (Importar valores ).
2. Renomeie a dimensão de negócios hierárquica > clique em Avançar para atualizar.
3. Carregue um arquivo de mapeamento revisado > clique em “Procurar” para selecionar um arquivo ou arraste e solte um arquivo. CSV na caixa de importação. Clique em Update (Atualizar ) para importar o arquivo de mapeamento e atualizar o HBM com os novos mapeamentos.

   ![editar captura de tela da dimensão de negócios](../../../../03-media/cloudability-premium/images/hier-business-mapping-upload-rev.png)

   Nota:

   Qualquer visualização hierárquica associada será atualizada automaticamente para refletir as alterações no mapeamento revisado.

   Para obter mais informações, consulte [Organizar visualizações usando visualizações hierárquicas.](hierarchical-views.html)

Eliminação de dimensões de negócios hierárquicas

Para excluir um mapeamento hierárquico de negócios existente, selecione a opção Excluir mapeamento de negócios no menu Opções (engrenagem). Isso removerá o mapeamento hierárquico de negócios do sistema e excluirá as dimensões de negócios de nível HBM, mas não a dimensão de negócios básica.

Nota:

Antes de excluir um HBM, como prática recomendada, você deve primeiro excluir a visualização hierárquica associada a ele.

Para obter mais informações, consulte [Organizar visualizações usando visualizações hierárquicas.](hierarchical-views.html)

**Tópico principal:** [Mapeamento de negócios](../admin/business-tags.html)
