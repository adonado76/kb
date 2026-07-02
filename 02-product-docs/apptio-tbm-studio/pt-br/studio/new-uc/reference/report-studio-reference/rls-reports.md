---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Segurança por linha nos relatórios"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Permissões do relatório"
source_path: "studio/new-uc/reference/report-studio-reference/rls-reports.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Segurança por linha nos relatórios

**Como o RLS se aplica aos dados de relatórios**

A segurança por linha filtra os dados exibidos nos componentes do relatório com base na identidade do usuário atual. Quando o RLS está configurado:

1. O sistema identifica o usuário atual
2. Ele procura o usuário nas tabelas de mapeamento do RLS
3. Só são exibidas as linhas que correspondem às permissões do usuário
4. Os cálculos agregados refletem apenas os dados visíveis

**Etapas de configuração do RLS:**

1. **Crie tabelas de mapeamento** no projeto de Segurança em Nível de Linha que definam quais itens cada usuário pode visualizar
2. **Adicione etapas do pipeline RLS** para transformar as tabelas que devem ser filtradas
3. **Configure regras de filtro** que correspondam às colunas da tabela aos valores da tabela de mapeamento

**Interação entre RLS e permissões de relatórios**

As permissões RLS e de relatório são independentes, mas complementares:

|  |  |  |  |
| --- | --- | --- | --- |
| **Cenário** | **Permissão para relatar** | **Acesso ao RLS** | **Experiência de Usuário** |
| **Um** | ✓ Concedido | ✓ Todos os dados | Relatório completo, todos os dados |
| **B** | ✓ Concedido | ✓ Filtrado | Relatório completo, dados filtrados |
| **B** | ✓ Concedido | ✗ Sem dados | Componentes vazios do relatório |
| **P** | ✗ Recusado | — | Não é possível acessar o relatório |

**Cenário comum:** um usuário tem acesso ao relatório, mas não vê nenhum dado. Isso geralmente indica que:

- O RLS está configurado nas tabelas subjacentes
- O ID do usuário não consta nas tabelas de mapeamento do RLS
- O usuário precisa ser adicionado à lista de acesso RLS apropriada

**Depuração do RLS**

**Sintoma: O usuário não vê dados nos relatórios**

Verifique estes itens na seguinte ordem:

1. **Tabelas de mapeamento de RLS:** Verifique se o ID do usuário existe nas tabelas de mapeamento apropriadas no projeto de Segurança em Nível de Linha
2. **Formato do ID do usuário:** Certifique-se de que o ID do usuário nas tabelas de mapeamento corresponda exatamente ao nome de login do usuário (distingue maiúsculas de minúsculas)
3. **Etapas do RLS Pipeline:** Confirme se as etapas do RLS estão configuradas nas tabelas que alimentam o relatório
4. **Correspondência de colunas:** Verifique se a coluna de filtro na tabela corresponde aos valores na tabela de mapeamento

Importante: As tabelas não herdam automaticamente as configurações de RLS. É necessário adicionar uma etapa RLS para cada etapa do modelo que deva ser filtrada.

**Tópico principal:** [Permissões de relatórios](../../../../studio/new-uc/reference/report-studio-reference/report-permissions.html)
