---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Práticas recomendadas: Check-out e check-in"
breadcrumb: []
source_path: "studio/admin/bp-check-out.html"
images:
  - "resources/images/studio_images/changehist.png"
  - "resources/images/studio_images/check-in-tab.png"
  - "resources/images/studio_images/checkin-errors.png"
  - "resources/images/studio_images/checkout.png"
  - "resources/images/studio_images/checkout1.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Práticas recomendadas: Check-out e check-in

aplica-se a: Apptio TBM Studio 12.x e posterior. Em Apptio TBM Studio R12, todos os elementos são documentos, incluindo tabelas de dados, métricas, perspectivas e modelos. Para editar um documento, você deve primeiro verificá-lo. Quando você faz o check-out de um documento, ele é bloqueado para que outras pessoas não possam editá-lo. Você pode salvar suas alterações no documento sem acionar um novo cálculo. Quando terminar de editar um documento, você poderá fazer o check-in. O registro em um documento aciona um novo cálculo. Outras pessoas verão as alterações que você fez no documento quando o cálculo do modo de desenvolvimento for concluído e o espaço de trabalho delas for atualizado. Além disso, outras pessoas agora poderão conferir esse documento.

As informações abaixo detalham o check-out e o check-in do documento e as práticas recomendadas a serem seguidas para uma experiência ideal.

## Check-out

Para fazer o check-out de um documento, siga estas etapas:

1. Selecione o documento no **Project Explorer**.
2. Na guia **Home**, no grupo **Document**, selecione **Check Out**![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/checkout1.png).
3. Quando você faz o check-out de um documento, um ícone de check-out aparece ao lado do nome do documento, e o nome do documento é exibido em texto **laranja** na guia na parte inferior do espaço de trabalho.![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/checkout.png)

## Desfazer, refazer e reverter

Às vezes, quando você está editando documentos no seu espaço de trabalho, pode querer retornar a uma versão anterior ou refazê-la. Quando os documentos são retirados, você pode usar três opções para fazer isso:

- **Desfazer**
- **Refazer**
- **Reverter alteração**

Desfazer e refazer são úteis para reverter alterações pequenas e discretas na configuração, como as seguintes:

- Posicionamento de elementos de relatório em um relatório
- Edições discretas na configuração dos elementos de relatório (por exemplo: texto do botão, conteúdo HTML, etc.)
- Edição de fórmulas para colunas na etapa de fórmula de uma tabela

## Reverter

Você pode encontrar a opção desfazer e refazer na guia Página **inicial**, grupo **Alterações**. Reverter abandona todas as alterações feitas nos documentos de check-out que você selecionou e, em seguida, descarta o check-out. Para reverter, siga estas etapas:

1. Na guia Página **inicial**, no grupo **Documento**, clique em **Reverter alterações**.
2. Marque a caixa de seleção ao lado dos documentos que você deseja reverter e clique em **Revert Check Out**.

## Check-in

**Examinar relatórios de desempenho**

Ao avaliar a integridade do sistema após fazer alterações nos dados ou na configuração, é útil examinar os relatórios criados para avaliar possíveis problemas de desempenho.

Observação: As próximas versões do site TBM Studio terão relatórios projetados especificamente para avaliar os impactos das alterações no desempenho. Quando esses relatórios estiverem disponíveis, este documento será atualizado para fornecer orientações específicas. No entanto, até que esses relatórios estejam disponíveis, você simplesmente escolhe um relatório conhecido por exercitar bem o sistema. Se você não tiver certeza de qual relatório usar, consulte o CSM ou o suporte do Apptio.

## Confirmar se a carga de dados está correta

O princípio orientador dos espaços de trabalho do projeto é que essa área é seu ambiente de desenvolvimento. Você deve ter muita confiança nos dados e na configuração dessa área antes de fazer o check-in dos dados. Use a lista de verificação a seguir antes de fazer o check-in de documentos e depois de fazer um upload de dados.

## Lista de verificação de documentos

