---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Resolução de problemas"
breadcrumb:
  - "Cloudability Premium"
  - "Governança"
source_path: "admin/governance-troubleshooting.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Resolução de problemas

Antes de solucionar o problema, verifique se os itens a seguir foram concluídos:

- Você tem a função Cloudability e as permissões corretas atribuídas.
- O aplicativo IBM Cloudability GitHub está instalado em sua organização GitHub.
- **Clientes HCP / TFE:** A tarefa de execução foi configurada.
- **Clientes da comunidade Terraform:**

  - Seus fluxos de trabalho do GitHub Actions estão configurados para invocar as ações de governança do Cloudability e os segredos necessários do GitHub estão configurados.
  - A saída do plano do Terraform está disponível no fluxo de trabalho do PR

## Detalhes da solução de problemas

| Problema | Possível causa | Resolução |
| --- | --- | --- |
| **a mensagem "Access Denied" (Acesso negado) é exibida na interface do usuário Cloudability**  **Recursos de governança ausentes - exemplo: incapacidade de criar políticas** | Atribuição incorreta de função/permissões em Cloudability | Certifique-se de que seu usuário tenha as permissões adequadas listadas na [seção “Visão geral das permissões”](governance-getting-started.html#governance-getting-started__overview) |
| **Não é possível instalar o aplicativo GitHub** | - Falta de permissões de administrador em GitHub.  - Tentativa de instalação a partir do local errado. | - Verifique se você é um **administrador da organização GitHub** ou se tem **acesso de administrador aos repositórios de destino**.  - Use o link **"Install GitHub App" (Instalar o aplicativo** ) na **guia Governance Settings (Configurações de governança** ) em Cloudability. |
| **GitHub O aplicativo foi instalado, mas não está funcionando** | - O aplicativo não recebeu acesso aos repositórios necessários. - Permissões ausentes durante a instalação. | Reinstale o aplicativo e garanta:   - Ele tem acesso somente de leitura aos metadados e às solicitações pull. - Ele tem acesso de leitura/gravação às verificações. - Ele é instalado em **todos os repositórios ou em repositórios selecionados** que contêm código do Terraform. |
| **Uma alteração de PR está bloqueada devido a uma política bloqueada com falha em Cloudability e não está sendo aprovada** |  | 1. Solicite uma revisão e aprovação de um usuário com a permissão **GovernanceFeaturePRApproval** ou a função **Cloudability Governance PR Approver**. 2. Se o aprovador estiver temporariamente indisponível e o PR precisar ser desbloqueado com urgência, você tem duas opções:    - Peça a um administrador do GitHub para remover temporariamente a regra de proteção de ramificação que exige que as execuções de verificação de governança sejam aprovadas antes da mesclagem.    - Peça a um usuário com permissão **GovernanceFeaturePolicyFullAccess** permissão ou a função **Cloudability Governance Policy Admin** para atualizar temporariamente o escopo da política para que ela não se aplique ao projeto associado a esse PR específico |
| **GitHub Falha na execução da ação (para usuários da Comunidade Terraform)** | - Segredos ausentes ou variáveis de ambiente incorretas.  - O plano do Terraform não foi gerado. | Verifique se os seguintes segredos de GitHub estão definidos:  - FD\_URL (por exemplo, [https://frontdoor.apptio.com](https://frontdoor.apptio.com/ "(Abre em uma nova guia ou janela)") ) - FD\_KEY e FD\_SECRET (de um usuário com a função " Cloudability Governance Automation User") - FD\_ENV\_ID - CLOUDABILITY\_HOST (por exemplo, https://api.cloudability.com )   Certifique-se de que seu fluxo de trabalho inclua:   - Geração de planos do Terraform - Etapas de recuperação de metadados - Etapa de busca do token do frontdoor   Nota: Observação: a Cloudability Governance espera apenas um terraform plan json de nível superior para cada invocação. |
| **Uma alteração de PR que falhou em uma política Cloudability fechada foi aprovada, mas a alteração não pode ser aplicada no HCP** | A tarefa HCP Run tem seu próprio nível de aplicação que pode ser definido como consultivo ou obrigatório. Se sua aplicação for definida como Obrigatória e uma política fechada falhar, a alteração não poderá ser aplicada, independentemente da aprovação. | Atualize o nível de aplicação da tarefa de execução para "Advisory" e acione outra execução para permitir que a alteração seja aplicada. |
| **Os repositórios não aparecem após a instalação do aplicativo “ GitHub ”** | O problema ocorre porque a instalação é dividida em duas etapas por meio de um fluxo de trabalho de aprovaçõ GitHub's. Quando um administrador aprovar a instalação pendente posteriormente, o contexto original da sessão será perdido. Como resultado, o Cloudability nunca é notificado de que a instalação foi concluída. | 1. Exclua a instalação atual, que está incompleta. 2. Reinstale o aplicativo usando uma conta do GitHub que tenha permissões para instalação imediata, a fim de concluir o processo em uma única etapa. |
