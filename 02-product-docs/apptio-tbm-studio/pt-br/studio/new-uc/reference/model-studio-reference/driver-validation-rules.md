---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Regras de validação de motoristas"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Model Studio"
  - "Motoristas"
source_path: "studio/new-uc/reference/model-studio-reference/driver-validation-rules.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Regras de validação de motoristas

**Verificações de validação**

- A coluna deve existir na tabela subjacente
- O tipo de dados da coluna deve ser numérico para colunas de valor
- A sintaxe da fórmula deve ser válida
- As métricas referenciadas devem existir no projeto
- As referências entre projetos devem apontar para projetos acessíveis

**Problemas comuns com drivers**

|  |  |  |
| --- | --- | --- |
| **Problema** | **Causa** | **Resolução** |
| O valor do motorista é de $0 | A coluna contém dados não numéricos | Verificar o tipo da coluna no ` Data Studio ` |
| Motorista desaparecido há algum tempo | Não há dados carregados para esse período | Carregar dados para os períodos solicitados |
| Erro de fórmula | Sintaxe inválida ou referência ausente | Verifique a sintaxe e as referências da fórmula |
| Valores incorretos | Coluna selecionada incorretamente | Verifique se a coluna contém os dados esperados |

*→ Consulte [a seção de solução de problemas do driver para obter soluções detalhadas](../../ts-support/bd-issues.html)*

*→ Consulte [a Referência](../data-studio-reference.html) do Data Studio para obter informações sobre a configuração dos tipos de dados*

**Tópico principal:** [Motoristas](../../../../studio/new-uc/reference/model-studio-reference/drivers.html)
