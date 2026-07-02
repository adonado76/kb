---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Códigos de itens de linha"
breadcrumb:
  - "Planning"
  - "Configuração e administração"
source_path: "it-planning/planning/line-item-codes.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Códigos de itens de linha

Observação: *as funções de administrador ou responsável pelo processo orçamentário são necessárias para gerenciar códigos de itens de linha.*

**Os códigos de item de linha** fornecem um identificador exclusivo para cada item de linha criado nas principais tabelas de planejamento. Esses códigos facilitam o rastreamento de alterações, a solução de problemas de atualizações e a referência a linhas específicas em planos enviados, instantâneos e histórico do Log de Eventos.

Os códigos aplicam-se às seguintes tabelas de itens:

- **Finanças** (guia Resumo e outras guias)
- **Ativo**
- **Contrato**
  - **Mão de Obra**
- **Atividade Laboral**

## Como funcionam os códigos de itens de linha

Cada código de item de linha é composto por duas partes:

1. **Prefixo** – identifica o tipo de item da linha
2. **Código numérico** – um número único gerado pelo sistema dentro do plano

Apptio O planejamento atribui automaticamente a parte numérica quando um novo item de linha é criado.

Planos de referência

Ao criar um novo plano a partir de um plano existente:

- Você pode copiar todos os códigos de itens da linha do plano de origem ou
- Gerar novos códigos de itens de linha

Para obter detalhes sobre a criação de planos, consulte [Criando planos](create-plan.html).

## Prefixos padrão

Cada tipo de item de linha tem seu próprio prefixo padrão:

|  |  |
| --- | --- |
| **Tipo de item de linha** | **Prefixo padrão** |
| Finanças | **F-** |
| Ativo | **A-** |
| Contrato | **C-** |
| Mão de Obra | **L-** |
| Atividade Laboral | **LAP-** |

## Alterando o prefixo do código de um item de linha

As alterações nos prefixos dos códigos dos itens de linha aplicam-se a todos os planos.

1. Navegue até **Configuração** → **Prefixo do código do item da linha**.
2. Selecione o **Tipo de Item de Linha** que deseja atualizar.
3. A caixa de diálogo **Editar prefixo** é exibida.
4. Insira um novo prefixo, seguindo estas regras:
   1. Deve ter **entre 1 e 10 caracteres**
   2. Não pode conter **dígitos**
   3. Não pode estar **vazio**
5. Selecione **Salvar**.

As alterações entram em vigor imediatamente para todos os planos do locatário.

## Códigos de itens de linha de origem

**Um código de item de linha de origem** identifica o item de linha de origem quando uma linha é criada a partir de outra fonte, como:

- **Delegações** (para contratos ou ativos) criadas pelo item original
- **Finanças geradas** (para ativos, contratos, mão de obra e atividades de mão de obra)

Os códigos de item da linha de origem aparecem quando um item da linha não foi criado manualmente. As informações financeiras geradas na guia Resumo não recebem códigos de item de linha, mas exibem um código de item de linha de origem que remete ao item de linha original.

Se [a opção Resumir finanças trabalhistas](labor-summarization.html "O recurso Summarize Labor Financials permite determinar como os dados de custo de mão de obra são agregados e apresentados na guia Summary (Resumo). Ele controla quais dimensões (por exemplo, centro de custo, conta, local) são usadas para agrupar e agrupar linhas de custo de mão de obra, garantindo que você obtenha o nível certo de visibilidade e confidencialidade para as finanças da mão de obra.") estiver ativada:

- Uma única linha financeira resumida pode ter origem em várias linhas de mão de obra
- Nesse caso, o Código do Item da Linha de Origem pode exibir **“varia”.**

## Plano de origem

O **Plano de origem** identifica o plano do qual um item de linha foi copiado.

Exemplo:

- O Plano B é criado a partir do Plano A
- O Plano C é criado a partir do Plano B

Para itens originalmente criados no **Plano A**, o Plano de Origem continuará a mostrar **o Plano A** tanto no Plano B como no Plano C.

## Códigos de itens na história de alterações

Os códigos de itens aparecem no **Log** de Eventos na coluna **Detalhes**, permitindo que você acompanhe a linha exata alterada em um plano.

O Log de Eventos exibe o **prefixo usado no momento em que o evento ocorreu** :

- Os eventos **anteriores** a uma alteração de prefixo mostram o prefixo *antigo.*
- Os eventos **após** a alteração mostram o *novo* prefixo

Isso significa que dois itens do mesmo tipo podem exibir prefixos diferentes, dependendo de quando foram modificados.

Para mais detalhes, consulte [Histórico de alterações](change-history.html "O Change History fornece uma trilha de auditoria das principais ações executadas no ambiente de planejamento. Ele permite que as organizações mantenham a transparência, atendam aos requisitos de conformidade e solucionem problemas de planejamento, rastreando quem alterou o quê, quando e como.").
