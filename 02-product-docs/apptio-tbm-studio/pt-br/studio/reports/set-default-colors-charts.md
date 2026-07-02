---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Definir as cores padrão para métricas em gráficos"
breadcrumb: []
source_path: "studio/reports/set-default-colors-charts.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Definir as cores padrão para métricas em gráficos

**Aplica-se a** : TBM Studio 12.0 e posterior

Use a propriedade **Color Spec** para alterar as cores padrão das métricas em todos os gráficos ou em um único gráfico.

- Para todos os gráficos, use a propriedade **Color Spec** para projetos. Acesse a propriedade clicando em **Configurações do projeto** na guia **Projeto**.
- Para um gráfico individual, use a propriedade **Color Spec (Especificação de cor** ) na guia **Chart (Gráfico** ) da caixa de diálogo **Properties (Propriedades** ).

Você pode especificar cores alternativas para métricas inserindo uma string **de especificação de cor** no seguinte formato:

> `metric=color-spec[;metric=color-spec]`

Os elementos da string estão descritos abaixo.

**métrica** - Qualquer métrica no gráfico conforme seu nome aparece na legenda do gráfico. Não há suporte para asteriscos.

**Especificação de cor** - Uma cadeia de caracteres que descreve a cor. As sequências de especificações de cores válidas são:

- **Cores planas** : preto, cinza, cinza claro, cinza escuro e branco. a opção "Transparente" também é compatível e tornará uma barra ou linha invisível.
- **Cores gradientes** : azul, vermelho, verde, amarelo, violeta, marrom, azul-celeste, verde-claro, laranja, azul-escuro, verde-escuro, roxo, aqua, rosa, azul-petróleo, carmesim.
- Você também pode prefixar qualquer uma das cores gradientes com **flat** para obter uma versão não gradiente, por exemplo: **flatblue**.
- Um ponto de exclamação (! ) antes de uma especificação de cor indica que a especificação de cor seguinte não deve ser usada em nenhum lugar do gráfico.

Você pode especificar várias especificações de cores separando-as com ponto e vírgula (; ), como no exemplo a seguir:

> `Cost=blue;Budget=green;!purple`

Este exemplo especifica: Custo é azul, Orçamento é verde e não use roxo.

Só há suporte para uma métrica por cor. Se você definir duas métricas com a mesma cor, somente a primeira métrica usará a cor selecionada.

Os códigos de cores hexadecimais (por exemplo, #ff55ff ) são válidos, assim como as palavras-chave de cores. Por exemplo, para especificar azul para a métrica de custo:

> `Cost=#082f6d`

As cores disponíveis são mostradas abaixo:

| Cor | Amostra | Cor | Amostra | Cor | Amostra |
| --- | --- | --- | --- | --- | --- |
| azul | imagem | roxo | imagem | preto | Preto |
| vermelho | imagem | azul-claro | imagem | cinza | Cinza |
| verde | imagem | rosa | imagem | cinza claro |  |
| amarelo | imagem | azul esverdeado | imagem | cinza escuro | Cinza escuro |
| violeta | imagem | carmesim | imagem | branco | Branco |
| marrom | imagem | laranja | imagem |  |  |
| azul-celeste | imagem | azul-escuro | imagem |  |  |
| verde-claro | imagem | verde-escuro | imagem |  |  |

## Paleta de cores personalizada

**Aplica-se a** : 12.10.10 e posterior

O valor no campo Color Spec é o valor primário e não pode ser substituído pela paleta de cores personalizada escolhida para o relatório.

Para saber mais, consulte [Paleta de cores personalizada](../admin/color-enhancement.html).
