---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Identificar serviços compartilhados"
breadcrumb: []
source_path: "cost-transparency/configuration/idsharedservices.html"
images:
  - "resources/images/ct_images/7877_1.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Identificar serviços compartilhados

Uma parte dos seus custos de nuvem pode ser atribuída a serviços de infraestrutura de nuvem pública compartilhados entre os departamentos que criam aplicativos na nuvem pública. Um bom exemplo é o Suporte Empresarial, cujos custos podem ser uma grande quantia fixa que precisa ser alocada aos serviços em nuvem que são consumidos diretamente pelas equipes e departamentos da sua organização. Os custos desses serviços de infraestrutura compartilhada podem ser alocados para os serviços que são consumidos diretamente, garantindo que os custos para os departamentos de aplicativos contabilizem todos os custos incorridos com o uso de provedores de nuvem pública.

Aplica-se a: Apptio Costing Standard ou Apptio Cloud Cost Management em execução em TBM Studio v12.3.3 ou posterior.

Nota:

Os custos do serviço compartilhado serão distribuídos por todos os serviços em nuvem consumidos diretamente e ponderados pelo custo desses serviços consumidos diretamente.

## Visão geral

Para alocar esses custos de infraestrutura compartilhados, é necessário identificar os custos compartilhados na conta do provedor. Apptio é flexível em termos das colunas de faturamento que você usa para identificar os conjuntos de itens de linha de faturamento que representam serviços compartilhados. Por exemplo, para o Suporte Empresarial, você pode identificar serviços compartilhados por meio de valores na coluna do produto ou em alguma outra conta que crie ferramentas de implantação e entrega compartilhadas pelos grupos que criam aplicativos na nuvem pública. No último caso, você identificaria os serviços compartilhados por meio de valores na coluna da conta.

## Identificação de serviços compartilhados

A identificação de serviços compartilhados é amplamente baseada na função Tablematch, que permite procurar valores em uma tabela de pesquisa criada separadamente usando valores na fatura do provedor de nuvem. O CBM vem com arquivos Tablematch pré-existentes para AWS e Azure. O CBM usa o Tablematch para determinar se um item de linha de faturamento é considerado um serviço compartilhado com base nas colunas e valores que você fornece nos arquivos do Tablematch. Para obter mais informações, consulte a definição da função em [TableMatch function](../../studio/formulas-and-functions/functions/tablematch.htm "(Abre em uma nova guia ou janela)").

## Alocar os custos do AWS no Tablematch de Serviços Compartilhados

Identificar e alocar custos de serviços compartilhados para AWS :

1. No Project Explorer do site TBM Studio , expanda a seção **Tables (Tabelas** ).
2. Clique em **AWS Cost AllocationShared Services Tablematch**.
3. Clique em **Check Out**.
4. Na área Source (Fonte), clique em **Enter Manually (Inserir manualmente** ).

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/7877_1.png)
5. Clique em **Blank Table (Tabela em branco** ).
6. Na etapa Editable Table (Tabela editável), identifique o serviço compartilhado e defina IsSelfService como Yes (Sim). Você pode usar as colunas existentes ou adicionar e remover colunas conforme necessário. Por exemplo, para identificar o Suporte Empresarial como um serviço compartilhado e alocar os custos a todos os serviços consumidos diretamente, use um dos métodos a seguir:
   - Em **Product Code (Código do produto** ), digite " AWS Support Business" (ou o termo que você vê para suporte em sua fatura de alocação de custos AWS ) e, em seguida, defina **IsSharedService** para Yes (Sim).
   - Se uma conta vinculada específica for responsável pela criação de ferramentas de infraestrutura compartilhada, clique com o botão direito do mouse nessa conta e adicione uma nova coluna chamada "LinkedAccountId" à tabela; em seguida, adicione uma nova linha e insira o ID dessa conta vinculada na nova linha em que o valor da coluna **IsSelfService** valor da coluna está definido como Yes (Sim).
7. Salve suas alterações.
8. Verifique suas alterações.

## Alocar os custos do Azure no Tablematch de Serviços Compartilhados

Identificar e alocar custos de serviços compartilhados para Azure :

1. No Project Explorer do site TBM Studio , expanda a seção **Tables (Tabelas** ).
2. Clique em **AzureShared Services Tablematch**.
3. Clique em **Check Out**.
4. Na área Source (Fonte), clique em **Enter Manually (Inserir manualmente** ).
5. Clique em **Blank Table (Tabela em branco** ).
6. Na etapa Editable Table (Tabela editável), identifique o serviço compartilhado e defina **IsSelfService** para Sim. Você pode usar as colunas existentes ou adicionar e remover colunas conforme necessário. Por exemplo, para identificar um item de linha específico para um proprietário de conta específico como serviço compartilhado e alocar esses custos diretamente aos serviços consumidos, insira o ID do proprietário da conta no campo **AccountOwnerId** e defina **IsSharedService** como Yes (Sim).
7. Salve suas alterações.
8. Verifique suas alterações.

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
