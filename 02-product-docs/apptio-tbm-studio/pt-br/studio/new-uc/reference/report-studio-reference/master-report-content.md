---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Conteúdo do Relatório Principal"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Relatórios principais"
source_path: "studio/new-uc/reference/report-studio-reference/master-report-content.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Conteúdo do Relatório Principal

**Componentes adequados para relatórios principais**

Os relatórios principais podem conter todos os componentes disponíveis nos relatórios comuns. No entanto, certos componentes são mais adequados para masters:

|  |  |  |
| --- | --- | --- |
| **Componente** | **Uso recomendado** | **Considerações** |
| **Caixas de grupo** | Estrutura do layout, contêineres visuais | Perda da funcionalidade de agrupamento nos relatórios secundários |
| **Botões** | Navegação entre relatórios | O texto da Wiki utiliza o contexto do relatório secundário |
| **Componentes com abas** | Layouts com várias seções | Incluir todo o conteúdo das guias na guia principal; o conteúdo da guia secundária se sobrepõe a todas as guias |
| **Notas** | Instruções, avisos legais, texto estático | Apenas estático; não pode ser editado na subpágina |
| **Cabeçalhos/Rodapés** | Identidade visual, títulos, números de página | Os cabeçalhos suportam texto dinâmico; os rodapés não |

**Elementos comuns do relatório mestre**

**Cabeçalhos e rodapés**

É possível adicionar cabeçalhos aos relatórios mestre para que sejam exibidos em todas as páginas ou apenas na primeira página. Você pode formatar o texto do cabeçalho usando tags de formatação HTML e incluir texto dinâmico. Por exemplo, use `<%=CurrentDate()%>` para exibir o período atual. Os rodapés podem ser totalmente personalizados, embora, ao contrário dos cabeçalhos, não suportem texto dinâmico.

**Elementos de navegação**

Os botões e links nos relatórios principais permitem a navegação entre os relatórios. Quando você adiciona um botão a um relatório mestre que utiliza texto Wiki e não especificou um "Data URL " para o botão, o aplicativo utilizará o relatório atual (o relatório filho) como contexto quando os usuários interagirem com ele.

**Identidade visual (logotipos e cores)**

Os administradores podem definir paletas de cores personalizadas no nível do ambiente para adequar os relatórios às diretrizes de identidade visual da organização. Essas paletas de cores podem ser aplicadas a coleções de relatórios e a relatórios individuais. As paletas de cores são definidas em **Configurações > Paleta de cores personalizada** e estão disponíveis para as funções de Administrador do Apptio, Administrador e Administrador de parceiros. Cada paleta de cores contém 12 cores, com até 10 paletas personalizadas disponíveis.

**Caixas de grupo como contêineres de layout**

As caixas de grupo são particularmente úteis em relatórios principais para criar seções visuais e delimitações. No entanto, observe que as caixas de grupo adicionadas a um relatório mestre perdem sua funcionalidade de agrupamento de componentes quando o relatório mestre é aplicado a um relatório filho. Nos relatórios filhos, as caixas de grupo do relatório mestre servem apenas como bordas visuais em torno das áreas de conteúdo.

**Tópico principal:** [Relatórios principais](../../../../studio/new-uc/reference/report-studio-reference/master-report.html)
