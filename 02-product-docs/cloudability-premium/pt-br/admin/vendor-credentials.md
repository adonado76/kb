---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Credenciais do fornecedor"
breadcrumb:
  - "Cloudability Premium"
  - "Administração"
source_path: "admin/vendor-credentials.html"
images:
  - "images/Vendor-Credentials-Details.png"
  - "images/vc1.jpg"
  - "images/vc2.jpg"
  - "images/vc3.jpg"
  - "images/vc5.jpg"
  - "images/vc6.jpg"
  - "images/vc_icon1.jpg"
  - "images/vc_icon2.jpg"
  - "images/vc_icon3.jpg"
  - "images/vc_icon4.jpg"
  - "images/vc_icon5.jpg"
  - "images/vc_icon6.jpg"
  - "images/vc_icon7.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Credenciais do fornecedor

Visão geral:

A página “Credenciais de fornecedores” em Cloudability ajuda os usuários administradores a visualizar e se conectar a várias fontes de dados disponíveis. Esta página também permite que os administradores visualizem, atualizem ou excluam contas individuais nas fontes de dados. Os administradores podem pesquisar e filtrar as contas, além de visualizar o nível de permissão de cada conta individualmente.

Observação: Cloudability exibe o status das credenciais dos fornecedores em várias páginas. Caso você enfrente algum problema, entre em contato com o administrador do Cloudability da sua organização. Se você for um administrador, entre em contato com seu CSM/TAM da IBM, que poderá ajudá-lo a atualizar as credenciais de suas contas para garantir que Cloudability tenha as permissões necessárias.

Pré-requisitos

Acesso de administrador às credenciais de fornecedores do Cloudability

Introdução

1. Para adicionar uma nova fonte de dados, clique em Adicionar fonte de dados. Isso mostraria todas as fontes de dados disponíveis. ![Captura de tela da adição de fonte de dados no VC](../../../../03-media/cloudability-premium/images/vc1.jpg)
2. Selecione uma fonte de dados para a qual você deseja definir credenciais.

   Observação: Algumas das fontes de dados exigiriam uma configuração prévia. Para obter instruções específicas sobre sua fonte de dados, procure-a na lista da seção “Importando dados para o **Cloudability** ” da documentação.
3. Após o login, os administradores poderão visualizar uma aba para cada fonte de dados, por exemplo, AWS.![Captura de tela da visualização VC com fonte de dados adicionada](../../../../03-media/cloudability-premium/images/vc2.jpg)
4. Na guia “Fonte de dados”, os administradores podem pesquisar e filtrar por colunas individuais.![Captura de tela da fonte de dados de pesquisa do VC](../../../../03-media/cloudability-premium/images/vc3.jpg)
5. Exportar — O status das credenciais de uma fonte de dados também pode ser exportado no formato CSV usando a opção de exportação.
6. Clique em “…” para realizar as seguintes ações.
   - Ver detalhes – Exibe os detalhes da conta, juntamente com suas permissões

   ![](../../../../03-media/cloudability-premium/images/Vendor-Credentials-Details.png)

   - Editar conta – Permite editar as credenciais existentes
   - Verificar novamente – Verifica manualmente as credenciais da conta e suas permissões
   - Arquivar – Arquiva a conta
   - Excluir – Exclui a conta
7. As contas estarão ocultas por padrão. No entanto, existem ícones que:
   - Expandir todas as contas![Captura de tela do VC com todas as contas expandidas](../../../../03-media/cloudability-premium/images/vc5.jpg)
   - Ocultar todas as contas![Captura de tela da fonte de dados do VC com todas as contas recolhidas](../../../../03-media/cloudability-premium/images/vc6.jpg)
8. O status das contas é indicado por diversos ícones. A tabela abaixo explica as correspondências entre ícones e status.

   | Cloudability Status | Turbonomic Status | Ícone |
   | --- | --- | --- |
   | Credencial verificada | Normal | ícone de credencial verificada , Ícone de credencial verificada 2 |
   | Credencial inválida | Crítico | ícone de credencial inválida 2 , ícone de credencial inválida |
   | Credencial necessária | Desconhecido | Ícone “sem credenciais” |
   | Credenciais incompletas | Grave | ícone de incompleto |
   | Credenciais arquivadas |  | ícone arquivado |

**Re - Recertificação**

Cloudability atualiza frequentemente os serviços que oferece em diversos provedores de serviços em nuvem, seja para casos de uso de otimização — como incluir mais serviços em programas de rightsizing ou compromissos —, seja para aprimorar uma conexão existente com uma fonte de dados. Para aproveitar ao máximo os recursos d Cloudability, recomenda-se a recertificação periódica.

