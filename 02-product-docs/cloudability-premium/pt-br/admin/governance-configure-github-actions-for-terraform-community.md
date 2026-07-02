---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Configurar GitHub Actions for Terraform Community"
breadcrumb:
  - "Cloudability Premium"
  - "Governança"
  - "Configurar Cloudability Governança"
source_path: "admin/governance-configure-github-actions-for-terraform-community.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Configurar GitHub Actions for Terraform Community

Para usuários que utilizam o Terraform Community, [a ação Cloudability Governance GitHub](https://github.com/IBM/ibm-cloudability-governance/blob/main/README.md "(Abre em uma nova guia ou janela)") é acionada como parte do fluxo de trabalho de CI/CD para pull requests. Essa integração permite que a Cloudability Governance forneça insights relacionados a custos diretamente no PR por meio de comentários e execuções de verificação GitHub.

Consulte esta página para obter as informações/atualizações mais recentes: [https://GitHub. com/IBM/ibm-cloudability-governance/blob/main/README.md](https://github.com/IBM/ibm-cloudability-governance/blob/main/README.md "(Abre em uma nova guia ou janela)")

**Pré-requisito:** Certifique-se de ter instalado o aplicativo IBM Cloudability GitHub antes de prosseguir com a configuração do GitHub Actions.

**Insumos necessários para a governança GitHub Actions:**

1. **Saída do plano de terraformação para a alteração em PR** - Executar plano de terraformação para as alterações em PR. Os clientes podem configurar isso na ação GitHub com base em como seu código de terraform está organizado e configurado.

Você pode encontrar neste link [https://GitHub.com/ IBM](https://github.com/IBM/ibm-cloudability-governance "(Abre em uma nova guia ou janela)") /ibm-cloudability-governance exemplos para atualizar GitHub Actions for repositories that contains IaC code for one deployment or multiple ones.

O exemplo usa a [aws-actions/configure-aws-credentials@v4.1.0](https://github.com/aws-actions/configure-aws-credentials "(Abre em uma nova guia ou janela)") GitHub para buscar as credenciais do AWS para poder executar o plano do terraform. GitHub variables/secrets podem ser usadas para armazenar o ARN do AWS\_ROLE a ser usado aqui. Os clientes também podem optar por fazer isso de outras formas.

1. **Exemplo em que um repositório contém o código IaC para apenas uma implantação:**

   ```
   name: Demo Pipeline 

   run-name: Deployment 

   on: 

     pull_request: 

       types: [opened, reopened, synchronize] 

       paths: 

       - '**.tf' 

       - 'usage.yaml' 

       - '!README.md' 

        

   jobs: 

     terraform: 

       runs-on: ubuntu-latest 

       permissions: 

         id-token: write 

         contents: read 

       defaults: 

        run: 

          shell: bash 

          # Can change to specific directory here where Terraform files are present 

          working-directory: ./ 

       steps: 

         - name: Checkout repository 

           uses: actions/checkout@v4 

        

         - name: Setup AWS credentials 

           uses: aws-actions/configure-aws-credentials@v4.1.0 

           with: 

             aws-region: us-west-2 

             role-to-assume: ${{ secrets.AWS_ROLE }} 

             role-session-name: ${{ GitHub.run_id }} 

        

         - name: Setup Terraform with specified version on the runner 

           uses: hashicorp/setup-terraform@v3 

           with: 

             terraform_version: 1.10.5 

             terraform_wrapper: false 

        

         - name: Terraform init 

           id: init 

           run: terraform init 

        

         - name: Terraform plan 

           id: plan 

           run: | 

             terraform plan -lock=false -input=false -out=tfplan 

             terraform show -json tfplan > tfplan.json 

           continue-on-error: false 

        

         - name: Redact secrets from tfplan 

           run: | 

             sed -i 's/"password":"[^"]*"/"password":""/g' tfplan.json 

             sed -i 's/"secret_string":"{[^}]*}"/"secret_string":""/g' tfplan.json
   ```
2. **Chaves de API do Frontdoor** - O token do Frontdoor é necessário para invocar ações de governança. A ação GitHub abaixo deve ser capaz de buscar o token do Frontdoor usando as chaves de API fornecidas.

   É possível definir as seguintes variáveis como GitHub variables/secret

   - FD\_URL (exemplo: [https://frontdoor.apptio.com](https://frontdoor.apptio.com/ "(Abre em uma nova guia ou janela)") )
   - FD\_KEY (Gerar chave de API e segredo para um usuário do Frontdoor com a função " Cloudability Governance Automation User")
   - FD\_SECRET (Gerar chave de API e segredo para um usuário do Frontdoor com a função " Cloudability Governance Automation User")

   ```
    - name: Get Frontdoor token 

           uses: cloudability/costguard-GitHub-action/actions/frontdoor/login@main 

           with: 

             fd-url: ${{ secrets.FD_URL }} 

             fd-public-key: ${{ secrets.FD_KEY }} 

             fd-secret-key: ${{ secrets.FD_SECRET }}
   ```
3. **Metadados** - Os metadados associados a um pull-request e à governança do Cloudability são necessários para capturar a configuração da governança para a organização dos clientes.
   - **Obter metadados do PR GitHub** - Chame [a API GitHub](https://docs.github.com/en/rest/pulls/pulls?apiVersion=2022-11-28#get-a-pull-request "(Abre em uma nova guia ou janela)") para obter metadados relacionados ao PR de GitHub

     ```
       - name: Get GitHub PR metadata 

             uses: ibm/ibm-cloudability-governance/actions/GitHub-info@v0.1.0 

             with: 

               GitHub-token: ${{ secrets.GitHub_TOKEN }} 

               pr-number: ${{ GitHub.event.pull_request.number }}
     ```
   - **Execute Cloudability Governance Metadata Retrieval** - Obtenha metadados relacionados à configuração de governança (projeto, implantação, solicitação pull, instalações de aplicativos GitHub ) de Cloudability

     ```
     - name: Run Cloudability Governance Metadata Retrieval 

             uses: ibm/ibm-cloudability-governance/actions/metadata@v0.1.0 

             with: 

               cloudability-host: ${{ vars.CLOUDABILITY_HOST }} 

               fd-env-id: ${{ secrets.FD_ENV_ID }}
     ```
   - Download tfplan (opcional) - Se o plano de terraformação for carregado como artefato em um trabalho separado
   - Esta etapa requer o Frontdoor Environment Id para os clientes da organização Cloudability e o host de url Cloudability. Eles podem ser definidos como segredos ou variáveis do repositório GitHub.
     - FD\_ENV\_ID (Identificação do ambiente do frontdoor)
     - CLOUDABILITY\_HOST (exemplo: [https://api.cloudability.com](https://api.cloudability.com/ "(Abre em uma nova guia ou janela)") )
4. **Governança** - As próximas etapas permitem que você obtenha insights sobre estimativa de custos, avaliação de políticas, recomendações alternativas

   Para essas três etapas, a entrada necessária é o mapa "provider-accounts". É um mapeamento da chave do provedor de terraform para o ID da conta do fornecedor de nuvem ( AWS ). Isso é necessário para obter as informações de preço do ID correto da conta do fornecedor de nuvem ( AWS ). A chave do provedor pode ser "\*", o que indica que é a conta padrão para todos os provedores, ou exatamente a chave de configuração do provedor mostrada no mapa configuration.provider\_config em um plano json do terraform. Por exemplo, se um provedor com o nome local “aws\_usw2” for definido em um módulo chamado "database" e o módulo raiz do terraform estiver chamando o módulo "database", a chave do provedor será module.database:aws\_usw2.

   **Exemplo de implementação em uma única conta de fornecedor de nuvem (use \* como chave no mapa de contas de fornecedor)**

   ```
      - name: Run Cloudability Cost Estimation 

           uses: ibm/ibm-cloudability-governance/actions/cost-estimation@v0.1.0 

           with: 

             GitHub-token: ${{ secrets.GitHub_TOKEN }} 

             pr-number: ${{ GitHub.event.pull_request.number }} 

             cloudability-host: ${{ secrets.CLOUDABILITY_HOST }} 

             fd-env-id: ${{ secrets.FD_ENV_ID }} 

             deployment-name: "demo" 

             provider-accounts: | 

               { 

                 "*": { 

                   "account_id": "${{ secrets.AWS_ACCOUNT_ID }}",  

                   "vendor": "aws" 

                 } 

               } 

             tf-plan: "tfplan.json" 

             resource-usage: "usage.json" 

    

         - name: Run Cloudability Governance Policy Evaluation 

           uses: ibm/ibm-cloudability-governance/actions/policy-evaluation@v0.1.0 

           with: 

             GitHub-token: ${{ secrets.GitHub_TOKEN }} 

             pr-number: ${{ GitHub.event.pull_request.number }} 

             cloudability-host: ${{ secrets.CLOUDABILITY_HOST }} 

             fd-env-id: ${{ secrets.FD_ENV_ID }} 

             deployment-name: "demo" 

             provider-accounts: | 

               { 

                 "*": { 

                   "account_id": "${{ secrets.AWS_ACCOUNT_ID }}",  

                   "vendor": "aws" 

                 } 

               } 

             tf-plan: "tfplan.json" 

             resource-usage: "usage.json" 

    

         - name: Run Cloudability Recommendation 

           uses: ibm/ibm-cloudability-governance/actions/recommendation@v0.1.0 

           with: 

             GitHub-token: ${{ secrets.GitHub_TOKEN }} 

             pr-number: ${{ GitHub.event.pull_request.number }} 

             cloudability-host: ${{ secrets.CLOUDABILITY_HOST }} 

             fd-env-id: ${{ secrets.FD_ENV_ID }} 

             deployment-name: "demo" 

             provider-accounts: | 

               { 

                 "*": { 

                   "account_id": "${{ secrets.AWS_ACCOUNT_ID }}",  

                   "vendor": "aws" 

                 } 

               } 

             tf-plan: "tfplan.json" 

             resource-usage: "usage.json"
   ```

   Como alternativa, essa é a configuração para um cenário com um alias de conta específico.

   ```
         - name: Run Cloudability Cost Estimation 

           uses: ibm/ibm-cloudability-governance/actions/cost-estimation@v0.1.0 

           with: 

             GitHub-token: ${{ secrets.GitHub_TOKEN }} 

             pr-number: ${{ GitHub.event.pull_request.number }} 

             cloudability-host: ${{ secrets.CLOUDABILITY_HOST }} 

             fd-env-id: ${{ secrets.FD_ENV_ID }} 

             deployment-name: "demo" 

             provider-accounts: | 

               { 

                 "module.database:aws_usw2": { 

                   "account_id": "${{ secrets.AWS_ACCOUNT_ID }}",  

                   "vendor": "aws" 

                 }, 

                 "*": { 

                   "account_id": "${{ secrets.SECOND_AWS_ACCOUNT_ID }}",  

                   "vendor": "aws" 

                 } 

               } 

             tf-plan: "tfplan.json" 

             resource-usage: "usage.json" 

             pr-number: ${{ GitHub.event.pull_request.number }} 

             cloudability-host: ${{ secrets.CLOUDABILITY_HOST }} 

             fd-env-id: ${{ secrets.FD_ENV_ID }} 

             deployment-name: "demo" 

             provider-accounts: | 

               { 

                 "module.database:aws_usw2": { 

                   "account_id": "${{ secrets.AWS_ACCOUNT_ID }}",  

                   "vendor": "aws" 

                 } 

               } 

             tf-plan: "tfplan.json" 

             resource-usage: "usage.json"
   ```

**Tópico principal:** [Configurar Cloudability Governança](../admin/governance-setup-cldy-governance.html)
