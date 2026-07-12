---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Visão geral do planejamento de APIs REST"
breadcrumb:
  - "Planning"
  - "APIs"
source_path: "it-planning/planning/plan-api.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Visão geral do planejamento de APIs REST

**As APIs REST** do Planning do Apptio oferecem acesso programático e seguro a planos, dados de planejamento, metadados e artefatos relacionados no Planning d Apptio. Essas APIs foram projetadas para oferecer suporte à automação e às integrações de sistemas em casos de uso relacionados a planejamento, previsão, análise, governança e troca de dados.

**Ao utilizar as APIs de planejamento, os usuários podem:**

- Descubra os planos disponíveis no ambiente de planejamento do Apptio
- Exportar e importar dados de despesas do plano usando arquivos do tipo “ CSV ”
- Obter resultados analíticos, como análise de variação e status do plano
- Gerenciar e validar permissões de usuário em nível de plano ou global
- Integrar a importação de dados reais na gestão de despesas
- Acessar os metadados de layout utilizados para estruturar os dados de planejamento

Todas as APIs seguem os princípios REST, utilizam métodos padrão de interface de programação de aplicativos ( HTTP ) e trocam dados por meio de respostas JSON e arquivos de interface de programação de aplicativos ( CSV ). As APIs de exportação retornam arquivos do tipo ` CSV ` que podem ser baixados, enquanto as APIs de importação aceitam arquivos do tipo ` CSV ` e retornam resultados detalhados de validação para dar suporte a integrações em grande escala e repetíveis.

## Pré-requisitos

Para usar as APIs do Plano, você deve:

1. [Crie chaves de API](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=apis-api-overview-api-keys-faq "(Abre em uma nova guia ou janela)") para o ambiente na Administração d Apptio.
2. [Gerar um token de acesso d Apptio](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=apis-enhanced-access-administration-api-authentication-via-api-keys "(Abre em uma nova guia ou janela)") usando chaves de API.
3. [Recupere o **ID do ambiente**](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=apis-how-access-r12-api-through-enhanced-access-administration-via-curl#HowtoaccessR12APIthroughEnhancedAccessAdministrationviacurl__GetaenvIDuseopentoken__title__1 "(Abre em uma nova guia ou janela)"), que é obrigatório em todos os cabeçalhos da API.

Observação: a conta de usuário utilizada para gerar chaves de API deve ter privilégios **de Proprietário do Processo Orçamentário** ou **de Administrador** para acessar todas as APIs disponíveis. Se for utilizada uma conta de serviço para criar chaves de API, entre em contato com o suporte do Apptio para garantir que as permissões necessárias sejam concedidas a essa conta.

**Cabeçalhos de autenticação**

- Todas as solicitações de API exigem os seguintes cabeçalhos:
  - apptio-opentoken
  - Token de autenticação gerado usando chaves de API
- apptio-ambiente atual
  - ID do ambiente que identifica o ambiente de planejamento Apptio

  Observação: as solicitações que não incluírem esses cabeçalhos ou que utilizem credenciais inválidas resultarão em erros de autorização ou de acesso.

**Pontos finais regionais**

- As solicitações de API devem ser enviadas ao endpoint regional correto para a sua implantação do Apptio (por exemplo, app.apptio.com, app-eu.apptio.com ou app-au.apptio.com ).
- Verifique se o domínio de base URL corresponde à sua região antes de enviar solicitações.

- **[APIs](../../it-planning/planning/plan-data-api.html)**  
   de planos As **APIs de planos** permitem que você identifique os planos disponíveis e gerencie dados de despesas por plano por meio de operações de importação e exportação. Essas APIs constituem a base da maioria das integrações de dados de planejamento com o Microsoft Apptio Planning.
- **[APIs](../../it-planning/planning/variance-analysis-api.html)**  
   de análise de variação As **APIs de análise de variação** permitem a exportação programática de dados de análise de variação para um plano específico.
- **[APIs](../../it-planning/planning/pln-status-api.html)**  
   **de status do plano As APIs de status do plano** permitem exportar informações sobre a aprovação e o status do plano. Essas APIs são comumente utilizadas para fins de governança, auditoria e geração de relatórios, a fim de compreender o ciclo de vida e o status de aprovação dos planos.
- **[APIs](../../it-planning/planning/spnd-mgmt-api.html)**  
   **de gestão de despesas As APIs de gestão de despesas** permitem a exportação e importação de dados reais utilizados no planejamento e na análise financeira.
- **[APIs](../../it-planning/planning/user-perm-api.html)**  
   de permissões de usuário As **APIs de permissões de usuário** permitem a exportação e a importação de dados de permissões globais e no nível do plano. Essas APIs oferecem suporte ao gerenciamento automatizado de acesso e à validação de permissões de usuário no Apptio Planning.
- **[APIs](../../it-planning/planning/chng-hist-api.html)**  
   **de histórico de alterações** As APIs de histórico de alterações permitem exportar dados do registro de eventos que capturam as alterações realizadas no Apptio Planning.Change Os dados do histórico são exportados como um arquivo CSV e podem ser usados para auditar as modificações de um plano específico, incluindo **quais alterações foram feitas**, **quem as fez** e **quando ocorreram**.
- **[APIs](../../it-planning/planning/tab-lay-api.html)**  
   de layouts de tabela A **API de layouts de tabela** fornece acesso aos metadados de layout utilizados para exibir e organizar dados de despesas no Apptio Planning. Os layouts definem como os dados do plano são estruturados e apresentados nos diferentes tipos de despesas.
