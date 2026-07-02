---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Instantâneos (Controle de versão)"
breadcrumb:
  - "Planning"
  - "Fluxos de trabalho e colaboração"
source_path: "it-planning/planning/snapshots.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Instantâneos (Controle de versão)

Um instantâneo é uma cópia somente leitura, com registro de data e hora, de uma versão do plano. Os instantâneos preservam as visualizações históricas de um plano para que você possa comparar planos enviados, aprovados ou finalizados com versões anteriores.

Os instantâneos são especialmente úteis para:

- Acompanhamento das alterações entre envios
- Comparando os valores orçamentários atuais com as versões anteriores
- Auditoria das atualizações ao longo do ciclo de planejamento

Os instantâneos **não** são editáveis e estão disponíveis apenas para **departamentos folha**.

## Quando os instantâneos são criados automaticamente

Apptio O planejamento cria instantâneos automaticamente durante pontos-chave do processo de planejamento:

- Quando um plano é **apresentado**
- Quando o status de um plano muda de **Novo → Aberto**

Essas capturas automáticas garantem que uma versão de referência esteja sempre disponível para comparação.

## Criar um instantâneo manualmente

Você pode criar instantâneos adicionais a qualquer momento para suas próprias necessidades de comparação ou análise.

**Etapas para criar um instantâneo**

1. No menu **Plano**, selecione o plano no qual deseja trabalhar.
2. Navegue até **Plano → Despesas**.
3. No menu suspenso **Departamento**, selecione um **Departamento folha**.
4. Abra o menu suspenso **Versões do plano**.
5. Selecione **Salvar instantâneo**.
6. Digite um **nome** para o instantâneo.
7. Clique em **Criar**.

Seu instantâneo agora está salvo e pode ser acessado a qualquer momento.

## Acessando instantâneos salvos

Para visualizar instantâneos existentes:

1. Siga o mesmo caminho de navegação: **Plano → Despesas**.
2. No menu suspenso **Versões do plano**, você verá todos os instantâneos salvos disponíveis para o Departamento selecionado.

Os instantâneos são sempre somente para leitura, a fim de preservar a precisão histórica.

## Usando instantâneos para comparação

Os instantâneos podem ser selecionados ao adicionar **comparações** na página Despesas. Isso permite que você:

- Compare os valores atuais com um instantâneo anterior do plano
- Destaque as alterações ao longo das iterações do planejamento
- Apoiar discussões sobre variações durante as revisões orçamentárias

## Restaurar o departamento para a versão anterior do instantâneo

Você pode restaurar um instantâneo anterior e torná-lo a versão atual (mais recente) dos dados do plano para um departamento. Isso permite que você se recupere rapidamente de alterações indesejadas e continue o planejamento a partir de um ponto no tempo conhecido e confiável.

Restaurar um instantâneo como a versão mais recente

Para restaurar um instantâneo como a versão mais recente, siga as etapas abaixo:

1. Na visualização **Despesas**, acesse o **departamento** específico usando o menu suspenso **Departamentos**.
2. No menu suspenso “**Versão do plano** ”, selecione o **instantâneo** que você deseja restaurar como a versão mais recente.
3. Na caixa de diálogo de confirmação "**Restaurar instantâneo** ", digite um **nome para o instantâneo**. Esse nome será usado para salvar uma cópia da versão mais recente atual antes da restauração.
4. Clique em **Restaurar**.

**Resultado**

Quando a operação de restauração é executada:

- **A versão mais recente** existente é primeiro salva como um **novo instantâneo** usando o nome de instantâneo fornecido.
- Os dados da **versão** mais recente são então apagados.
- Os dados do instantâneo selecionado são copiados e definidos como a nova **versão mais recente**.

**Observação:** Esta operação não pode ser realizada se o departamento **não** estiver no estado “Em andamento”.
