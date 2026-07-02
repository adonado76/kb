---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Mapeamento de tags e rótulos"
breadcrumb:
  - "Cloudability Premium"
  - "Configuração"
  - "Organize seus gastos com a nuvem"
source_path: "admin/map-tags.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Mapeamento de tags e rótulos

Cloudability permite uma alocação abrangente de custos por meio da importação e normalização de tags e rótulos de provedores de nuvem compatíveis, plataformas de SaaS e e ambientes de contêineres. Este documento descreve os tipos de tags e rótulos suportados por cada fornecedor, como são coletados (dados de faturamento versus APIs), as permissões necessárias e considerações importantes, como diferenças de formatação, regras de precedência e limitações conhecidas

## Suporte a tags e etiquetas por fornecedor

AWS Tags

Cloudability suporta os tipos de tags mencionados a seguir para o AWS

- **Tags de nível de recurso**

  Esses arquivos fazem parte dos arquivos CUR do AWS e não são necessárias permissões adicionais no Cloudability para ativá-los
- **Tags no nível da conta** (por meio da API)

  Para obter tags no nível da conta de organizações do AWS, o Cloudability precisa de uma permissão adicional chamada “ **organizations:ListTagsForResource** ”. Observação: as tags no nível da conta não estão disponíveis no momento no Cloudability Gov.

  Elas são exibidas no seguinte formato no site Cloudability :

  `cldy:aws:accountLevelTag:<tag
  key>`

Observação: Se um cliente migrar do CUR antigo para o CUR 2.0, ele deverá reconfigurar suas tags e etiquetas no site Cloudability.

Diferença entre as tags CUR e CUR 2.0 do AWS :

Formato das tags CUR antigas:

- AWS tags = `aws:<tag key>` por exemplo, `aws:autoscaling:groupname`
- tags do usuário = `<tag key>`

Formato das tags CUR 2.0 :

- AWS tags= `aws_<tag key>` serão separadas por um sublinhado = por exemplo: `aws_autoscaling_group_name`
- tags do usuário = `user_<tag key>` por exemplo: `user_application`

Azure Tags

Cloudability suporta os tipos de tags a seguir para o Azure :

- **Tags de nível de recurso**
  - Esses arquivos fazem parte dos arquivos de exportação do Azure e não são necessárias permissões adicionais no Cloudability para ativá-los
  - Formato das tags - `cldy:Azure:ResourceTag:<resource tag key>`
- **Tags de grupos de recursos** (via API)
  - Para obter as tags do grupo de recursos em Azure, o Cloudability precisa de permissões adicionais para credenciais avançadas, seja **“management:Reader”** ou “ **Microsoft.Resources/subscriptions/resourceGroups/read** ” na assinatura.
  - Formato das tags - `cldy:Azure:ResourceGroupTag:<resource group tag key>`

  Importante:

  Se uma chave de tag existir em um recurso tanto no nível do recurso quanto no nível do grupo de recursos, e você mapear a **chave de tag simples** a partir do menu suspenso (por exemplo, `project`), o Cloudability resolverá o valor da seguinte forma:

  - A tag no nível do recurso é utilizada quando estiver presente.
  - Se a tag no nível do recurso estiver ausente ou for nula, a tag do grupo de recursos será usada como alternativa.

  Se você não quiser que a tag do grupo de recursos seja usada como alternativa, mapeie a **tag explícita no nível do recurso** (por exemplo, `cldy:Azure:ResourceTag:project`).
- **Tags de nível de assinatura** (via API)
  - Para obter tags de nível de assinatura do Azure, o Cloudability precisa de uma permissão adicional: **subscription:ReadSubscription**
  - Formato das tags - `cldy:Azure:SubscriptionLevelTag:<subscription tag key>`

GCP Tags e etiquetas

Cloudability suporta os tipos de tags e rótulos mencionados a seguir para o GCP :

