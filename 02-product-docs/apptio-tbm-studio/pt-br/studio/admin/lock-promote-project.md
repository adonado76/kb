---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Bloquear e promover um projeto"
breadcrumb: []
source_path: "studio/admin/lock-promote-project.html"
images:
  - "resources/images/studio_images/et-hour.png"
  - "resources/images/studio_images/fp-popup.png"
  - "resources/images/studio_images/fp-success.png"
  - "resources/images/studio_images/promote-later.png"
  - "resources/images/studio_images/promotion-options.png"
  - "resources/images/studio_images/recurring-promotion-popup.png"
  - "resources/images/studio_images/staging-lock.png"
  - "resources/images/studio_images/staging.png"
  - "resources/images/studio_images/studioimages/force-promotion.png"
  - "resources/images/studio_images/studioimages/locked_866x93.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Bloquear e promover um projeto

**Aplica-se a** : TBM Studio 12.0 e posterior. Apptio TBM Studio oferece suporte a dois modos, *sob demanda* e *recorrente*, para promoções.

## Promoções sob demanda

Esse é um modo básico em que as TBMAs promovem construções conforme a necessidade. Não é necessário que as TBMAs da equipe se coordenem entre si nesse modo. As etapas a seguir mostram a sequência esperada e de alto nível de promoção que o TBMA segue. Consulte [Gerenciar promoções sob demanda](#Lockandpromoteaproject__Manage) para obter instruções detalhadas.

1. O TBMA valida a construção atual no estágio.
2. A TBMA bloqueia o projeto.

   Observação: Um cálculo em andamento pode acionar uma nova construção. Caso contrário, nenhuma nova construção será acionada.
3. O bloqueio impede novos check-ins de outros TBMAs enquanto a construção e a promoção subsequente estiverem em andamento.
4. O TBMA promove a compilação com uma das duas opções a seguir (essas opções estão disponíveis somente se o projeto estiver bloqueado):
   - Promova agora
   - Promover mais tarde

## Promoções recorrentes

Esse é um modo avançado. Esse modo é apropriado para uma equipe que atenda aos seguintes critérios:

- A equipe tem um ritmo bem estabelecido de check-ins e validação em um cronograma.
- A equipe quer garantir que o produto seja atualizado em uma cadência conhecida para consumo.
- As TBMAs da equipe coordenam entre si o mesmo.

As etapas a seguir mostram a sequência esperada de alto nível de promoção recorrente que o TBMA segue. Consulte [Gerenciar promoções sob demanda](#Lockandpromoteaproject__Manage) para obter instruções detalhadas.

1. A equipe configura o cronograma de promoção.
2. A equipe garante que o estágio seja validado bem antes da promoção programada.
3. A promoção ocorre no horário programado.

Se, durante o tempo de promoção programada pré-configurado, o projeto estiver bloqueado, a promoção programada falhará. Como resultado, o bloqueio não pode ser usado em conjunto com promoções programadas.

## Gerencie promoções sob demanda

- Quando um projeto está bloqueado, os usuários podem fazer check-out de documentos, mas não podem fazer check-in de documentos.
- Para que um projeto seja promovido do ambiente de preparação para o ambiente de produção, o projeto deve ser bloqueado.
- Somente usuários com privilégios de administrador podem promover um projeto para o ambiente de produção.

  Observação: Quando um projeto está bloqueado, o menu suspenso Ambiente no cabeçalho global é definido como **Bloqueado**.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/locked_866x93.png)

O bloqueio deve ser coordenado para que o que será promovido seja conhecido. Em equipes pequenas, é mais fácil acompanhar informalmente. No entanto, em equipes maiores ou em situações em que os check-ins ocorrem com frequência com uma variedade de alterações em diferentes documentos dentro do sistema, pode ser necessário coordenar para ajudar a garantir que, quando o conjunto específico de alterações direcionadas para o produto for verificado, a compilação associada seja bloqueada.

Quando o Stage estiver bloqueado, os usuários não poderão fazer o check-in. O mecanismo de bloqueio é fornecido para que os TBMAs tenham uma maneira de impedir que outras alterações afetem um evento de publicação.

## Bloquear ou desbloquear um projeto

1. Selecione o ambiente de teste.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/staging.png)
2. Na guia **Build**, selecione **Lock** (ou, se já estiver bloqueado, selecione **Unlock** ).

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/staging-lock.png)

Depois de bloquear um projeto, você pode promovê-lo. Os botões **Promote Now (Promover agora** ) e **Promote Later (Promover mais tarde** ) serão ativados e o botão **Force Promotion (Forçar promoção** ) será desativado.

## Promover um projeto do ambiente de preparação para o ambiente de produção

Para promover um projeto, vá até a guia **Build** e selecione **Promotion Options**. Selecione uma das seguintes opções:

**Promova agora**

Promove imediatamente o projeto. Esse botão é desativado quando a compilação está desbloqueada ou quando outra compilação ainda está em execução.

