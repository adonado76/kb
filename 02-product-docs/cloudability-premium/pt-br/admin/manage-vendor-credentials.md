---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Gerencie as credenciais do fornecedor em Cloudability"
breadcrumb:
  - "Cloudability Premium"
  - "Administração"
  - "Credenciais do fornecedor"
source_path: "admin/manage-vendor-credentials.html"
images:
  - "images/archivecredential.png"
  - "images/deleting__a_credential_19_34_am_png.jpg"
  - "images/regenerate_cloudability_more_options.jpg"
  - "images/reverify-cloudability-icon.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Gerencie as credenciais do fornecedor em Cloudability

Visão geral

Esta página fornece informações sobre como gerenciar as credenciais do fornecedor em Cloudability.

Pré-requisitos 

- Acesso de administrador às credenciais do fornecedor Cloudability
- As contas de fornecedores devem ser credenciadas em Cloudability

**Introdução**

Para gerenciar as credenciais, clique em... no lado direito da conta e clique em uma das opções:

- Verificar novamente as credenciais
- Credenciais de arquivo
- Excluir credenciais

Reverificar uma credencial

Verificar novamente as credenciais implica verificar as conexões do fornecedor para garantir que todas as permissões estejam disponíveis e atualizadas com as alterações. Se você tiver excluído ou arquivado acidentalmente sua conta, fique tranquilo, pois seus dados serão preservados assim que você verificar novamente sua credencial.

**Para verificar novamente sua credencial manualmente:**

1. No menu principal, navegue até Settings > Vendor Credentials (Configurações > Credenciais do fornecedor ).

   Observação: o acesso à página “Credenciais do fornecedor” requer permissões de administrador.
2. Localize a conta que você deseja verificar novamente.
3. Passe o cursor sobre o ![Ícone de notas](../../../../03-media/cloudability-premium/images/regenerate_cloudability_more_options.jpg) ícone.
4. Clique no ícone ![reverificar o ícone da credencial](../../../../03-media/cloudability-premium/images/reverify-cloudability-icon.png) “Re-Verify” na lista suspensa.

   Isso inicia a validação e exibe uma marca de seleção em caso de sucesso.

**Para verificar novamente sua credencial em massa:**

Clique em **Bulk Actions (Ações em massa** ) depois que o fornecedor for selecionado. Isso abrirá uma tela com várias guias.

Clique na guia **Verify Credentials (Verificar credenciais** ).

Observação: Isso está disponível em AWS e GCP.

Essa tela exibe todas as contas, exceto aquelas com status Credentials Needed (X).

Para verificar as credenciais

1. Selecione as contas que precisam ser verificadas.
2. Clique em **Revisar seleção**
3. Clique em **Verify (Verificar).**

Isso acionaria o processo de verificação em massa e o botão de ações em massa seria desativado até que o processo fosse concluído.

Depois de concluídas, as contas passarão para o status de Credencial verificada ou Credencial inválida (devido a erros).

Observação: Se o número de contas for grande, isso pode levar alguns minutos.

Arquivar uma credencial

O arquivamento de uma credencial exclui o link do fornecedor, mantendo os dados históricos intactos. Isso é usado para contas desativadas.

1. No menu principal, navegue até Configurações > Credenciais do fornecedor.
2. Clique em Vendor Credentials (Credenciais do fornecedor ).
3. Localize a conta que você deseja arquivar.
4. Passe o cursor sobre o ![Ícone de notas](../../../../03-media/cloudability-premium/images/regenerate_cloudability_more_options.jpg) ícone.
5. Clique no ícone ![ícone de credencial de arquivo](../../../../03-media/cloudability-premium/images/archivecredential.png) “Arquivar” e selecione **“Confirmar”** quando solicitado.

   Observação: Depois de arquivada, a conta não poderá ser recuperada.

Excluir uma credencial

Para excluir uma credencial:

1. No menu principal, navegue até Configurações > Credenciais do fornecedor.
2. Localize a conta que você deseja excluir.
3. Passe o cursor sobre o ![Ícone de notas](../../../../03-media/cloudability-premium/images/regenerate_cloudability_more_options.jpg) ícone.
4. Selecione o ícone ![ícone de exclusão de credenciais](../../../../03-media/cloudability-premium/images/deleting__a_credential_19_34_am_png.jpg) “Excluir” e clique em “Confirmar” quando solicitado.

Sua conta é excluída.

Observação: a exclusão de uma conta de pagador remove todas as contas vinculadas ou subordinadas.

A exclusão de uma conta vinculada ou de uma conta secundária remove apenas a conta selecionada.

Perguntas Frequentes

- **O arquivamento de uma conta exclui os dados de Cloudability?**
  - Não, o arquivamento de uma conta não exclui os dados de Cloudability
- **A exclusão de uma conta** **exclui os dados de Cloudability?**
  - Não, a exclusão de uma conta não exclui os dados de Cloudability
- **Posso restaurar uma conta arquivada?**
  - Não, você precisará credenciar novamente a conta.
- **Posso arquivar uma conta não credenciada?**
  - Sim, você pode arquivar diretamente uma conta que não tenha credenciais.
- **Arquivei uma conta secundária (ligada a AWS, assinatura em Azure, projeto em GCP etc.). Ainda receberei os dados de custos relativos a ela?**
  - Sim Os dados de custo serão extraídos, pois os dados de custo estão vinculados à conta principal. O arquivamento ou a exclusão da conta secundária interromperia apenas os dados necessários para o credenciamento avançado, por exemplo, dados de utilização/compromissos etc.
- **Como devo baixar o modelo atualizado com as permissões mais recentes, caso tenha havido uma atualização das permissões?**

  - É possível baixar o modelo atualizado editando a conta de cobrança existente e baixando o modelo mais recente correspondente a ela. Após o download, siga as etapas de credenciamento indicadas após o download do modelo.
- **O que os diferentes ícones indicam na interface do usuário do Cloudability?**
  - Consulte a página [Credenciais do fornecedor](vendor-credentials.html)

**Tópico pai:** [Credenciais do fornecedor](../admin/vendor-credentials.html)
