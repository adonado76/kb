---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Lançamentos recentes"
breadcrumb:
  - "Billing"
  - "Notas sobre a liberação"
source_path: "boit/billing/release-notes/whats-new.html"
images:
  - "resources/images/boit_images/jan17rn.png"
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Lançamentos recentes

Esta seção descreve apenas as alterações no conteúdo de faturamento pronto para uso, não na plataforma subjacente. Para atualizações no nível da plataforma, como o comportamento do TBM Studio e do servidor cliente, os leitores devem revisar as Notas de lançamento do TBM Studio e considerar as alterações aplicáveis juntamente com o que está documentado aqui.

As alterações listadas nesta seção limitam-se às atualizações fornecidas por meio dos Modelos de Componentes para Faturamento. O Billing Essentials está associado exclusivamente ao modelo de componente versão 200, enquanto o Billing Standard está associado ao modelo de componente versão 120 e anteriores. Ao revisar uma alteração, sempre confirme qual versão do modelo de componente ou edição de faturamento seu ambiente está usando para entender se essa alteração se aplica à sua implementação de faturamento.

## Anúncios importantes

Nenhum

## Fundamentos de faturamento (modelo versão 200) - 28 de fevereiro de 2025

- O suporte ao idioma japonês foi adicionado para melhorar a acessibilidade dos usuários.
- O relatório de gerenciamento de taxas agora inclui uma nova métrica de impacto do ajuste de taxas, fornecendo informações adicionais sobre as alterações nas taxas.
- Um novo relatório “Modelo de Custos de Faturamento” foi adicionado à coleção de relatórios “Faturamento” para fornecer um resumo dos fluxos de alocação de faturamento.

## Fundamentos de faturamento (modelo versão 200) – 17 de janeiro de 2025

Esta versão oferece as seguintes melhorias para aprimorar a experiência geral do usuário e proporcionar um gerenciamento mais eficiente dos processos de faturamento e upload de dados.

- **Relatórios aprimorados** : o Relatório administrativo do processo de faturamento foi integrado à coleção de faturamento, com permissões de controle de acesso baseado em função (RBAC) configuradas para restringir o acesso aos proprietários autorizados do processo de faturamento.
- **Exportação e arquivamento de lançamentos contábeis** : a guia Arquivo de lançamentos contábeis de faturamento agora permite que os usuários exportem lançamentos contábeis para um arquivo Excel (.xlsx) e criem uma tabela simplificada para fins de relatórios de auditoria, utilizando um script CopyTable para garantir a integridade dos dados.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/jan17rn.png)

Fig. n.º: IBM Apptio Relatório “Administração do processo de faturamento” do Billing, demonstrando o recurso de exportação de lançamentos contábeis.

- **Arquivamento de faturas** : A guia Arquivo de faturas apresenta um botão Copiar detalhes da fatura, que facilita o arquivamento de faturas criando uma cópia duplicada da fatura original, garantindo um registro permanente para fins de auditoria e conformidade.
