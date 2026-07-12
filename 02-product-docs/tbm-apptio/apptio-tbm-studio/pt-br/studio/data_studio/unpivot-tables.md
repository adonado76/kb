---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Desvincular dados"
breadcrumb: []
source_path: "studio/data_studio/unpivot-tables.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Desvincular dados

**Aplica-se a** : TBM Studio 12.0 e posterior

Às vezes, é útil converter valores em colunas em linhas adicionais. Use a etapa **Unpivot** pipeline em uma tabela para fazer isso.

Por exemplo, a tabela a seguir tem colunas para a cidade, o estado, a população do censo de 2023 e a população do censo de 2020.

| Cidade | Estado | 2023 | 2020 |
| --- | --- | --- | --- |
| Nova Iorque | NOVA YORK | 8258035 | 8804190 |
| Los Angeles | CA | 3820914 | 3898747 |
| Chicago | IL | 2664452 | 2746388 |

Para converter as colunas com os valores do censo em linhas:

1. **[Dê uma olhada na](../admin/navigate-tbm-studio.html#FindyourwayaroundTBMStudio__Checkoutandcheckin)** tabela.
2. Adicione uma etapa **Unpivot** ao pipeline da tabela. Para obter mais informações, consulte o [pipeline Transform Steps (Transformar etapas](transform-workspace.html#Thedatatransformworkspace__TransformStepspipeline) ).
3. Clique em **Configure Columns (Configurar colunas** ) e selecione as colunas que você **não** deseja converter em linhas. Neste exemplo, escolheríamos "City" (Cidade) e "State" (Estado).
4. Clique em **Salvar** na faixa de opções.

Isso resulta em uma tabela de saída com duas colunas: *Coluna de recolhimento* e *Valor de recolhimento*.

- **Colapsar coluna:** Inclui valores correspondentes às colunas que você não selecionou.
- **Valor de recolhimento:** Inclui valores das colunas que foram convertidas em linhas.

Essa tabela de saída tem a seguinte aparência:

| Colapsar coluna | Valor de colapso | Cidade | Estado |
| --- | --- | --- | --- |
| 2023 | 8258035 | Nova Iorque | NOVA YORK |
| 2020 | 8804190 | Nova Iorque | NOVA YORK |
| 2023 | 3820914 | Los Angeles | CA |
| 2020 | 3898747 | Los Angeles | CA |
| 2023 | 2664452 | Chicago | IL |
| 2020 | 2746388 | Chicago | IL |

## Observações importantes

**Evite misturar tipos de colunas**

Se as colunas que não forem selecionadas incluírem colunas dos tipos numérico e de rótulo, a coluna "Collapse Value" resultante será uma mistura de valores numéricos e de rótulo. Isso pode levar a problemas posteriores no pipeline da tabela ou em outras tabelas baseadas na tabela com a etapa Unpivot.

Exemplos dos tipos de problemas que podem ocorrer incluem o fato de uma coluna não estar disponível para escolha no identificador de uma etapa do modelo ou o fato de os valores numéricos da coluna não serem somáveis.

Se precisar de uma coluna com valores numéricos e de rótulo misturados, recomendamos que você insira uma etapa de Fórmula após a etapa de Unpivot e edite a coluna existente para substituir o tipo de coluna por um rótulo. Consulte a documentação [Editar uma coluna](add-edit-columns.html#Addandeditcolumns__Editacolumn) para obter mais informações.

**Evitar a expansão excessiva da linha**

O uso da etapa Unpivot expande a contagem de linhas em um valor igual ao número de linhas antes da etapa Unpivot vezes o número de colunas que estão sendo convertidas em linhas. Por exemplo, se a contagem de linhas antes do Unpivot for 10 linhas e você Unpivotar 2 colunas, a contagem de linhas após o Unpivot será: 10 + (2 \* 10) = 30.

Como a etapa Unpivot permite que você especifique as colunas que *não* devem ser convertidas em linhas, se a fonte de dados for alterada para incluir colunas adicionais, isso pode resultar em uma expansão inesperada das linhas, dependendo das propriedades dos dados. Isso pode levar a desafios de desempenho, como lentidão para carregar no TBM Studio ou tempos de cálculo mais longos para o projeto em que a tabela está. O grau do impacto no desempenho varia de acordo com o número de linhas resultantes do pivô e como a tabela é usada posteriormente.
