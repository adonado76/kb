---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Configurar e gerenciar a integração do planejamento financeiro na nuvem"
breadcrumb:
  - "Planning"
  - "Integrações"
  - "Conecte-se a Cloudability Financial Planning"
source_path: "it-planning/planning/cfp-integration.html"
images:
  - "resources/images/it_planning_images/cfp-drn.png"
  - "resources/images/it_planning_images/cfp-liv.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Configurar e gerenciar a integração do planejamento financeiro na nuvem

Observação: as funções de administrador ou responsável pelo processo orçamentário são necessárias para realizar essas tarefas.

Importante: Disponível com *a assinatura* ***do Padrão de Planejamento*** Apptio

Lembre-se: a Nova Visualização está ativada.

As configurações de integração do Cloud Financial Planning (CFP) são definidas **por plano** nas Configurações do plano. Essas configurações estabelecem a conexão entre o Planejamento do Apptio e o **Plano CFP** específico e **a Visualização de Propriedade de Custos**, e definem como as dimensões do Planejamento (Departamento, Centro de Custos, Conta, etc.) mapa das estruturas de propriedade de custos da CFP.

**Para configurar as definições de integração CFP**

1. **Abra o plano** que deseja conectar ao CFP.
2. Na navegação à esquerda, vá para **Configurações do plano → Integração do Cloud Financial Planning**.
3. Na página Configurações de integração do CFP, revise os **detalhes do ambiente gerado** (somente leitura):
   - **Domínio** – Seu domínio de cliente Apptio
   - **Nome do ambiente** – O nome do seu ambiente Apptio
   - **Cloudability Moeda** – A moeda configurada no CFP
4. No menu suspenso **Nome da** visualização, selecione a visualização de propriedade de custos CFP apropriada.
5. Selecione o **nome do plano** no CFP. Apenas os planos CFP com o **mesmo ano de início** que o plano de planejamento atual Apptio serão exibidos.
6. Configure os mapeamentos padrão usados quando os valores de propriedade de custo CFP não têm mapeamentos explícitos:
   - **Departamento padrão** – Aplicado quando um valor de propriedade de custo não tem mapeamento no nível do departamento
   - **Centro de custo padrão** – Aplicado quando não existe nenhum mapeamento de centro de custo
   - **Conta padrão** – Aplicada quando não existe nenhum mapeamento de conta
   - **Projeto padrão** *(opcional)* – Usado se for necessário mapear o projeto
   - **Fornecedor padrão** *(opcional)* – Usado quando o mapeamento do fornecedor é relevante
7. Selecione o comportamento **Preencher para a frente** que determina como os dados CFP são estendidos para os anos futuros em um planejament Apptio :
   - **Nenhum** – Nenhum dado é copiado para anos não presentes no Plano CFP
   - **Copiar último período** – O período final do Plano CFP é copiado para todos os anos restantes
   - **Copiar o ano anterior** – O último ano do Plano CFP é copiado para todos os anos restantes

## Para configurar mapeamentos de dados

Essa configuração define como **os valores** de Propriedade de Custos no CFP são mapeados para as **dimensões de negócios** correspondentes no Planejamento d Apptio. Esses mapeamentos garantem que todas as despesas importadas do CFP sejam atribuídas às dimensões corretas do Planejamento.

1. Cada valor **de Propriedade de Custo** deve ser mapeado para um **Departamento**, **Centro de Custo** e **Conta** para que o mapeamento seja válido.
2. Você também pode, opcionalmente, mapear os valores de Propriedade de Custos para as dimensões **Projeto** e **Fornecedor**.
3. Para criar um mapeamento, selecione um valor **de Propriedade de custo** no menu suspenso e escolha os valores apropriados **de Departamento**, **Centro de custo**, **Conta**, **Projeto** e **Fornecedor** nas respectivas listas.
4. Você também pode **fazer upload de mapeamentos por meio de CSV** para atualizações em massa.
5. Durante a importação, o Planejamento de Apptio realiza a validação dos dados de referência para garantir que o **Departamento** mapeado esteja alinhado com o Centro de Custos e que o **Projeto esteja alinhado com o Centro de Custos**.

Observação: a verificação de validação dos dados de referência é realizada durante o processo de importação do CFP para garantir que o Departamento mapeado esteja corretamente associado ao Centro de Custos selecionado e que o Projeto mapeado seja válido para esse Centro de Custos.

