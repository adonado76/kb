---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Insira os custos estimados não relacionados ao provedor"
breadcrumb: []
source_path: "cost-transparency/configuration/estmatednonprov.html"
images:
  - "resources/images/ct_images/7873_1.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Insira os custos estimados não relacionados ao provedor

Os custos estimados e inseridos manualmente não relacionados ao provedor são principalmente para os novos clientes do Cloud Cost Management que ainda não registraram os dados reais em seu GL em Costing Standard. Para quem tem o site Costing Standard, a melhor opção é extrair os custos não relacionados ao provedor dos custos reais no modelo Costing Standard Cost. Há um link entre os dois modelos (modelo CT Cost e modelo CCM Cloud Invoice) para permitir que você faça isso por meio do objeto IT Resource Towers.

Aplica-se a: Apptio Costing Standard ou Apptio Cloud Cost Management em execução em TBM Studio v12.3.3 ou posterior.

Todos os custos no modelo de custo que tiverem a opção "Is Cloud" definida como "Yes" (Sim) no objeto ITRT e que não forem gerados a partir do objeto Cloud Service Provider (Provedor de serviços de nuvem) fluirão para o modelo Cloud Invoice (Fatura de nuvem) e serão a origem dos custos de não provedores.

Para inserir custos estimados não relacionados ao provedor:

1. Faça login em Apptio e, na página inicial, clique em **Public Cloud**.
2. No painel Public Cloud , clique no ícone **Estimated Non-Provider Costs (Custos estimados de não provedores** ).
3. Leia "Saiba mais sobre os custos estimados de não provedores" para entender melhor a finalidade e o raciocínio por trás dos custos de não provedores. O formato dos dados:

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/7873_1.png)
4. Para carregar os dados do usuário, no Studio, expanda **Tables (Tabelas** ) e clique em **Public Burdened Cost Master Data (Dados mestre de custos públicos sobrecarregados** ).
5. Na faixa de opções Projeto, clique em **Check Out**.
6. Na seção Etapa, clique em **Anexar**.
7. Anexe manualmente o custo onerado, o conjunto de dados que você criou. Os campos obrigatórios:
   - Custo anual ou custo mensal
   - Pool de custos
   - Subpolo de custos
   - Entrega
   - Descrição
   - Nome da torre de recursos de TI
   - Tipo
   - Unidade
   - Unidade de medida
8. Verifique suas alterações.
9. Para garantir que os dados do usuário foram anexados e carregados corretamente, no relatório Non-Provider Costs (Custos de não prestadores de serviços) (Public Cloud > Estimated Non-Provider Costs), clique na guia **My Estimated Non-Provider Costs (Meus custos estimados de não prestadores** de serviços) e verifique se os dados carregados aparecem corretamente.

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
