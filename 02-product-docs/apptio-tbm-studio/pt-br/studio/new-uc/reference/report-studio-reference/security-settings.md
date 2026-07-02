---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Configurações de segurança"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Propriedades do relatório"
source_path: "studio/new-uc/reference/report-studio-reference/security-settings.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configurações de segurança

As configurações de segurança dos relatórios determinam quais usuários e funções podem visualizar e interagir com os relatórios. As permissões podem ser configuradas no nível da coleção de relatórios e herdadas por relatórios individuais, ou definidas especificamente para cada relatório.

**Permissões do relatório**

**Para configurar as permissões dos relatórios:**

1. Confira o relatório
2. Vá até a guia Relatório > Permissões (ou guia Projeto > grupo Avançado > Permissões)
3. Selecione as funções que devem ter acesso
4. Clique em OK para aplicar

**Opções de permissão:**

|  |  |
| --- | --- |
| **Opção** | **Descrição** |
| Todos | Todos os usuários com acesso ao projeto podem visualizar o relatório. Esta é a configuração mais flexível. |
| Funções específicas | Somente os usuários atribuídos às funções selecionadas podem visualizar o relatório. É possível selecionar várias funções. |

**Permissões para coleta de relatórios**

As permissões definidas no nível da coleção de relatórios se aplicam a todos os relatórios da coleção, a menos que sejam substituídas no nível de cada relatório individual. Isso permite uma gestão eficiente das permissões para grupos de relatórios relacionados.

**Visibilidade dos componentes**

Os componentes individuais de um relatório podem ter regras de visibilidade que controlam quando e para quem eles são exibidos:

|  |  |
| --- | --- |
| **Regra de visibilidade** | **Comportamento** |
| O componente contém dados | Oculta o componente se ele não contiver nem calcular dados |
| A função atual do usuário é | Mostra o componente apenas aos usuários com funções específicas |
| O texto dinâmico resulta em "oculto" | Oculta o componente com base em uma fórmula ou condição de dados |

**Para definir a visibilidade de um componente:** selecione o componente e, em seguida, acesse a guia Relatório > grupo Avançado > Visibilidade

**Tópico principal:** [Propriedades do relatório](../../../../studio/new-uc/reference/report-studio-reference/report-properties.html)
