---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Configuração de detalhamento"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Navegação"
source_path: "studio/new-uc/reference/report-studio-reference/drill-through-config.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configuração de detalhamento

A navegação por detalhamento é um recurso essencial nos relatórios do TBM Studio, permitindo que os usuários explorem os dados com níveis crescentes de detalhe. Caminhos de detalhamento devidamente configurados ajudam os usuários a compreender os fluxos de custos, investigar desvios e rastrear as transações até sua origem.

**Exploração detalhada a partir das linhas da tabela**

Configure as colunas da tabela para que funcionem como links de detalhamento. Quando um usuário clica em um valor na coluna configurada, ele é direcionado para o relatório de destino com os filtros apropriados aplicados.

**Etapas de configuração**

1. Selecione a coluna que você deseja habilitar como um link de detalhamento
2. Abra a guia Ad Hoc e clique em Drill na seção Navegação
3. Marque a opção “Ativar navegação” para ativar os links
4. Selecione o relatório de destino no campo “Ir para”
5. Configure as opções de passagem de contexto para controlar quais filtros são aplicados

**Exploração detalhada a partir de elementos do gráfico**

Os gráficos também podem oferecer navegação detalhada. Quando ativada, clicar em uma barra, fatia ou outro elemento do gráfico leva ao relatório de destino, filtrado de acordo com o ponto de dados selecionado.

**Importante:** Nos gráficos, a navegação deve ser baseada na coluna de valores, e não na coluna de rótulos. Configure a função de detalhamento na medida numérica, e não nos rótulos das dimensões.

**Opções de passagem de contexto**

Controle quais dados de contexto são passados para o relatório de destino:

- **Filtrar em todas as colunas de linhas:** aplica todas as dimensões de linha como filtros
- **Filtrar apenas nas colunas agrupadas:** Passa apenas as dimensões agrupadas
- **Filtrar apenas na coluna selecionada no momento:** Passa apenas o valor da coluna clicada
- **Filtrar com base nas seleções do segmentador aplicado:** inclui os valores atuais do filtro do segmentador
- **Incluir os filtros do relatório atual:** Aplica os filtros predefinidos do relatório

Dica: Para que a função de detalhamento funcione corretamente, os dados dos relatórios de origem e de destino devem estar vinculados por meio do mecanismo de inferência. Certifique-se de que ambos os relatórios utilizem tabelas com as relações adequadas definidas no modelo.

**Análise detalhada em vários níveis**

Crie caminhos de detalhamento em cascata que permitam aos usuários explorar os dados progressivamente em vários níveis. Por exemplo, um usuário pode detalhar a partir de um relatório resumido até os detalhes da unidade de negócios, depois até os detalhes do centro de custo e, por fim, até os dados no nível da transação.

**Exemplo: Trajetória de perfuração em três níveis**

**Nível 1 - Relatório resumido:**

- Tabela de custos por unidade de negócios com detalhamento na coluna “Unidade de negócios”
- Configurar o filtro na linha selecionada com as colunas “Filtrar em todas as linhas”

**Nível 2 - Relatório detalhado da unidade de negócios:**

- Recebe o filtro do Nível 1, exibindo apenas a unidade de negócios selecionada
- Tabela de Centros de Custo com detalhamento até o Nível 3

**Nível 3 - Relatório detalhado do centro de custo:**

- Mostra detalhes no nível da transação para o centro de custo selecionado

**Tópico principal:** [Componentes do relatório: Navegação](../../../../studio/new-uc/reference/report-studio-reference/report-component-navigation.html)
