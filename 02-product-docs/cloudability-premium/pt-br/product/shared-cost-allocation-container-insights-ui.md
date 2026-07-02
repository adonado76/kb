---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Alocação de custos compartilhados - UI do Container Insights"
breadcrumb:
  - "Cloudability Premium"
  - "Insights"
  - "Alocação de custos de contêineres"
source_path: "product/shared-cost-allocation-container-insights-ui.html"
images:
  - "images/container_cost_allocation.jpg"
  - "images/namespace.jpg"
  - "images/shared_rules.jpg"
  - "images/shared_rules1.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Alocação de custos compartilhados - UI do Container Insights

Estamos introduzindo um novo recurso de alocação de custos de contêineres que transforma a forma como as despesas de infraestrutura compartilhada são rastreadas em ambientes Kubernetes. Esse recurso permite que os clientes anotem e aloquem custos de infraestrutura compartilhada, como proxies de sistema, ferramentas de monitoramento e outros recursos operacionais, para proprietários de aplicativos ou centros de custo específicos.

Anteriormente, esses custos de infraestrutura compartilhada eram indistintamente relatados como despesas de carga de trabalho padrão. Agora, as organizações podem marcar e distribuir com precisão esses custos operacionais, fornecendo às equipes de aplicativos e aos gerentes financeiros uma visão mais transparente e granular do verdadeiro gasto total com infraestrutura.

Para começar, esse recurso suporta a alocação de custos compartilhados no nível do namespace Kubernetes. No futuro, procuraremos expandir o suporte para outros construtos do Kubernetes.

## Ferramentas Importantes

Identificação automatizada de custos compartilhados

- Reconhece automaticamente os custos de infraestrutura compartilhada de namespaces predefinidos:

  - `kube-system`
  - `Cloudability`

- Aplicado de forma consistente em todos os grupos

Controles administrativos flexíveis

- Cloudability os administradores podem:

  - Definir regras de custo de infraestrutura compartilhada para namespaces aplicáveis
  - Configurar alocações de custos em nível de organização ou específicas do cluster
  - Direcionar com precisão as cargas de trabalho relacionadas à infraestrutura (namespaces) e a data efetiva de aplicação das regras

Novas métricas de custo

- Novas métricas de custo foram introduzidas na interface do usuário do Container Insights para fornecer visibilidade dos custos compartilhados alocados, incluindo o custo compartilhado, bem como os recursos específicos de rede compartilhada, memória compartilhada, CPU compartilhada, GPU compartilhada e outros. Essa métrica de custo compartilhado reflete o custo total, incluindo os custos compartilhados alocados, depois que as regras compartilhadas são aplicadas.

Nota:

Os custos compartilhados só serão calculados a partir da data de lançamento do recurso. As consultas que incluam datas anteriores à data de lançamento retornarão resultados vazios na coluna “*Custo compartilhado* ”.

Como configurar as regras de gerenciamento de compartilhamento

Para configurar a alocação de custos compartilhados, use Manage Share Rules na interface Container Insights para definir como os custos compartilhados devem ser distribuídos entre os namespaces Kubernetes.

1. Navegue até a UI de alocação de custos de contêineres.
2. Localize o menu de reticências (...) no canto superior direito, ao lado do botão Provision Clusters.
3. Clique nas reticências para abrir um menu suspenso.
4. No menu suspenso, selecione Manage Share Rules (Gerenciar regras de compartilhamento ). ![captura de tela da alocação de custos do contêiner](../../../../03-media/cloudability-premium/images/container_cost_allocation.jpg)
5. Configurar regras e fornecer a data de vigência.![captura de tela de regras compartilhadas](../../../../03-media/cloudability-premium/images/shared_rules.jpg)![captura de tela de regras compartilhadas](../../../../03-media/cloudability-premium/images/shared_rules1.jpg)
6. Selecione All Clusters (Todos os clusters ) para configuração em nível de organização ou escolha um cluster específico no menu suspenso para configuração em nível de cluster. Em seguida, especifique os valores do namespace para alocar os custos compartilhados.
7. Salve as alterações.

A métrica de custo compartilhado oferece maior visibilidade dos custos totais dos namespaces Kubernetes, incluindo os custos compartilhados alocados. Depois que as regras de custo compartilhado são aplicadas, a coluna Custo compartilhado reflete o custo combinado, distribuindo os recursos compartilhados proporcionalmente entre os namespaces selecionados.

Esse recurso garante maior precisão na alocação de custos para processos de showback e chargeback, ajudando-o a contabilizar a infraestrutura compartilhada e o uso de recursos de forma eficaz.

![captura de tela de clusters compartilhados](../../../../03-media/cloudability-premium/images/namespace.jpg)

## Conscientização do cliente: Comportamentos conhecidos e esclarecimentos

Para garantir uma experiência tranquila, observe o seguinte:

- Somente regras com data futura
  - As regras para alocação de custos compartilhados só podem ser criadas, atualizadas ou excluídas para datas futuras (em UTC).
  - As alterações não serão aplicadas retroativamente aos dados históricos.

- Datas de vigência para atualizações e exclusões de regras
  - As atualizações ou exclusões de regras não entram em vigor imediatamente.
  - Em vez disso, uma nova regra agendada com o valor atualizado ou vazio será criada, entrando em vigor na data agendada.

- Relação de união para várias regras
  - Quando várias regras são aplicadas, elas funcionam como uma união.
  - Exemplo: Se uma regra All Clusters incluir os namespaces A e B, e uma regra para *o cluster-foo* incluir o namespace C, então todos os três namespaces (A, B, C) serão tratados como custos compartilhados para *o cluster-foo*.

- Custo compartilhado zerado antes da data de lançamento do recurso
  - Se uma consulta incluir datas anteriores à data de lançamento, a coluna “Custo compartilhado” ficará vazia, pois os custos compartilhados não são calculados retroativamente.
- Espaço de nomes compartilhado que reflete um valor de custo compartilhado diferente de zero
  - Se você estiver observando um custo compartilhado diferente de zero para um determinado namespace compartilhado, como `kube-system`, é provável que isso se deva ao fato de o namespace existir em um nó que não possui nenhuma carga de trabalho de aplicativo não compartilhada (namespaces). Isso fará com que o custo de repartição justa seja refletido como o custo compartilhado para este namespace, uma vez que não há cargas de trabalho “normais” com as quais dividir o custo no nó.

**Tópico pai:** [Alocação de custos de contêineres](../product/k8s-cost-allocation.html)
