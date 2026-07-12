---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Validação"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório - Componentes de entrada"
source_path: "studio/new-uc/reference/report-studio-reference/validation.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Validação

O TBM Studio oferece vários mecanismos de validação para garantir a integridade dos dados.

**Validação de campos obrigatórios**

Propriedade: Valor obrigatório - Quando marcada, os usuários não podem salvar a tabela se uma linha tiver um valor em branco nesta coluna.

**Validação de tipos de dados**

A propriedade Type verifica automaticamente se os valores inseridos correspondem ao tipo de dados esperado:

|  |  |
| --- | --- |
| **Tipo** | **Validação** |
| Rótulo | Aceita qualquer texto |
| Numérico | Valida o formato numérico de acordo com a configuração regional do projeto |
| Data | Valida o formato da data de acordo com o formato de data configurado |

**Validação da exclusividade**

Propriedade: Permitir apenas valores únicos - Quando marcada, os usuários não podem salvar a tabela se a coluna contiver valores duplicados.

**Validação de intervalo (nível da tabela)**

Configure a validação de intervalo por meio das propriedades "Validate Total":

- Validador de Total da Coluna: Verifica se os totais das linhas estão dentro dos intervalos aceitáveis
- Validador de Total da Linha: Verifica se os totais das colunas atendem aos requisitos (por exemplo, se as porcentagens somam 100%)

**Exibição de erro de validação**

Quando a validação falha:

- As mensagens de aviso ou erro aparecem ao lado da respectiva célula
- As linhas com erros são destacadas e movidas para o topo da tabela
- Os usuários podem salvar e registrar relatórios mesmo que haja erros (para trabalhos em rascunho)
- Linhas inválidas não podem ser publicadas com sucesso nas tabelas de transformação

**Tópico principal:** [Componentes do relatório - Componentes de entrada](../../../../studio/new-uc/reference/report-studio-reference/report-component-input-components.html)
