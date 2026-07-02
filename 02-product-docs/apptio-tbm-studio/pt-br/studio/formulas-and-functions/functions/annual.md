---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função anual"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/annual.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função anual

Retorna um valor para a métrica especificada ajustada para frente ou para trás por um número de anos, com base no tipo de calendário selecionado.

## Sintaxe

`Annual(metric, delta, calendarType)`

## Parâmetros

*métrica* : O nome da métrica que você deseja ajustar. Opcional.

*delta* : Opcional. O número de anos para olhar para frente (valor positivo) ou para trás (valor negativo). Se não for especificado, o padrão é 0.

*calendarType* : Opcional. O sistema de calendário a ser usado. Os valores suportados são "FY" para ano fiscal (padrão) e "CY" para ano civil. Se não for especificado, o padrão é "FY".

## Comportamento

- Requer uma métrica como entrada.
- Opcionalmente, ajusta o valor com base no número de anos especificado por delta.
- Usa o tipo de calendário especificado para determinar como os anos são calculados.
- Se delta não for especificado, o padrão é 0 (sem ajuste).
- Se calendarType não for especificado, o padrão será 'FY' (Fiscal Year).

## Tipo de retorno

Número

## Exemplo

O exemplo a seguir retorna o custo total do ano atual.

`=Annual(Cost)`

`=Annual(Budget,0,"CY`

`Annual(Budget)`: Retorna a métrica "Orçamento" para o ano fiscal atual.

`Annual(Budget, -1)`: Retorna a métrica "Orçamento" de um ano fiscal atrás.

`Annual(Budget, 1, "CY")`: Retorna a métrica "Orçamento" para o próximo ano civil.

Nota:

- O parâmetro delta deve ser um valor numérico, como 0, 1 ou -1.
- Use "FY" (Fiscal Year) para calendários fiscais de 445 variantes e 13 períodos.
- Use "CY" (Calendar Year) para calendários gregorianos padrão.
