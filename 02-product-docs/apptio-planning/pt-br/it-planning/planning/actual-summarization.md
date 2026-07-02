---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Configurações reais de compactação"
breadcrumb:
  - "Planning"
  - "Gerenciamento de despesas"
source_path: "it-planning/planning/actual-summarization.html"
images:
  - "resources/images/it_planning_images/act-sum.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Configurações reais de compactação

Esse recurso descreve como as partidas individuais reais são segregadas, com base nas colunas escolhidas para compactação.

Observação: As funções de Administrador ou Proprietário do processo orçamentário são necessárias para modificar as configurações de Compactação real.

Ao criar um plano de previsão, você pode escolher como os dados reais devem ser resumidos (agregados) antes de serem importados para o plano. O Actual Summarization permite que você controle o nível de granularidade em que os dados reais são trazidos, garantindo que os dados estejam alinhados com a forma como sua equipe planeja e analisa as despesas.

## O que ele faz

A Compactação real agrupa os valores reais pelas dimensões selecionadas e, em seguida, agrega as partidas individuais reais de acordo.

Isso é especialmente útil se os dados reais forem mais granulares do que o modelo de planejamento - por exemplo, se os dados reais incluírem detalhes no nível da transação, mas o plano de previsão precisar ser resumido apenas no nível do departamento e da conta.

Você pode resumir os dados reais usando dimensões padrão (por exemplo, departamento, conta, centro de custo) e/ou dimensões personalizadas, desde que essas dimensões existam nos esquemas de dados reais e financeiros.

## Como configurar a compactação real

- Vá para **Settings (ícone de engrenagem)** → **Company Profile**.
- Na seção **Resumir dados reais**, selecione as **dimensões** pelas quais deseja que os dados reais sejam agregados.
- Clique em **Save and Exit (Salvar e sair** ).

**Observações importantes:**

- Essas configurações serão aplicadas somente aos planos recém-criados daqui para frente.
- Para planos existentes, é necessário criar um novo plano para aplicar as configurações de compactação atualizadas.
- As dimensões só estarão disponíveis para compactação se existirem nos esquemas Real e Financeiro.

![imagem da compactação real](../../../../../03-media/apptio-planning/resources/images/it_planning_images/act-sum.png)
