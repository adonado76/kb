---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Solução de problemas nos relatórios principais"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Relatórios principais"
source_path: "studio/new-uc/reference/report-studio-reference/troubleshoot-master-reports.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Solução de problemas nos relatórios principais

**Problemas comuns e soluções**

|  |  |  |
| --- | --- | --- |
| **Problema** | **Possível causa** | **Solução** |
| O mestre não aparece no menu suspenso | O relatório não foi salvo ou registrado após a ativação da opção "Relatório mestre" | Salve e confirme o relatório mestre; aguarde até que o cálculo seja concluído |
| Os componentes colocados dentro da caixa de grupo principal não estão agrupados | Comportamento esperado: as caixas de grupo perdem a funcionalidade de agrupamento nos relatórios filhos | Use caixas de grupo nos modelos apenas para fins de estrutura visual; adicione grupos funcionais nos relatórios filhos |
| O conteúdo secundário é exibido em todas as guias | Componentes posicionados sobre o componente com abas no relatório filho | Adicione o conteúdo da guia apenas no relatório mestre; evite colocar componentes nas guias dos relatórios filhos |
| Não é possível excluir o relatório mestre | Tentativa de excluir um mestre padrão (OOTB) | Os modelos padrão não podem ser excluídos; use “Salvar como” para criar uma versão personalizada que você possa modificar ou excluir |
| O botão "Master" leva ao relatório errado | O botão de texto Wiki sem o atributo `data URL ` utiliza o contexto atual do relatório | Especifique um `Data URL ` explícito para os botões de navegação nos relatórios mestre |

**Tópico principal:** [Relatórios principais](../../../../studio/new-uc/reference/report-studio-reference/master-report.html)
