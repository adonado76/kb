---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Enviar, revisar, aprovar e devolver planos"
breadcrumb:
  - "Planning"
  - "Fluxos de trabalho e colaboração"
source_path: "it-planning/planning/aw-sub-return-approve.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Enviar, revisar, aprovar e devolver planos

Apptio O planejamento fornece um fluxo de trabalho estruturado para o envio, revisão, aprovação e devolução dos orçamentos departamentais. Isso garante que todos os dados do plano passem pelos níveis de aprovação apropriados antes que o plano seja finalizado.

Independentemente do status do envio, **todas as alterações ficam sempre visíveis no nível Todos os Departamentos**. O status do envio não restringe nem bloqueia edições. As etapas de envio e aprovação foram concebidas para proporcionar visibilidade, coordenação e responsabilidade, e não para restringir as alterações ao plano.

## Envio de planos

Quando um departamento apresenta seu plano:

- É criado um **instantâneo** da versão enviada (somente leitura).
- Se as notificações por e-mail estiverem ativadas, os aprovadores apropriados serão notificados com base no fluxo de trabalho de aprovação em uso.

Você pode enviar planos na página **Despesas** ou na página **Status**.

**Enviar a partir da página Despesas**

1. No menu **Plano**, selecione um plano.
2. Navegue até **Plano** → **Despesas**.
3. No menu suspenso **Departamento**, selecione um departamento.
4. Abra o **menu de reticências (⋮)** e selecione **Enviar**.
5. *(Opcional)* Digite um nome para o instantâneo.
6. Clique em **Enviar**.

**Enviar a partir da página de status**

1. Navegue até **Plano** → **Status**.
2. Para enviar vários departamentos, marque as caixas de seleção dos departamentos e selecione **Ações** → **Enviar selecionados.**
3. Para enviar um departamento, selecione **Enviar** na coluna **Ações**.

**O que acontece após o envio**

- **Aprovações hierárquicas:** o *proprietário do departamento pai* do nível seguinte é notificado.
- **Aprovações em vários níveis:** os aprovadores do nível 1 são notificados primeiro, depois os do nível 2 e assim por diante.

**Notas para aprovações hierárquicas:**

- Envio de um **departamento de grupo** :
  - Aprova automaticamente todos os departamentos subordinados
  - Cria instantâneos para todos os filhos
  - Os departamentos infantis já aprovados permanecem inalterados
- Um Departamento do Grupo passa para **Em andamento** quando pelo menos uma criança envia um plano.
- Se um plano for **devolvido**, a versão enviada será marcada como *Devolvida*. Qualquer edição cria uma **nova versão**.

## Aprovação e devolução de planos

Os usuários com permissões de aprovação podem aprovar ou devolver planos a qualquer momento. Se vários usuários compartilharem o mesmo nível de aprovação, apenas uma aprovação será necessária para avançar.

Nas aprovações hierárquicas, os usuários com nível de edição **de proprietário** atuam como aprovadores. Quando um proprietário de nível superior aprova um plano, todas as aprovações de nível inferior são automaticamente concluídas.

**Revise os planos na página Despesas**

1. Navegue até **Plano** → **Despesas**.
2. Selecione um departamento.
3. *(Opcional)* Ative **a opção Exibir atualizações** para mostrar apenas os itens alterados.
4. Abra o **menu de reticências (⋮)** → selecione **Aprovar** ou **Devolver**.
5. Ao devolver um plano, você pode adicionar um comentário.

**Revise os planos na página de status**

1. Navegue até **Planejamento** → **Status**.
2. *(Opcional)* Alternar **Incluir objetos de custo somente para visualização** (requer *Aplicar permissões de visualização* ).
3. Aprovar/devolver usando:
   1. **Coluna Ações** (Aprovar, Devolver, Comentar) ou
   2. **Ações** em massa selecionando as caixas de seleção do Departamento e, em seguida**, Ações** → **Aprovar selecionados** ou **Devolver selecionados**

Se as notificações por e-mail estiverem ativadas, a aprovação de um plano aciona o envio de um e-mail para o aprovador do próximo nível.

Nas aprovações hierárquicas, devolver um plano envia um e-mail para o proprietário do nível anterior, e o plano deve ser devolvido passo a passo ao longo da hierarquia.

