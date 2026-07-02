---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Alocação de custos de contêineres"
breadcrumb:
  - "Cloudability Premium"
  - "Insights"
source_path: "product/k8s-cost-allocation.html"
images:
  - "images/k83_cost_allocation-1.jpg"
  - "images/k83_cost_allocation-2.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Alocação de custos de contêineres

Você pode integrar os dados de contêineres Kubernetes ( k8s ) ou OpenShift ( ROSA ) em Cloudability para obter visibilidade da parte de seus gastos com a nuvem devido aos custos de contêineres e para garantir que sejam alocados adequadamente.

Visualizar os dados de custo e uso do contêiner

Você pode visualizar os dados de Kubernetes ou OpenShift na página Containers ou em Cloudability em ferramentas como Reports, TrueCost Explorer e Tag Explorer.

Para obter uma visão holística dos dados de custo e utilização de seu contêiner, use a página Contêineres.

Para investigar os custos do contêiner em relação ao gasto total com a nuvem, use os relatórios, o TrueCost Explorer e o Tag Explorer.

Analisar os dados do contêiner usando relatórios e outras ferramentas

Os custos de contêineres podem ser visualizados juntamente com outros custos de nuvem em um único relatório. Usando rótulos de kubernetes e mapeamentos de negócios, é possível combinar custos fora do cluster (por exemplo, balanceadores de carga e bancos de dados, entre outros) com custos de contêineres em um único relatório.

Para ver cada dimensão aparecer como um item de linha em seu relatório (sujeito a filtragem), selecione essa dimensão como uma dimensão de custo.

Existem duas dimensões integradas para relatórios de custos:

- Nome do cluster
- Namespace:

Você pode usar essas dimensões para criar novos relatórios de custos ou aprimorar os relatórios de custos existentes.

![captura de tela do relatório de custos](../../../../03-media/cloudability-premium/images/k83_cost_allocation-1.jpg)

Use a dimensão Nome do cluster

Para ver cada nome de cluster Kubernetes ( k8s ) ou OpenShift aparecer como um item de linha em seu relatório (sujeito a filtragem), selecione Cluster Name como uma dimensão de custo. A métrica Custo (Total) representa o custo total atribuído a esse cluster, incluindo recursos ociosos, custos utilizados e ociosos dos nós de computação subjacentes e, em AWS, volumes de armazenamento EBS.

Haverá também um valor (não definido) para Cluster Name (Nome do cluster), representando todos os custos da conta que não fazem parte de nenhum cluster k8s ou OpenShift. Também está disponível o suporte a métricas de custo adicionais, como custo (amortizado), custo (ajustado) e custo (amortizado ajustado).

Usar a dimensão Namespace

Para ver cada namespace exclusivo aparecer como um item de linha em seu relatório (sujeito a filtragem), selecione Namespace como uma dimensão de custo. A métrica Custo (Total) representa os custos k8s atribuídos a esse namespace. Também está disponível o suporte a métricas de custo adicionais, como custo (amortizado), custo (ajustado) e custo (amortizado ajustado).

:NONE.

- Quando você inclui o Namespace como uma dimensão em um relatório, os custos que representam os recursos alocados, mas não utilizados em um cluster, aparecem como um item de linha separado rotulado como "RECURSOS OCIOSOS" por padrão. Para dividir ou compartilhar de forma justa esses recursos ociosos em cada namespace e para ver detalhes mais detalhados sobre os custos ociosos e alocados na análise principal do site Cloudability (relatórios e painéis), use a categoria de métrica "Containers", que apresenta seis métricas adicionais.
- Ao adicionar outras dimensões a um relatório, como Usage Family (Família de uso) ou Service Name (Nome do serviço), você verá detalhes adicionais de custo em torno de cada nome de cluster ou namespace (sujeito a filtragem).

Para ver apenas os recursos e custos associados a um namespace ou nome de cluster específico, use a função de filtro integrada.

Para ver detalhes mais detalhados sobre os custos ociosos e alocados na análise principal do site Cloudability (relatórios e painéis) no cluster, dimensão Namespace, use a categoria de métrica "Containers", que apresenta seis métricas adicionais. Essas métricas permitem que os usuários visualizem separadamente os custos utilizados, ociosos e de fairshare em uma base de caixa ou amortizada. Para clientes com preços personalizados ativados, essas métricas serão representadas como métricas "ajustadas".

O recurso de alocação de custos de contêineres avalia a utilização de recursos em cada nó e correlaciona isso com os dados de faturamento para calcular o custo de cada cluster. Ele associa um "custo utilizado" direto a Kubernetes namespace e valores de rótulo. Isso está disponível nos relatórios principais usando o namespace ou uma dimensão de rótulo. Com esse aprimoramento, você também pode informar sobre o custo de ociosidade por meio da nova métrica, que é alocada aos valores de namespace e rótulo proporcionalmente com base na contribuição de custo direto de cada nó. O custo do Fairshare é a combinação do custo utilizado e do custo ocioso, representando o custo total.

Considerações e ideias de relatórios para essas novas métricas:

- Para custos sem contêineres, essas métricas retornarão como US$ 0. Para filtrar os dados somente do contêiner, tente um filtro como "Cluster Name not equals (not set)"
- Use essas métricas com diferentes dimensões para visualizar facilmente os custos utilizados e ociosos. Por exemplo, listar por nome do cluster ou ID do recurso.
- Pela primeira vez, você pode usar as bases de custos amortizados e de caixa juntas para obter relatórios detalhados de custos de contêineres.

