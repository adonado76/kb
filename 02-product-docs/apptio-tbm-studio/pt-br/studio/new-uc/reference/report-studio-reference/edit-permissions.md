---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Editar permissões"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Tabelas editáveis nos relatórios"
source_path: "studio/new-uc/reference/report-studio-reference/edit-permissions.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Editar permissões

As permissões determinam quem pode realizar operações específicas no componente de tabela editável.

**Permissões por linha**

Configure as permissões de operação na seção Permissões da faixa de opções Tabelas editáveis:

|  |  |  |
| --- | --- | --- |
| **Permissão** | **Controles** | **Padrão** |
| Permissão para adicionar linha | Quem pode adicionar novas linhas | Todos |
| Permissão para editar linha | Quem pode modificar as linhas existentes | Todos |
| Permissão para excluir linha | Quem pode excluir linhas individuais | Todos |
| Permissão para duplicar linha | Quem pode duplicar linhas | Todos |
| Permissão para publicar linha | Quem pode publicar alterações | Todos |
| Permissão para excluir todas as linhas | Quem pode excluir todas as linhas de uma só vez | Administrador e Parceiro |
| Permissão para baixar | Quem pode baixar a tabela | Todos |
| Permissão para fazer upload | Quem pode enviar dados | Todos |
| Mostrar permissão de histórico | Quem pode visualizar o histórico de alterações | Todos |

Para cada permissão, selecione “Todos” ou “Funções selecionadas” e especifique as funções permitidas.

**Integração da Segurança em Nível de Linha (RLS)**

Quando o RLS está ativado na tabela editável subjacente:

- Os usuários veem apenas as linhas que correspondem à sua dimensão de segurança (por exemplo, seu centro de custo)
- O acesso de gravação está restrito apenas às linhas visíveis
- As linhas ocultas são mantidas durante as operações de publicação
- O RLS é aplicado além das permissões no nível do relatório

**Desativação da edição dinâmica**

Use o campo "Desativar edições" para desativar a edição de forma condicional com base em condições dinâmicas:

Exemplo: `{$CurrentUser:Users.ID}=ddavis@ABCCompany.com`

Esta expressão desativa a edição para o usuário especificado. Você pode usar qualquer expressão de texto dinâmico cujo resultado seja verdadeiro ou falso.

**Tópico principal:** [Componentes de relatórios: Tabelas editáveis em relatórios](../../../../studio/new-uc/reference/report-studio-reference/report-component-editable-components.html)
