---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Calendários de trabalho"
breadcrumb:
  - "Planning"
  - "Planejamento trabalhista"
source_path: "it-planning/planning/configure-working-days.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Calendários de trabalho

O calendário de trabalho define quantos dias e horas de trabalho são usados para o planejamento de mão de obra, o que influencia a conversão de equivalentes de tempo integral (FTE), a amortização de custos de mão de obra e os cálculos de despesas mensais.

Você pode configurar vários calendários no sistema (por exemplo: tempo integral, meio período, programação global de feriados) e designar um calendário de trabalho padrão. As alterações no calendário afetam a modelagem das despesas com mão de obra e devem ser gerenciadas com cuidado.

Observação: As funções de administrador ou de proprietário do processo orçamentário são necessárias para configurar os calendários de trabalho.

## Tipos de calendários de trabalho

**Calendário fixo**

- Defina um número definido de horas de trabalho por mês (por exemplo: 168 horas por mês).
- Use essa opção quando sua organização usar um modelo padrão de horas de trabalho mensais, independentemente dos dias úteis reais.

**Calendário variável**

- Defina os dias úteis por dia da semana, defina as horas por dia e especifique os dias não úteis (feriados, paralisações).
- Use-o quando o planejamento de mão de obra refletir dias úteis reais, feriados ou programações não padronizadas.

## Configurar calendários de trabalho

1. Navegue até **Configuration → Calendar Setup**.
2. Clique em **Add (Adicionar** ) e escolha **Fixed Calendar (Calendário fixo** ) ou **Variable Calendar (Calendário variável** ).
3. Digite um **nome** para o calendário e clique em **Add (Adicionar** ).
4. Clique no ícone **Editar (lápis)** ao lado do nome do calendário para configurar os detalhes.

**Para calendários fixos:**

- Insira o valor **das horas de trabalho por mês**.

**Para calendários variáveis:**

1. Selecione os **dias úteis da semana**.
2. Insira as **horas por dia de trabalho** (por exemplo, 8 para um dia de trabalho padrão).
3. Para adicionar dias não úteis:
   1. Clique em **Edit (Editar) em** *Non-Working Days (Dias não úteis* ).
   2. Selecione o **ano** e, em seguida, insira um **nome** e uma **data** (MM/DD) para cada feriado ou dia não útil.
   3. Clique em **Salvar**.

Ao passar o mouse sobre um calendário, selecione **Marcar como padrão** para defini-lo como o calendário de trabalho padrão. O calendário padrão será aplicado automaticamente aos novos itens de linha de mão de obra.

## Atribuição e uso de calendários de trabalho

- O calendário de trabalho padrão é automaticamente atribuído às linhas de trabalho, a menos que um calendário diferente seja selecionado.
- Se você tiver vários calendários (por exemplo, para diferentes regiões ou tipos de trabalho), os usuários poderão substituir o calendário para itens de linha de mão de obra específicos.
- Para usar o calendário de trabalho na amortização de despesas trabalhistas: Atualize o **Método de amortização de mão de obra** nas **Regras de alocação de mão de obra** e publique as alterações. Consulte [as Regras de Alocação de Mão de Obra](manage-labor-allocation-rules.html) para obter mais informações.

## Solução de problemas e considerações

|  |  |  |
| --- | --- | --- |
| **Problema** | **Descrição** | **Recomendação** |
| A conversão de horas para FTE parece incorreta | O calendário pode não refletir as horas/dia ou os dias úteis/semana corretos. | Revise o calendário atribuído, verifique as configurações de horas por dia e dias úteis. |
| Falta de dias não úteis (por exemplo, feriados) | A lista de dias não úteis pode não estar preenchida para esse ano ou região. | Adicione as datas de feriado em Non-Working Days (Dias não úteis) e Save (Salvar). |
| Vários calendários que confundem os usuários | Os usuários podem não saber qual calendário selecionar para os itens de linha. | Defina uma convenção de nomenclatura clara (por exemplo, “US-FullTime”, “EU-PartTime” ) e defina um padrão. |
| Amortização de despesas trabalhistas não refletindo o calendário | A regra de amortização não pode fazer referência ao calendário de trabalho. | Atualize as Regras de Alocação de Trabalho para usar o calendário de trabalho e republique as alterações. |
