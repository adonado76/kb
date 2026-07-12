---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Comportamento da tabela"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Tabelas"
source_path: "studio/new-uc/reference/report-studio-reference/table-behavior.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Comportamento da tabela

**Colunas de congelamento**

Congele as colunas para mantê-las visíveis durante a rolagem horizontal. As colunas congeladas são movidas para a extremidade esquerda.

**Para congelar uma coluna:**

- Selecione a coluna e clique no ícone “Fixar” na guia “Dados”, OU
- Clique com o botão direito do mouse no cabeçalho da coluna > Formatação > Fixar coluna.

Para desbloquear: clique com o botão direito do mouse no cabeçalho da coluna > Formatação > Desbloquear coluna.

**Paginação**

As tabelas com muitas linhas exibem uma barra de paginação para facilitar a navegação. Configure a paginação usando a opção “Máximo de linhas” na caixa de diálogo “Propriedades”.

|  |  |
| --- | --- |
| **Opção** | **Comportamento** |
| Número máximo de linhas = 20 | Exibe 20 linhas por página com barra de navegação. |
| Ocultar barra de navegação = Sim | Mostra apenas as primeiras linhas, sem navegação. |
| Caso de uso | Listas dos 10 melhores, tabelas resumidas nas quais não é desejável ter que rolar a tela. |

**Configuração de detalhamento**

Habilite a navegação dos valores da tabela para relatórios detalhados. Os links aparecem em azul.

**Para configurar o drill-through:**

1. Selecione uma coluna na tabela.
2. Clique na guia Ad Hoc e clique em Drill na seção Navegação.
3. Configurar propriedades de navegação.

|  |  |
| --- | --- |
| **Propriedade** | **Descrição** |
| Ativar navegação | Transforma os valores da coluna em links. |
| Abrir como janela modal | Abre o relatório de destino em uma janela pop-up. O usuário está prestes a sair. |
| Relatório da Target | O relatório para o qual se deve ser direcionado ao clicar. |
| O contexto inclui | Que contexto de dados passar: Filtro de linha, Valores de coluna, Seleção. |

**Observação:** os links dos relatórios funcionam apenas com tabelas baseadas em objetos. As tabelas de transformação não suportam navegação detalhada.

**Opções de exportação**

As tabelas podem ser exportadas como parte de relatórios em vários formatos.

|  |  |
| --- | --- |
| **Formato** | **Detalhes** |
| PDF | Exporte através da guia Início > Exportar > PDF. Use o modo de layout de impressão para layouts personalizados. Tabelas com várias páginas são compatíveis com a opção “Imprimir todas as páginas”. |
| Excel | As colunas mantêm a ordem da configuração do relatório. Colunas não configuradas foram anexadas. As tabelas em árvore são exportadas como tabelas planas com recuo. |
| E-mail | Os relatórios podem ser enviados por e-mail como anexos em PDF ou links. Configurar por meio da assinatura por e-mail. |

**Atualização diferida**

Para relatórios complexos com muitos controles interativos, configure o comportamento de atualização para evitar atualizações excessivas da tela.

|  |  |
| --- | --- |
| **Opção** | **Descrição** |
| Atraso na atualização: 3s | O sistema aguarda 3 segundos antes de atualizar após a interação do usuário. Configuração padrão. |
| Atualização manual | O usuário deve clicar em Atualizar para atualizar. Ideal para relatórios com vários filtros e seletores. |

Configurar globalmente: guia Projeto > Configurações do projeto > Atualização diferida. Substituir por relatório: Relatório de checkout > guia Relatório > Atualizar configurações.

**Tópico principal:** [Componentes do relatório: Tabelas](../../../../studio/new-uc/reference/report-studio-reference/report-component-table.html)
