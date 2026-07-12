---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Scripting"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Integrar e ampliar"
source_path: "studio/new-uc/howtoguides/integrate-extend/scripting.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Scripting

|  |  |
| --- | --- |
| **Tipo de Conteúdo** | Guia prático |
| **Público-alvo** | Analistas de negócios, desenvolvedores |
| **Pré-requisitos** | Conhecimento básico do TBM Studio e compreensão de tabelas editáveis |

ApptioScript é a linguagem de script da TBM Studio para a criação de aplicativos empresariais interativos. Ele permite automatizar operações de dados, implementar lógica de negócios e criar processos orientados por fluxos de trabalho que vão além dos recursos integrados do TBM Studio.

Esta seção contém dois guias práticos: o primeiro apresenta os fundamentos d ApptioScript e mostra como escrever [seus primeiros scripts](htg-write-as.html), enquanto o segundo aborda [padrões comuns](htg-use-common-pattern.html) que você pode adaptar aos seus cenários de negócios. Para obter a documentação completa da função, consulte a seção 5.6: ApptioScript Reference.

**O que você pode fazer com o ApptioScript**

- **Automatize a inserção e a atualização de dados** — Adicione, edite ou exclua linhas em tabelas editáveis por meio de programação
- **Implementar fluxos de trabalho empresariais** — Criar processos de aprovação, transições de status e notificações automáticas
- **Controle a experiência do usuário** — Defina células como obrigatórias ou somente para leitura com base em condições, implemente menus suspensos em cascata
- **Criar registros de auditoria** — Rastrear automaticamente quem editou os dados e quando
- **Copiar e transformar dados** — Transferir dados entre tabelas, projetos ou períodos
- **Enviar notificações** — Acionar e-mails quando condições específicas forem atendidas

## Quando usar o " ApptioScript " em vez dos recursos integrados

O TBM Studio oferece diversos recursos integrados. Use ` ApptioScript ` quando precisar de um comportamento que vá além da configuração padrão.

|  |  |  |
| --- | --- | --- |
| **Cenário** | **Recurso integrado** | **Quando usar o " ApptioScript "** |
| Listas suspensas simples | Coluna Valores possíveis | Use o script para menus suspensos em cascata com lógica complexa |
| Validação de dados | Regras de validação na configuração da coluna | Use o script para validação entre campos |
| Valores calculados | Métricas calculadas | Use o script para cálculos no nível da linha em tabelas editáveis |
| Notificações ao usuário | Não disponível | Use a função ` SendEmail( )` |
| Alterações no status do fluxo de trabalho | Não disponível | Use o ` EditRows( )` com ações de botão |
| Registros de auditoria | Registro de auditoria do sistema | Use o script para rastrear edições visíveis ao usuário em tabelas |

- **[Guia prático: Como escrever fórmulas n ApptioScript](../../../../studio/new-uc/howtoguides/integrate-extend/htg-write-as.html)**
- **[Guia prático: Como usar padrões comuns de script](../../../../studio/new-uc/howtoguides/integrate-extend/htg-use-common-pattern.html)**
