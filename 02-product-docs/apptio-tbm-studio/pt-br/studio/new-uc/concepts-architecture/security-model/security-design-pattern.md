---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Padrões de projeto de segurança"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Modelo de segurança"
  - "Melhores práticas de segurança"
source_path: "studio/new-uc/concepts-architecture/security-model/security-design-pattern.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Padrões de projeto de segurança

Os padrões a seguir abordam cenários comuns de segurança no TBM Studio. Use essas sugestões como ponto de partida e adapte-as às necessidades específicas da sua organização.

**Modelo 1: Acesso baseado em funções por cargo**

|  |  |
| --- | --- |
| **Aspecto** | **Detalhes** |
| Cenário | Diferentes equipes precisam de diferentes níveis de acesso: analistas financeiros criam modelos, gerentes de departamento visualizam relatórios e executivos consultam painéis de resumo. |
| implementação | Crie três funções: Criador de Modelos (Usuário Avançado + permissões de modelo), Visualizador de Relatórios (Usuário de Negócios + acesso a coleções específicas de relatórios) e Executivo (Usuário de Negócios + acesso a coleções de painéis executivos). |
| RLS | Não é necessário se todas as funções devem ter acesso a todos os dados. Aplique o RLS apenas se algumas funções precisarem ter acesso a dados restritos. |
| Permissões do relatório | Atribua conjuntos de relatórios a funções específicas. Use a visibilidade dos componentes para exibir layouts de gráfico diferentes para executivos e analistas. |

**Padrão 2: Hierarquia organizacional**

|  |  |
| --- | --- |
| **Aspecto** | **Detalhes** |
| Cenário | Os gerentes devem ter acesso aos dados de suas equipes, os diretores devem ter acesso aos dados de seus departamentos e os vice-presidentes devem ter acesso aos dados de suas divisões. |
| implementação | Crie tabelas de mapeamento que reflitam a hierarquia organizacional. O mapa de cada gerente inclui os centros de custo de sua equipe. Os mapeamentos dos diretores incluem todos os centros de custo de seus departamentos. |
| RLS | Aplique a filtragem RLS por centro de custo ou unidade organizacional. Se necessário, utilize várias tabelas de mapeamento para gerenciar a hierarquia de forma organizada. |
| Acesso total | Crie uma tabela de mapeamento separada com acesso total para vice-presidentes e executivos que precisam ter acesso a todos os dados, utilizando o padrão de sinalizador “Is Admin”. |

**Padrão 3: Dados multilocatários**

|  |  |
| --- | --- |
| **Aspecto** | **Detalhes** |
| Cenário | Várias unidades de negócios compartilham uma única instância do TBM Studio, mas devem visualizar apenas seus próprios dados. |
| implementação | Criar tabelas de mapeamento RLS organizadas por unidade de negócios. Cada usuário está vinculado a uma ou mais unidades de negócios. Aplique o RLS a todas as tabelas que contenham dados da unidade de negócios. |
| Integralidade do RLS | Importante: O RLS deve ser aplicado a TODAS as tabelas do modelo que contenham dados específicos da unidade de negócios, incluindo os destinos de detalhamento. A ausência de RLS em qualquer tabela gera um vazamento de dados. |
| Teste | Use o Filtro de Visualização e a representação para verificar se os usuários de cada unidade de negócios visualizam apenas seus próprios dados em todos os relatórios e caminhos de detalhamento. |

**Tópico principal:** [Melhores práticas de segurança](../../../../studio/new-uc/concepts-architecture/security-model/security-best-practices.html)
