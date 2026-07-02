---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "AWS Credenciamento usando ações em massa"
breadcrumb:
  - "Cloudability Premium"
  - "Obtendo dados em Cloudability"
  - "Conexão com AWS - Guia de integração do cliente"
source_path: "admin/aws-credentialing-bulk-actions.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# AWS Credenciamento usando ações em massa

**Visão geral**

A tela Bulk Actions on Vendor Credentials (Ações em massa nas credenciais do fornecedor) permite que os administradores concluam rapidamente o processo de credenciamento avançado em Cloudability.

Atualmente, isso está disponível para contas vinculadas ao AWS, onde é possível:

1. Salvar rapidamente várias contas não credenciadas
2. Atualizar várias contas
3. Verifique várias contas em massa para concluir o processo de credenciamento de maneira mais fácil e rápida.

**Pré-requisitos**

**Salvar novas credenciais:**Verifique se você optou pelo credenciamento automatizado de contas vinculadas para AWS durante o credenciamento**.****Verificar credenciais:**Não é necessário nenhum pré-requisito, e você poderá verificar todas as contas.

**Instruções**

Clicar em **Ações em massa** abrirá uma tela com várias guias.

Observação: A funcionalidade das guias individuais é independente uma da outra.

**Salvar novas credenciais**

Esse recurso é aplicável às contas AWS se os pré-requisitos mencionados acima forem atendidos.

1. Essa tela não será exibida se não houver contas configuradas usando o credenciamento automatizado de contas vinculadas.

A tela exibe todas as contas com o status Credentials Needed (X vermelho). Para salvar as credenciais

1. Selecione as contas que precisam ser credenciadas.
2. Clique em **Revisar seleção**
   1. Adicione a região SCP conforme necessário para AWS.
3. Clique em **Salvar.**

Isso acionaria o processo de salvamento em massa e o botão de ações em massa seria desativado até que o processo fosse concluído.

1. Quando o salvamento for concluído, as contas passarão para o status Não verificado.
2. Faça o download do modelo Cloud Formation de uma das contas que foram salvas e aplique-o às contas AWS no console AWS como um stackset.
3. Depois de concluído, acione a(s) conta(s) de verificação para as contas selecionadas na etapa anterior.

**Atualizar credenciais**

A tela exibe todas as contas, exceto aquelas com status Credentials Needed (X). Para atualizar as credenciais

1. Selecione as contas que precisam ser atualizadas.
2. Clique em "Review Selection" (Revisar seleção)
   1. Adicione a região SCP conforme necessário para AWS.
3. Clique em **Salvar.**

Isso acionaria o processo de atualização em massa e o botão de ações em massa seria desativado até que o processo fosse concluído.

Depois de concluído, acione Verify Credentials (Verificar credenciais).

**Verificar credenciais**

Essa tela exibe todas as contas, exceto aquelas com status Credentials Needed (X).

Antes de acionar a verificação em massa, certifique-se de que o modelo foi baixado e aplicado ao console AWS para as contas vinculadas ao AWS. Para verificar as credenciais

1. Selecione as contas que precisam ser verificadas.
2. Clique em **Revisar seleção**
3. Clique em **Verify (Verificar).**

Isso acionaria o processo de verificação em massa e o botão de ações em massa seria desativado até que o processo fosse concluído.

Depois de concluídas, as contas passarão para o status de Credencial verificada ou Credencial inválida (devido a erros).

Observação: Se o número de contas for grande, isso pode levar alguns minutos.

**Tópico principal:** [Conexão com AWS - Guia de integração do cliente](../admin/aws-credentialing-premium-home.html)
