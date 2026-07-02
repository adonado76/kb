---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Visão geral do planejamento de atividades trabalhistas"
breadcrumb:
  - "Planning"
  - "Planejamento de atividades de trabalho do projeto"
source_path: "it-planning/planning/iip/labor-resource-planning.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Visão geral do planejamento de atividades trabalhistas

Importante: *Disponível com a* *assinatura* ***do Apptio Planning Standard***

Lembre-se: *o recurso de Planejamento Integrado de Investimentos (IIP) está ativado.*

**O Planejamento de Atividades de Mão de Obra** permite que as organizações planejem o esforço de mão de obra necessário para os projetos por horas ou FTE, ao mesmo tempo em que oferece suporte a cobranças cruzadas, alocação de custos de mão de obra e visibilidade das alocações acima ou abaixo do normal entre os recursos do projeto.

Quando o recurso Planejamento Integrado de Investimentos (IIP) está ativado, dois atributos opcionais de mão de obra ficam disponíveis em **Despesas** → **Mão de obra** :

- **Função do Trabalho no Projeto**
- **Tipo de atividade laboral**

## Habilitar planejamento de atividades de mão de obra

Nota:

- *As funções de administrador ou responsável pelo processo orçamentário são necessárias para realizar essas tarefas.*
- O recurso **Planejamento Integrado de Investimentos (IIP)** deve ser ativado *antes que* a Atividade de Trabalho possa ser ativada.

Antes que os usuários possam alocar esforços de trabalho na guia **Despesas** → **Atividade de Trabalho**, o Planejamento de Atividade de Trabalho deve estar habilitado no Perfil da Empresa.

**Etapas para ativar o planejamento de atividades de mão de obra**

1. Vá até o ícone de **Configurações (engrenagem)** → **Perfil da empresa**.
2. Certifique-se de que **o Planejamento Integrado de Investimentos (IIP)** esteja habilitado primeiro — a Atividade de Trabalho não pode ser ativada sem ele.
3. Habilitar **atividade de trabalho**.
4. Escolha se deseja **impedir a alocação excessiva** ou **permitir a alocação excessiva** de recursos de mão de obra.
5. **Evite a alocação excessiva:** o sistema bloqueará alocações que excedam a capacidade disponível de recursos.
6. **Permitir alocação acima da capacidade:** O sistema permitirá alocações acima da capacidade.
7. Se a alocação excessiva for permitida, especifique a **porcentagem de al** ocação excessiva/insuficiente permitida.

Uma vez ativada, a guia **Atividade de mão de obra** fica disponível para o planejamento da mão de obra do projeto.

## Função e taxa do projeto de trabalho

Os dados de referência **da Função de Trabalho do** Projeto definem as funções específicas do projeto utilizadas para recursos de trabalho internos ou externos, juntamente com as taxas horárias de trabalho aplicadas quando esses recursos cobram tempo a um projeto.

Essa dimensão permite o planejamento de mão de obra em nível de projeto, permitindo que as organizações mapeiem funções de RH em funções específicas do projeto e definam taxas de cobrança ou cobrança cruzada apropriadas. Por exemplo, um funcionário com uma função de RH de Desenvolvedor de Software 2 pode receber a Função de Trabalho no Projeto de Desenvolvedor ao trabalhar em um projeto.

Para obter detalhes sobre a configuração, consulte [Funções de trabalho do](manage-project-labor-role-data-ref.html) projeto.

## Tipo de atividade laboral

Os dados de referência **do Tipo de Atividade Laboral** definem o mapeamento entre a Conta do Centro de Custos do Departamento (o provedor) e a Conta do Centro de Custos do Projeto (o consumidor) para um determinado tipo de atividade. Esse mapeamento determina como os custos de mão de obra e os custos cruzados fluem entre os centros de custo.

Os tipos de atividade de mão de obra são usados durante o planejamento de atividades de mão de obra para:

- Identifique qual centro de custos fornece a mão de obra
- Identifique qual projeto ou centro de custos consome a mão de obra
- Atribua os valores correspondentes de cobrança e cobrança cruzada às contas corretas do fornecedor e do consumidor

Para obter detalhes sobre a configuração, consulte [Tipo](manage-labor-activity-type-data-ref.html) de atividade de trabalho.

