---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Permissões de objeto de custo"
breadcrumb:
  - "Planning"
  - "Configuração e administração"
source_path: "it-planning/planning/manage-cost-object.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Permissões de objeto de custo

Observação: *somente os usuários com funções de administrador ou proprietário do processo orçamentário podem gerenciar as permissões de objetos de custo.*

As permissões de objetos de custo controlam quais usuários têm acesso a departamentos específicos dentro de um plano. Os administradores podem gerenciar o acesso globalmente em todo o ambiente ou no nível do plano individual para garantir visibilidade, colaboração e segurança de dados adequadas.

## Permissões globais versus permissões em nível de plano

Apptio O planejamento suporta dois níveis de gerenciamento de acesso:

**Permissões de objeto de custo global**

A página global **Cost Object Permissions** serve como modelo para definir padrões de acesso em toda a organização.

- Localizado em **Configuração → Dados de referência → Permissões de objeto de custo**.
- Define as configurações de acesso padrão que se aplicam quando novos planos são criados.
- As atualizações nas permissões de objeto de custo serão registradas no histórico de alterações.

**Permissões de usuário em nível de plano**

Lembre-se: o recurso Permissões de objetos de custo do nível do plano está ativado

Os usuários devem ter permissão **ManagePlans** (concedida por padrão às funções de administrador e proprietário do processo orçamentário) para visualizar ou editar permissões no nível do plano.

Cada plano inclui sua própria página de **permissões de usuário**, acessível em **Plan → Settings → User Permissions**, permitindo que os administradores atribuam ou ajustem o acesso diretamente em um plano.

- Controla o acesso do usuário no **nível do plano** para cada departamento.
- Substitui as permissões globais quando um plano é criado.
- Quando um plano é criado a partir de uma linha de base, as permissões de usuário do plano de linha de base são copiadas para o novo plano.

Quando o recurso **“Permissões de objeto de custo por nível de plano”** está ativado, as permissões globais não determinam mais o acesso automaticamente. Em vez disso:

- **Novo plano (sem linha de base):** as permissões globais do objeto de custo são copiadas para o plano no momento da criação.
- **Novo plano (com plano de referência):** as permissões de usuário do plano de referência são copiadas para o novo plano.

## Configuração de permissões de objetos de custo

**Para configurar as permissões globais:**

1. Navegue até **Configuration → Cost Object Permissions**.
2. Use a tabela para definir os níveis de acesso por usuário e departamento.
3. Use **Export → Export All** para baixar a lista de permissões como um arquivo.csv para atualizações em massa.

**Para configurar as permissões no nível do plano:**

1. Navegue até **Configurações** **(ícone de engrenagem)** → **Perfil da empresa**.
2. Selecione **Configuração Geral → Acesso e Permissões**
3. Certifique-se de que a caixa de seleção **Ativar permissões de objeto de custo no nível do plano** esteja marcada
4. Abra um plano e vá para **Plan → Settings → User Permissions**.
5. Use a tabela para definir os níveis de acesso por usuário e departamento.
6. Use **Permissões de exportação** no menu suspenso do nível da tabela (...) para baixar a lista de permissões como um arquivo.csv para atualizações em massa.
7. Use **Importar permissões** do menu suspenso do nível da tabela (...) para carregar o arquivo.csv modificado.

**Descrições de campo**

|  |  |
| --- | --- |
| **Campo** | **Descrição** |
| Objeto de custo | O identificador exclusivo do departamento ou centro de custos. |
| Nome do usuário | O usuário atribuído ao departamento. A lista é baseada nos usuários que têm acesso ao ambiente de planejamento em Apptio Frontdoor. |
| Nível de edição | Concede permissões de edição: Proprietário, Editar e enviar, Editar ou Somente visualização. Consulte [Fluxos de trabalho de](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=workflows-about-approval "(Abre em uma nova guia ou janela)") aprovação para obter mais detalhes. |
| Nível de aprovação | Define os direitos de aprovação (níveis 1 a 10) para aprovações multinível. Consulte [Fluxos de trabalho de](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=workflows-about-approval "(Abre em uma nova guia ou janela)") aprovação para obter mais detalhes. |
| Pode exibir colunas sensíveis | Permite a visualização de colunas marcadas como sensíveis no esquema de item de linha Trabalho nas guias Trabalho e Resumo. Consulte [*as Perguntas Frequentes: Ocultar dados confidenciais sobre mão de obra*](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=planning-faq-hide-sensitive-labor-data "(Abre em uma nova guia ou janela)")*.* |
| Pode visualizar informações financeiras confidenciais | Concede visibilidade aos itens de linha financeira da guia Resumo que são derivados de dados de mão de obra. Consulte [*as Perguntas Frequentes: Ocultar dados confidenciais sobre mão de obra*](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=planning-faq-hide-sensitive-labor-data "(Abre em uma nova guia ou janela)")*.* |

Importante:

Quando o recurso “Permissões de objeto de custo por nível de plano” está ativado

