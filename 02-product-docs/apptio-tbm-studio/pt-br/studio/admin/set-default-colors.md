---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Definir as cores padrão para as métricas do projeto"
breadcrumb: []
source_path: "studio/admin/set-default-colors.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Definir as cores padrão para as métricas do projeto

**Aplica-se a** : TBM Studio 12.0 e posterior

Use a propriedade **Color Spec** para alterar as cores padrão das métricas em um projeto.

- Para todos os gráficos, use a propriedade Color Spec na caixa de diálogo Edit Project Settings (Editar configurações do projeto). Acesse a caixa de diálogo clicando em Definição na guia Projeto.
- Para um gráfico individual, use a propriedade **Color Spec (Especificação de cor** ) na guia **Chart (Gráfico** ) da caixa de diálogo **Properties (Propriedades** ) do gráfico.

Para acessar a propriedade, na guia **Projeto**, no grupo **Configuração de página**, clique em **Configurações do projeto.** Você pode especificar cores alternativas para métricas inserindo uma string **de especificação de cor** no seguinte formato:

`metric=color-spec[;metric=color-spec]`

Os elementos da string são descritos abaixo.

- **métrica** - Qualquer métrica no gráfico conforme seu nome aparece na legenda do gráfico. Não há suporte para asteriscos.
- **Especificação de cor** - Uma cadeia de caracteres que descreve a cor. As cadeias de especificações de cores válidas são:
  - **Cores planas** : preto, cinza, cinza claro, cinza escuro e branco. a opção "Transparente" também é compatível e tornará uma barra ou linha invisível.
  - **Cores gradientes** : azul, vermelho, verde, amarelo, violeta, marrom, azul-celeste, verde-claro, laranja, azul-escuro, verde-escuro, roxo, aqua, rosa, azul-petróleo, carmesim.
  - Você também pode prefixar qualquer uma das cores gradientes com **flat** para obter uma versão não gradiente, por exemplo: **flatblue**.
  - Um ponto de exclamação (! ) antes de uma especificação de cor indica que a especificação de cor seguinte não deve ser usada em nenhum lugar do gráfico.

Você pode especificar várias especificações de cores separando-as com ponto e vírgula (; ), como no exemplo a seguir:

`Cost=blue;Budget=green;!purple`

Este exemplo especifica: Custo é azul, Orçamento é verde e não use roxo. Só há suporte para uma métrica por cor. Se você definir duas métricas com a mesma cor, somente a primeira métrica usará a cor selecionada. Você pode usar códigos hexadecimais para especificar cores. Por exemplo, para especificar azul:

`Cost=#082f6d`
