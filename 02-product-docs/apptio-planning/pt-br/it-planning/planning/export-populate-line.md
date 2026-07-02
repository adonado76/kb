---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Exportar dados planejados"
breadcrumb:
  - "Planning"
  - "Trabalhando com planos"
source_path: "it-planning/planning/export-populate-line.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Exportar dados planejados

Em qualquer visualização de tabela de despesas que exiba tabelas de itens de linha (por exemplo, Resumo, Trabalho, Atividade de trabalho, Contratos, Ativos ou Outros), os usuários com as permissões adequadas podem exportar esses dados para um arquivo.csv.

Há **três modos de exportação** disponíveis:

|  |  |
| --- | --- |
| **Modo de exportação** | **Descrição** |
| **Exportar tudo** | Exporta o conjunto de dados completo, incluindo todas as dimensões e atributos definidos no esquema do plano. |
| **Layout de exportação** | Exporta apenas os dados atualmente visíveis em seu layout, incluindo colunas, filtros e groupings.If agrupamentos aplicados, a exportação incluirá subtotais em nível de grupo em vez de itens de linha individuais filhos. |
| **Exportar para reimportar** | Exporta todos os campos editáveis em um formato adequado para reimportar as alterações. Essa opção ignora filtros e seletores de tempo (mas respeita as restrições de permissão). Observação: Colunas adicionais de Nome e campos gerados pelo sistema estão incluídos no formato Exportar para reimportar para melhorar a legibilidade. Esses campos não são obrigatórios e você pode ignorar com segurança quaisquer avisos relacionados a eles durante o processo de importação. |

## Antes de exportar

- Os resultados da exportação são limitados pelo seu acesso aos dados - por exemplo, o escopo de propriedade do objeto de custo ou as permissões de função do usuário.
- Para controlar quais campos são incluídos ou como os dados são organizados, primeiro ajuste e salve o layout da tabela.
- Os administradores e o proprietário do processo orçamentário podem selecionar um layout padrão para todos os usuários.

## Como exportar dados de itens de linha

1. No plano, selecione o departamento que deseja exportar.
2. Opcionalmente, escolha o Layout relevante no menu **Layout**.
3. Selecione a guia apropriada (por exemplo, Resumo, Trabalho, Atividade de trabalho, Contratos, Ativos ou Outros).
4. Clique no menu **Ações** no canto superior direito e selecione **Exportar...**
5. Escolha o modo de exportação de sua preferência (Exportar tudo, Exportar layout ou Exportar para reimportação) e as configurações de formato de exportação (delimitador de vírgula, formato de data, separador de data, símbolo decimal, precisão decimal, exibição de porcentagem, codificação de caracteres).
6. Clique em **OK**.