- Agora, os usuários devem receber acesso **explicitamente no nível do plano**.
- As permissões globais de objetos de custo, por si só, não fornecem acesso aos planos.

Nota:

- Os usuários com funções de **Administrador** ou **Proprietário do processo orçamentário** têm automaticamente acesso a **todos os Departamentos** por padrão. Todos os outros usuários devem ter acesso explicitamente concedido.
- Para restringir os proprietários de orçamento apenas aos departamentos que eles têm permissão para visualizar, ative **a opção Enforce View Permissions (Aplicar permissões de visualização** ) no **Company Profile (Perfil da empresa** ).
- Quando desativado, os usuários podem visualizar toda a hierarquia de departamentos, mas só podem interagir com os departamentos aos quais estão atribuídos.
- **As permissões do objeto de custo** são distribuídas em cascata pela hierarquia, a menos que um objeto de custo de nível inferior tenha permissões mais específicas definidas.

## Comportamento de acesso em comparações de planos

Se o recurso “Permissões de objeto de custo no nível do plano” estiver ativado, a comparação de planos funcionará da seguinte forma:

- Os dados da tabela Despesas serão exibidos com base nas permissões do usuário no **plano** de origem (de comparação). Por exemplo, se um usuário tiver acesso ao departamento D1 no plano *de* origem Plano A, mas não tiver acesso a D1 no plano de comparação *Plano B*, ele ainda poderá visualizar os detalhes da comparação para D1, pois o acesso é concedido no plano de origem.
- Os detalhes do relatório de Análise de Variação também serão exibidos com base nos direitos de acesso do usuário no plano de origem.
- Se os dados relacionados a mão de obra estiverem habilitados, o usuário deverá ter permissão tanto para as colunas relacionadas a mão de obra quanto para os dados financeiros em **todos os planos comparados**, a fim de visualizar os resultados da comparação.

## Publicar permissões de nível de plano para todos os planos

Observação: esta opção não está disponível quando o recurso **de aprovação em vários níveis** está ativado,

**Para aplicar permissões de nível de plano em massa a todos os planos** :

1. Selecione as permissões por meio da caixa de seleção na página **Permissões do** usuário (Plano > Configurações > Permissões do usuário)
2. Clique com o botão direito do mouse ou use o menu de overflow do nível da tabela (**...** ) para abrir o menu de ações e selecionar **Publicar em todos os planos**.
3. Clique **em Confirmar** para aplicar as permissões selecionadas a todos os planos.

**Para aplicar em massa permissões de nível de plano às Permissões globais de objeto de custo** :

1. Selecione as permissões por meio da caixa de seleção na página **Permissões do** usuário (Plano > Configurações > Permissões do usuário)
2. Clique com o botão direito do mouse ou use o menu de overflow do nível da tabela (**...** ) para abrir o menu de ações e selecionar **Publicar nos dados de referência**.
3. Clique em **Confirmar** para aplicar as permissões selecionadas em Configuração > Permissões de objeto de custo

## Publicar permissões globais de objeto de custo em todos os planos

Com **as permissões de usuário no nível do plano** ativadas, os administradores e os responsáveis pelo processo orçamentário podem publicar **permissões globais de objeto de custo** diretamente nos planos selecionados. Isso simplifica o gerenciamento centralizado de permissões e mantém vários planos alinhados sem a necessidade de intervenção manual.

**Para publicar permissões globais em todos os planos:**

1. Acesse Configuração **→** Permissões de objeto de custo
2. No **menu** de três pontos, selecione “**Publicar todas as permissões nos planos** ”.
3. Na caixa de diálogo “**Publicar configuração** ”, escolha uma das seguintes opções:
   1. **Atualizar permissões** : atualiza apenas as permissões correspondentes das Permissões globais do objeto de custo e das Permissões do usuário no nível do plano para os planos selecionados.
   2. **Substituir todas as permissões** : Remove todas as permissões existentes dos planos selecionados e as substitui totalmente pelas permissões globais do objeto de custo.
4. Use o menu suspenso de seleção múltipla **“Planos”** para escolher um, vários ou todos os planos aos quais as permissões devem ser publicadas.
5. Clique **em Confirmar**

**Resultado:** Todas as permissões de **“Permissões globais do objeto de custo”** são copiadas para **“Permissões do usuário no nível do plano”** dos planos selecionados, com base na opção de publicação escolhida.

## Excluir em massa as permissões de usuário de todos os planos

Observação: esta opção não está disponível quando o recurso **de aprovação em vários níveis** está ativado,

**Para excluir em massa as permissões de um usuário de todos os planos** :

1. Selecione as permissões por meio da caixa de seleção na página **Permissões do** usuário (Plano > Configurações > Permissões do usuário)
2. Clique com o botão direito do mouse ou use o menu de overflow do nível da tabela (**...** ) para abrir o menu de ações e selecionar “**Excluir permissão de todos os planos** ”.
3. Clique em **Confirmar** para excluir as permissões selecionadas de todos os planos e da seção Configuração > Permissões de objeto de custo.
