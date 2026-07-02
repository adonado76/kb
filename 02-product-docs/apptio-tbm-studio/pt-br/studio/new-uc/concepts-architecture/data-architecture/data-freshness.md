---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Atualização e validação de dados"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Arquitetura de dados"
source_path: "studio/new-uc/concepts-architecture/data-architecture/data-freshness.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Atualização e validação de dados

Uma análise precisa dos custos depende de dados atualizados e de alta qualidade. O TBM Studio oferece vários mecanismos para ajudar você a monitorar a atualidade dos dados e validar a qualidade dos dados ao longo de todo o pipeline.

## Atualidade dos dados

A atualização dos dados verifica se os seus dados foram atualizados de acordo com o cronograma de atualização previsto. Quando você configura uma tabela com um ciclo de atualização mensal, o TBM Studio verifica se os dados de cada mês foram efetivamente carregados dentro do prazo.

**Por que a frescura é importante**

Dados desatualizados levam a modelos de custo imprecisos. Se o seu arquivo do Razão de janeiro não for carregado e o modelo fizer o cálculo usando os dados de dezembro (ou sem dados), as alocações e os relatórios resultantes serão enganosos. O monitoramento da atualidade dos dados ajuda a identificar essas lacunas antes que elas afetem a tomada de decisões.

**Monitoramento da frescura**

A TBM Studio oferece dois recursos de monitoramento de atualização:

- **Verificação de validade dos dados:** notificações por e-mail configuráveis que alertam usuários designados quando os dados carregados expiram, com base no ciclo de atualização da tabela. Você pode especificar os endereços de e-mail dos destinatários, o número de dias após o vencimento para enviar a primeira notificação e se deseja enviar lembretes diários até que novos dados sejam carregados.
- **Painel de atualização de dados:** acessível na guia “Projeto”, este painel exibe um resumo de todas as tabelas com seu status de validade e uma lista das regras de atualização configuradas.

## Validação de dados

A validação garante que os dados que entram no fluxo de trabalho atendam aos padrões de qualidade esperados. O TBM Studio oferece validação em vários níveis:

**Validação do esquema**

- **Detecção do tipo de coluna:** a plataforma detecta automaticamente se as colunas são do tipo Rótulo (texto), Numérico ou Estado. Detecções incorretas são identificadas durante a importação e podem ser substituídas manualmente.
- **Campos obrigatórios:** As tabelas de transformação que se relacionam com conjuntos de dados principais exigem campos específicos. Campos obrigatórios ausentes geram erros no pipeline que bloqueiam os cálculos do modelo a jusante.
- **Validação de cardinalidade:** verifica se os dados correspondem aos padrões esperados durante o upload.

**Validação de tabelas editáveis**

As tabelas editáveis suportam regras de validação configuráveis que detectam entradas inválidas do usuário antes que elas cheguem ao pipeline:

- Validação do intervalo numérico (por exemplo, os valores devem estar entre 0 e 100).
- Verificação de campos obrigatórios.
- Listas de valores restritos por meio de menus suspensos (enumerações estáticas ou valores dinâmicos baseados em fórmulas).
- Lógica de menus suspensos em cascata que filtra os valores permitidos com base nas seleções feitas em outras colunas.

As linhas inválidas são destacadas com mensagens de erro e não podem ser publicadas na tabela de transformação até que o usuário as corrija.

**Manipulação de erros**

O TBM Studio identifica problemas de qualidade dos dados por meio de um painel centralizado de erros que agrega os erros de todas as tabelas do projeto. Os tipos de erros mais comuns incluem:

- Incompatibilidades de tipo (um valor de texto em uma coluna numérica)
- Faltam campos obrigatórios nos objetos do modelo a jusante
- Valores de data inválidos que impedem a atribuição correta do período
- Erros na configuração das etapas de transformação

Os erros se propagam para cima: um erro de dados em uma transformação anterior pode bloquear os cálculos do modelo para qualquer objeto do modelo que dependa dessa transformação. O painel Erros ajuda você a identificar e localizar rapidamente a origem dos problemas.

## Melhores práticas de qualidade de dados

- **Validar na ingestão:** Confirmar os tipos de coluna durante a importação. Detectar incompatibilidades de tipos logo no início evita erros em cadeia nas etapas posteriores.
- **Ativar o monitoramento da atualização:** Configure notificações por e-mail para todas as tabelas de dados críticos, especialmente os dados financeiros que alimentam os processos de fechamento mensal.
- **Use entradas restritas em tabelas editáveis:** os menus suspensos e as regras de validação evitam erros de texto livre em campos que alimentam as dimensões do modelo.
- **Verifique os erros regularmente:** verifique o painel Erros após cada carregamento de dados. Erros não resolvidos podem prejudicar silenciosamente a precisão do modelo.
- **Limpar tabelas não utilizadas:** use o recurso de análise de documentos não utilizados para identificar tabelas que não são mais referenciadas. Retirá-los reduz o ruído e simplifica a resolução de problemas.
