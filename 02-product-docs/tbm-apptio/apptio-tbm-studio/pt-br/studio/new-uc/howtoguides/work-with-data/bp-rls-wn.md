---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Melhores práticas para segurança no nível da linha"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Trabalhar com dados"
  - "Segurança de dados"
source_path: "studio/new-uc/howtoguides/work-with-data/bp-rls-wn.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Melhores práticas para segurança no nível da linha

## Planejando sua estratégia de RLS

- **Comece com requisitos claros:** documente quem precisa de acesso a quais dados antes de implementar o RLS. Isso evita retrabalho e garante uma segurança consistente em todas as tabelas.
- **Use nomes de tabelas significativos:** nomeie as tabelas de mapeamento de forma descritiva (por exemplo, “Acesso à Unidade de Negócios – Usuários Padrão”, “Acesso Regional – Gerentes”) para que outras pessoas possam entender sua finalidade.
- **Leve em conta o crescimento futuro:** utilize um modelo de tabela de “acesso total” em vez de listar todos os valores para usuários avançados. Dessa forma, a adição de novas unidades de negócios ou centros de custo não exige a atualização de vários registros de usuários.

**Dicas de implementação**

- **Aplique o RLS de forma consistente:** se você proteger a tabela “Cost Source”, proteja também as tabelas relacionadas, como “IT Resource Towers”, para evitar o vazamento de dados por meio de detalhamentos ou relatórios relacionados.
- **Teste exaustivamente:** use o filtro de visualização e os recursos de representação para verificar se o RLS funciona conforme o esperado para diferentes tipos de usuários antes de implantar em produção.
- **Documente sua configuração:** mantenha registros indicando quais tabelas possuem RLS, a quais tabelas de mapeamento elas fazem referência e quais regras de negócios elas implementam.

**Considerações sobre manutenção**

- **Estabelecer processos de atualização:** criar procedimentos para adicionar/remover usuários e alterar permissões de acesso. Considere a automação com o DataLink para grandes organizações.
- **Faça auditorias regularmente:** revise periodicamente as tabelas de mapeamento para garantir que elas reflitam a estrutura organizacional atual e os requisitos de acesso.
- **Coordenar com RH/TI:** Alinhar as atualizações do RLS com a integração e a saída de funcionários, bem como com as mudanças organizacionais.

## Como funciona o RLS no TBM Studio

Compreender como o RLS se comporta em diferentes contextos ajuda a implementar uma segurança abrangente:

**RLS em tabelas de transformação**

- O RLS filtra os dados no momento da recuperação, de modo que as linhas não autorizadas nunca chegam ao usuário.
- Cada tabela requer sua própria etapa de RLS; a segurança não é herdada de tabelas relacionadas.

**RLS em tabelas editáveis**

- O RLS restringe quais linhas os usuários podem ver e editar em tabelas editáveis.
- Quando uma tabela editável é publicada, as linhas ocultas (aquelas que o usuário não consegue ver) são mantidas — não são sobrescritas nem excluídas.
- Isso é fundamental em situações em que gerentes distribuídos atualizam os dados de seus próprios centros de custo.

**RLS nos relatórios**

- Os relatórios exibem apenas as linhas que o usuário está autorizado a ver, com base nas regras do RLS.
- As agregações (totais, médias) refletem apenas os dados filtrados pelo usuário.
- Nos relatórios de visão geral do modelo, cada camada reflete suas próprias configurações de RLS — os valores podem não corresponder entre as camadas se o RLS for aplicado de forma diferente em tabelas distintas.

**RLS com alocações de modelos**

- O RLS não afeta a forma como as alocações são calculadas. O modelo processa todos os dados, independentemente das configurações de segurança.
- Os usuários visualizam os custos alocados apenas para as unidades de negócios ou centros de custo aos quais têm acesso, mesmo que esses custos tenham origem em outras áreas.

## O que vem a seguir

- [Modelo de segurança](../../concepts-architecture/studio-model/security-architecture.html) — Compreender a arquitetura conceitual da segurança no TBM Studio, incluindo autenticação, autorização e como o RLS se encaixa na estrutura de segurança mais ampla.
- Seção 6.3: Segurança e conformidade — Saiba mais sobre a configuração de segurança no nível de administrador, registros de auditoria, considerações de conformidade e melhores práticas de segurança corporativa.
- [Criar relatórios](../create-reports/report-basic.html) — Saiba como criar relatórios que utilizam o RLS para oferecer visualizações personalizadas a diferentes públicos-alvo.
- [Entrada manual de dados](manual-data-entry.html) — Saiba mais sobre tabelas editáveis e como o RLS permite o gerenciamento distribuído de dados.

**Tópico principal:** [Segurança de dados](../../../../studio/new-uc/howtoguides/work-with-data/data-security.html)
