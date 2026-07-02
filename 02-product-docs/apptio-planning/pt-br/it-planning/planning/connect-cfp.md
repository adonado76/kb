---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Conecte-se a Cloudability Financial Planning"
breadcrumb:
  - "Planning"
  - "Integrações"
source_path: "it-planning/planning/connect-cfp.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Conecte-se a Cloudability Financial Planning

Importante: Disponível com *a assinatura* ***do Padrão de Planejamento*** Apptio

Lembre-se: a Nova Visualização está ativada.

A integração do Cloud Financial Planning (CFP) permite que o Apptio Planning incorpore orçamentos e previsões na nuvem diretamente do IBM Cloudability nos fluxos de trabalho de planejamento.

Com essa integração, as organizações podem alinhar os planos financeiros em nuvem criados no CFP com os orçamentos e previsões departamentais no Apptio Planning. Os itens da previsão da nuvem importados do CFP são automaticamente mapeados para as estruturas financeiras do Planning, reduzindo a duplicação de esforços e melhorando a consistência entre o planejamento financeiro da nuvem e da empresa.

A integração é opcional. Os clientes podem usar a guia Nuvem no Planejamento de Apptio para gerenciar gastos específicos da nuvem independentemente do CFP. Quando o CFP está conectado, os orçamentos e previsões importados da nuvem podem coexistir com as despesas da nuvem inseridas diretamente no Planning, proporcionando flexibilidade para complementar os dados do CFP quando necessário.

Esse recurso oferece suporte a um planejamento financeiro em nuvem mais preciso, simplificado e conectado entre sistemas.

**Principais recursos:**

**Guia Nuvem**

- Os clientes podem ativar uma nova **guia Nuvem** na Nova Visualização de Despesas para gerenciar os custos da nuvem diretamente nos Orçamentos e Previsões d Apptio.
- A guia Nuvem pode ser ativada independentemente e não requer integração com o CFP.

**Integração CFP**

- Os clientes podem conectar o Planejamento Financeiro na Nuvem ( Apptio ) ao Planejamento Financeiro na Nuvem (CFP) para importar orçamentos e previsões da nuvem do CFP em uma única ação.
- As despesas com nuvem importadas são automaticamente mapeadas para a estrutura financeira do Planning.

## Pré-requisitos

Antes de ativar o Cloud Planning ou a integração CFP:

1. Apptio É necessária uma licença padrão de planejamento.
2. A integração CFP suporta **apenas calendários fiscais gregorianos** (445 e 13‑Period não são suportados). A guia Nuvem funciona com todos os calendários fiscais suportados
3. **A nova experiência da página Despesas (Beta)** deve estar ativada.

## Habilitando o planejamento em nuvem e a integração CFP

***Observação:*** *as funções de administrador ou responsável pelo processo orçamentário são necessárias para realizar essas tarefas.*

1. Navegue até **Configurações** **(ícone de engrenagem)** → **Perfil da empresa**.
2. Certifique-se de que **a Experiência da página Novas despesas (Beta)** esteja ativada primeiro — a guia Nuvem não pode ser usada sem ela. Para ativar o recurso, siga estas etapas:
   - **Configuração geral** → **Acesso e permissões** → Selecione **Ativar nova experiência da página de despesas (Beta)**
3. Selecione **Planejamento em nuvem** → **Ativar planejamento em nuvem.** Esta etapa ativa a guia Nuvem em Despesas.
4. Para se conectar ao Cloud Financial Planning (CFP) d IBMCloudability, selecione **Planejamento em nuvem** → **Ativar integração com o Cloud Financial Planning.**
5. Clique no botão **Salvar e Sair**

## Permissões

Você pode controlar quem pode visualizar ou editar as despesas na nuvem:

- **ViewCloud -** Permite visualizar e editar linhas na guia Nuvem.
- **CanImportFromCloudability -** Permite importar dados do CFP e excluir as linhas importadas.
- Por padrão, ambas as permissões são concedidas às funções **de** administrador e **proprietário do processo orçamentário**, e **o proprietário do centro de custos** tem apenas a permissão **d ViewCloud**.

- **[Gerencie despesas com nuvem (sem integração com CFP)](../../it-planning/planning/manage-cfp-wo-int.html)**
- **[Configurar e gerenciar a integração do planejamento financeiro na nuvem](../../it-planning/planning/cfp-integration.html)**