- **GCP Etiquetas**

  Esses dados fazem parte da extração de dados de faturamento do GCP e não são necessárias permissões adicionais no Cloudability para ativá-los. Cloudability suporta os rótulos a seguir:

  - Etiquetas de recursos
  - Etiquetas do projeto
  - Rótulos do sistema

  Se a mesma chave estiver configurada para os rótulos de projeto, sistema e recurso, a ordem de prioridade para exibir o rótulo na interface do usuário d Cloudability é a seguinte: **Recurso** > **Projeto** > **Sistema**

  Observação: O Cloudability não oferece suporte ao mapeamento de rótulos resultantes do recurso “alocação de custos GKE ” disponível em GCP. Etiquetas como `goog-k8s-*` ou `k8s-*` resultarão em valores (não definidos). Para aproveitar os benefícios da alocação de custos de contêineres, os clusters devem ser provisionados para uso no recurso “ *Cloudability* ” (Contêineres), que permite a alocação de custos no nível de namespace e de rótulo.
- **GCP Tags**

  Esses dados fazem parte da extração de dados de faturamento do GCP e não são necessárias permissões adicionais no Cloudability para ativá-los

  Formato das tags ` GCP ` compatíveis com o ` Cloudability `:

  `cldy:gcp:tag:<tagKey>` para atribuições diretas de tags

  `cldy:gcp:tag:<tagKey>:inherited` para tags herdadas

  `cldy:gcp:tag:<tagKey>:namespace` para o nível de anexação da tag

Tags OCI

- **Etiquetas no nível de recurso e de compartimento**
  - Nível de recurso ou nível de compartimento atribuído por namespace. Esses dados fazem parte dos dados de faturamento da OCI e não são necessárias permissões adicionais no Cloudability para habilitá-los
  - As tags no nível do compartimento devem ser atribuídas primeiro por meio de um espaço de nomes de tags e, em seguida, definidas como padrão de tag no OCI

Observação: Mapeamos os campos de faturamento da OCI — *nome do* compartimento e *ID do compartimento —* para chaves de tag denominadas `cldy:oci:compartmentname` e `cldy:oci:compartmentid`

IBM Tags

- **Tags de nível de recurso**
  - Esses dados fazem parte dos dados de faturamento do IBM e não são necessárias permissões adicionais no Cloudability para ativá-los

Tags do Databricks

- **Tags personalizadas no nível do recurso**

  Esses dados fazem parte dos dados de faturamento do Databricks e não são necessárias permissões adicionais no Cloudability para habilitá-los

Observação: Nós transmitimos os metadados de uso do Databricks, os metadados de identidade e os recursos do produto como tags. *WorkspaceId* ficará visível como uma chave de tag em `cldy:databricks:workspaceid`

MongoDB Tags

- **Tags de nível de recurso**
  - Esses dados fazem parte dos dados de fatura do MongoDB e não são necessárias permissões adicionais no Cloudability para ativá-los

Observação: Mapeamos os campos de cobrança “ MongoDB ” ( *ID do* grupo e *Nome do grupo*) para chaves de tag denominadas `cldy:mongodb:groupid` e `cldy:mongodb:groupname`

Snowflake Tags

Oferecemos suporte às tags de nível de armazém e de conta d Snowflake, no formato abaixo. Esteja ciente de que há requisitos específicos para o preenchimento das etiquetas de armazém, incluindo a ativação da visualização TAG\_REFERENCES no Snowflake. Consulte a documentação de credenciamento para obter mais detalhes.

`cldy:snowflake:account:<tagkey>`

`cldy:snowflake:warehouse:<tagkey>`

Kubernetes ( K8s ) Etiquetas para recipientes

Diferentemente das etiquetas típicas de alocação de custos de fornecedores, as etiquetas “ Kubernetes ” também são compatíveis com o recurso “Mapeamento de Etiquetas e Rótulos”. Essas etiquetas são fundamentalmente diferentes das etiquetas de custo, pois não constam nos dados de faturamento; em vez disso, são resultado do recurso Container Insights do Cloudability, que oferece alocação granular de custos para seus gastos com contêineres compatíveis (EKS, GKE, AKS, OpenShift ).

