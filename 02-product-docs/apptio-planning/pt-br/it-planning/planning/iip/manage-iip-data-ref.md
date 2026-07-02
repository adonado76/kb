---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Configurar projetos"
breadcrumb:
  - "Planning"
  - "Planejamento de projetos"
source_path: "it-planning/planning/iip/manage-iip-data-ref.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Configurar projetos

Importante: *Disponível com a* *assinatura* ***do Apptio Planning Standard***

Lembre-se: *o recurso de Planejamento Integrado de Investimentos (IIP) está ativado.*

Ao usar o Planejamento de projetos no Apptio Planning, é necessário configurar a tabela de dados de referência do projeto para ativar o planejamento baseado em projetos. Os projetos podem ser organizados como uma lista simples ou dentro de uma hierarquia e são usados para marcar itens de linha do plano, navegar nos planos por projeto e atribuir permissões de usuário no nível do projeto.

## Configurar o planejamento do projeto

Observação: *As funções de administrador ou proprietário do processo orçamentário são necessárias para executar essas tarefas.*

Antes de começar a inserir os itens de linha do projeto, será necessário ativar o Planejamento Integrado de Investimentos (IIP) e configurar os dados de referência para que os projetos se comportem de forma consistente no modelo.

A ativação do Planejamento integrado de investimentos ativa as tabelas de dados de referência relacionadas e adiciona o menu suspenso Projeto para navegar pelos planos**.**

**Permitir o planejamento de projetos**

1. Vá para **Settings** (ícone de engrenagem) **→ Company Profile**.
2. Selecione **Ativar planejamento integrado de investimentos.**
3. Clique em **Save and Exit (Salvar e sair** ).

**Configurar dados de referência do grupo de projetos**

Os dados de referência **do grupo de projetos** definem a estrutura hierárquica para a qual os projetos são transferidos. Os grupos de projetos são normalmente usados para representar portfólios, fluxos de valor ou programas estratégicos que organizam projetos relacionados em uma única camada de gerenciamento ou relatório.

Os grupos de projetos são opcionais se você tiver uma lista simples de projetos.

1. Navegue até **Configuration → Reference Data → Project Group.**
2. Exportar o modelo e preencher os campos-chave:

   |  |  |  |
   | --- | --- | --- |
   | **Campo** | **Necessário** | **Descrição** |
   | Código | x | Um identificador exclusivo para o Grupo de Projetos. Usado como chave para o mapeamento da hierarquia do projeto. |
   | Nome | x | O nome de exibição do grupo de projetos (por exemplo, "Portfólio de experiência do cliente" ou "Modernização do data center"). |
   | Código dos pais | Condicional | Necessário se a hierarquia do grupo de projetos incluir vários níveis (por exemplo, fluxo de valor → portfólio → programa). Deixe em branco para grupos de nível superior. |
   | Código de unidade monetária | Condicional | Necessário se a opção de várias moedas estiver ativada. Define a moeda padrão para todos os projetos dentro desse grupo de projetos. |
   | Código do centro de custo |  | Centros de custo associados a esse grupo de projetos. Insira os códigos de centro de custo correspondentes, separados por vírgulas. Esse campo é opcional - os centros de custo também podem ser definidos no nível do projeto. |
   | Grupo de preços |  | Campo opcional para agrupar projetos ou serviços semelhantes para modelagem interna de preços ou taxas. |
3. Importe o CSV atualizado e **publique** as alterações para que elas fiquem disponíveis para novos planos.

**Configurar dados de referência do projeto**

A tabela de dados de referência **do projeto** define todos os **projetos ou investimentos em nível de folha** que representam o nível mais baixo da hierarquia do projeto. Esses são os registros que serão atribuídos às partidas individuais do orçamento em Apptio Planning.

1. Navegue até **Configuration → Reference Data → Project.**
2. Exportar o modelo e preencher os campos-chave:

   |  |  |  |
   | --- | --- | --- |
   | **Campo** | **Necessário** | **Descrição** |
   | Código | x | Um identificador exclusivo para o projeto. Usado como a chave para importações de dados, mapeamentos e relatórios. |
   | Nome | x | O nome de exibição do projeto, normalmente o nome completo do projeto ou do investimento. |
   | Código dos pais | x | O código do Grupo de Projetos pai para o qual esse projeto é transferido. Define o alinhamento hierárquico entre projetos e grupos de projetos. |
   | Permitir qualquer centro de custo | x | Valor booleano (verdadeiro/falso). Quando definido como **True**, permite que o projeto seja associado a qualquer centro de custo durante o planejamento. Quando **Falso**, restringe o planejamento apenas aos centros de custo mapeados. |
   | Centro de custo padrão |  | O centro de custo padrão associado ao projeto. Quando um item de linha é marcado com esse projeto, o centro de custo é preenchido automaticamente. Insira o código do centro de custo correspondente. Certifique-se de que esse Código do centro de custo esteja listado no campo Código do centro de custo. |
   | Código do centro de custo | x | Centros de custo onde as despesas desse projeto são incorridas. Insira os códigos de centro de custo correspondentes, separados por vírgulas. |
   | Descrição |  | Campo de texto opcional que descreve o objetivo, o escopo ou os principais resultados do projeto. |
   | Gestor de Projeto |  | O indivíduo responsável pela execução e entrega diária do projeto. |
   | Data de Início |  | A data planejada para o início do projeto. Pode ser usado para relatórios ou filtragem baseados em linha do tempo. |
   | Abertos |  | Um campo de agrupamento para associar este projeto a uma iniciativa ou programa estratégico de nível superior. Pode ser usado para geração de relatórios ou filtragem |
   | Tipo de investimento |  | Define o tipo de investimento. Pode ser usado para geração de relatórios ou filtragem. |
   | Prioridade |  | Indica a prioridade ou a classificação do projeto no portfólio. Útil para relatórios de PMO ou de alinhamento estratégico. |
   | Proprietário do projeto |  | O indivíduo ou função responsável pelo financiamento, direção e tomada de decisões do projeto. |
   | Patrocinador BU |  | A unidade de negócios patrocinadora que financia ou se beneficia do projeto. |
3. Importe o CSV atualizado e **publique** as alterações para que elas fiquem disponíveis para novos planos.
