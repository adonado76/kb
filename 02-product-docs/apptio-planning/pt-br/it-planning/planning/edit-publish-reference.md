---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Visão geral dos dados de referência"
breadcrumb:
  - "Planning"
  - "Configuração e administração"
source_path: "it-planning/planning/edit-publish-reference.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Visão geral dos dados de referência

Observação: as funções de administrador ou responsável pelo processo orçamentário são necessárias para gerenciar os dados de referência.

Os dados de referência definem as dimensões principais e os valores de pesquisa utilizados em todo Apptio o Planejamento. Essas dimensões categorizam e contextualizam dados financeiros, trabalhistas, contratuais, patrimoniais e de projetos — garantindo consistência, precisão e tratamento de dados limpos em todos os planos.

Pense nos dados de referência como o “vocabulário” que seu ambiente de planejamento usa para classificar custos, recursos, centros de custo, projetos, departamentos, contas e outros atributos importantes.

## Quando gerenciar dados de referência

Como administrador ou responsável pelo processo orçamentário, você configurará os dados de referência quando:

- Configure um novo ambiente ou plano
- Incorpore novos centros de custo, departamentos, projetos, fornecedores, contas ou outras entidades
- Necessidade de atualizar códigos de classificação, adicionar novos valores ou reorganizar hierarquias
- Deseja adaptar os dados de referência à estrutura ou ao plano de contas da sua organização?

Essas tarefas são realizadas em **Configuração > Dados de referência**. As alterações nos dados de referência aplicam-se automaticamente a todos os planos recém-criados. Para aplicar essas alterações a um plano existente, você deve executar **a função Atualizar dados de referência** para esse plano.

## Dimensões padrão

Apptio Planejamento com um conjunto de “dimensões padrão” integradas que cobrem as principais necessidades de planejamento. A lista exata pode variar de acordo com os recursos habilitados em seu ambiente.

|  |  |  |
| --- | --- | --- |
| **Categoria** | **Nome da dimensão** | **Descrição** |
| Finanças | Conta | O campo Conta categoriza o tipo de despesa ou receita que um item representa, como software, hardware, viagens, salários ou serviços. As contas normalmente se alinham ao plano de contas da organização e proporcionam consistência entre o planejamento, o orçamento e os relatórios financeiros. |
| Categoria da conta | A categoria de conta agrupa contas financeiras semelhantes em categorias de relatório mais amplas (por exemplo, viagens, instalações, salários) para simplificar o planejamento e a geração de relatórios. |
| Centro de Custos | Um centro de custos representa uma unidade organizacional utilizada para rastrear e gerenciar onde os custos são incorridos. |
| Departamento | Um departamento representa um grupo funcional dentro da organização. Usado para definir propriedade e responsabilidade no Apptio Planejamento. |
| Local | O campo Localização identifica o local geográfico ou região associada a um item de linha, como um centro de dados, escritório ou país. |
| Fator de variação | O Variance Driver é usado para agrupar e explicar variações, identificando as causas principais ou os fatores contribuintes. |
| Fornecedor | O campo Fornecedor representa prestadores de serviços ou recursos terceirizados. Utilizado para acompanhar e planejar despesas externas por fornecedor. |
| Planejamento de mão de obra | Regras de alocação de mão de obra | As regras de alocação de mão de obra definem em quais contas contábeis os custos de mão de obra são lançados para um determinado número de funcionários. Essas regras controlam como as despesas com mão de obra são geradas e alocadas com base em atributos como função, fornecedor, localização ou tipo de funcionário, garantindo que as finanças relacionadas à mão de obra sejam mapeadas para as contas corretas de forma consistente em todos os planos. |
| Taxas de mão de obra | As taxas de mão de obra capturam as premissas das taxas de mão de obra por atributos como função, localização, tipo de funcionário e fornecedor — utilizadas para o planejamento do quadro de funcionários. |
| Função | O campo Função representa as funções ou cargos utilizados no planejamento de mão de obra para aplicar premissas de custo adequadas. |
| Planejamento de contratos | Tipo de contrato | Padrões do tipo de contrato especifica os atributos padrão para diferentes tipos de contrato, incluindo como os custos são amortizados e a quais contas eles são mapeados. |
| Taxa de IVA | A taxa de IVA define as porcentagens do imposto sobre o valor agregado que podem ser aplicadas a itens de linha de contrato elegíveis. As taxas de IVA garantem que os impostos sejam calculados de forma consistente e precisa em todos os planos, com base nos requisitos fiscais regionais ou organizacionais. |
| Planejamento de ativos | Classe de ativos | As predefinições de classe de ativos definem as configurações padrão de contabilidade e depreciação para diferentes tipos de ativos de capital (por exemplo, hardware, software, melhorias em edifícios). |
| Planejamento do projeto | Projeto | O campo Projeto representa o trabalho planejado ou em andamento, como desenvolvimento de aplicativos, atualizações de infraestrutura ou iniciativas de transformação de negócios. Associar os gastos aos projetos permite que as organizações acompanhem os custos, a mão de obra e os recursos em relação a investimentos específicos, proporcionando visibilidade dos gastos totais do projeto e apoiando a análise ao nível do portfólio. |
| Grupo do Projeto | O Grupo de Projetos organiza vários projetos relacionados sob uma estrutura comum para fins de relatórios ou orçamentos. |
| Planejamento das atividades laborais | Tipo de atividade laboral | O Tipo de atividade de mão de obra define como os custos de mão de obra são cobrados e cobrados entre centros de custo quando o esforço de mão de obra é alocado a projetos. Cada tipo de atividade mapeia uma conta de provedor (departamento) e uma conta de consumidor (projeto), garantindo que os custos de mão de obra sejam alocados corretamente nas contas apropriadas. |
| Função do Trabalho no Projeto | A função de trabalho do projeto especifica as definições das funções de trabalho no contexto de um projeto, incluindo as taxas de trabalho associadas e a moeda de faturamento. |
| Multimoeda | Taxa de câmbio real | A taxa de câmbio real representa as taxas de câmbio utilizadas para converter os gastos reais da moeda de origem para a moeda de destino. |
| Taxa de câmbio do plano | A taxa de câmbio do plano representa as taxas de câmbio utilizadas durante o processo de planejamento para converter os valores planejados da moeda de entrada do planejamento para a moeda de relatório ou corporativa. |