Essas etiquetas estarão disponíveis para mapeamento assim que você provisionar um cluster compatível com o agente IBM FinOps. Para obter mais informações, consulte “Definir dimensões adicionais com base em rótulos d K8s ” na seção [Alocação de custos de contêiner](../product/k8s-cost-allocation.html).

## Perguntas Frequentes

Por que as tags de nível de recurso AWS não aparecem na página “Mapeamento de tags e rótulos”?

Antes do mapeamento, você deve indicar ao AWS quais tags devem ser incluídas nas exportações de dados de custos. Você pode fazer isso nas Preferências de cobrança do AWS. Apenas as chaves de tag selecionadas aparecerão no CUR.

Por que vejo um valor de tag (não definido) nos relatórios?

Se você já criou um relatório no Cloudability com uma coluna de tag, provavelmente já viu um valor chamado **(não definido)**.

Isso pode significar uma das seguintes coisas:

- Você não solicitou ao fornecedor (como AWS ) que incluísse todas as suas tags nos dados de cobrança
- Você tem recursos que podem ser marcados, mas que ainda não foram marcados
- Você tem despesas que não podem ser categorizadas
- Você não solicitou o reprocessamento dos dados históricos

Como posso saber quais recursos podem ser marcados?

Cada fornecedor tem suas próprias definições e restrições sobre o que considera um “recurso marcável”. Cloudability oferece o recurso *Tag Explorer* para ajudá-lo a obter transparência sobre seus principais gastos que podem ou não ser marcados, o que pode ajudá-lo a entender onde concentrar seus esforços de marcação.

Em caso de dúvida, é melhor consultar a documentação específica do fornecedor para saber se um determinado tipo de uso pode ser marcado. Exemplos comuns de despesas que não podem ser categorizadas são: custos de suporte, taxas de compromisso, impostos, instantâneos do EBS e algumas taxas de marketplace.

Por que as tags do meu grupo de recursos do Azure não estão aparecendo?

Para preencher as tags no nível do grupo de recursos e da assinatura para o Azure, precisamos de permissões adicionais para obtê-las da API Azure (conhecidas como “credenciais avançadas” em Cloudability ). Consulte a parte anterior deste documento para verificar as permissões necessárias.

É possível mapear várias chaves de tag para uma única dimensão de tag no Cloudability utilizando uma ferramenta como expressões regulares ou caracteres curinga?

Atualmente, o Cloudability não permite mapear várias chaves de tag para uma única dimensão usando expressões regulares ou caracteres curinga.

Como o ` Cloudability ` lida com várias chaves de tag?

Se um mesmo recurso tiver várias chaves de tag, o ` Cloudability ` selecionará a primeira chave de tag válida (aquela com um valor) que foi adicionada à lista de chaves de tag para a dimensão em questão.

Como posso extrair um valor de uma tag?

No ` Cloudability `, existem algumas maneiras de obter o valor de uma tag:

1. Como usar o Tag Explorer: Acesse Insights > Tag Explorer e, na guia “*Taggable Spend* ”, aplique um filtro para a dimensão “Tags & Labels”. No gráfico, você pode passar o mouse sobre as diferentes tags para visualizar seus valores.
2. Como usar relatórios: É possível gerar um relatório incluindo uma dimensão específica *de “Tag” (Valor)* no relatório. O resultado exibirá todos os diferentes valores de tag para as diferentes chaves de tag.

Qual é o limite de tags que podem ser mapeadas em “tags” e “labels”?

No Cloudability, o limite atual para o número de tags e rótulos é de 50.

É possível adicionar mais de 30 mapeamentos de tags e rótulos?

Cloudability aumentou em 20 o número de mapeamentos disponíveis de “Tags & Label” no Cloudability. Isso significa que os clientes agora podem ter até 50 dimensões de relatório na plataforma específicas para tags e rótulos mapeados. Isso será especialmente útil para clientes que utilizam uma infraestrutura multicloud e possuem muitas chaves de tags ou rótulos em seu ambiente. Cloudability Os administradores podem adicionar esses mapeamentos adicionais no recurso de mapeamento “Tags e rótulos”.

Se o valor de uma tag for alterado nos dados brutos do CSP, como ele aparecerá no site Cloudability?

