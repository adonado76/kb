---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Análise de alocação a mais ou a menos de atividades trabalhistas"
breadcrumb:
  - "Planning"
  - "Planejamento de atividades de trabalho do projeto"
source_path: "it-planning/planning/iip/manage-over-under-allocation.html"
images:
  - "resources/images/it_planning_images/la-2.png"
  - "resources/images/it_planning_images/la-color1.png"
  - "resources/images/it_planning_images/la-colors.png"
  - "resources/images/it_planning_images/la-first.png"
  - "resources/images/it_planning_images/lc-example1.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Análise de alocação a mais ou a menos de atividades trabalhistas

Importante: *Disponível com a* *assinatura* ***do Apptio Planning Standard***

Lembre-se: *o recurso de Planejamento Integrado de Investimentos (IIP) está ativado.*

A mão de obra alocada frequentemente representa uma parte significativa das despesas totais de um projeto ou investimento. Compreender como a mão de obra é utilizada é essencial para avaliar a capacidade disponível em relação à demanda, tomar decisões de contratação, determinar quando pausar ou interromper projetos não essenciais e identificar recursos subutilizados cuja capacidade pode ser melhor alocada em outras áreas.

Em muitas organizações, o **centro de custos dos recursos** difere do **centro de custos do** projeto, e um único recurso de mão de obra pode apoiar vários projetos. Isso torna o planejamento de capacidade mais complexo e pode levar a:

- **Subalocação**, em que se perde capacidade valiosa
- **A alocação excessiva**, que causa atrasos nos projetos e deturpa a disponibilidade real de recursos
- Dificuldade em avaliar a demanda total por funções-chave em comparação com a capacidade disponível
- Desafios na estimativa das necessidades de financiamento da mão de obra durante a elaboração do orçamento

**O Planejamento Integrado de Investimentos (IIP)** aborda esses desafios fornecendo controles para **evitar totalmente a alocação excessiva de recursos** ou para **definir limites personalizados de alocação excessiva e insuficiente**. Esses limites facilitam a identificação de atribuições de trabalho que excedem ou ficam aquém dos limites aceitáveis, garantindo uma previsão precisa da capacidade e um planejamento de mão de obra mais eficaz em toda a organização.

## Habilitar configurações de planejamento e alocação de atividades de trabalho

1. Navegue até **Configurações** administrativas (ícone de engrenagem) → **Perfil da empresa**.
2. Certifique-se de que **o Planejamento Integrado de Investimentos (IIP)** esteja habilitado primeiro — a Atividade de Trabalho não pode ser ativada sem ele.
3. Habilitar **atividade laboral**.
4. Escolha se deseja **impedir a alocação excessiva** ou **permitir a alocação excessiva** de recursos de mão de obra.
   1. **Evite a alocação excessiva:** o sistema bloqueará alocações que excedam a capacidade disponível dos recursos.
   2. **Permitir alocação acima da capacidade:** O sistema permitirá alocações acima da capacidade.
5. Se a alocação excessiva for permitida, especifique a **porcentagem de alocação excessiva/insuficiente** permitida.

   ![](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/la-first.png)

   Uma vez ativada, a guia **Atividade de mão de obra** fica disponível para o planejamento da mão de obra do projeto.

## Ativar análise de alocação de mão de obra

**Requisitos:** *Página de novas despesas ativada*

1. Navegue até **Despesas** → guia **Atividade de mão de obra**.
2. Ativar **Nova Visualização**
3. Clique no menu **reticências**.
4. Selecione **Analisar alocação de mão de obra**.

   ![](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/la-2.png)

As células agora serão codificadas por cores para refletir a utilização da mão de obra:

- **Azul** – Subalocação (abaixo do limite configurado)
- **Vermelho** – Alocação excessiva (acima do limite configurado)
- **Sem cor** – Dentro dos limites permitidos

Os itens da linha de atividade de mão de obra são agrupados por recurso, e quaisquer alocações que estejam fora dos limites definidos são destacadas na cor correspondente. As células sem cor indicam que a alocação está dentro da faixa aceitável.

![](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/la-colors.png)

Você pode passar o mouse sobre qualquer célula para ver a capacidade total do recurso e a quantidade alocada. As alocações podem ser visualizadas em **horas** ou em **FTE**.

![](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/la-color1.png)

## Capacidade de trabalho

Cada recurso de mão de obra recebe um calendário de trabalho que define seus dias e horários de trabalho. Para saber mais sobre como configurar calendários, consulte [Trabalhando com calendários](../configure-working-days.html "O calendário de trabalho define quantos dias e horas de trabalho são usados para o planejamento de mão de obra, o que influencia a conversão de equivalentes de tempo integral (FTE), a amortização de custos de mão de obra e os cálculos de despesas mensais.").

Em **Despesas** → **Mão de obra**, **a Data de início**, **a Data de término** e **a Capacidade FTE mensal** de um recurso determinam a quantidade de capacidade disponível para planejamento. A capacidade de trabalho em horas é calculada utilizando a seguinte fórmula:

**Capacidade mensal = (dias úteis mensais × horas úteis diárias × quantidade mensal de mão de obra)**

Essa capacidade calculada é usada na guia Atividade de mão de obra para determinar a alocação excessiva ou insuficiente.

**Exemplo:**

![](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/lc-example1.png)

Assumindo um calendário gregoriano com a configuração do calendário de trabalho acima (5 dias por semana, 8 horas por dia) e um dia não útil para o Dia de Ano Novo:

**Capacidade de trabalho para janeiro = (23 dias úteis − 1 feriado) × 8 horas = 176 horas**
