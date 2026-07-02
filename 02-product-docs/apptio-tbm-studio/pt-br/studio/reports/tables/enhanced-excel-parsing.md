---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Como funciona a análise aprimorada do Excel em Apptio"
breadcrumb: []
source_path: "studio/reports/tables/enhanced-excel-parsing.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Como funciona a análise aprimorada do Excel em Apptio

Observação: a partir da versão 12.11.16, o recurso Enhanced Excel Parsing é ativado automaticamente para novos clientes. No momento, não há nenhuma alteração para os clientes existentes. Mais informações serão fornecidas nas próximas atualizações.

## O que esperar ao fazer upload de arquivos

Ao fazer upload de arquivos para Apptio, você pode esperar o seguinte:

- O arquivo será analisado e os dados serão extraídos como brutos, em vez de qualquer formatação aplicada no Excel.
- Os dados na transformação da tabela serão preenchidos de acordo com os valores brutos definidos na especificação Apptio.
- Se houver algum problema com as etapas de transformação da tabela ou se precisar de dados em um formato específico, consulte o documento de ajuda para aplicar a formatação correta.
- Se o arquivo do Excel contiver alguma formatação especial ou macros, ele poderá não ser carregado corretamente e a formatação precisará ser aplicada como parte das etapas de transformação da tabela, se necessário.

**Dicas de solução de problemas**

Se você tiver algum problema com as etapas de transformação, tente o seguinte:

- Verifique as etapas de transformação da tabela e corrija o formatador se os dados não estiverem no formato solicitado.
- Verifique se o arquivo não contém nenhuma formatação especial ou macros.
- Entre em contato com nossa equipe de suporte para obter assistência.

Benefícios da mudança para o novo analisador de planilhas.

- **Formatação padronizada de dados do Excel:** O novo analisador estabelece um formato consistente para os dados do Excel.
- **Precisão numérica aprimorada:** Ele lê valores numéricos brutos diretamente, ignorando qualquer formatação que possa alterar os dados originais, o que resulta em cálculos mais precisos.
- **Representação consistente de data e hora:** Todos os valores de data e hora são convertidos para o formato de época, eliminando a necessidade de conversões complexas e propensas a erros.

## Perguntas mais frequentes

P: **Quais formatos de planilhas são compatíveis com o Apptio?**

R: O site Apptio é compatível com XLSX, XLS

P: **E se eu tiver problemas com o upload ou a análise de arquivos do Excel?**

R: Entre em contato com nossa equipe de suporte para obter assistência.

## O que está mudando no novo analisador do Excel em relação ao antigo

|  |  |  |  |
| --- | --- | --- | --- |
| Formatos | Analisador de planilhas atual | Novo analisador de planilhas | Funções para converter do novo formato de analisador para o formato antigo |
| Geral | Olá | Olá | Nenhuma ação necessária |
| Número | 1 | 0.99999999 | =Round( {Column},0) |
| Moeda | $10.50 | 10.5 | =Currency( {Column}, "#,## 0.00 ") |
| Contabilidade | 34, 343.00 | 34343 | =NumberFormat({Column},"#,##0.00") |
| **Data: Retorna a hora da época** | **1-Jan-24** | **1704047400 (época)** | =DateFormat({Column }, "d-MMM-aaaa") |
| **Tempo: (Época de 1/1/1970 + tempo na célula)** | **12h30** | **45000 (época de 1/1/1970:12:30 )** | =DateFormat({Column }-25569)\*86400, "M/d/yy")}, "hh:mm") O Excel armazena datas como números de série sequenciais, começando com 1, que representa 1º de janeiro de 1900. A época do Unix começa em 1º de janeiro de 1970, 00:00:00 UTC. Para converter de uma data do Excel para segundos da época do Unix ( DateFormat requer isso) Calcule o número de dias entre a data do Excel e a data de início da época do Unix (25569) Converta o número de dias em segundos (\*86400) |
| Percentual | 10% | 0.1 | =NumberFormat({Column }, "#.00%") |
| Fração | 1/2 | 0.5 | Criar o texto da coluna no Excel |
| Científico | 9.88E+11 | 9.87654E+11 | Crie o texto da coluna no Excel (isso se você realmente quiser que a notação científica apareça assim em Apptio ) |
| Texto | As nuvens se afastam, os sussurros ecoam, o tempo. | As nuvens se afastam, os sussurros ecoam, o tempo. | Nenhuma ação necessária |
| Especial | (91987) 654-3456 | 9.19877E+11 | Crie o texto da coluna no Excel ou escreva uma fórmula para adicionar texto onde for necessário IE ="("&Left( Column,5 )&")"&Mid( Column,5,3 )&"-"&Right( Column,4 ) |
| Personalizado | 43333.45 | 43333.44555 | Crie o texto da coluna no Excel ou escreva uma fórmula para formatar conforme desejado |
| Fórmula | 100 | 100 | No Action Needed (Nenhuma ação necessária) - Exibe os resultados da fórmula |

Como a hora e a data se comportarão com a mudança no formato

1. Date (Data) - Se o valor da data que chega ao site Apptio for um tipo de data do Excel, ele precisará ser convertido para a época do Unix.

   O Excel armazena datas como números de série sequenciais, começando com 1, que representa 1º de janeiro de 1900.   
   A época do Unix começa em 1º de janeiro de 1970, 00:00:00 UTC.   
   Para converter de uma data do Excel para segundos da época do Unix ( DateFormat requer isso)   
   Calcule o número de dias entre a data do Excel e a data de início da época do Unix (25569)   
   Converta o número de dias em segundos (\*86400)

   `=DateFormat(({Column}-25569)*86400,"M/d/yy")`

**Tópico pai:** [Componente Upload de tabela](../../../studio/reports/table-report-upload-component.html "Aplica-se a: TBM Studio 12.9.3 e posterior")
