---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Valores de tag em Azure para Apptio Schema"
breadcrumb: []
source_path: "cost-transparency/configuration/tagazuretoschema.html"
images:
  - "resources/images/ct_images/azure_ea.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Valores de tag em Azure para Apptio Schema

Este artigo o ajudará a marcar os valores em Azure de acordo com o esquema Apptio. Embora este artigo explique como analisar valores na coluna Tag da fatura de Azure para que ela possa fornecer informações de marcação relevantes em Apptio, observe que outras colunas em Azure, incluindo Account, Subscription, Cost Center e Department, podem ser mapeadas diretamente em Apptio. O objetivo deste artigo é fornecer orientação sobre como você pode mapear quaisquer colunas ou tags em Apptio a partir de Azure.

Aplica-se a: Apptio Costing Standard em TBM Studio 12.3.3 e posterior

## Analisar valores de tag em Azure

As tags de recursos estão disponíveis no arquivo de faturamento detalhado Azure disponível em seu portal EA e podem ser inseridas em Apptio via Datalink (Classic). Essas tags são codificadas como uma string em formato JSON na coluna Tags da fatura. A análise dos valores das tags em atributos utilizáveis requer algumas configurações adicionais em Apptio. Este documento o guiará pelas etapas necessárias para analisar os valores de tag desejados a partir da cadeia de caracteres formatada em JSON e em novas colunas no conjunto de dados Apptio.

Exemplo:

{ "Dept": "Engineering", "Function": "Product Development", "Environment": "Development", "CostCenter": "4739"}

As etapas descritas abaixo funcionarão para uma única tag e devem ser repetidas para cada tag que você deseja analisar na coluna Tags.

Observação: **Definições usadas nas etapas abaixo** - Cada tag é composta por uma estrutura comum chamada par chave-valor. Com relação às tags, pense na chave do par chave-valor como o nome da coluna e o valor como os dados armazenados nessa coluna. No exemplo incluído nas etapas abaixo, analisaremos os valores de uma tag Environment, em que a chave é igual a Environment e o valor são os dados associados à chave Environment.

## Resumo das tarefas

1. Abra TBM Studio em Apptio e verifique Azure EA Detailed Bill Raw.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/azure_ea.png)
2. Em Steps (Etapas), adicione uma etapa Formulas (Fórmulas).
3. Crie uma nova coluna chamada "Environment" (Ambiente).
4. Set Environment =IF(FIND("Environment", Tags)>0, split((RIGHT(Tags,LEN(Tags)-FIND("Environment", Tags)-(LEN("Environment")+2)),1,""""), "")
5. Para implementar isso para outras tags em seu ambiente Apptio, copie a fórmula da Etapa 2 acima e copie/substitua "Environment" pelo valor da chave da tag que você deseja analisar na coluna Tags.
6. Salve e registre as alterações quando todas as edições estiverem concluídas em seu espaço de trabalho.

Nota:

- A operação básica aqui é localizar a palavra "Environment" (Ambiente) e, a partir de dois caracteres após seu final, pegar tudo na coluna de tags até o próximo símbolo **"**. Observe que Apptio diferencia maiúsculas de minúsculas e, portanto, tanto o valor quanto as maiúsculas precisam corresponder.
- Apptio recomenda uma coluna por tag. Evite executar essa operação em várias colunas porque é mais difícil limpar e otimizar sua configuração no futuro e pode ter um impacto negativo no desempenho.

## Mapear as tags Azure para o esquema Apptio

Depois que as tags Azure forem analisadas na tabela Azure EA Detailed Bill Raw, essas colunas poderão ser usadas para mapear o esquema Apptio, mapeando-o no conjunto de dados mestre Azure EA Detailed Bill. Observe que você pode seguir as etapas abaixo para mapear também outras colunas do site Azure (Conta, Assinatura, Centro de Custo, Departamento etc.).

Para mapear as tags Azure para o esquema Apptio :

1. Navegue até Azure EA Detailed Bill Master Data e verifique.
2. Em Etapas, selecione Anexar > Editar.
3. Mapeie as colunas que foram analisadas a partir dessa coluna Tag na seção anterior e quaisquer outras colunas que queira mapear. Abaixo estão alguns exemplos de colunas que podem ser mapeadas:
   - Aplicativo
   - Centro de custos
   - Meio ambiente
   - Projeto
   - Propósito
   - Proprietário do sistema
4. Salve os mapeamentos.
5. Salve Azure EA Detailed Bill Master Data e faça o check-in.

Isso preencherá os dados no conjunto de dados mestre conforme configurado.

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
