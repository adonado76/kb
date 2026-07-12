---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Comportamento do filtro"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Filtros e segmentadores"
source_path: "studio/new-uc/reference/report-studio-reference/filter-behavior.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Comportamento do filtro

**Configuração de valores padrão**

Você pode definir seleções de filtro padrão que aparecem quando os usuários abrem um relatório pela primeira vez:

1. Selecione os valores desejados no filtro
2. Salvar o relatório

Quando os usuários abrem o relatório, os filtros exibem os valores padrão selecionados. Os usuários podem alterar suas seleções durante a sessão.

**Para cortadores Global Compact:**

- Cada usuário pode salvar suas próprias configurações de filtro
- As configurações salvas são mantidas mesmo após o logout e o login
- As alterações feitas em um relatório se aplicam a todos os relatórios que utilizam o mesmo filtro global

**Estados do Slicer e feedback visual**

Os valores do Slicer são exibidos em três estados, indicados por cores:

|  |  |  |
| --- | --- | --- |
| **Estado** | **Descrição** | **Interação do usuário** |
| Selecionado | Valores do filtro atualmente ativos | Destacado; clique para desmarcar |
| Relacionados | Valores relacionados à exibição dos dados atuais | Aparência padrão; filtrará os dados se selecionado |
| Não relacionado | Valores não relacionados aos dados exibidos no momento | Desativado; a seleção não tem efeito |

**Comportamento do estado:**

- As seleções em um filtro podem alterar o estado em outros filtros (tornando alguns valores não relacionados)
- Valores combinados usando a lógica OR dentro de um filtro
- Valores combinados usando a lógica AND entre filtros

**Opções de procura**

Ao adicionar um filtro, configure como a caixa de pesquisa automática filtra os valores:

|  |  |  |
| --- | --- | --- |
| **Opção** | **Comportamento** | **Exemplo: O usuário digita "abc"** |
| Contém | Encontra valores que contenham o texto em qualquer lugar | Resultados: abcefg, defabc, defabcefg |
| Começa com | Encontra valores que começam com o texto | Corresponde a: abcefg, abc (não dabc nem 1abc ) |
| Pesquisa por grupo | Agrupa valores por prefixo mais um caractere (apenas códigos de hierarquia) | Cria grupos: ABC1, ABC2, etc. |

**Tópico principal:** [Componentes do relatório: Filtros e segmentadores](../../../../studio/new-uc/reference/report-studio-reference/report-component-filters-slicers.html)