**Promover mais tarde**

Esse botão é desativado quando a compilação é desbloqueada.

1. A caixa de diálogo Promote Later é exibida.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/promote-later.png)
2. Selecione **uma** das opções:
   - Promover assim que a construção estiver concluída, mas não após o tempo especificado
   - Promover no horário especificado se a compilação estiver concluída
3. Insira a **data** e **a hora** para agendar a promoção
4. Marque ou desmarque a caixa de seleção **Desbloqueio automático após promoção bem-sucedida**
5. Insira os IDs de e-mail na caixa de texto **Email Recipients (Destinatários de e-mail** )
6. Selecione Salvar.

## Promoção da força

Aplica-se a: 12.11.0 e posterior. O botão **Forçar promoção** permite que você promova a última compilação calculada do projeto para Produção, sem bloquear o ambiente de preparação. Para forçar a promoção da compilação, faça o seguinte:

1. Navegue até a guia **Build** e verifique se a compilação está desbloqueada.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/force-promotion.png)
2. Selecione o botão **Forçar promoção**. Aparece uma janela pop-up de aviso, conforme mostrado:

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/fp-popup.png)
3. Selecione **Ok** para concluir a ação

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/fp-success.png)

   .

## Gerenciar promoções recorrentes

Observação: conforme descrito na Introdução, a configuração de uma promoção recorrente é um recurso avançado destinado a equipes maduras.

## Promoção recorrente

1. Na guia Ambiente de preparação e compilação, selecione Opções de promoção.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/promotion-options.png)
2. Selecione **Recurring Promotion (Promoção recorrente** ). A caixa de diálogo Recurring Promotion é exibida.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/recurring-promotion-popup.png)
3. Insira dados nos seguintes campos

   | Campos | Descrição |
   | --- | --- |
   | Nome | Nome da promoção recorrente |
   | Descrição | Descrição do motivo pelo qual a promoção recorrente é necessária |
   | Recorrência | **Repetir** : Selecione Daily, Weekly ou Monthly a cada <frequência de repetições> dias  **Hora de início** : Digite <hh:mm> <AM/PM> e selecione **UTC/GMT** <fuso horário> |
   | Destinatários de e-mail | Digite o ID de e-mail das pessoas que devem receber as notificações |
   | Ativar | Marque essa caixa de seleção para ativar/desativar as notificações por e-mail |
4. Selecione **Salvar**

## Atualizações recorrentes para tabelas editáveis

1. Em Promotion Options (Opções de promoção), selecione **Recurring Updates for Editable Tables (Atualizações recorrentes para tabelas editáveis** ).

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/et-hour.png)
2. Insira dados nos seguintes campos

   | Campos | Descrição |
   | --- | --- |
   | Recorrência | **Repetição** : selecione por hora (padrão), diariamente, semanalmente ou mensalmente a cada <frequência de repetições> hora/dias/mês.  **Hora de início** : Digite <hh:mm> <AM/PM> e selecione **UTC/GMT** <fuso horário> |
   | Adicionar nova hora de início | Esse botão é exibido para recorrência diária, semanal e mensal.  Clique no botão para adicionar valores de **Repetição** e **Hora de início**, conforme mencionado acima. Você pode clicar nesse botão 23 vezes (para repetir a hora de início para cada hora), após o que o botão será desativado.  Clique no ícone x para excluir qualquer hora de início |
   | Repetir em | Esse campo é exibido para a recorrência **semanal**. Selecione os dias em que você deseja que a recorrência funcione. |
   | Ativar | Marque essa caixa de seleção para ativar/desativar as notificações por e-mail |
3. Selecione **Salvar**.

## Cenários e práticas recomendadas

**Cenário** - A equipe tem um ritmo diário de mudanças menores, mas um TBMA, ou um conjunto de TBMAs, deseja realizar uma atividade de configuração de longa duração.

**Prática recomendada** - A equipe pode usar promoções de agendamento na filial principal. Uma ramificação separada pode ser criada para a configuração de longa duração, que usa promoções sob demanda.

**Cenário** A equipe tem um ritmo diário de mudanças menores, mas novos dados são carregados no sistema todos os meses com um link de dados.

**Melhores práticas**

- A equipe pode usar promoções de agendamento na filial principal.
- O carregamento de dados via Datalink (Classic) ocorre em uma ramificação, é validado e, em seguida, mesclado à ramificação principal.

**Cenário** - A equipe tem um ritmo de promoção estabelecido, mas devido a eventos específicos ou a alguma interrupção, a equipe precisa realizar uma promoção única fora da banda.

**Melhores práticas**

- A equipe configura e usa uma promoção programada.
- A equipe pode usar a promoção sob demanda fora da banda sem que a promoção programada entre em conflito com a promoção sob demanda. Em caso de conflito, a promoção sob demanda prossegue e a promoção programada é abortada.