## Atribuição de funções de trabalho e planejamento do esforço do projeto

O planejamento das atividades de trabalho é um processo em duas etapas. Primeiro, atribua um recurso de mão de obra a uma **função de mão de obra do projeto** na guia **Mão de obra**. Em seguida, planeje o esforço do projeto do recurso (horas ou FTE) na guia **Atividade de mão de obra**.

Apenas os recursos de mão de obra com uma função de trabalho no projeto atribuída aparecerão como **Recursos** na guia **Atividade de mão de obra**.

**Etapa 1: Atribuir uma função e uma taxa de mão de obra ao projeto (guia Mão de obra)**

Para definir a função do recurso no projeto e a taxa faturável:

1. Vá para **Despesas** → **Mão de obra** e crie ou edite uma linha de recurso de mão de obra.
2. Selecione a **função do projeto** na lista suspensa.
3. **A Taxa de Mão de Obra do** Projeto é preenchida automaticamente com base nos dados de referência.

***Comportamentos importantes:***

- A seleção de uma **função de trabalho no projeto** define automaticamente a **taxa de trabalho do projeto**.
- Você pode substituir a taxa padrão.
- Se um recurso de mão de obra **não** for cobrado em um projeto, você pode deixar os campos Função e Taxa de mão de obra do projeto em branco.
- As cobranças cruzadas de mão de obra são geradas na guia **Resumo** usando Preço x Quantidade (Horas).

**Etapa 2: Alocar horas ou FTE aos projetos (guia Atividade de mão de obra)**

A guia Atividade de mão de obra permite planejar o esforço de mão de obra para projetos por **Função de mão de obra do projeto** ou por **Recurso nomeado**. Os recursos exibidos nesta guia são filtrados com base nas atribuições de Funções de Trabalho do Projeto feitas em **Despesas** → **Trabalho**.

Siga as etapas abaixo para alocar mão de obra a um projeto:

1. **Selecione o projeto** - Na guia **Atividade de mão de obra**, escolha o **projeto** para o qual deseja planejar a mão de obra.
2. **Escolha como alocar recursos** - Você pode alocar mão de obra de duas maneiras:
   1. **Por função no projeto**
   2. **Por recurso nomeado**
3. **Selecione uma função no projeto**
   1. Selecione a **função do projeto** na lista suspensa.
   2. **A Taxa de Mão de Obra do** Projeto será preenchida automaticamente com base nos dados de referência da Função de Mão de Obra do Projeto.
   3. Você pode substituir a taxa, se necessário.
4. **Selecione um recurso nomeado (opcional)**
   1. Na dimensão **Recurso**, escolha um recurso nomeado para alocar.
   2. A lista de recursos é filtrada automaticamente para mostrar apenas aqueles mapeados para a **Função de Trabalho do Projeto** selecionada na guia Trabalho.
      1. Use a dimensão **Centro de custos de recursos** para limitar a lista aos recursos pertencentes a um centro de custos específico.
      2. Observação: a alocação de recursos não pode ser realizada quando um **Centro de Custos de Recursos** está no estado **“enviado”** ou “**bloqueado** ”. Qualquer tentativa de alterar ou atribuir um Centro de Custos de Recurso que já tenha sido enviado/bloqueado resultará em um erro de validação, e a alteração não será salva.
5. **Selecione o tipo de atividade** - Se a mão de obra é faturável ou cobrada de forma cruzada:
   1. Escolha o **tipo de atividade** apropriado.
   2. Isso determina como as cobranças e cobranças cruzadas são alocadas entre as contas do provedor e do consumidor com base nos mapeamentos do Tipo de Atividade de Trabalho.
6. **Insira o esforço em horas ou FTE**
   1. Insira o esforço de trabalho necessário em **horas mensais** ou **FTE**.
   2. O esforço inserido determinará os cálculos dos custos de mão de obra.
7. **Revisar custos de mão de obra** - Os custos de mão de obra são calculados usando **Preço × Quantidade** com base na Função de mão de obra do projeto, Taxa de mão de obra, Tipo de atividade e regras de alocação selecionados. Os valores resultantes aparecem na guia **Resumo**, onde o centro de custos do fornecedor recebe um crédito e o centro de custos do consumidor recebe um débito.
