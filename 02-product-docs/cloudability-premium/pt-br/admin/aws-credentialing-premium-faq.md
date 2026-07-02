---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Perguntas frequentes sobre como se conectar com AWS"
breadcrumb:
  - "Cloudability Premium"
  - "Obtendo dados em Cloudability"
  - "Conexão com AWS - Guia de integração do cliente"
source_path: "admin/aws-credentialing-premium-faq.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Perguntas frequentes sobre como se conectar com AWS

- **Não vejo nenhum dado de custo após concluir as etapas de credenciamento da conta. O que deve ser feito?**
  - Verifique se os arquivos de faturamento corretos estão em seu bucket S3
  - Navegue até o seu bucket S3 mostrado na [página AWS Billing and Cost Management](https://us-east-1.console.aws.amazon.com/costmanagement/home?region=us-east-1#/bcm-data-exports "(Abre em uma nova guia ou janela)"), encontrado em Cost and Usage Analysis - Data Exports. Quando selecionado, você verá o prefixo criado anteriormente. Você pode clicar nele e navegar até as exportações de faturamento
  - Verifique se você vê arquivos semelhantes aos seguintes:
    - **<BillingReportName>.csv.gz**
    - **<BillingReportName>-Manifest.json**
  - Se você não vir arquivos como esses, precisará garantir que seu relatório de custo e uso esteja ativado para IDs e tags de recursos. Para obter mais informações, consulte [Configurar credenciais de conta consolidada](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=cloudability-connect-amazon-web-services#connectamazonwebservices__account_credentials "(Abre em uma nova guia ou janela)").

- **Recentemente, ativei o relatório AWS Cost and Usage e fiz o credenciamento em Cloudability. Quanto tempo levará para ver os dados de custo e uso?**

  Pode levar até 24 horas para que seu primeiro relatório de custo e uso seja gerado em AWS. Para mais informações, consulte: [https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=ts-cloudability-cloudability-cost-usage-data-availability-in-reporting](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=ts-cloudability-cloudability-cost-usage-data-availability-in-reporting "(Abre em uma nova guia ou janela)")

- **Posso usar o credenciamento de contas vinculadas diretamente em vez do credenciamento de contas consolidadas?**

  Cloudability suporta apenas o faturamento consolidado e não o faturamento em um nível de conta vinculada. **O acesso ao faturamento** programático é transferido para a conta consolidada, de modo que as contas vinculadas não recebem os arquivos necessários no S3 Bucket. Você precisa adicionar a conta consolidada com o **Programmatic Billing Access** ativado em Cloudability.

- **Como faço para atualizar para o modelo mais recente do site CloudFormation?**

  Isso pode ser feito usando Cloudability Gerenciar AWS credenciais

  - Mantenha suas credenciais do AWS atualizadas em Cloudability com as instruções a seguir.
  - **Regenerar um modelo de formação de nuvem**
  - Para gerar novamente o modelo do Cloud Formation e reconfigurar seu acesso a AWS, faça o seguinte:
  - Em Cloudability, navegue até **Settings > Vendor Credentials > AWS**.**Observação:** A página **Vendor Credentials (Credenciais do fornecedor** ) requer permissões de administrador para ser acessada.
  - Salvar e fazer o download do modelo atual do site CloudFormation
  - Em AWS, navegue até CloudFormation à Stacks
  - Descubra qual pilha ele executou anteriormente para instalar o modelo anterior Cloudability CloudFormation.
  - Selecione a mesma pilha e clique no botão **atualizar pilha**
  - Selecione " **fazer uma atualização direta** ", selecione substituir o modelo existente e carregue um arquivo de modelo. Faça upload do novo arquivo de modelo CloudFormation.
  - Se a atualização for bem-sucedida, verifique novamente a conta.

- Veja como você pode atualizar para a versão mais recente todas as contas de pagadores e contas vinculadas de sua organização.
  - Contas consolidadas (precisam de acesso ao bucket S3 ): consulte Configurar credenciais da conta consolidada
  - Contas vinculadas (não precisam de acesso ao bucket S3 ): consulte Configurar o acesso à API AWS

- **Quais formatos são compatíveis com arquivos AWS CUR****?**

  Cloudability suporta CUR e AWS CUR legados 2.0 em ambos os formatos.

  - gzip - texto/csv
  - Pavimento em parquet - Pavimento em parquet
- **Como mudar de CUR legado para CUR 2.0?**

  Isso pode ser feito de duas maneiras:

- **Opção 1: Criar o CUR 2.0 exportar da mesma forma que o CUR antigo**
  - A maneira mais simples é criar uma exportação CUR 2.0 no mesmo bucket com o mesmo nome de exportação e o mesmo prefixo de exportação do CUR herdado. Se essa opção for escolhida, não será necessário executar nenhuma etapa adicional na interface do usuário Cloudability. Na próxima extração de dados, o site Cloudability iniciará automaticamente a leitura do CUR 2.0.
- **Opção 2:** **Criar um novo CUR 2.0 e atualizar as credenciais**
  - **Em AWS :**
    - Crie uma nova exportação CUR 2.0 em AWS Management Billing com um novo nome.
    - Use o mesmo bucket (que foi usado para o Legacy CUR) para a exportação ou crie um novo.
    - Crie a exportação de acordo com as etapas acima em Credenciamento de conta consolidada.
  - **Em Cloudability :**
    - Selecione a conta consolidada para a qual o CUR 2.0 está configurado.
    - Clique em Edit:
    - Atualize o nome do bucket S3 (se for um novo)
    - Atualizar o nome do relatório de custo e uso (se for um novo)
    - Atualizar o prefixo de custo e uso. (se for um novo)
    - Faça o download do modelo de formação de nuvem (CFT).

    Observação: isso só é necessário se você criar um novo bucket. Se você não tiver criado um novo bucket, pule o download do CFT, clique em Save and Verify Credential (Salvar e verificar credenciais).
  - **Em AWS :**
    - Faça upload e execute o CFT como uma pilha.
  - **Em Cloudability**
    - Selecione a mesma conta consolidada
    - Clique em Editar
    - Clique em Salvar
    - Verificar credencialDepois de mudar de CUR legado para CUR 2.0, você precisará reconfigurar as tags em Cloudability.

    Observação: O comando `Cloudability ` procura o arquivo de manifesto no seguinte local:

    **CUR herdado** - <prefixo do relatório de custo e uso>/<nome do relatório de custo e uso>/YYYYMMDD-YYYYMMDD/<nome do relatório de custo e uso> -Manifest.json

    **CUR 2.0** - <Prefixo do relatório de custo e uso>/<Nome do relatório de custo e uso>/metadata/BILLING\_PERIOD=YYYYY-MM/<Nome do relatório de custo e uso> -Manifest.json

    A exportação de dados que você criar de acordo com as etapas de capacidade de nuvem, por padrão, carregará os dados no local acima. Se algum dado histórico for obtido, o cloudability espera que os arquivos de manifesto estejam no local acima.

- **O Cloudability é compatível com arquivos CUR personalizados?**

  Não, não oferecemos suporte a arquivos CUR personalizados; alterar esses arquivos pode causar diversos impactos no sistema, dependendo da alteração.
- **Podemos ingerir dados históricos de custos em Cloudability? Em caso afirmativo, até que ponto os dados anteriores podem ser**  **ingeridos?**

  Sim, podemos. Consulte as equipes de suporte do site IBM Cloudability para saber como trazer dados históricos.

- **O Cloudability suporta criptografia em buckets do S3?**

  Sim, os clientes podem configurar a criptografia do lado do servidor com chaves gerenciadas do Amazon S3 ( SSE-S3 ) em seus buckets S3. Cloudability não suporta criptografia usando KMS ou chaves de criptografia fornecidas pelo cliente.
- **O que aconteceria se não fossem atualizadas as permissões do Turbonomic?**

  Caso você não tenha credenciado novamente as contas em Cloudability depois de fazer o upgrade para Cloudability Premium, então:

- **Cloudability**
  - AWS o recurso de ingestão e otimização de dados de faturamento continuará funcionando.
  - A caixa de diálogo Automatizar ações será exibida como DESLIGADA.
  - Na guia "Detalhes", nas seções "Conta consolidada" OU "Contas vinculadas", todas as permissões específicas de Turbonomic aparecerão marcadas com um X VERMELHO.
- **Turbonomic**
  - Turbonomic não funcionaria devido à falta de permissões; haveria problemas com os alvos em TurbonomicDepois que as novas permissões forem ativadas usando o CFT com Somente leitura, que será adicionado ao console AWS e as contas serão verificadas:

- **Cloudability**
  - As ações **automatizadas** ainda serão exibidas como **DESLIGADAS**.
  - Na guia **Details (Detalhes** ), as permissões Turbo para Custo, faturamento e execução de faturamento aparecerão com uma marca verde.
- **Turbonomic**
  - Turbonomic passaria a funcionar com base em permissões **de somente leitura**.Depois que as novas permissões forem ativadas usando os recursos CFT with **Optimize** no console AWS e as contas forem verificadas:

- **Cloudability**
  - As **ações automatizadas** serão marcadas como **ATIVADAS**.
  - Na guia **Details (Detalhes** ), todas as permissões aparecem com uma marca de seleção verde.
- Turbonomic
  - Turbonomic passaria a funcionar com base nas permissões **de “Otimizar Recursos** ”.

    Observação: a opção Automatizar ações **LIGADO** / **DESLIGADO** é exibida na interface do usuário de credenciais do fornecedor com base na seleção em Alternar e baixar o modelo.
- **O status da conta Cloudability e o status do destino Turbonomic não coincidem nas telas de credenciais do fornecedor? Quais poderiam ser as razões?**

  Os clientes atuais do Cloudability que estiverem atualizando para o Cloudability Premium precisam atualizar as credenciais de suas contas para obter as permissões mais recentes do Turbonomic.

  A incompatibilidade no status da conta pode ser causada por alguns motivos:
  - A recertificação não foi feita com base nos modelos/permissões mais recentes.
  - Se a recertificação foi feita, então provavelmente foi feita usando uma versão anterior do modelo e, desde então, algumas novas permissões foram adicionadas para Cloudability Premium.
  - Se a recertificação não ajudar, entre em contato com as IBM equipes de suporte.

  **O formato FOCUS pode ser usado em vez do CUR para a integração dos dados do AWS?**

  Cloudability é compatível com FOCUS e AWS CUR. Entretanto, para os dados do site AWS, recomendamos o uso do arquivo CUR.
- **Onde posso encontrar as APIs de credenciais de fornecedor do Cloudability para AWS**

  [Ponto final das credenciais do fornecedor ( AWS )](../api-v3/vendor_credentials_end_point_1.html)
- **Onde posso encontrar ícones diferentes nas descrições do status das contas****?**

  [Indicadores de status das credenciais do fornecedor](vendor-credentials.html)

**Tópico principal:** [Conexão com AWS - Guia de integração do cliente](../admin/aws-credentialing-premium-home.html)
