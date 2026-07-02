---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "AWS Tags"
breadcrumb:
  - "Cloudability Premium"
  - "Obtendo dados em Cloudability"
  - "Conexão com AWS - Guia de integração do cliente"
source_path: "admin/support-for-aws-tags.html"
images:
  - "images/Tag1.png"
  - "images/tag2.png"
  - "images/tag3.png"
  - "images/tag4.png"
  - "images/tag5.png"
  - "images/tag6.png"
  - "images/tag7.png"
  - "images/tag8.png"
  - "images/tag9.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# AWS Tags

Cloudability suporta as seguintes tags para o ` AWS `:

- **Tags de nível de recurso**
  - Esses arquivos fazem parte dos arquivos CUR do AWS e não são necessárias permissões adicionais no Cloudability para ativá-los
- **Tags no nível da conta**
  - Para obter tags no nível da conta de organizações do AWS, o Cloudability precisa de uma permissão adicional chamada
    - organizations:ListTagsForResource
  - Eles são exibidos no formato abaixo em Cloudability
    - cldy:aws:accountLevelTag:<tag chave>

      Observação: Se um cliente migrar do CUR antigo para o CUR 2.0, ele precisará reconfigurar suas tags e etiquetas no site Cloudability.

      Atualmente, as tags no nível da conta não estão disponíveis no Cloudability Gov.Diferença entre as tags CUR e CUR 2.0 do AWS (versão antiga)
  - Formato antigo das tags CUR
    - tags da AWS = aws:<tagkey>, por exemplo, aws:autoscaling:groupname
    - tags do usuário = <tagkey> p. ex., aplicativo
  - Formato das tags CUR 2.0
    - tags da AWS = aws\_<a chave da tag será separada por \_> = por exemplo, aws\_autoscaling\_group\_name
    - tags de usuário = user\_<tagkey>, por exemplo, user\_application

Para habilitar **as tags** no nível do recurso, certifique-se de ter habilitado as seguintes opções:

No Console do AWS — Ativar tags de alocação de custos

- No **painel de controle de faturamento e gestão de custos**, acesse as [**etiquetas de alocação de custos.**.](https://console.aws.amazon.com/billing/home#/tags "(Abre em uma nova guia ou janela)")
- Selecione as tags que você deseja incluir
- Observação – Preste atenção ao uso de maiúsculas e minúsculas (camel case); por exemplo, se você tiver “Name” ou “name” como chave de tag, ambas precisam estar ativadas para que sejam gravadas no CUR.
- **Sel** ecione “Ativar”.

Para habilitar **as tags** no nível da conta das organizações do AWS, o Cloudability precisa de uma permissão adicional chamada “ ***organizations:ListTagsForResource*** ”

**Se você já é cliente do AWS no Cloudability, pode ativar esse recurso usando duas opções:**

**Opção 1** — Atualize as credenciais da(s) sua(s) conta(s) de pagador principal do AWS para as quais você deseja habilitar as tags de nível de conta d AWS

**Opção 2** — Se você não quiser fazer uma nova autenticação, pode conceder a permissão mencionada acima a uma função do IAM d Cloudability, adicionada à sua conta do AWS, seguindo as etapas abaixo:

1. Acesse **o Painel do** IAM em AWS e clique em “**Funções** ”.![identificação](../../../../03-media/cloudability-premium/images/Tag1.png)
2. Procure a função que você atribuiu a Cloudability. Se você não tiver renomeado a função, ela deverá aparecer como “ **CloudabilityRole** ”. Clique nesta função.![identificação](../../../../03-media/cloudability-premium/images/tag2.png)
3. Na seção **“Políticas de permissão”**, clique em “ **CloudabilityManagementAccountPolicy** ”![](../../../../03-media/cloudability-premium/images/tag3.png)
4. Clique **em “Editar** ”.![identificação](../../../../03-media/cloudability-premium/images/tag4.png)
5. Mude para a visualização **Visual,** no canto superior direito. Expandir “**Organizações** ”.![identificação](../../../../03-media/cloudability-premium/images/tag5.png)
6. Verifique a permissão “ **ListTagsForResource** ”.

   ![identificação](../../../../03-media/cloudability-premium/images/tag6.png)
7. Selecione “**Próximo** ”.![identificação](../../../../03-media/cloudability-premium/images/tag7.png)
8. Na seção **“Revisão e salvamento”,** clique em “**Salvar alterações** ”.

   ![identificação](../../../../03-media/cloudability-premium/images/tag8.png)
9. Verifique se a permissão apresenta **uma marca de seleção verde na** guia **“Custo”** no painel de permissões (exibido ao clicar no ícone de olho da respectiva conta mestre) no site Cloudability, conforme mostrado abaixo:

![identificação](../../../../03-media/cloudability-premium/images/tag9.png)

Observação: pode levar algumas horas para que as permissões sejam atualizadas na interface do usuário do Cloudability Vendor Credentialis.

**Tópico principal:** [Conexão com o AWS - Guia de integração do cliente](../admin/aws-credentialing-premium-home.html)
