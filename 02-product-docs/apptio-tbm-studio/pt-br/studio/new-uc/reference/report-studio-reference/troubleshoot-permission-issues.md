---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Solução de problemas relacionados a permissões"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Permissões do relatório"
source_path: "studio/new-uc/reference/report-studio-reference/troubleshoot-permission-issues.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Solução de problemas relacionados a permissões

**Problemas comuns com permissões**

|  |  |  |
| --- | --- | --- |
| **Problema** | **Causa provável** | **Solução** |
| Relatório não visível | Atribuição incorreta de função | Adicionar função às permissões do relatório |
| Componentes vazios do relatório | Filtragem RLS | Adicionar usuário às tabelas de mapeamento do RLS |
| Não é possível finalizar a compra | Já foi retirado | Aguarde outro usuário ou entre em contato com o administrador |
| Componentes em falta | Visibilidade dos componentes | Verifique se a função está incluída nas configurações de visibilidade |
| Não é possível exportar | Permissões de exportação | Verificar permissões de exportação por função |
| Não é possível se inscrever | Permissão ausente | Conceder permissão a EmailSubscriptionsCreate |

**Lista de verificação para autorizações**

Antes de enviar os relatórios para produção, verifique:

- Permissões de relatório configuradas para as funções apropriadas
- As tabelas de mapeamento RLS incluem todos os usuários necessários
- Configurações de visibilidade dos componentes testadas para cada função
- O artigo aparece na(s) coleção(ões) correta(s)
- O relatório está ativo e em cálculo
- Assinaturas por e-mail configuradas corretamente (se aplicável)
- Funcionalidades de exportação e impressão testadas

**Tópico principal:** [Permissões de relatórios](../../../../studio/new-uc/reference/report-studio-reference/report-permissions.html)
