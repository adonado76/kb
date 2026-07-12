---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Componentes do contêiner"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Opções de layout"
source_path: "studio/new-uc/reference/report-studio-reference/container-components.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Componentes do contêiner

Os componentes de contêiner agrupam elementos relacionados e fornecem uma estrutura organizacional aos relatórios.

**Caixas de grupo**

As caixas de grupo agrupam visual e logicamente os componentes do relatório. Os componentes dentro de uma caixa de grupo se movem como uma unidade quando o grupo é reposicionado.

**Principais comportamentos:**

- Os filtros dentro de uma caixa de grupo se aplicam apenas às tabelas e gráficos contidos nessa caixa de grupo (e em quaisquer grupos aninhados).
- Os filtros fora das caixas de grupo se aplicam a todas as tabelas e gráficos do relatório.

**Para adicionar uma caixa de grupo:**

1. Na guia Relatório, clique no ícone Grupo.
2. Mova e redimensione a caixa conforme necessário, arrastando o cabeçalho (para mover) ou as bordas (para redimensionar).

**Opções de layout de grupo (disponíveis na guia Grupo):**

|  |  |
| --- | --- |
| **Layout** | **Comportamento** |
| **Manual** | Posicione os componentes em qualquer lugar; eles permanecem onde forem colocados |
| **Vertical** | Alinha automaticamente os componentes em uma coluna vertical |
| **Horizontal** | Alinha automaticamente os componentes em linhas horizontais |
| **Espaçamento** | Abre uma caixa de diálogo para definir o espaçamento vertical e horizontal entre os componentes |

Dica: use layouts verticais ou horizontais quando os componentes puderem ser ocultados condicionalmente com base nas funções dos usuários. Os componentes restantes preencherão automaticamente o espaço deixado pelos componentes ocultos.

**Componentes com abas**

Os componentes com guias organizam vários elementos em guias selecionáveis, economizando espaço no relatório e, ao mesmo tempo, proporcionando acesso a conteúdos relacionados.

Para adicionar um componente com guias: Na guia Relatório, clique no ícone Guias.

**Trabalhando com guias:**

|  |  |
| --- | --- |
| **Ação** | **Instruções** |
| **Adicionar uma guia** | Clique na guia com o sinal de +; digite um nome e pressione Enter |
| **Adicionar componente a uma guia** | Crie o componente na área de trabalho do relatório e arraste-o para o grupo com abas |
| **Remover componente da guia** | Arraste o componente para fora ou clique no ícone de exclusão no canto superior direito |
| **Alterar a ordem de tabulação** | Selecione uma guia e clique nos ícones de seta dupla para a esquerda/direita (<< / >>) |
| **Excluir uma guia** | Selecione a guia e clique no ícone Excluir |
| **Redimensionar o grupo com guias** | Clique e arraste as bordas |
| **Definir a cor de fundo da guia** | Clique com o botão direito do mouse na guia → Propriedades → Cor de fundo da guia |

**Controlando a visibilidade das guias com texto dinâmico:**

Você pode usar expressões de texto dinâmicas para controlar a visibilidade das guias com base nos dados ou nas funções do usuário:

|  |  |
| --- | --- |
| **Valor** | **Comportamento** |
| **ativado** | A guia está visível e pode ser selecionada |
| **oculto** | A guia não está visível |
| **desativado** | A guia está visível, mas não pode ser selecionada |

Observação: Todos os componentes, exceto as caixas de grupo, podem ser colocados em uma guia.

**Tópico principal:** [Opções de layout](../../../../studio/new-uc/reference/report-studio-reference/layout-options.html)