## Dependências entre dimensões

Muitas dimensões são interdependentes, o que significa que certos atributos dependem de valores definidos em outras dimensões. Por exemplo:

- Um **departamento** pode fazer referência a um código **de centro de custos**.
- **Uma classe** de **ativo ou tipo de contrato** pode fazer referência a um código **de conta** para conta de depreciação ou amortização.
- **Uma regra de alocação de mão de obra** pode fazer referência a um código **de conta** para alocação de custos.

Essas dependências garantem a integridade dos dados e a classificação consistente entre diferentes tipos de lançamentos financeiros. Ao editar ou excluir valores, sempre revise as dependências para evitar quebrar referências.

## Dimensões personalizadas

Apptio O planejamento oferece suporte a dimensões personalizadas, permitindo que você amplie o modelo de dados padrão para capturar atributos específicos da organização. Você pode criar até 40 dimensões personalizadas para atender às suas necessidades de planejamento e relatórios.

Para criar e gerenciar dimensões personalizadas, consulte Esquemas.

## Atualização dos dados de referência em um plano

Quando um plano é criado, ele utiliza automaticamente a versão mais recente dos dados de referência disponíveis naquele momento. Se os dados de referência forem atualizados posteriormente, os planos existentes não herdam automaticamente essas alterações. Você deve atualizar explicitamente o plano para aplicar os dados de referência mais recentes.

Como atualizar dados de referência

1. Abra o plano que deseja atualizar.
2. Certifique-se de que está visualizando **Todos os Departamentos**.
3. Abra os **pontos de suspensão (...) menu** e selecione **Atualizar dados de referência**.
4. Analise o **resumo do impacto** apresentado na janela modal de confirmação, que inclui:
   1. Itens a serem atualizados
   2. Itens a serem excluídos
   3. Novos itens
   4. Itens removidos
   5. Códigos pai alterados
5. Se o impacto parecer correto, selecione **Atualizar** para aplicar as alterações.

**Observações importantes**

- Por padrão, as atualizações que excluiriam itens de linha existentes são bloqueadas para evitar a perda acidental de dados.
- Para permitir atualizações destrutivas, um administrador deve habilitar **a opção Desativar restrições de dados de referência de atualização** no perfil da empresa.
- Quando atualizações destrutivas são permitidas, um **plano de backup é criado automaticamente** antes da aplicação da atualização dos dados de referência.

- **[Dimensões padrão](../../it-planning/planning/manage-reference-data.html)**