- Revise os dados antes de carregá-los em seu espaço de trabalho (por exemplo, confirme se o arquivo tem conteúdo, se está delimitado corretamente e assim por diante).
- Certifique-se de que as tabelas de dados tenham dados e que a validação de cardinalidade esteja ativada.
- Clique em **Save (Salvar)** na tabela de dados alterada.
- Valide colunas (por exemplo, a adição de colunas ou a renomeação de colunas) e tipos (consulte [Recursos adicionais](#BestpracticesCheckoutandcheckin__addresources) ).
- Se as colunas estiverem faltando, determine o efeito que isso terá na configuração.
- Verifique a qualidade geral dos dados (por exemplo, se há dados faltando, se os totais das colunas numéricas parecem sensatos) e crie sua própria rotina de validação em torno desse ponto.
- Examine um relatório diretamente associado aos dados e certifique-se de que nada de estranho tenha ocorrido.
- Navegue até os [relatórios de desempenho](#BestpracticesCheckoutandcheckin__perfreports) e verifique se eles respondem bem.
- **Se os relatórios não responderem bem ou se forem indicados problemas, resolva-os antes do check-in.**
- Coordenar e combinar com os colegas o momento de fazer o check-in dos dados e garantir que ninguém esteja esperando para ser promovido do estágio para a produção.

## Datalink (Classic) considerações

Ao usar o site Datalink (Classic), **além dos** pontos acima, aplica-se o seguinte:

- Quando o Datalink (Classic) faz upload de um documento, esse documento é carregado em um espaço de trabalho do Datalink (Classic) e, em seguida, é *imediatamente* registrado.
  - Considere o uso de grupos de conectores Datalink (Classic) para gerenciar grandes conjuntos de uploads. O uso de um grupo de conectores resultará em um único check-in para o grupo em vez de check-ins individuais para cada carga. Para obter mais informações, consulte [Agrupar vários conectores](../../datalink-classic/datalink/group-connectors.html "(Abre em uma nova guia ou janela)").
- Se houver problemas de validação, o documento será mantido no espaço de trabalho Datalink
  (Classic) até que os erros de validação sejam resolvidos e o documento seja registrado manualmente.

## Confirmar as alterações de configuração

Assim como ocorre com os carregamentos de dados, tome cuidado antes de fazer o check-in das alterações de configuração. Use a lista de verificação a seguir antes de fazer o check-in das alterações de configuração. Para obter orientação sobre maneiras de acelerar sua validação, consulte [Dicas de técnicas de validação](#BestpracticesCheckoutandcheckin__validation).

## Lista de verificação

- Clique em **Salvar** quando terminar de modificar qualquer documento.
- Resolva os erros selecionando os números exibidos ao lado das tabelas de dados, por exemplo:![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/checkin-errors.png)
- Validar como as alterações nos dados e na configuração afetaram as alocações.
- Validar como as alterações nos dados e na configuração afetaram os relatórios.
- Verifique o tamanho das taxas de alocação das tabelas modeladas em cada métrica modelada associada a essa tabela.
- Verifique se os relatórios em que você trabalhou respondem quando visualizados. Se um relatório não for carregado como esperado, isso pode indicar um problema de configuração (por exemplo, se o relatório nunca for carregado ou se for carregado após um tempo MUITO longo). Se achar que é um problema do navegador, atualize-o e volte ao relatório para garantir que ele seja carregado corretamente. Se ele não carregar corretamente, resolva o problema antes do check-in.
- Navegue até os [relatórios de desempenho](#BestpracticesCheckoutandcheckin__perfreports) e verifique se eles respondem bem. Se os relatórios não responderem bem ou se forem indicados problemas, resolva-os antes do check-in.
- Coordenar e concordar com os colegas sobre quando fazer o check-in dos documentos e garantir que ninguém esteja esperando para ser promovido do estágio para a produção.

## Fazer o check-in de um projeto

Quando várias pessoas estiverem trabalhando em um único projeto com a possibilidade de várias verificações de documentos no mesmo dia, siga estas diretrizes para controlar o que é calculado e quando. Essa etapa deve fazer parte do processo de ciclo de vida de desenvolvimento de software (SDLC) de qualquer cliente. Vale a pena recapitular o que acontece depois de um check-in. As atividades em cada ambiente em um único projeto Apptio quando ocorre um check-in:

- **Desenvolvimento** - Um check-in aciona o(s) nó(s) de cálculo de desenvolvimento para processar:
  - Transformações
  - Métricas
- **Estágio** - Um check-in aciona o provisionamento do nó de cálculo do estágio, que pode levar até 15 minutos e, uma vez provisionado, os nós de cálculo do estágio calculam o seguinte após a conclusão do desenvolvimento do cálculo:
- - Exercícios
  - Relatórios

    Observação: Quando vários eventos de check-in ocorrem em um período de tempo suficientemente longo (por exemplo, alguns minutos), isso pode resultar em mais de um evento de cálculo. Quando um cálculo estiver em andamento, todos os check-ins subsequentes serão incluídos no próximo evento de cálculo. As soluções para isso são fornecidas mais adiante neste documento.
- **Produção** - Uma publicação para produção só pode ser executada depois que todos os cálculos de estágio pendentes tiverem sido concluídos. A publicação no site v.12 é quase instantânea.

## Cálculos de controle

Quando você faz o check-in de dados, configurações ou alterações de relatórios, ele aciona cálculos no desenvolvimento e no estágio. Isso causará uma carga de trabalho no meio ambiente. Até que o cálculo do estágio seja concluído, o estágio de navegação dos usuários receberá um aviso de que o ambiente está desatualizado. A promoção para produção não será possível até que todos os cálculos de estágio sejam concluídos.

## Estabelecer uma política de check-in

Recomenda-se que a equipe mais ampla do TBMA determine uma política de check-in no início do projeto e a revise conforme necessário. As diretrizes a seguir provaram ser bem-sucedidas em outras implementações do Apptio v.12 :

- Coordene o check-in para que ocorra uma ou duas vezes por dia (por exemplo, no almoço e no final do dia).
- Se um projeto tiver um tempo de cálculo de estágio mais longo, coordene o check-in em toda a equipe para que ocorra ao mesmo tempo. Isso ajudará a limitar a possibilidade de ocorrência de cálculos em dois estágios.*Se você receber cálculos em fila de qualquer maneira,* consulte [Limitar o tempo de cálculo](#BestpracticesCheckoutandcheckin__limitcalc) para limitar o tempo de cálculo.
- Se houver necessidade de publicar para produção, bloqueie o estágio quando todas as verificações acordadas tiverem sido concluídas para evitar que outra verificação ocorra antes da publicação para produção.

## Exibir o status do cálculo

Até agora, discutimos 1) o que acontece quando você clica em check-in, 2) o que você deve fazer antes de clicar em check-in e 3) quando você deve clicar em check-in. Esta seção explica o que acontece **depois de um check-in**. A fila de cálculo mostra o que foi calculado (e quanto tempo levou), o que está sendo calculado e o que está esperando para ser calculado. Para visualizar a fila de cálculo:

1. No menu TBM Studio , selecione a guia **Build (Construir** ).
2. Clique em **Calculation Queue (Fila de cálculo** ).

Isso mostra a compilação mais recente para cada ambiente e exibe as compilações que terminaram de calcular, estão calculando ativamente e terminaram de calcular. [Saiba mais sobre a fila de cálculo](monitor-builds-calculation.html "(Abre em uma nova guia ou janela)")

## Limitar o tempo de cálculo

Se um cálculo estiver em andamento e ocorrerem check-ins subsequentes, essas alterações ficarão na fila até que o cálculo em execução seja concluído. Se o tempo de cálculo do estágio for longo, considere a possibilidade de usar o recurso Cancelar compilação ( v.12.3.1+ ) para cancelar a compilação em execução, de modo que as alterações pendentes sejam incluídas na próxima compilação. Para obter mais informações, consulte [Cancelar um cálculo em andamento](https://community.apptio.com/docs/DOC-8376 "(Abre em uma nova guia ou janela)").

## Exibir histórico de check-in

Para ver um histórico de quem fez check-in em um documento específico, siga estas etapas:

1. Selecione o documento no **Project Explorer**.
2. Clique com o botão direito do mouse na guia na parte inferior do espaço de trabalho e selecione **Check In History** :![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/check-in-tab.png)
3. É exibida uma tabela com a data, o usuário, o status, a descrição e qualquer mensagem incluída no check-in.![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/changehist.png)
4. Para retornar à visualização do documento, clique novamente com o botão direito do mouse na guia e selecione **Mostrar documento**.

## Retroceder

A partir do site v.12.2.2, é possível reverter as alterações feitas em um projeto a partir de uma alteração específica. Todas as alterações feitas após essa alteração específica serão revertidas. No entanto, há algumas considerações importantes antes de usar esse recurso. Para obter mais informações, consulte [Reverter uma configuração](roll-back-configuration.html "(Abre em uma nova guia ou janela)").

## Bloquear e promover um projeto

O bloqueio e a promoção são abordados em [Bloquear e promover um projeto](lock-promote-project.htm "(Abre em uma nova guia ou janela)").

## Técnicas de validação

Uma maneira de acelerar a validação é ter *duas* guias do navegador abertas: uma guia com o que você vê em seu espaço de trabalho e uma guia com o que está visível na construção do estágio atual. Isso é mais útil quando há alterações de configuração, mas não há alterações de dados, e quando não há cálculos de estágio pendentes. No entanto, ele também pode ser útil em outras circunstâncias. Para usar duas guias do navegador:

1. Navegue até o documento que está validando (tabela, relatório, modelo, etc.).
2. Abra outra guia e navegue até o mesmo documento em stage, prod e assim por diante.
3. Alguns navegadores, como o Chrome, têm a opção Duplicar guia quando você clica com o botão direito do mouse em uma guia aberta do navegador. Isso pode acelerar a criação de uma nova guia, pois não é necessário repetir a navegação para Enhanced Access Administration, e assim por diante.
4. Mantenha pressionada **a tecla Ctrl** e clique no botão **da guia**. Isso deve alternar entre as duas guias abertas. Isso permite que você avalie rapidamente as diferenças entre as visualizações.

**Recursos adicionais**

- Localizar e corrigir problemas de validade de dados: [Localizar e corrigir problemas de validade de dados](https://community.apptio.com/docs/DOC-6790 "(Abre em uma nova guia ou janela)")
- Vídeos de validação de dados: [Validação de dados ( v.12 )](https://community.apptio.com/videos/1305 "(Abre em uma nova guia ou janela)")