Nas aprovações multinível, a devolução de um plano notifica todos os usuários com acesso de edição ao departamento folha, e o plano é devolvido diretamente ao proprietário original do departamento, ignorando os níveis de aprovação intermediários.

## Aprovações hierárquicas: ações e comportamento de aprovação

|  |  |  |
| --- | --- | --- |
| **Ação** | **Departamento de Folhas** | **Departamento do Grupo** |
| **Enviar** | Atualiza o status do departamento para **Enviado** e cria um instantâneo da versão enviada. Os usuários com nível de edição “Proprietário” para o departamento enviado recebem uma notificação por e-mail para revisar e aprovar o plano. | Atualiza o status do departamento do grupo para **“Enviado”**, aprova automaticamente todos os departamentos filhos e cria instantâneos para todos os departamentos folha. As crianças já aprovadas não são afetadas. Os usuários com nível de edição "Proprietário" do Group Department enviado recebem uma notificação por e-mail para revisar e aprovar o plano. |
| **Aprovar** | Atualiza o status do departamento para **Aprovado.** O proprietário de nível seguinte na hierarquia do departamento recebe uma notificação por e-mail para revisar e aprovar o plano. | Atualiza o status do departamento do grupo e de quaisquer departamentos subordinados para **Aprovado**. O proprietário de nível seguinte na hierarquia do departamento recebe uma notificação por e-mail para revisar e aprovar o plano. |
| **Voltar** | Atualiza o status do departamento para **Devolvido**. Os usuários com nível de edição "Proprietário" para o departamento devolvido recebem uma notificação por e-mail para revisar e reenviar o plano. | Atualiza o status do departamento de grupo como **devolvido**. Os Departamentos filhos permanecem inalterados, a menos que sejam explicitamente devolvidos por seus proprietários. A devolução de um plano envia um e-mail para o proprietário do nível anterior, e o plano deve ser devolvido passo a passo ao longo da hierarquia. |

## Aprovações em vários níveis: ações e comportamento de aprovação

|  |  |
| --- | --- |
| **Ação** | **Comportamento** |
| **Enviar** | Atualiza o status do departamento para **Enviado** e cria um instantâneo da versão enviada. Os aprovadores de nível 1 recebem uma notificação por e-mail solicitando que revisem e aprovem o plano enviado. |
| **Aprovar** | Atualiza o status do Departamento para **L[n] Aprovado**. Os aprovadores no nível [ n+1 ] recebem uma notificação por e-mail para revisar e aprovar o plano. Depois que todos os níveis de aprovação forem concluídos, o status do Departamento será definido como **Aprovado.** |
| **Voltar** | Atualiza o status do Departamento para **Devolvido**. Os usuários com acesso de edição são notificados por e-mail para revisar e reenviar o plano. |

## Desbloqueio de um plano

Os planos enviados, aprovados ou devolvidos são somente para leitura. Os usuários com nível **de edição e envio** ou **edição** de proprietário podem desbloquear um plano para continuar editando. O desbloqueio redefine o status do Departamento para **Em andamento** e torna o plano editável.

1. Navegue até **Plano** → **Despesas**
2. Selecione um departamento folha e clique **em Desbloquear este objeto de custo** na mensagem do banner ou selecione o menu Versões do plano e clique em **Desbloquear**.
3. Como alternativa, em **Plano** → **Status**, marque a caixa de seleção Departamento e, em seguida, selecione **Ações** → **Desbloquear selecionados**.

## Finalizando os planos

Quando todos os departamentos forem aprovados, os administradores ou responsáveis pelo processo orçamentário poderão **finalizar o plano** na página Despesas para bloqueá-lo.

1. Navegue até **Plano** → **Despesas**.
2. Selecione **Todos os Departamentos** no menu suspenso Departamento.
3. Abra o **menu de reticências (⋮)** → selecione **Finalizar plano**.
4. Selecione **Finalizar**.

Se houver alterações não enviadas, você será notificado. Essas alterações serão incluídas no plano finalizado, mas não terão o status **de Aprovadas**. Você pode reabrir um plano a qualquer momento para fazer alterações adicionais.
