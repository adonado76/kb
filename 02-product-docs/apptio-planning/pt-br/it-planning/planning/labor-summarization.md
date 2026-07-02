---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Resumir as finanças trabalhistas"
breadcrumb:
  - "Planning"
  - "Planejamento trabalhista"
source_path: "it-planning/planning/labor-summarization.html"
images:
  - "resources/images/it_planning_images/config1.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Resumir as finanças trabalhistas

O recurso Summarize Labor Financials permite determinar como os dados de custo de mão de obra são agregados e apresentados na guia Summary (Resumo). Ele controla quais dimensões (por exemplo, centro de custo, conta, local) são usadas para agrupar e agrupar linhas de custo de mão de obra, garantindo que você obtenha o nível certo de visibilidade e confidencialidade para as finanças da mão de obra.

Observação: As funções de administrador ou de proprietário do processo orçamentário são necessárias para configurar a compactação de mão de obra.

## Como ela funciona

- Quando os itens de linha de mão de obra são inseridos na guia Mão de obra, o sistema usa as Regras de alocação de mão de obra definidas para gerar entradas financeiras por conta.
- As **Configurações de compactação de trabalho** especificam quais dimensões são usadas para agrupar e agregar esses lançamentos financeiros na guia Resumo.
- Isso permite que você mantenha os custos de mão de obra resumidos (por exemplo, por centro de custo ou conta) em vez de ver cada entrada de mão de obra individualmente.
- A escolha de dimensões de compactação também ajuda a proteger dados confidenciais, pois a agregação oculta detalhes de remuneração em nível individual.

## Dimensões de compactação padrão

Por padrão, as seguintes dimensões estão disponíveis para serem resumidas:

- **Conta**
- **Centro de custos**
- **Objeto de custo**
- **Comentário**
- **Local**
- **Projeto**
- **Fornecedor**
- **Descrição**
- **Nome do funcionário**

**Centro de custo, Objeto de custo** e **Conta** são *sempre selecionados* e não podem ser removidos, pois são necessários para a agregação. Se o Planejamento integrado de investimentos estiver ativado, o projeto também será selecionado e não poderá ser removido.

Além desses campos padrão, **as dimensões personalizadas** que existem nos esquemas Financeiro e Trabalhista também aparecerão nessa lista e poderão ser selecionadas para compactação.

## Etapas de configuração

1. Navegue até **Settings (ícone de engrenagem) → Company Profile**
2. Na seção **Labor Headcount**, ative **Labor Summarization**
3. Selecione as dimensões que você deseja usar para compactação.
4. Clique em **Save and Exit (Salvar e sair)** para aplicar as alterações.

Os planos recém-criados usarão automaticamente essas configurações de compactação. Para planos existentes, é necessário recriar o plano para aplicar as configurações atualizadas.

![imagem das etapas de configuração](../../../../../03-media/apptio-planning/resources/images/it_planning_images/config1.png)

## Boas Práticas

- Escolha dimensões amplas para compactação (como centro de custo ou conta) quando precisar de confidencialidade e roll-up de alto nível.
- Inclua dimensões mais granulares (como Localização ou Descrição) somente quando for necessária uma visibilidade detalhada - e certifique-se de que os controles de acesso aos dados estejam em vigor. Consulte “[Ocultar dados confidenciais](hide-sensitive-labor-data.html "Os administradores podem restringir a visibilidade de colunas específicas na guia “Trabalho” — como nome do funcionário, salário ou outros detalhes de remuneração — para que os usuários sem a permissão necessária possam visualizar os registros de trabalho sem ver os campos confidenciais.") sobre mão de obra” para obter mais detalhes.
