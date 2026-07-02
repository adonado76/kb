---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Funções customizadas"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Modelo de segurança"
  - "Controle de acesso baseado em funções (RBAC)"
source_path: "studio/new-uc/concepts-architecture/security-model/custom-roles.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Funções customizadas

Quando as funções padrão não atendem às necessidades da sua organização, você pode criar funções personalizadas com exatamente as permissões necessárias. As funções personalizadas permitem seguir o princípio do privilégio mínimo — concedendo a cada usuário exatamente o acesso de que precisa e nada mais.

**Quando criar funções personalizadas**

- Você precisa de uma função entre o usuário avançado e o usuário de negócios — por exemplo, usuários que possam visualizar dados em ambiente de teste, mas não editar modelos
- Você deseja restringir o acesso ao envio de dados a uma equipe específica, permitindo, ao mesmo tempo, a visualização mais ampla dos relatórios
- As contas de serviço da API precisam de permissões mínimas (como acesso apenas para upload ou apenas para download)
- Você deseja separar as responsabilidades de edição de relatórios das de edição de modelos

**Granularidade das permissões**

As permissões no TBM Studio se dividem em quatro categorias:

|  |  |  |
| --- | --- | --- |
| **Categoria** | **Exemplos** | **Utilização típica** |
| Visualizar permissões | ViewObjectReports, ViewMetricReports, ViewTransformReports, ViewReportsSavedForEveryone, ViewAllData | Controlar quais tipos de relatórios e dados os usuários podem visualizar |
| Editar permissões | Editar modelos, Editar relatórios pessoais, UploadData | Controlar quem pode modificar modelos, criar relatórios e enviar dados |
| Permissões de acesso | AccessDev, AccessStg, AccessProd | Controlar quais ambientes (desenvolvimento, staging, produção) os usuários podem acessar |
| Permissões de execução | DrillDown, InteractiveBenchmarksAndCostData, Ver Proativo | Controle de recursos interativos, como navegação detalhada e acesso a referências |

**Princípios de design de funções personalizadas**

1. Comece com a função padrão mais próxima e ajuste as permissões, em vez de criar tudo do zero.
2. Documente a finalidade e o público-alvo de cada função personalizada.
3. Teste funções personalizadas assumindo a identidade de um usuário atribuído à função antes da implantação.
4. Revise periodicamente as funções personalizadas para garantir que elas ainda atendam às necessidades da organização.

Nota:

**Melhores práticas: Funções da API**

Para contas de serviço de API, crie funções personalizadas exclusivas com apenas as permissões necessárias para a integração específica. Para contas apenas para upload, conceda os direitos AccessDev, e UploadData. Para contas apenas para download, conceda a AccessProd,, AccessStg, e DrillDown, as permissões de visualização pertinentes

**Tópico principal:** [Controle de acesso baseado em funções (RBAC)](../../../../studio/new-uc/concepts-architecture/security-model/role-based-access.html)
