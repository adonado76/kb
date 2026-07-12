---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Configuração de validação"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Tabelas editáveis nos relatórios"
source_path: "studio/new-uc/reference/report-studio-reference/validation-config.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configuração de validação

As regras de validação garantem a qualidade dos dados, impedindo entradas inválidas. O TBM Studio oferece vários mecanismos de validação.

**Campos obrigatórios**

Marque as colunas necessárias para impedir o salvamento de linhas com valores em branco:

- Ativar a opção “Valor obrigatório” na configuração da coluna “ Data Studio ”
- Os usuários não podem salvar a tabela se os campos obrigatórios estiverem em branco
- Os campos obrigatórios são indicados visualmente na interface do relatório

**Validação de tipos de dados**

A configuração do tipo de coluna aplica uma validação básica dos dados:

- **Numérico:** Aceita apenas entradas numéricas no formato da localidade do projeto
- **Data:** Verifica se as entradas correspondem ao formato de data configurado
- **Rótulo:** Aceita qualquer entrada de texto

**Validação de valor único**

Ative a opção “Permitir apenas valores únicos” para evitar entradas duplicadas em uma coluna. Isso é essencial para colunas de chave primária ou qualquer coluna que deva conter valores distintos.

**Validação do menu suspenso**

Quando os valores possíveis estão configurados:

- **Permitir valores que não constam na lista de valores possíveis:** Se a opção não estiver marcada (padrão), os usuários deverão selecionar um valor no menu suspenso
- **Desativar edição na célula de valores possíveis:** se marcada, impede a digitação na célula (útil para controles de seleção rigorosos)

**Total de validadores**

Para colunas numéricas, é possível validar os totais das linhas ou das colunas:

- **Validador de Total da Coluna:** Verifica se os totais das linhas atendem aos critérios (por exemplo, devem ser iguais a 100 para alocações percentuais)
- **Validador de Total da Linha:** Verifica se os totais das colunas estão dentro dos intervalos especificados

Configure os validadores clicando no ícone ao lado de “Validar total” na faixa de opções “Tabelas editáveis”. Selecione um operador de comparação (=, <, >, <=, >=) e especifique o valor de destino.

**Exibição de erro de validação**

Quando a validação falha:

- As células inválidas são destacadas em vermelho
- As mensagens de erro aparecem ao lado dos valores afetados
- As linhas com erros aparecem na parte superior da tabela para facilitar a identificação
- Os usuários podem salvar o relatório com erros de validação, mas não podem publicar dados inválidos

Observação: *para que a validação avançada funcione, o recurso “Ativar etapa de validação para tabelas editáveis” deve estar ativado em Configurações do projeto > Ativar recursos.*

**Tópico principal:** [Componentes de relatórios: Tabelas editáveis em relatórios](../../../../studio/new-uc/reference/report-studio-reference/report-component-editable-components.html)
