---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Resolução de problemas"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Tabelas editáveis nos relatórios"
source_path: "studio/new-uc/reference/report-studio-reference/editable-troubleshoot.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Resolução de problemas

Problemas comuns e soluções para componentes de tabela editáveis.

**Erros comuns ao salvar**

|  |  |
| --- | --- |
| **Problema** | **Solução** |
| Erros de validação impedem o salvamento | Verifique as células destacadas, corrija valores inválidos e certifique-se de que os campos obrigatórios estejam preenchidos |
| A célula está bloqueada por outro usuário | Aguarde até que o outro usuário salve ou cancele sua edição, ou entre em contato com ele para liberar o bloqueio |
| Não é possível publicar as alterações | Certifique-se de que possui permissão para publicar linhas e acesso aos ambientes de desenvolvimento e teste; verifique se há erros de validação |
| Alterações que não aparecem nos relatórios | Verifique se a publicação foi concluída com sucesso; aguarde a conclusão da compilação/cálculo; atualize o relatório |
| Os valores do menu suspenso não estão carregando | Verifique a sintaxe da fórmula "Valores possíveis"; verifique se a tabela de origem existe e se é calculada |
| Não é possível excluir linhas na tabela enriquecida | As linhas provenientes da transformação de origem não podem ser excluídas; apenas as linhas adicionadas pelo usuário podem ser removidas |

**Considerações sobre desempenho**

Para tabelas grandes editáveis:

- Ative a opção “Suprimir solicitação inicial de dados” em Propriedades avançadas para carregar os dados sob demanda
- Use filtros ou RLS para limitar o número de linhas exibidas
- Limitar o número de colunas com fórmulas complexas em menus suspensos
- Considere usar o upload de arquivos para a inserção em massa de dados (mais de 100 linhas)

**Tópico principal:** [Componentes de relatórios: Tabelas editáveis em relatórios](../../../../studio/new-uc/reference/report-studio-reference/report-component-editable-components.html)
