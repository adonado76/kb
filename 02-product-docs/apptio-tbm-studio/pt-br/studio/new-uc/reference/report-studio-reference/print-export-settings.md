---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Configurações de impressão e exportação"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Propriedades do relatório"
source_path: "studio/new-uc/reference/report-studio-reference/print-export-settings.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configurações de impressão e exportação

As configurações de layout de impressão determinam a forma como os relatórios são exibidos quando exportados para o formato PDF ou impressos. Essas configurações podem ser personalizadas para cada relatório, a fim de otimizar a impressão.

**Acessando o modo de layout de impressão**

1. Confira o relatório
2. Na guia Página inicial, clique em Exibir > Layout de impressão
3. A guia "Layout de impressão" fica disponível para configuração

**Opções de configuração da página**

|  |  |
| --- | --- |
| **Opção** | **Descrição** |
| Tamanho da página | Selecione o tamanho do papel no menu suspenso (Letter, A4, Legal, etc.) |
| Orientação | Orientação da página: retrato (vertical) ou paisagem (horizontal) |
| Margens | Configurar as margens superior, inferior, esquerda e direita |
| Fluxo | Manual: Os componentes permanecem onde foram colocados. Vertical: os componentes são dispostos em uma única coluna. Horizontal: os componentes são dispostos em fileiras, com o número máximo de componentes por fileira. |

**Cabeçalhos e rodapés**

**Opções de cabeçalho:**

- Exibir em todas as páginas ou apenas na primeira página
- Redimensione arrastando as bordas do cabeçalho
- Formate o texto usando tags HTML
- Use texto dinâmico (por exemplo, <%=CurrentDate( )%> para o período atual)

**Opções de rodapé:**

- Personalizar as seções do rodapé à esquerda, no centro e à direita
- Especifique o texto do rodapé ou deixe em branco para não exibir rodapé
- O texto dinâmico não é compatível com rodapés

**Opções de impressão de componentes**

|  |  |
| --- | --- |
| **Opção** | **Descrição** |
| Fixar/Desfixar | Prenda um componente (como os filtros) no final do relatório para registrar os filtros aplicados |
| Mostrar/Ocultar | Ocultar componentes específicos na impressão. Use o campo Filtro para procurar componentes em listas extensas. |

**Opções de exportação**

Os relatórios podem ser exportados usando os seguintes métodos:

|  |  |
| --- | --- |
| **Método de exportação** | **Descrição** |
| Baixar diretamente em PDF | Gera um PDF e o abre no navegador ou permite o download, dependendo das configurações do navegador |
| Incluir link para o PDF no e-mail | Envia um e-mail com um link para acessar o PDF gerado |
| Anexar PDF ao e-mail | Envia um e-mail com o PDF em anexo |

Observação: *ao compartilhar relatórios por meio de um link de e-mail, os destinatários visualizam o relatório com os mesmos filtros, segmentadores, seletores e intervalo de datas que foram aplicados no momento do compartilhamento.*

**Tópico principal:** [Propriedades do relatório](../../../../studio/new-uc/reference/report-studio-reference/report-properties.html)
