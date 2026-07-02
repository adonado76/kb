---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "VM ponderações baseadas na família"
breadcrumb:
  - "Cloudability Premium"
  - "Insights"
  - "Alocação de custos de contêineres"
source_path: "product/instance-type-weighting-container-cost.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# VM ponderações baseadas na família

O que é ponderação de recursos?

Embora seja relativamente simples calcular o custo de cada cluster do K8s — por meio do mapeamento das VMs e dos discos subjacentes —, é necessário um trabalho adicional para dividir cada VM /disco, de modo que possam ser alocados (não há informações nos arquivos de faturamento do fornecedor que ajudem nessa tarefa). Identificação de quais recursos (CPU, memória, rede etc.) estão sendo consumidos em Namespaces ou rótulos, é fundamental poder vincular uma contribuição de custo a esses recursos. É nesse ponto que entra a ponderação de recursos.

Quando falamos em “peso da CPU” ou “peso da memória”, estamos nos referindo à porcentagem do custo total do nó (ou seja, VM ) que deve ser atribuída ao uso da CPU ou da memória. Quando lançamos pela primeira vez nossa funcionalidade de alocação de custos de contêineres, ela se baseava em ponderações padrão aplicadas a todos os tipos de contêineres ( VM ). Embora isso tenha funcionado bem, ficou claro que a grande variedade de tipos de nós em uso exigiu uma abordagem mais diferenciada.

Novas ponderações baseadas na família do programa “ VM ”

VM O sistema de ponderação que melhor se adequar à forma como cada um dos fornecedores relaciona o custo com a CPU, a memória, o disco e a rede — isso pode ser determinado comparando-se os preços e a quantidade de cada recurso entre as duas famílias. Veja como fazer isso começando com o disco e a rede.

Disco e rede

Para as famílias d VM s que não dispõem de armazenamento local, a situação é simples: a contribuição para os custos é de 0%. Para as famílias que têm armazenamento local, calculamos o impacto desse armazenamento. Por exemplo, ao analisar AWS EC2, os tipos m5.xlarge, m5d.xlarge e VM têm exatamente o mesmo vCPU e memória, sendo que apenas m5d possui armazenamento local. Considerando que o serviço m5.xlarge custa US$ 0.192 por hora e o m5d.xlarge US$ 0.226 por hora, essa taxa adicional de US$ 0,034 por armazenamento representa 15% do custo total do m5d.xlarge.

No que diz respeito às taxas de rede, uma vez que não se trata de um elemento específico d VM e e normalmente representa um fator de menor importância, atribuímos um custo padrão de 5% a todos os tipos de VM. O restante do custo do VM é, portanto, dividido entre a memória e a CPU, o que, no caso de m5.xlarge, representaria 95%, e no caso de m5d.xlarge, 80%.

Memória e CPU

Para dividir esse custo restante, podemos fazer uma comparação semelhante — embora mais complexa — entre as famílias d VM s, a fim de calcular o custo por vCPU e por GB de memória. Para qualquer VM,

VM taxa por hora = contagem de vCPU s \* taxa de vCPU s + memória \* taxa de memória

Se conseguirmos calcular a taxa de vCPU o e a taxa de memória, será possível estabelecer a proporção (ou seja, as ponderações) para qualquer família de VM. Embora haja duas variáveis desconhecidas (as taxas), podemos resolvê-las utilizando duas equações distintas – uma para a família de alvos VM e outra para a família “base” VM.

Vale a pena discutir brevemente como é escolhida uma família de VM s de base. A primeira coisa a se notar é que a placa-mãe VM será do mesmo fabricante do processador, seja ele AMD, Intel ou Graviton. Também daremos prioridade a uma família de “ VM ” da mesma geração. Por exemplo, se o endereço de destino for c6i, a família de domínios VM utilizada provavelmente será m6i ou r6i.

Depois de determinar a taxa de processamento da CPU ( vCPU ) e a taxa de memória para cada família de processadores ( VM ), é simples calcular as ponderações: basta multiplicar a quantidade de processamento da CPU ( vCPU ) e de memória pelas respectivas taxas e, em seguida, estabelecer a relação entre o custo da CPU e o custo da memória. Observe que, devido à forma como os fornecedores faturam suas VMs, essas proporções são consistentes no nível da família.

O que isso significa para sua alocação de custos?

- Os valores de custo em nível de cluster não são afetados. Essa alteração se aplica apenas a Namespaces e Labels.
- As ponderações padrão usadas anteriormente inclinavam a alocação para o uso da memória. Com esta versão, a avaliação depende agora inteiramente da forma como o fornecedor cobra pela família específica de produtos “ VM ”, mas, de modo geral, isso fez com que o peso da avaliação voltasse a recair sobre o uso da CPU.
- Essa alteração foi feita nos valores encontrados no recurso de alocação de custos de contêineres e nas dimensões de espaço de nome e rótulo nos relatórios principais.
- Esse aprimoramento se aplica aos clusters Kubernetes e ROSA

**Tópico principal:** [Alocação de custos de contêineres](../product/k8s-cost-allocation.html)
