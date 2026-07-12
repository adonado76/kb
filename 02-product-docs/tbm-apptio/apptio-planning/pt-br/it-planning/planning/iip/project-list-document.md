---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Gerencie projetos"
breadcrumb:
  - "Planning"
  - "Planejamento de projetos"
source_path: "it-planning/planning/iip/project-list-document.html"
images:
  - "resources/images/it_planning_images/sync-data.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Gerencie projetos

Observação: Disponível com a assinatura Apptio do Planning Standard

Lembre-se: *o recurso de Planejamento Integrado de Investimentos (IIP) está ativado.*

O planejamento de investimentos é um processo contínuo impulsionado por mudanças nas prioridades, condições de mercado e necessidades organizacionais. Embora os clientes normalmente elaborem seu orçamento anual durante a temporada de planejamento, eles devem manter a flexibilidade para:

- Adicione projetos recém-aprovados ou financiados ao longo do ano
- Remova projetos que não são mais relevantes
- Atualize os atributos do projeto à medida que os planos evoluem

O recurso **Lista de** projetos permite essa flexibilidade, permitindo que usuários selecionados gerenciem projetos diretamente em cada plano.

## Quem pode gerenciar projetos?

As seguintes funções podem adicionar, editar ou excluir projetos em um plano:

1. **Admin**
2. **Responsável pelo processo orçamentário**
3. **Gerente de Portfólio IIP**
4. Usuários com a **IIPProjectManage** permissão

Os projetos são tratados como uma **dimensão no nível do plano**, o que significa que podem ser gerenciados de forma independente dentro de cada plano, sem modificar os dados de referência globais.

## Projetos globais vs. Lista de projetos no nível do plano

Apptio O planejamento apoia a gestão de projetos em dois níveis:

**Dimensão do projeto global (dados de referência)**

**A dimensão global do projeto** é a sua lista principal de projetos em todo o sistema. Representa a fonte oficial de verdade utilizada em todo Apptio o Planejamento.

**Comportamentos-chave:**

- Ao criar um plano **sem uma linha de base**, todos os projetos globais são copiados para o novo plano.
- Os valores reais carregados no Spend Management são validados em relação a essa dimensão global.
- Se um código de projeto nos dados reais **não** existir na dimensão global Projeto, seu valor será apagado durante o upload.
- Quaisquer atualizações na dimensão global do projeto **não** são automaticamente incorporadas aos planos existentes.

**Lista de projetos no nível do plano**

Cada plano contém sua própria **Lista de Projetos**, que é uma cópia local dos projetos usados **apenas dentro desse plano**. Isso permite que os responsáveis pelo orçamento e os administradores personalizem o conjunto de projetos para cada plano anual ou previsão sem afetar a lista mestre global.

**Comportamentos-chave:**

- A Lista de Projetos é criada durante a criação do plano (a partir da dimensão global ou do plano de referência).
- Você pode **adicionar**, **editar** ou **excluir** projetos no nível do plano sem afetar a dimensão global do projeto.
- As alterações personalizadas feitas diretamente em um plano (por exemplo, novos códigos de projeto) são aplicadas apenas a esse plano, a menos que sejam adicionadas separadamente à dimensão global.
- As listas de projetos no nível do plano seguem o mesmo esquema da dimensão global, garantindo a consistência em todos os planos.

## Gerenciamento de projetos

**A Lista de projetos** do nível do plano permite que usuários selecionados adicionem, editem ou excluam projetos dentro de um plano. Essas ações ajudam a manter um portfólio de projetos atualizado ao longo do ciclo de planejamento.

**Adicionar um projeto**

1. No painel de navegação à esquerda, selecione **Plano** > **Projetos**.
2. Isso abre a página **Lista de projetos**.
3. No menu suspenso **“Planos”**, selecione o plano ao qual deseja adicionar um novo projeto.
4. Selecione **Adicionar projeto** (ícone +). É exibida a caixa de diálogo **Novo projeto**.
5. Insira os detalhes do projeto:
   1. **Código** – Um identificador único do projeto dentro do plano selecionado. *(obrigatório)*
   2. **Nome** – Nome do projeto.
   3. **Código pai** – Código do grupo de projetos pai. Este campo é obtido a partir dos dados de referência **do Grupo de Projetos**.
   4. **Permitir qualquer centro de custos** – Ative esta opção para permitir que todos os centros de custos cobrem pelo projeto.
   5. **C** **ódigo do centro de custos padrão** – Selecione o centro de custos padrão associado ao projeto.
   6. **C** **ódigo do centro de custos** – Selecione os centros de custos disponíveis para uso no projeto.
6. Clique em **Adicionar** para criar o novo projeto.

**Editar atributos do projeto**

1. Na Lista de projetos, selecione **Editar** (ícone de lápis) ao lado do projeto que deseja modificar.

   É exibida uma caixa de diálogo **Editar projeto**.
2. Atualize os atributos necessários. As alterações são salvas automaticamente.

**Excluir um projeto**

1. Na Lista de Projetos, selecione um ou mais projetos para excluir.
2. Ou:
   1. Clique com o botão direito do mouse para abrir o menu de contexto e selecione **Excluir** ou
   2. Selecione **Excluir projetos selecionados** no menu de reticências.

      *Para selecionar vários projetos, mantenha pressionada a tecla Command no Mac ou a tecla Control no Windows enquanto seleciona as linhas.*
