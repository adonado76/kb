---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Visão geral da arquitetura de segurança"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Modelo de segurança"
source_path: "studio/new-uc/concepts-architecture/security-model/security-architecture.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Visão geral da arquitetura de segurança

O TBM Studio oferece um modelo de segurança em várias camadas que controla quem pode acessar o sistema, quais ações podem ser realizadas e quais dados podem ser visualizados. Compreender essas camadas — e como elas interagem — é essencial para projetar uma configuração de segurança que proteja dados financeiros confidenciais e, ao mesmo tempo, permita que as pessoas certas realizem seu trabalho com eficácia.

## Camadas de segurança

A arquitetura de segurança do TBM Studio opera em três camadas distintas. Cada camada responde a uma pergunta diferente e utiliza um mecanismo distinto para aplicar o controle de acesso.

|  |  |  |  |
| --- | --- | --- | --- |
| **Camada** | **Pergunta respondida** | **Mecanismo** | **Escopo** |
| 1. Autenticação | Quem é você? | Nome de usuário/senha, SSO, chaves de API | Em todo o domínio |
| 2. Autorização (RBAC) | O que pode ser feito? | Funções e permissões atribuídas aos usuários | Nível do projeto e nível do relatório |
| 3. Segurança de dados (RLS) | Que dados você consegue ver? | Filtros de segurança em nível de linha nas tabelas | Nível de tabela, fluxos para relatórios |

Essas camadas funcionam em conjunto como anéis concêntricos. A autenticação é a primeira etapa — ela determina se você terá acesso ao TBM Studio. A autorização é o anel do meio — ela determina quais recursos, relatórios e ações estão disponíveis para você. A segurança dos dados é o anel mais interno — ela filtra as linhas de dados efetivamente visíveis para você nos relatórios e tabelas aos quais você tem acesso.

## Âmbito de segurança

A segurança no TBM Studio é aplicada em vários níveis, desde o mais amplo (domínio) até o mais granular (linhas de dados individuais).

- **Segurança no nível do domínio:** as políticas de senha, o gerenciamento de sessões e as configurações de autenticação se aplicam a todos os usuários em todos os projetos de um domínio. Configurado na caixa de diálogo "Segurança do domínio", na guia "Projeto".
- **Segurança no nível do projeto:** os usuários e as funções são definidos no nível do projeto. A função de um usuário em um projeto pode ser diferente da função que ele desempenha em outro projeto dentro do mesmo domínio.
- **Segurança no nível do relatório:** as permissões de relatório controlam quais funções podem visualizar ou editar relatórios específicos. As coleções de relatórios também podem ser restringidas por função.
- **Segurança no nível dos componentes:** os componentes individuais do relatório (tabelas, gráficos, grupos) podem ser configurados para serem exibidos ou ocultados de acordo com a função atual do usuário.
- **Segurança no nível dos dados (RLS):** os filtros de segurança no nível das linhas restringem quais linhas de dados um usuário pode ver, independentemente do relatório que esteja visualizando. O RLS opera em tabelas d Data Studio, objetos de modelo, tabelas editáveis e relatórios.

Nota: **Como as camadas interagem**

O usuário deve passar por todas as camadas aplicáveis para visualizar os dados. Por exemplo, um usuário corporativo com uma função que concede acesso a um relatório de custos continuará vendo apenas as linhas de dados permitidas pela sua configuração de RLS. Se a função deles não incluir o relatório, eles não o verão de forma alguma — independentemente de o RLS ter ou não permitido o acesso aos dados.

## Estrutura de Decisões de Segurança

Ao planejar sua configuração de segurança, considere estas questões na seguinte ordem:

1. Quem precisa de acesso ao TBM Studio? → Configure contas de usuário e autenticação.
2. O que cada pessoa deve ser capaz de fazer? → Atribuir funções com as permissões adequadas.
3. Quais relatórios cada pessoa deve ver? → Configure as permissões de relatórios por função.
4. Deveriam pessoas diferentes ver dados diferentes no mesmo relatório? → Implemente a segurança no nível da linha.
5. Os layouts dos relatórios devem variar de acordo com a função? → Use as configurações de visibilidade dos componentes
