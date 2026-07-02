---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Funções de trabalho de projeto"
breadcrumb:
  - "Planning"
  - "Planejamento de atividades de trabalho do projeto"
source_path: "it-planning/planning/iip/manage-project-labor-role-data-ref.html"
images:
  - "resources/images/it_planning_images/three-dots.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Funções de trabalho de projeto

Importante: Disponível com a *assinatura* ***Apptio do Planning Standard.***

Lembre-se: *o recurso de Planejamento Integrado de Investimentos (IIP) está ativado.*

Os dados de referência **da Função de Trabalho do** Projeto definem as funções específicas do projeto utilizadas para recursos de trabalho internos ou externos, juntamente com as taxas horárias de trabalho aplicadas quando esses recursos cobram tempo a um projeto.

Essa dimensão permite o planejamento de mão de obra em nível de projeto, permitindo que as organizações mapeiem funções de RH para funções específicas do projeto e definam taxas de cobrança ou cobrança cruzada apropriadas. Por exemplo, um funcionário com uma função de RH de Desenvolvedor de Software 2 pode receber a Função de Trabalho no Projeto de Desenvolvedor ao trabalhar em um projeto.

## Configurar funções de trabalho do projeto

***Observação:*** *as funções de administrador ou responsável pelo processo orçamentário são necessárias para realizar essas tarefas.*

1. No menu de navegação, vá para **Configuração** → **Dados de referência** → **Dimensões padrão** → **Função de trabalho do projeto**.
2. Exporte o modelo e preencha os campos principais:

   |  |  |
   | --- | --- |
   | **Campo** | **Descrição** |
   | **Nome** | O nome de exibição da Função de Trabalho do Projeto. Isso é obrigatório. |
   | **Moeda** | O código da moeda para a taxa de mão de obra. Obrigatório quando o suporte a várias moedas está ativado no *Perfil da Empresa*. Se deixado em branco, o sistema usa a moeda comum padrão. |
   | **Taxa de mão de obra do projeto** | A taxa horária associada à Função Trabalhista do Projeto. Suporta valores decimais. Utilizado para cobranças cruzadas de mão de obra. |
   | **Origem** | A origem da função de trabalho (por exemplo, *interna*, *externa*, *nome do fornecedor* ). Ajuda a distinguir a atribuição de mão de obra em vários modelos de sourcing. |
3. Importar o CSV atualizado
4. Clique em ![menu de elipses](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/three-dots.jpg) e **publique** as alterações para que elas fiquem disponíveis para os planos.

## Como as funções do projeto de trabalho são utilizadas

As funções de trabalho do projeto são utilizadas no **planejamento das atividades de trabalho**, onde as organizações atribuem recursos de trabalho a funções específicas do projeto para estimar o esforço e o custo.

- **Mapeamento de funções específicas do projeto:**

  As funções de RH podem não refletir como a mão de obra é alocada nos projetos. As funções de trabalho do projeto permitem definir categorias de funções relacionadas ao projeto (por exemplo, desenvolvedor, analista, arquiteto).
- **Planejamento do esforço de mão de obra:**

  Durante o planejamento do projeto, horas ou FTEs podem ser alocadas às Funções de Trabalho do Projeto para estimar o esforço de trabalho.
- **Cobrança cruzada ou aplicação de taxa interna:**

  As taxas horárias atribuídas às funções de trabalho do projeto determinam o custo cobrado aos projetos pelo uso dos recursos dessa função.