## Importar dados do plano do Cloud Financial Planning

Observação: as funções de administrador ou responsável pelo processo orçamentário são necessárias para realizar essas tarefas. Além disso, funções de usuário personalizadas com permissão CanImportFromCloudability também podem realizar essas tarefas.

***Para importar dados do Cloud Financial Planning:***

- Abra seu plano e navegue até a guia **Nuvem** em **Despesas** > **Nova visualização.**
- No menu de ações da tabela (botão com três pontos), selecione **Importar itens da linha de nuvens.**
- Na caixa de diálogo de confirmação da importação, verifique o nome do plano CFP e o nome da visualização e clique no botão **Importar**.
- Quando a importação estiver concluída, será exibida uma mensagem de sucesso com o número de linhas importadas.
- Em caso de erros de importação, os detalhes serão exibidos juntamente com uma opção para baixar o arquivo de ajuda CSV para uma análise mais aprofundada da importação com falha.

***Comportamento de importação:***

1. As linhas importadas seguem a configuração **Preencher para frente** definida em Configurações do plano:
   - **Nenhum** – Não há projeções para os próximos anos.
   - **Copiar último período** – O período final do Plano CFP é copiado para os anos futuros.
   - **Copiar o ano anterior** – O último ano do Plano CFP é copiado para os anos futuros.
2. Todas as linhas importadas do CFP são criadas como **Linhas Externas**, o que significa que são **somente de leitura** para todos os usuários.
3. Cada linha importada recebe um **código** **de item de linha** exclusivo com o prefixo **CL** na primeira vez em que é importada para o plano.
4. As importações subsequentes do CFP **substituem as linhas importadas do CFP existentes** com valores atualizados, mantendo os mesmos códigos de item de linha.
5. As linhas importadas pelo CFP são adicionadas à **versão** mais recente do objeto de custo e ficam visíveis apenas nos departamentos em que o usuário importador tem acesso de edição.
6. As linhas de nuvem importadas também aparecem em **Despesas → Resumo** no modo somente leitura com **Tipo** **de item de linha** = Nuvem.
7. A importação é **bloqueada** se o departamento de destino estiver bloqueado devido à apresentação do orçamento.
8. Para planos com várias moedas, todas as conversões de moeda seguem as **Taxas de Várias Moedas** definidas em Apptio Planning.
9. Para remover todas as linhas importadas do CFP da guia Nuvem, use **a opção Excluir itens de linha do Cloudability** no menu **de ações da tabela**. Esta ação exclui *todas* as linhas importadas pelo CFP para o plano.

**Visão detalhada do item da linha CFP**

Observação: o usuário precisa de permissão no Plano CFP para visualizar a exibição detalhada dos itens.

1. As linhas importadas do CFP são exibidas no Apptio Planning como entradas resumidas com base na configuração de mapeamento de dados definida nas configurações de integração do Cloud Financial Planning do plano.
2. Para visualizar os detalhes subjacentes, os usuários podem clicar no botão **Detalhes** na coluna **Detalhes** da guia Nuvem.
3. Isso abre uma **gaveta somente leitura** que exibe as linhas do plano CFP.

![imagem da visualização do item da linha cf](../../../../../03-media/apptio-planning/resources/images/it_planning_images/cfp-liv.png)

**Notificação de atualização de dados CFP**

**Observação:** para visualizar esta notificação, é necessário ter **CanImportFromCloudability** permissão.

1. Quando são feitas atualizações no Plano conectado no CFP, o Apptio Planning exibe um **banner de notificação** para os usuários com acesso apropriado — incluindo **administradores**, **proprietários do processo orçamentário** e usuários com permissão **CanImportFromCloudability** — indicando que novos dados estão disponíveis para importação.
2. Para atualizar os dados na guia Nuvem, os usuários podem simplesmente **reimportar os itens de linha Cloudability**, o que atualiza o plano com as informações mais recentes do CFP.

![imagem da notificação de atualização dos dados cf](../../../../../03-media/apptio-planning/resources/images/it_planning_images/cfp-drn.png)

**Tópico principal:** [Conecte-se a Cloudability Financial Planning](../../it-planning/planning/connect-cfp.html)