Definir dimensões adicionais com base nos rótulos do site K8s

Muitas organizações utilizam rótulos em suas implementações no site k8s de forma semelhante à utilização de tags de recursos em seus ambientes de nuvem. Para ver esses pares de chave/valor de rótulo aparecerem no ambiente Cloudability, você pode mapear essas chaves de rótulo em dimensões da mesma forma que as tags de recursos são mapeadas. Usando a página Tag & Label Mapping, você pode definir novas dimensões (e editar as existentes) e atribuir tags de recursos ou rótulos k8s a cada dimensão.

![captura de tela do mapeamento de etiquetas e rótulos](../../../../03-media/cloudability-premium/images/k83_cost_allocation-2.jpg)

Se você optar por mapear os rótulos k8s e as tags de recursos na mesma dimensão, há alguns itens importantes a serem observados.

- K8s Os rótulos só devem ser mapeados para dimensões com tags de recursos quando os valores dos rótulos e das tags forem homogêneos. Da mesma forma que o mapeamento de tags de recursos não relacionados na mesma dimensão pode causar confusão, o mapeamento de rótulos e tags de recursos não relacionados na mesma dimensão só aumentará essa confusão.
- Caso uma tag de recurso e o rótulo k8s (ambos mapeados para a mesma dimensão) tenham valores diferentes, o valor do rótulo k8s será selecionado e usado, e o valor da tag de recurso será descartado.

Você pode mapear até 20 chaves exclusivas de etiquetas k8s na página Tag & Label Mapping (Mapeamento de etiquetas e rótulos). Lembre-se de que, ao adicionar ou editar esses mapeamentos, você começará a ver os valores nos relatórios na próxima vez que ingerirmos um novo arquivo de faturamento do fornecedor. Atualizaremos o mapeamento de etiquetas ao longo deste mês.

Importante:

Em relatórios e painéis, um valor **(não definido)** para uma etiqueta do ` Kubernetes ` representa os custos incorridos quando o Pod, a Implantação ou outro objeto do ` Kubernetes ` não possuía um valor para essa etiqueta.

**(não definido)** também aparecerá nas partidas individuais de custo que foram importadas e processadas pelo Cloudability *antes que* o rótulo fosse mapeado para uma dimensão.

Cloudability Atualmente, não é possível preencher retroativamente as etiquetas de " Kubernetes "

Usar o Tag Explorer

Assim como em qualquer outro mapeamento de negócios, os mapeamentos que você define usando dimensões específicas do contêiner podem ser usados no Tag Explorer. Isso pode ajudar a entender os custos associados aos clusters e namespaces do site k8s.

Use o TrueCost Explorer

Assim como em qualquer outro mapeamento de negócios, os mapeamentos que você define usando dimensões específicas do contêiner podem ser usados no TrueCost Explorer. Isso pode ajudar a entender como os custos fluem pelos clusters e namespaces do site k8s.

Criar mapeamentos de negócios

Você pode criar um novo mapeamento de negócios (ou editar um existente) e usar dimensões específicas de contêineres. A inclusão dessas dimensões em um mapeamento é uma ferramenta poderosa que permite combinar diferentes custos em um único construto. Você pode reunir os custos do cluster k8s com outros custos fora do cluster para criar uma visão holística dos custos gerais de computação k8s.

Criar visualizações

Você pode criar uma nova visualização (ou editar uma existente) e usar um mapeamento criado a partir de dimensões específicas do contêiner. Observe que, na página Contêineres, não há suporte para o uso de visualizações baseadas em mapeamentos de negócios, independentemente de as dimensões específicas do contêiner serem usadas na definição da visualização.

Assim como em outras dimensões mapeadas a partir de tags de recursos, você pode usar dimensões com rótulos k8s em mapeamentos de negócios, visualizações, TrueCost Explorer, Tag Explorer e relatórios.

Nota:

Ao comparar a alocação de custos entre a página Contêineres e um relatório, você poderá ver diferenças. Embora o custo no nível do cluster k8s seja muito semelhante (dentro de uma fração de um por cento), os custos alocados a namespaces individuais podem ser diferentes.

Nota:

Nas contas AWS, os custos EBS são tratados de forma diferente. Na página Contêineres, os custos do EBS são alocados em cada namespace com base em sua proporção de uso de recursos. Em um relatório, entretanto, esses custos EBS são agrupados e deixados com o cluster. Portanto, você verá um intervalo (não definido) de custos de EBS com o cluster k8s.O mesmo se aplica a todos os recursos que não sejam de nós em Azure. Em um futuro próximo, alocaremos todos os recursos do cluster com base em seu uso.

- **[Analise os dados de seus contêineres Kubernetes](../product/analyze-data-for-your-containers.html)**
- **[Configurar seu agente de contêiner](../product/container-metrics-agent-provisioning.html)**
- **[Custos de contêineres alocados por fornecedor](../product/container-costs-by-vendor.html)**
- **[VM coeficientes de ponderação baseados na família](../product/instance-type-weighting-container-cost.html)**
- **[Insights sobre contêineres: Guia do painel e do widget](../product/containers-insight-2-dashboard-widget-guide.html)**
- **[Alocação de custos compartilhados - UI do Container Insights](../product/shared-cost-allocation-container-insights-ui.html)**
- **[Container Insights: Guia de configuração de alertas baseados em limites](../product/container-insights-threshold-based-alerting-configuration-guide.html)**
- **[Ferramenta do Observatório de Agentes](../product/agent-observatory-tool.html)**
- **[Cloudability Contêineres avançados](../product/advanced-containers.html)**
