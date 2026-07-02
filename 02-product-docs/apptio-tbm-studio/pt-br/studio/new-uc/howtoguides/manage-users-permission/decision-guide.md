---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Guia de decisão: Como escolher o sistema de controle de acesso certo"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Gerenciar usuários e permissões"
  - "Controle de acesso"
source_path: "studio/new-uc/howtoguides/manage-users-permission/decision-guide.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Guia de decisão: Como escolher o sistema de controle de acesso certo

Utilize este quadro de decisão para determinar qual mecanismo de controle de acesso (ou combinação) melhor atende às suas necessidades:

**Quando usar permissões de relatório**

- Você deseja ocultar relatórios ou painéis inteiros para determinadas funções
- Diferentes funções precisam de acesso a diferentes conjuntos de relatórios
- Você precisa de visualizações específicas para cada função dos mesmos dados subjacentes (usando a visibilidade de componentes)
- Você deseja restringir os direitos de criação de relatórios por função

**Quando usar a segurança no nível da linha**

- Os usuários devem ver apenas os dados relevantes para o âmbito da sua organização (unidade de negócios, região, centro de custo)
- Vários locatários ou divisões compartilham a mesma instância do TBM Studio
- As restrições de dados devem ser aplicadas de maneira consistente em todos os relatórios e tabelas
- Você precisa de uma filtragem de dados detalhada com base na identidade do usuário

**Quando usar permissões para tabelas editáveis**

- As equipes distribuídas precisam gerenciar seus próprios dados (por exemplo, gerentes de centros de custo inserindo orçamentos)
- Você deseja restringir quem pode inserir dados em tabelas específicas
- Cada usuário deve editar tabelas editáveis diferentes, de acordo com sua função
- Você precisa de um controle de auditoria sobre as atividades de entrada de dados

## Combinação de controles de acesso

Para uma segurança abrangente, combine várias camadas. Uma configuração típica de empresa pode incluir:

- **Permissões de relatórios** para controlar quais painéis cada função pode acessar
- **O RLS** deve garantir que os gerentes das unidades de negócios vejam apenas seus próprios dados de custos
- **Permissões editáveis** para que cada equipe possa manter suas próprias tabelas de mapeamento

Importante: O RLS não protege os dados contra usuários com privilégios de administrador. Os administradores têm acesso ao modo Studio e podem criar relatórios que contornam o RLS, adicionar-se às tabelas de mapeamento do RLS ou desativar completamente o RLS. Elabore seu modelo de segurança levando essa limitação em consideração.

**Tópico principal:** [Controle de acesso](../../../../studio/new-uc/howtoguides/manage-users-permission/access-control-intro.html)
