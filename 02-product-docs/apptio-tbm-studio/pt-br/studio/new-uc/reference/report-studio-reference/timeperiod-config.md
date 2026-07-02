---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Configuração do período"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Propriedades do relatório"
source_path: "studio/new-uc/reference/report-studio-reference/timeperiod-config.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configuração do período

As configurações de período determinam quais intervalos de dados os usuários veem ao visualizar relatórios. Essas configurações interagem com a configuração de tempo no nível do projeto e afetam os dados exibidos em tabelas, gráficos e KPIs.

**Herança de tempo no nível do projeto**

Os relatórios herdam as configurações de período da configuração do projeto. As seguintes configurações do projeto afetam todos os relatórios:

|  |  |
| --- | --- |
| **Contexto do projeto** | **Impacto nos relatórios** |
| Período padrão | O período exibido aos usuários quando abrem um relatório pela primeira vez. Normalmente definido como o período fiscal encerrado mais recentemente. Os usuários podem alterar essa seleção usando o seletor de hora. |
| Definição de exercício fiscal | Determina a estrutura do calendário fiscal (por exemplo, janeiro-dezembro, outubro-setembro, federal). Influencia a forma como os períodos são identificados e agrupados nos relatórios de tendências. |
| Período de início/término do projeto | Limita o intervalo de períodos disponíveis. Os dados fora desse intervalo não são calculados, o que melhora o desempenho em modelos de grande porte. |
| Períodos de fechamento | Os períodos marcados como encerrados continuam visíveis nos relatórios, mas seus dados não podem ser alterados. Fundamental para a governança financeira e as trilhas de auditoria. |

**Para definir as configurações de tempo do projeto:** acesse a guia Projeto > Configurações de tempo.

**Restrições de data específicas do relatório**

Os relatórios individuais podem substituir o período padrão do projeto e restringir o período em que ficam visíveis.

**Data de início de vigência**

Restringe a visibilidade do relatório às datas a partir de um período especificado. Esse recurso é útil para:

- Ocultar relatórios ainda em desenvolvimento
- Publicação de relatórios alinhados aos ciclos econômicos
- Impedir o acesso aos relatórios antes que os dados necessários estejam disponíveis

**Para definir a data mais próxima possível:**

1. Confira o relatório
2. Na guia Relatório, clique em Data de início
3. Na caixa de diálogo “Configurar a data mais antiga aplicável”, selecione uma data
4. Salve e verifique o relatório

Quando os usuários tentam visualizar o relatório antes da data mais antiga aplicável, eles veem uma mensagem explicando que o relatório ainda não está disponível, com um link para visualizá-lo assim que estiver disponível.

**Período de tempo no nível do componente**

Os componentes individuais do relatório (tabelas e gráficos) podem ter seu período bloqueado independentemente do período atual do relatório. Isso é configurado através do campo “Período de dados” nas propriedades avançadas de cada componente.

Exemplos de casos de uso:

- Exibir dados comparativos do ano anterior juntamente com os do período atual
- Mostrar o orçamento de um período bloqueado específico
- Crie gráficos de tendências com datas de início e término fixas

**Tópico principal:** [Propriedades do relatório](../../../../studio/new-uc/reference/report-studio-reference/report-properties.html)
