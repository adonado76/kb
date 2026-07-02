---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Configurar um conector REST d Datalink"
breadcrumb:
  - "Planning"
  - "APIs"
source_path: "it-planning/planning/config-data-rest.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Configurar um conector REST d Datalink

[O conector REST](https://www.ibm.com/docs/en/apptio-platform/datalink/saas?topic=connectors-datalink-rest-service-connector "(Abre em uma nova guia ou janela)") do Datalink permite integrar o Apptio Planning com o Apptio Costing — ou outros sistemas externos — através da troca segura de dados por meio de APIs REST.

1. **Tipo de Conector**

   Selecione: **Serviço REST / Serviço REST 2.0**
2. **Destino**

   Antes de configurar a conexão da API, defina onde os dados serão armazenados em Apptio :
   - Vá para a guia “ **Apptio** ” (Destino do aplicativo).
   - Configurar:
     - **Nome do destino:** por exemplo, Novo destino 1
     - **Aplicação:** selecione a aplicação (por exemplo, Cálculo de custos do Apptio )
     - **Domínio:** por exemplo, acme.apptio.com
     - **Projeto:** selecione o projeto (por exemplo, Transparência de Custos)
     - **Categoria:** definido como REST
   - Escolha o **período** (mês atual, mês anterior ou calendário personalizado).
3. **Método HTTP**

   Pode ser **GET** ou **POST**, dependendo do endpoint que você está chamando:
   - **GET** – para recuperar dados (somente leitura).
   - **POST** – para exportar dados (gerar um arquivo CSV).
4. **REST URL**

   No campo **REST URL**, insira: [https://app.apptio.com](https://app.apptio.com/ "(Abre em uma nova guia ou janela)")

   Observação: certifique-se de que o URL corresponda à sua região (por exemplo, app-eu.apptio.com, app-au.apptio.com ).

   No campo **Insira o caminho do recurso URL**, adicione o endpoint da documentação, por exemplo:

   `planning/api/v1/plans/<planId>/expenses/export`

   **Descrição:** Este endpoint exporta dados de despesas para um plano específico no formato CSV.
5. **Autenticação**

   **Tipo:** Selecione o apropriado de acordo com [o Conector de Serviço REST](https://www.ibm.com/docs/en/apptio-platform/datalink/saas?topic=connectors-datalink-rest-service-connector "(Abre em uma nova guia ou janela)") Datalink

   Insira:
   - **Chave da porta da frente** (chave pública)
   - **Segredo da porta da frente** (Chave secreta)

   Verificar **“Precisa de token de atualização?”** → **Sim** (permite várias execuções sem reautenticação).
6. **Cabeçalhos**

   Adicione um cabeçalho:

   **Chave:** apptio-ambiente-atual

   **Valor:** <valor do ambiente, por exemplo, GUID>
7. **Parâmetros de consulta**

   Adicione o parâmetro necessário. Consulte a documentação da API:

   **Chave:** tipo

   **Valor:** por exemplo, RESUMO

   Outros parâmetros opcionais (por exemplo, departmentCode, columnDelimiter ) podem ser adicionados na mesma seção.
8. **Paginação**

   **Definir:** Sem paginação (ou outro com base no [conector de serviço REST](https://www.ibm.com/docs/en/apptio-platform/datalink/saas?topic=connectors-datalink-rest-service-connector "(Abre em uma nova guia ou janela)") Datalink ).
9. **Salvar e testar**

   Clique em **Testar API** para verificar a configuração.

   Salve a conexão e configure uma programação se desejar automatizar a exportação.
