---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "GCP Credenciamento usando ações em massa"
breadcrumb:
  - "Cloudability Premium"
  - "Obtendo dados em Cloudability"
  - "Conectar Google Cloud"
source_path: "admin/gcp-credentialing-bulk-actions.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# GCP Credenciamento usando ações em massa

**Visão geral**

A tela Bulk Actions on Vendor Credentials (Ações em massa nas credenciais do fornecedor) permite que os administradores concluam rapidamente o processo de credenciamento avançado em Cloudability.

Atualmente, isso está disponível para projetos GCP, onde é possível:

1. Salvar rapidamente várias contas não credenciadas
2. Verifique várias contas em massa para concluir o processo de credenciamento de maneira mais fácil e rápida.

**Pré-requisitos**

**Salvar novas credenciais**Certifique-se de ter optado pela credenciação automatizada dos projetos GCP para usar o ID da organização GCP durante a credenciação**Verificar credenciais**Sem necessidade de pré-requisitos, você poderá verificar todas as contas.

**Instruções**

Clicar em **Ações em massa** abrirá uma tela com várias guias.

Observação: A funcionalidade das guias individuais é independente uma da outra.

**Salvar novas credenciais**

Este recurso é aplicável às contas GCP que atendam aos pré-requisitos mencionados acima.

1. Esta tela não será exibida se não houver contas configuradas usando o ID da organização GCP

A tela exibe todas as contas com o status Credentials Needed (X vermelho). Para salvar as credenciais

1. Selecione as contas que precisam ser credenciadas.
2. Clique em **Review Selection (Revisar seleção** ).
3. Clique em **Salvar.**

Isso acionaria o processo de salvamento em massa e o botão de ações em massa seria desativado até que o processo fosse concluído.

1. Quando Salvar for concluído, as contas passarão para o status Não verificado.
2. Faça o download do modelo GCP de uma das contas que foi salva e aplique-o às contas GCP no console GCP.
3. Depois de concluído, acione a verificação de credenciais para as contas selecionadas na etapa anterior.

**Verificar credenciais**

Essa tela exibe todas as contas, exceto aquelas com status Credentials Needed (X vermelho).

Antes de acionar a verificação em massa, certifique-se de que o modelo foi baixado e aplicado no console GCP.

1. Selecione as contas que precisam ser verificadas.
2. Clique em "Review Selection" (Revisar seleção)
3. Clique em **Verify (Verificar).**

Isso acionaria o processo de verificação em massa e o botão de ações em massa seria desativado até que o processo fosse concluído.

Depois de concluídas, as contas passarão para o status de Credencial verificada ou Credencial inválida (devido a erros).

Observação: A duração da conclusão das ações em massa depende do número de contas.

**Tópico principal:** [Conectar Google Cloud](../admin/connect-google-cloud-premium.html)