3. Se algum projeto selecionado for usado em linhas de despesas, uma caixa de diálogo de confirmação será exibida.
4. Selecione **Confirmar** para continuar.

**Observações importantes sobre a exclusão de projetos**

- A exclusão de um projeto remove-o da **Lista de Projetos** no nível do plano.
- Quaisquer linhas de despesas em que **o Projeto** seja um *atributo obrigatório* (por exemplo, **Atividade de Mão de Obra** ) serão excluídas.
- Para linhas de despesas em que o projeto *não* é obrigatório (por exemplo, **contratos**, **ativos**, **outras despesas** e **mão de obra** ), o valor do projeto será apagado, mas a linha de despesas permanecerá.

**Importar lista de projetos**

Você pode importar dados do projeto usando um arquivo.csv.

1. Selecione **Importar do arquivo** no menu de reticências.
2. Carregue o arquivo.csv.

   **Importante:**
   - A importação permite **adicionar novos projetos** e **atualizar atributos de projetos existentes**.
   - **A exclusão de projetos por meio da importação não é suportada.**

   Para importar a Lista de Projetos do Cálculo de Custos Apptio, consulte [Importar Lista de Projetos do Cálculo de Custos Apptio](../import-pl-acost.html).

**Exportar lista de projetos**

Para exportar a lista de projetos:

1. Selecione **Exportar para arquivo** no menu de reticências.
2. O sistema baixa a Lista de Projetos como um arquivo.csv.

**Publicar lista de projetos nos dados de referência**

Para publicar a lista de projetos no nível do plano, acesse Configuração > Dados de referência > Projeto:

1. Selecione **Publicar para dados de referência** no menu de reticências.
2. A Lista de projetos é importada para os dados de referência do projeto.
3. Publique os dados de referência do projeto para disponibilizar dados de referência atualizados para os planos.

## Sincronizando projetos globais e em nível de plano

Porque os planos fazem referência à sua própria Lista de Projetos local:

- As alterações nos projetos globais **não são automaticamente propagadas** para os planos existentes.
- Para obter atualizações globais (adições/exclusões/alterações de atributos), use **Projetos > Lista > Atualizar dados do projeto**.
- O processo de atualização irá adicionar, remover ou modificar projetos no nível do plano, dependendo do que foi alterado nos dados de referência globais do projeto.

Isso garante que cada plano permaneça estável ao longo do ciclo de planejamento, ao mesmo tempo em que dá aos administradores controle quando as definições do projeto evoluem.

![sincronização de dados de imagem](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/sync-data.png)

**Como as alterações do projeto são aplicadas**

Quando você executa **Atualizar dados do projeto** em um plano, Apptio compara a Lista de projetos do plano com a dimensão **Dados de referência** globais > Projeto e aplica as alterações de acordo com as regras abaixo.

1. **Um projeto foi excluído dos Dados de Referência globais, mas existe no plano.**

   Se um projeto for removido da dimensão global Projeto, as seguintes alterações ocorrerão quando a atualização for aplicada:
   - **As linhas de atividade de mão de obra** associadas a esse projeto são excluídas, incluindo todas as informações financeiras relacionadas à atividade de mão de obra.
     - Elas aparecem como *Linhas a serem excluídas* na caixa de diálogo de confirmação.
   - Para as linhas de despesas **com mão de obra, contratos, ativos e outras,** nas quais o projeto *não* é um atributo obrigatório, o valor do projeto é apagado.
     - Elas aparecem como *Linhas a serem atualizadas*.
   - O projeto é removido da Lista de Projetos do plano.
2. **Um novo projeto é adicionado aos Dados de Referência globais**

   Se um projeto existir globalmente, mas não no plano:
   - O novo projeto é adicionado à Lista de Projetos do plano.
3. **Um projeto foi criado apenas no plano (não globalmente)**

   Se um projeto existir no plano, mas não nos Dados de Referência globais:
   - Esse projeto é removido do plano durante a atualização.
   - Qualquer impacto nas despesas segue as mesmas regras descritas no **Cenário 1** (exclusão de projetos).
4. **Um centro de custos é removido de um projeto nos dados de referência globais.**

   Se um centro de custos for removido globalmente de um projeto, mas ainda estiver atribuído no plano:
   - Todas **as linhas de Atividade de Trabalho** que utilizam essa combinação de projeto/centro de custos são excluídas, juntamente com suas informações financeiras.
   - Para quaisquer outros tipos de despesas em que seja necessário um centro de custos, o valor do projeto é zerado e a despesa é reatribuída ao Departamento.
   - Essas ações aparecem como *Linhas a serem excluídas* ou *atualizadas* na caixa de diálogo de confirmação.

   Importante: se você deseja preservar as despesas associadas a um centro de custos antes de removê-lo de um projeto, reatribua essas despesas a um centro de custos válido antes de aplicar a atualização.
5. **Conflitos com outras atualizações de dados de referência pendentes**

   Se houver atualizações pendentes para outras dimensões de dados de referência (como Centro de Custos ou Grupo de Projetos), a atualização do projeto será **bloqueada** para evitar conflitos. Uma mensagem solicitará que você aplique essas atualizações primeiro.
