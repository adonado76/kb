---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Custos não alocados"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Arquitetura do modelo"
source_path: "studio/new-uc/concepts-architecture/model-architecture/unallocated-costs.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Custos não alocados

Os custos não alocados são um dos conceitos mais importantes a serem compreendidos na modelagem de custos. Esses custos representam despesas que foram inseridas no mecanismo de alocação, mas não encontraram um destino correspondente — dinheiro que “ficou de fora” do seu modelo.

## O que são custos não alocados?

Quando uma alocação é executada, ela tenta distribuir cada dólar da fonte para um ou mais destinos. Se o driver ou a lógica de correspondência não conseguir encontrar um destino para alguma parte dos custos de origem, esses custos permanecerão não alocados. Elas permanecem no objeto de origem, em vez de seguirem adiante.

Os custos não alocados não são um erro no sentido tradicional — são um sinal. Eles dizem que as regras do seu modelo não explicam totalmente todos os seus dados. Em um modelo bem ajustado, os custos não alocados devem ser mínimos.

## Causas comuns

|  |  |  |
| --- | --- | --- |
| **Causa** | **Exemplo** | **Resolução** |
| Dados do motorista ausentes | A tabela de contagem de ETI não inclui uma unidade de negócios recém-criada; portanto, os custos destinados a essa unidade não têm peso para serem distribuídos | Atualize a tabela de drivers para incluir a entidade que está faltando |
| Valores de dimensão incompatíveis | Os dados de origem utilizam o código de fornecedor “AWS-001”, mas a tabela de destino utiliza “ Amazon Web Services ” como chave de correspondência | Padronizar os valores das dimensões por meio de mapeamentos de transformação |
| Tabelas de mapeamento incompletas | Faltam 15 aplicativos que foram adicionados recentemente na tabela de mapeamento que relaciona os aplicativos às unidades de negócios | Adicione os mapeamentos que faltam à tabela de mapeamento |
| Problemas relacionados à qualidade dos dados | Uma coluna de ponderação contém valores nulos ou não numéricos em algumas linhas, o que faz com que elas sejam excluídas da alocação | Limpar os dados de ponderação em Data Studio |
| Novas categorias ainda não modeladas | Aparece um novo tipo de despesa nos dados do Razão que não corresponde a nenhuma regra de alocação existente | Adicionar uma nova regra de alocação ou mapeamento de categorias |

## Estratégias de gestão

**Estratégia 1: Investigar e resolver**

A melhor abordagem é considerar os custos não alocados como um indicador da qualidade dos dados e resolver a causa raiz. Use a visualização de alocação no Modelador de Objeto Único para identificar quais linhas permanecem sem alocação e, em seguida, analise o problema para determinar o motivo.

**Passos:**

1. Abra o objeto do modelo no Modelador de Objeto Único
2. Analise a pré-visualização da alocação para identificar as linhas não alocadas
3. Verifique se há lacunas nos dados do driver e na lógica de correspondência
4. Atualize as tabelas de transformação ou os dados de mapeamento conforme necessário
5. Execute novamente a compilação e verifique se os valores não alocados diminuíram

**Estratégia 2: Reservatórios residuais**

Quando alguns custos não podem ser atribuídos de forma significativa a um destino específico, é possível criar um pool residual — um objeto de modelo genérico que reúne os custos não alocados para fins de visibilidade e análise posterior.

- **Quando usar:** Quando você tem uma pequena porcentagem de custos que não se encaixam em nenhuma categoria e deseja torná-los visíveis nos relatórios, em vez de deixá-los ocultos.
- **Atenção:** uma grande quantidade de resíduos é um sinal de alerta. Se mais de 5 a 10% dos seus custos forem classificados como “residuais”, é provável que seu modelo precise de revisão.

**Estratégia 3: Distribuição uniforme dos resíduos**

Como último recurso, você pode distribuir os custos não alocados igualmente entre todos os destinos. Isso garante que seu modelo esteja “equilibrado” (o total da origem é igual ao total do destino), mas sacrifica a precisão da alocação.

- **Prós:** Equilíbrio geral do modelo; sem custos ocultos
- **Contras:** Reduz a precisão; atribui custos a entidades que podem não os ter incorrido

Nota:

**Monitorar continuamente os custos não alocados**

Após cada compilação, verifique os custos não alocados. Um modelo que estava perfeitamente equilibrado no mês passado pode apresentar novos valores não alocados neste mês devido a alterações nos dados. Crie o hábito de verificar os valores não alocados como parte do seu processo de fechamento mensal.
