---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Configure GitHub Acciones para Terraform Community"
breadcrumb:
  - "Cloudability Premium"
  - "Gobernabilidad"
  - "Configurar Cloudability Gobernanza"
source_path: "admin/governance-configure-github-actions-for-terraform-community.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Configure GitHub Acciones para Terraform Community

Para los usuarios que utilizan Terraform Community, [Cloudability Governance GitHub Action](https://github.com/IBM/ibm-cloudability-governance/blob/main/README.md "(se abre en una pestaña o una ventana nueva)") se activa como parte del flujo de trabajo CI/CD para pull requests. Esta integración permite a Cloudability Governance proporcionar información relacionada con los costes directamente en el RP a través de comentarios y comprobaciones de GitHub.

Consulte esta página para obtener la información/actualizaciones más recientes [com/IBM/ibm-cloudability-governance/blob/main/README.md https://GitHub](https://github.com/IBM/ibm-cloudability-governance/blob/main/README.md "(se abre en una pestaña o una ventana nueva)")

**Requisito previo:** Asegúrese de haber instalado IBM Cloudability GitHub app antes de proceder a la configuración de sus GitHub Acciones.

**Aportaciones necesarias para la gobernanza GitHub Acciones:**

1. **Salida del** plan de terraformación para el cambio en PR - Ejecutar el plan de terraformación para los cambios en PR. Los clientes pueden configurar esto en GitHub acción basada en cómo en su código terraforma está organizado y configurado.

Puede encontrar en este enlace [https://GitHub.com/ IBM](https://github.com/IBM/ibm-cloudability-governance "(se abre en una pestaña o una ventana nueva)") /ibm-cloudability-governance ejemplos para actualizar GitHub Acciones para repositorios que contienen IaC código para un despliegue o varios.

El ejemplo utiliza [aws-actions/configure-aws-credentials@v4.1.0](https://github.com/aws-actions/configure-aws-credentials "(se abre en una pestaña o una ventana nueva)") GitHub para obtener las credenciales de AWS y poder ejecutar el plan terraform. GitHub variables/secrets se puede utilizar para almacenar el ARN del AWS\_ROLE que se utilizará aquí. Los clientes también pueden optar por conseguirlo de otras maneras.

1. **Ejemplo en el que un repositorio contiene código IaC para un único despliegue:**

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
2. **Frontdoor API Keys** - El token de Frontdoor es necesario para invocar acciones de Gobernanza. A continuación GitHub acción debe ser capaz de obtener Frontdoor token utilizando las claves de API proporcionadas.

   Puede establecer las siguientes variables como GitHub variables/secret

   - FD\_URL (ejemplo: [https://frontdoor.apptio.com](https://frontdoor.apptio.com/ "(se abre en una pestaña o una ventana nueva)") )
   - FD\_KEY (Generar clave API y Secreto para un usuario Frontdoor con rol " Cloudability Governance Automation User")
   - FD\_SECRET (Generar clave API y Secreto para un usuario Frontdoor con rol " Cloudability Governance Automation User")

   ```
    - name: Get Frontdoor token 

           uses: cloudability/costguard-GitHub-action/actions/frontdoor/login@main 

           with: 

             fd-url: ${{ secrets.FD_URL }} 

             fd-public-key: ${{ secrets.FD_KEY }} 

             fd-secret-key: ${{ secrets.FD_SECRET }}
   ```
3. **Metadatos** : los metadatos asociados con una solicitud de extracción y Cloudability Governance son necesarios para capturar la configuración de Governance para la organización del cliente.
   - **Obtener metadatos de PR GitHub** : llamar a [la API GitHub](https://docs.github.com/en/rest/pulls/pulls?apiVersion=2022-11-28#get-a-pull-request "(se abre en una pestaña o una ventana nueva)") para obtener metadatos relacionados con el PR de GitHub

     ```
       - name: Get GitHub PR metadata 

             uses: ibm/ibm-cloudability-governance/actions/GitHub-info@v0.1.0 

             with: 

               GitHub-token: ${{ secrets.GitHub_TOKEN }} 

               pr-number: ${{ GitHub.event.pull_request.number }}
     ```
   - **Ejecute Cloudability Governance Metadata Retrieval** - Obtenga metadatos relacionados con la configuración de Governance (proyecto, despliegue, solicitud pull, instalaciones de aplicaciones GitHub ) de Cloudability

     ```
     - name: Run Cloudability Governance Metadata Retrieval 

             uses: ibm/ibm-cloudability-governance/actions/metadata@v0.1.0 

             with: 

               cloudability-host: ${{ vars.CLOUDABILITY_HOST }} 

               fd-env-id: ${{ secrets.FD_ENV_ID }}
     ```
   - Descargar plan de terraformación (opcional) - Si el plan de terraformación se carga como artefacto en un trabajo separado
   - Este paso requiere la Frontdoor Medio Ambiente Id para los clientes Cloudability organización y el Cloudability url host. Pueden establecerse como secretos o variables del repositorio GitHub.
     - FD\_ENV\_ID (Id. de entorno de puerta delantera)
     - CLOUDABILITY\_HOST (ejemplo: [https://api.cloudability.com](https://api.cloudability.com/ "(se abre en una pestaña o una ventana nueva)") )
4. **Gobernanza** - Los siguientes pasos le permiten obtener información sobre estimación de costes, evaluación de políticas, recomendaciones alternativas

   Para estos tres pasos, la entrada necesaria es el mapa "cuentas-proveedor". Se trata de una correspondencia entre la clave del proveedor de terraformación y el identificador de cuenta del proveedor de la nube ( AWS ). Esto es necesario para obtener la información de precios de la cuenta correcta del proveedor de la nube ( AWS ). La clave del proveedor puede ser "\*", que indica que es la cuenta por defecto para todos los proveedores, o la clave de configuración del proveedor exacta que se muestra en el mapa configuration.provider\_config en un plan terraform json. Por ejemplo, si se define un proveedor con nombre local “aws\_usw2” en un módulo llamado "base de datos" y el módulo raíz terraform está llamando al módulo "base de datos", la clave del proveedor será module.database:aws\_usw2.

   **Ejemplo de despliegue en una única cuenta de proveedor en la nube (utilice \* para la clave en el mapa de cuentas de proveedores)**

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

   Alternativamente, esta es la configuración para un escenario con un alias de cuenta específico.

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

**Tema principal:** [Configuración Cloudability Governance](../admin/governance-setup-cldy-governance.html)