Suponha que você tenha alterado a tag no lado do CSP de “playground” para “game”. O valor antigo da tag já foi registrado nos dados de faturamento anteriores, e qualquer alteração nesse valor não teria efeito retroativo. Portanto, quaisquer novos dados de cobrança associados refletirão o novo valor da tag. Você deve aproveitar os mapeamentos de negócios, que podem ser aplicados a dados históricos.

Não é possível atualizar tags históricas, a menos que você envie novos arquivos de faturamento referentes a meses anteriores com o novo valor da tag. Se você quiser dar continuidade a isso, abra um ticket de suporte e Apptio. A equipe de suporte pode acionar uma nova obtenção dos dados atualizados. **Esteja ciente de que**, quando os dados forem recarregados, todos os dados anteriores serão substituídos pelos valores atuais. Portanto, no caso de tags hierárquicas (nível de conta/assinatura), ` Cloudability ` irá considerar o valor **atual** dessas tags e aplicá-lo a todos os dados recarregados.

Como o Cloudability processará as tags se um mesmo recurso tiver várias categorias de tags atribuídas a ele, ou seja, tag de recurso, tag de grupo de recursos e tag no nível da conta?

Se um cliente tiver 3 recursos, a saber: Recurso A, Recurso B e Recurso C.

- O recurso A possui uma tag de recurso chamada **“Owner”,** cujo valor é “ **R1** ”
- O recurso B possui uma tag de recurso chamada **“Owner”,** cujo valor é “ **R2** ”
- O recurso C não tem nenhuma tag atribuída

Esses três recursos pertencem a um grupo de recursos chamado **“Recurso X”,** que possui uma tag de grupo de recursos chamada **“Proprietário”** com o valor = **RG1**

**O recurso X** pertence a uma assinatura do Azure, chamada **Assinatura Z,** que possui uma tag de nível de assinatura chamada **“Owner”** com o valor = **S1**

No Cloudability, o cliente cria uma nova dimensão de tag chamada **“CLDY Owner”** e mapeia as chaves de tag acima na sequência indicada a seguir:

cldy:azure:resourcetag:proprietário | cldy:azure:subscriptionleveltag:proprietário | cldy:azure:resourcegrouptag:proprietário

O Recurso A possui todas as três tags (tag de recurso, tag de grupo de recursos e tag de assinatura), mas, como a tag de recurso é a primeira na sequência de acordo com a dimensão criada acima (CLDY Owner), ela será selecionada primeiro para o Recurso A, com a chave de tag “Owner” e o valor = “ R1 ”, enquanto a tag de grupo de recursos e a tag de assinatura serão ignoradas. O mesmo ocorrerá com o Recurso B, onde a tag do recurso será selecionada com a chave “tag” = “Owner” e o valor = “ R2 ”. No caso do Recurso C, como não há nenhuma tag de recurso associada a ele, o sistema verificará qual é o próximo item na sequência da dimensão criada. Como a próxima é a tag do grupo de recursos, a tag do grupo de recursos com chave = Owner e valor = RG1 será atribuída ao Recurso C.

Agora, digamos que o cliente tenha criado a dimensão de tag em uma ordem diferente, como mostrado abaixo, em que as tags do grupo de recursos vêm primeiro:

cldy:azure:resourcegrouptag:owner | cldy:azure:resourcetag:owner | cldy:azure:subscriptionleveltag:owner

Nesse caso, a tag do grupo de recursos será atribuída a todos os três recursos, pois todos eles possuem tags de grupo de recursos (chave da tag = Owner e valor = RG1 ). As tags de recurso e as tags de assinatura serão ignoradas aqui, pois as tags de grupo de recursos vêm primeiro na sequência e todos os três recursos têm tags de grupo de recursos associadas a eles.

Da mesma forma, se a tag de nível de assinatura for a primeira adicionada na sequência, a tag de assinatura com chave de tag = Owner e valor = S1 será atribuída à dimensão de tag, e as tags de grupo de recursos e de recursos serão ignoradas.

**Tópico principal:** [Organize seus gastos com nuvem](../admin/tag-data.html)