- **Novos clientes** — Quando novos clientes realizam a ação de adicionar fontes de dados, o Cloudability fornece o conjunto mais recente de modelos, que inclui todas as permissões necessárias para habilitar todos os recursos com base no SKU do cliente no Cloudability.
- **Clientes atuais** — Os clientes atuais devem **renovar suas credenciais periodicamente** para continuar aproveitando ao máximo os recursos e aprimoramentos d Cloudability. No caso de atualização do SKU “ Cloudability ” — por exemplo, **para “ Cloudability Premium** ” —, os clientes **devem atualizar suas credenciais** para aproveitar plenamente os produtos oferecidos em Cloudability Premium.

Observação: O status das credenciais do fornecedor é exibido no banner da página de credenciais do fornecedor. Em implantações do Cloudability Premium, isso também é exibido na página “Rightsizing” → “Avançado”. Certifique-se de que todas as credenciais dos seus fornecedores tenham todas as permissões necessárias concedidas para garantir que as recomendações de otimização sejam geradas corretamente.

**Verificação de permissões**

Uma chamada em lote é feita passando todas as permissões relevantes na **solicitação de política AWS Simulate.**

- Exemplo 1: A política de simulação permite todas as permissões. Todas as permissões estão marcadas como verificadas
- Exemplo 2: Simular “Política não permitida”.
  - Vamos solicitar todas as autorizações, uma por uma, e fazer uma ligação **de teste**. Algumas APIs não permitem a execução de teste sem um ID de recurso válido. Por isso, configuramos um ID de recurso **fictício** para testar as chamadas.
  - Nenhum recurso real do cliente é utilizado para isso
    - Exemplo: Simulação em que a política permite permissões parciais — Suponhamos que Cloudability tenha tentado simular 100 permissões, mas a simulação permitiu apenas 70. 70 permissões serão consideradas verificadas, e faremos uma verificação individual das 30 permissões restantes. Posteriormente, combinaríamos os resultados das duas chamadas e marcaríamos todas as permissões relevantes como verificadas.

Qualquer permissão ou permissões que não tenham podido ser verificadas pela verificação “Simulate Policy” ou “Dry-Run” serão consideradas ausentes, e a interface do usuário marcará essas permissões com uma cruz vermelha.

Perguntas Frequentes

- **A funcionalidade de credenciais de fornecedores é a mesma para todos os fornecedores**?
  - Embora as etapas individuais de credenciamento variem de acordo com os diferentes fornecedores, o processo de filtragem, expansão, reverificação etc. é o mesmo em todas as diversas fontes de dados compatíveis com o Cloudability.
- **O que significam os diversos status no site Cloudability?**
  - **Credenciais verificadas** — indica que Cloudability possui as permissões mínimas na conta e que a função Cloudability ou os entidades de serviço foram instalados corretamente.
  - **Credenciais inválidas** — indica que houve algum erro na conta e que Cloudability não conseguiu verificá-la.
  - **Credencial necessária** — indica que esta é uma conta nova e que o processo de credenciamento ainda não foi iniciado.
  - **Credenciais incompletas** — indica que as contas foram salvas, mas não foram verificadas. Após a verificação, essas contas seriam transferidas para a seção abaixo, de acordo com a permissão concedida.
    - Credenciais verificadas
    - Credenciais inválidas
  - **Credenciais arquivadas** — indica que a conta foi arquivada
    - Se esta for uma conta principal, o arquivamento da conta interromperia a importação de dados de custos.
    - Se esta for uma conta secundária, a importação de dados de custos continuaria, e o arquivamento interromperia apenas os dados necessários para a credenciação antecipada, por exemplo, dados de utilização/compromissos, etc.
- **O que significam os diversos status no site Turbonomic?**
  - Conforme mencionado acima na tabela.
- **O status da conta Cloudability e o status do destino Turbonomic não coincidem nas telas de credenciais de fornecedores? Quais poderiam ser as razões?**

  - Os clientes atuais do Cloudability que estiverem atualizando para o Cloudability Premium precisam atualizar as credenciais de suas contas para obter as permissões mais recentes do Turbonomic.

    A discrepância no status da conta pode ser causada por alguns motivos:
    - A recertificação não foi realizada com base nos modelos/permissões mais recentes.
    - Se a recertificação foi realizada, é possível que tenha sido feita utilizando uma versão anterior do modelo e, desde então, algumas novas permissões foram adicionadas para o Cloudability Premium.
    - Caso a recertificação não resolva o problema, entre em contato com as equipes de suporte da IBM.
- **Onde posso encontrar a documentação sobre as fontes de dados individuais?**
  - Consulte a seção “**Como inserir dados no Cloudability** ” da documentação.

- **[Alertas por e-mail e banners sobre credenciais de fornecedores](../admin/email-alerts.html)**
- **[Gerenciar credenciais de fornecedores no Cloudability](../admin/manage-vendor-credentials.html)**
