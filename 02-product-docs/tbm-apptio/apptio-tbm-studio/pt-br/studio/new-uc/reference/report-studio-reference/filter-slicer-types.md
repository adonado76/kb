---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Tipos de componentes de filtro e segmentador"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Filtros e segmentadores"
source_path: "studio/new-uc/reference/report-studio-reference/filter-slicer-types.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tipos de componentes de filtro e segmentador

**Componentes do cortador**

O TBM Studio oferece vários tipos de filtros para atender a diferentes necessidades de filtragem:

**Seletor de linhas (Seletor de lista)**

O tipo de divisor padrão para campos de texto e categóricos. Exibe os valores em uma lista selecionável, na qual os usuários podem clicar para filtrar os dados.

|  |  |
| --- | --- |
| **Propriedade** | **Descrição** |
| Tipo de dados | Campos de texto/rótulo |
| Modo de seleção | Seleção múltipla (Ctrl + clique para selecionar vários) |
| Exibir | Lista de valores com status (Selecionado, Relacionado, Não relacionado) |
| Valores máximos | 250 valores por filtro |

**Quando usar:** filtragem por categoria, seleção de dimensões, qualquer campo de texto em que os usuários precisem selecionar entre valores distintos.

**Controle deslizante numérico**

É criado automaticamente quando você adiciona um campo numérico a um filtro. Oferece um controle deslizante de intervalo para filtrar dados numéricos.

|  |  |
| --- | --- |
| **Propriedade** | **Descrição** |
| Tipo de dados | Campos numéricos |
| Modo de seleção | Seleção de intervalo por meio de controles deslizantes |
| Exibir | Controle deslizante horizontal com marcadores mínimo e máximo |
| Operadores | Suporta maior que, menor que, entre |

**Quando usar:** limites de custo, intervalos de quantidade e qualquer métrica numérica em que os usuários precisem filtrar por intervalos de valores.

**Filtro hierárquico**

Permite a filtragem por níveis hierárquicos (por exemplo, Tipo → SubType e → Detalhe).

|  |  |
| --- | --- |
| **Propriedade** | **Descrição** |
| Base | Grupo de perspectivas personalizado com campos ordenados |
| Navegação | Estrutura em árvore expansível |
| Seleção | A seleção do elemento pai filtra os valores dos elementos filhos |
| Use com | Fatiadores compactos compatíveis |

**Quando usar:** Hierarquias geográficas, estruturas organizacionais, taxonomias de produtos, qualquer classificação em vários níveis.

**Fatiador compacto**

Reúne vários filtros em uma interface suspensa que economiza espaço. Disponível em duas versões:

**Fatiador compacto local**

- Utiliza campos bloqueados e desbloqueados
- As seleções não são salvas entre sessões
- Aplica-se como os filtros padrão (no âmbito do relatório ou do grupo)

**Fatiador Global Compact**

- Somente os campos vinculados a um objeto podem ser incluídos
- As seleções do usuário são mantidas entre sessões e ao fazer logout/login
- As alterações se aplicam a todos os relatórios que contenham o mesmo filtro do Pacto Global
- Substituição recomendada para filtros globais antigos

Dica: Sempre que possível, use segmentadores compactos globais em vez de filtros globais. Eles oferecem uma melhor experiência do usuário e configurações de filtro persistentes.

**Tipos e configuração de filtros**

**Filtros no nível do componente (Área de filtros)**

Os filtros adicionados à área “Filtros” do painel “Configuração do componente” restringem os dados antes que eles cheguem à tabela ou ao gráfico.

**Etapas de configuração:**

1. Arraste um campo de uma perspectiva para a área Filtros
2. Clique com o botão direito do mouse no campo e selecione “Editar filtro”
3. Selecione os valores a incluir ou excluir
4. Clique em OK para aplicar

**Opções da caixa de diálogo de filtro:**

|  |  |
| --- | --- |
| **Opção** | **Descrição** |
| Seleção de valores | Marque/desmarque os valores específicos a serem incluídos |
| Adicionar filtro personalizado | Insira valores de filtro personalizados que não constam na lista |
| Valores não exibidos no momento | Incluir valores que excedam o limite de exibição de 1.000 value1,000-value |
| Caixa de pesquisa com filtro | Pesquisar valores específicos quando a lista é extensa |

**Observação:** Se houver mais de 1.000 valores para um campo de filtro, use a caixa de pesquisa “Filtro” para localizar valores adicionais.

**Filtro de pesquisa automática (filtragem na tabela)**

As tabelas permitem a filtragem direta por meio dos campos de pesquisa localizados abaixo dos cabeçalhos das colunas.

**Operadores de pesquisa:**

|  |  |  |  |
| --- | --- | --- | --- |
| **Operador** | **Coluna Número** | **Coluna de texto** | **Descrição** |
| Texto | Não | Sim | Encontre as linhas que contêm o texto |
| !texto | Não | Sim | Encontrar linhas que NÃO contenham o texto |
| = | Sim | Sim | Correspondência exata (diferencia maiúsculas de minúsculas para texto) |
| > < >= <= != | Sim | Não | Comparações numéricas |
| BRANCO | Sim | Sim | Encontrar células vazias |
| !BRANCO | Sim | Sim | Encontrar células não vazias |
| && | Sim | Sim | Lógica "E" (por exemplo, Salvar && Mestre) |
| || | Sim | Sim | Lógica OR (por exemplo, Salvar || Mestre) |

Observação: você pode usar vários operadores && ou vários operadores || em uma pesquisa, mas não é possível combinar os dois operadores na mesma pesquisa.

**Tópico principal:** [Componentes do relatório: Filtros e segmentadores](../../../../studio/new-uc/reference/report-studio-reference/report-component-filters-slicers.html)
