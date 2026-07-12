---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Controle o acesso aos relatórios por meio de permissões baseadas em funções"
breadcrumb: []
source_path: "studio/reports/control-access-reports-11755.html"
images:
  - "resources/images/studio_images/studioimages/studio_reports_search.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Controle o acesso aos relatórios por meio de permissões baseadas em funções

**Aplica-se a** : Apptio TBM Studio 12.7 e posterior.

As permissões de relatório permitem que o administrador controle o acesso do usuário final aos relatórios, definindo as permissões para os relatórios por função. Consulte [Trabalho com funções e permissões de usuário no Apptio Studio](https://community.ibm.com/community/user/viewdocument/manage-user-permissions-and-roles "(Abre em uma nova guia ou janela)"). Antes da versão TBM Studio 12.7, a definição de permissões de relatórios individuais podia fazer com que o sistema criasse cópias extras de relatórios por função. Essa abordagem foi difícil de manter. Em TBM Studio12.7 e posteriores, a configuração de permissões não cria mais relatórios filhos específicos de função. Agora você pode configurar as permissões no nível das coleções de relatórios. Consulte [Criar e gerenciar coleções de relatórios](creating-report-collections.htm "(Abre em uma nova guia ou janela)"), além do nível do relatório.

Para aproveitar ao máximo o uso das permissões de relatório, considere o seguinte:

- As permissões **de relatórios existentes continuarão** a funcionar - Se os usuários tiverem definido permissões baseadas em funções em relatórios definidos antes de 12.7, essas permissões herdadas continuarão a funcionar em 12.7, mas podem ser difíceis de modificar.
- **página "Acesso negado"** - Anteriormente, quando os usuários não tinham permissão para ver um relatório, eles viam uma página de relatório com apenas um componente de relatório em branco. Os usuários acharam isso confuso. Em TBM Studio 12.7 e posteriores, o sistema avalia a função do usuário quando ele tenta acessar o relatório. Os usuários sem permissão suficiente verão a tela Access Denied (Acesso negado).
- **As permissões de relatório não são aplicadas em TBM Studio** - Isso pode ajudar os administradores a testar as permissões antes de verificá-las. Os testes ajudam a garantir a precisão das permissões e que os usuários não as configurem de forma a bloquear todos os usuários de uma determinada exibição de relatório.
- **As permissões de relatório são configurações em nível de projeto** - Isso significa que os usuários não precisarão verificar as permissões para defini-las, mas as permissões devem ser verificadas e a instância calculada anteriormente sem permissão suficiente veria a tela Access Denied (Acesso negado).
- **Filtro de relatório por função** - Em TBM Studio, os usuários têm a opção de filtrar a lista de relatórios no projeto por função. Isso mostra quais relatórios têm permissões específicas definidas para essa função. Para isso:
- Selecione o filtro do relatório. Em seguida, selecione **Roles (Funções** ). Isso exibe uma lista de todas as funções na instância.
- Selecione uma função na lista para que a lista de relatórios exiba apenas os relatórios com permissões especificamente definidas para essa função**.AVISO**

  Os relatórios com permissões definidas como "Everyone" (todos os relatórios OOTB até serem personalizados) não aparecerão nessas listas filtradas.

  ![Relatórios OOTB](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_reports_search.png)

## Configurar permissões

Você pode definir permissões de relatório por função no nível do relatório ou da coleção de relatórios.

## Definir permissões de coleta de relatórios

1. Em TBM Studio, na guia **Project (Projeto** ), no grupo Project Data (Dados do projeto), selecione **Report Collections (Coleções de relatórios** ).
2. Na caixa de diálogo **Manage Report Collections (Gerenciar coleções de relatórios** ), selecione a coleção de relatórios que terá suas permissões modificadas.
3. Em **Viewable By (Visualizável por** ), selecione **Selected Roles (Funções selecionadas** ) e, na lista suspensa exibida, selecione quais funções terão acesso a essa coleção de relatórios.
4. Depois que as permissões forem definidas, feche a caixa de diálogo e verifique as atualizações. As alterações de permissões aparecerão na caixa de diálogo Check-in como o nome da coleção de relatórios em que as permissões foram modificadas.

Depois que cada ambiente for calculado, por exemplo, Desenvolvimento e, em seguida, Preparação, outros usuários poderão ver as permissões aplicadas no ambiente calculado. Como outras configurações de projeto, essas configurações precisarão ser promovidas para Produção.

## Definir permissões de relatórios individuais

1. Para definir permissões para um relatório, primeiro verifique esse relatório. Em seguida, na guia **Report (Relatório** ), no grupo **Advanced (Avançado** ), selecione **Permissions (Permissões** ).
2. Na caixa de diálogo **Change Permissions (Alterar permissões** ), em **Viewable By (Visualizável por** ), selecione **Selected Roles (Funções selecionadas** ) e, na lista suspensa exibida, selecione quais funções terão acesso a esse relatório.
3. Depois que as funções forem definidas, salve as permissões e verifique as atualizações. As alterações de permissões aparecerão na caixa de diálogo Check-in como o nome do relatório em que as permissões foram modificadas.

Depois que cada ambiente tiver sido calculado, por exemplo, Desenvolvimento e, em seguida, Preparação, outros usuários poderão ver as permissões aplicadas no ambiente calculado. Como outras configurações de projeto, essas configurações precisarão ser promovidas para Produção.

## Práticas recomendadas de permissões

Com os recursos de permissões introduzidos em TBM Studio 12.7, é mais fácil para os usuários modificarem as permissões no nível do relatório sem todos os problemas que eram criados quando os usuários usavam as permissões antes de 12.7. Use as dicas a seguir para tirar o máximo proveito dessas habilidades:

- Ao **definir novas permissões, comece com as coleções de relatórios sempre que possível** - Ao atualizar as permissões, faça o máximo possível no nível da coleção de relatórios antes de fazer alterações em relatórios individuais. Isso ajudará a garantir que as alterações feitas nas permissões em nível de relatório não entrem em conflito com as permissões de toda a coleção.
- **Faça anotações ao fazer o check-in do trabalho** - A descrição padrão que aparecerá no Histórico de check-in para atualizações de permissões de relatório conterá apenas o nome da coleção ou do relatório para o qual as permissões foram atualizadas. Capturar notas mais descritivas ao fazer o check-in do trabalho pode ajudar na solução de problemas posteriormente.
- **Preencher o endereço de e-mail do suporte** - Esse endereço de e-mail pode ser especialmente útil quando um usuário tenta acessar um relatório para o qual não tem permissão. Embora isso não seja tão necessário em organizações menores, o número de usuários pode aumentar rapidamente, portanto, é útil ter esse valor definido para que os novos usuários possam canalizar suas perguntas por meio de um único endereço de e-mail. Para isso:
  1. Na guia **Projeto**, no grupo **Domínio**, clique em **Configurações de domínio**.
  2. Na caixa de diálogo **Configurações do locatário**, **campo E-mail de suporte**, adicione o endereço de e-mail do TBMO. **DICA** - Se quiser reverter a tela Access Denied para seu conteúdo original sem endereço de e-mail, substitua o endereço de e-mail personalizado acima por [support@apptio.com](mailto:support@apptio.com "(Abre em uma nova guia ou janela)").
- **Cuidado com os avisos de conflito** - Se você definir permissões que possam entrar em conflito com as permissões definidas em um nível mais alto (coleções) ou em um nível mais baixo (relatórios), certifique-se de observar os avisos de conflito de permissões que foram adicionados às caixas de diálogo de nível de relatório e de coleção de relatórios**.AVISO**

  Devido à forma como esse conflito é detectado, esse aviso aparecerá somente depois que as permissões baseadas em função para um relatório tiverem sido definidas, registradas e a instância tiver terminado de calcular.
- **Visualização no nível do relatório com conflitos no nível da coleção** - Mostra as permissões que já estão sendo reduzidas para a coleção que contém o relatório.
- **Exibição em nível de coleção com conflitos em relatórios subjacentes** - Mostra que as permissões definidas para a coleção de relatórios estão em conflito com as permissões definidas no relatório do portfólio de aplicativos.
- **Sugestões de teste e validação** - Muitos clientes usam o logon seguro (SSO), o que pode dificultar o teste dessa nova funcionalidade. Abaixo estão algumas sugestões para ajudar os usuários:
  - Como as permissões de relatório não são aplicadas em TBM Studio, qualquer administrador pode modificar as permissões de um relatório em TBM Studio e, em seguida, navegar para fora de TBM Studio e voltar para o aplicativo (por exemplo, para Costing Standard) onde as permissões são aplicadas. Se o administrador não tiver as permissões adequadas para visualizar um relatório, ele verá a tela Access Denied (Acesso negado) quando não estiver em TBM Studio.
  - Ao testar muitas funções, pode ser útil coordenar um pequeno grupo de usuários finais que estejam dispostos a testar clicando nos relatórios depois que um administrador tiver modificado as permissões de relatório (e possivelmente as funções de usuário se estiver testando muitas funções).

## Trabalhar com permissões prévias

Conforme mencionado acima, se você tiver relatórios que foram configurados para usar permissões de relatório antes de 12.7, essas permissões continuarão a funcionar. Entretanto, em algum momento, surgirá um novo requisito ou função que precisará ser adicionado a um dos relatórios personalizados por função. Nesse caso, consulte o [Guia de migração de controle de acesso a relatórios](migratereportaccesscontrol.htm "(Abre em uma nova guia ou janela)").

## Perguntas mais frequentes

**P: Se eu tiver personalizado relatórios usando permissões anteriores a 12.7, ainda poderei usar esses relatórios?**

R: Sim. A atualização para 12.7 não altera a forma como você navega e acessa os relatórios personalizados por função. Isso proporciona uma experiência mais limpa para quaisquer novas permissões que precisem ser aplicadas no futuro.

**P: Preciso fazer alguma alteração em minha instância para começar a usar a nova funcionalidade de permissões quando fizer o upgrade para 12.7?**

R: Não. As permissões de relatórios antigos continuarão a funcionar em paralelo com a nova funcionalidade, para que você possa decidir quando deseja começar a usar a nova funcionalidade.

**P: Como posso ver quais relatórios têm permissões definidas para minha função?**

R: No Project Explorer, você pode aplicar um filtro por função à lista Relatórios para ver todos os relatórios que têm permissões definidas para uma determinada função.

**P: Por que minha lista de funções não contém funções personalizadas?**

R: Normalmente, isso se deve ao fato de Enhanced Access Administration não estar configurado corretamente, fazendo com que a instância não se conecte adequadamente a Enhanced
Access Administration , onde a lista completa de funções personalizadas é mantida.

**P: Qual registro do histórico de check-in captura as permissões que apliquei a uma determinada coleção de relatórios, caso eu precise reverter?**

R: Se você não adicionou notas para qualificar quando uma coleção de relatórios foi modificada, pode ser difícil saber o que foi verificado como parte de um determinado registro. O histórico de check-in contém apenas o nome do relatório ou da coleção de relatórios após a expansão dos registros.
