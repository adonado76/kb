---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Migrar o controle de acesso aos relatórios"
breadcrumb: []
source_path: "studio/reports/migratereportaccesscontrol.html"
images:
  - "resources/images/studio_images/studioimages/reports/studio_reports_change_permissions.png"
  - "resources/images/studio_images/studioimages/reports/studio_reports_save_as.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Migrar o controle de acesso aos relatórios

aplica-se a: TBM Studio 12.7 e posterior.

Antes da versão Apptio TBM Studio 12.7, quando os usuários habilitavam as permissões baseadas em função para os relatórios, o sistema criava uma cópia extra do relatório para cada função à qual as permissões eram concedidas. Este artigo explica como remover esses relatórios extras quando você quiser começar a usar a funcionalidade aprimorada de permissões disponível em TBM Studio 12.7 e posterior.

**NOTAS** :

- A funcionalidade legada continua funcionando em TBM Studio 12.7. Não é necessário remover os relatórios antes de usar a nova funcionalidade de permissões. No entanto, quando forem feitas atualizações de configuração em um relatório que tenha permissões herdadas, certifique-se de avaliar se é necessário migrar o relatório para uma versão que não tenha relatórios filhos.
- Embora não seja necessário, você pode executar as etapas descritas neste artigo em uma ramificação, desde que siga as práticas recomendadas descritas em [Projetos de ramificação](../admin/bp-branching-projects.htm "(Abre em uma nova guia ou janela)").

## Migrar relatórios

Para todos os relatórios que você identificar para migrar, capture as seguintes informações:

- Nome do relatório.
- Coleção de relatórios (para ajudar a localizar no Project Explorer).
- Quais funções devem ter permissão.
- A cópia do relatório de qual função deve ser usada para criar o novo relatório. Se a resposta for mais de um relatório, anote todas as visualizações e componentes que precisam ser mantidos ou recriados no final do processo.

Observação: A seguir, há instruções sobre como fazer o check-in de relatórios e como esperar até que o cálculo seja concluído antes de prosseguir para a próxima etapa. Certifique-se de concluir cada etapa antes de passar para a próxima. Caso contrário, você poderá obter resultados inesperados que podem exigir uma reversão ou outra assistência do Suporte.

1. No Project Explorer, navegue até **Relatórios** e, em seguida, verifique o relatório filho a ser usado para criar o novo relatório (conforme identificado em Antes de migrar relatórios acima). Isso fará com que o relatório pai e todos os relatórios filhos pareçam ter sido verificados:

   ![Migrar relatórios](../../resources/images/studio_images/studioimages/studio_project%20explorer_reports_sui.png)
2. Para criar uma cópia do relatório, primeiro clique no relatório filho e, em seguida, clique em **Salvar como**. Salve-o com a cópia do prefixo que é adicionada automaticamente. Por exemplo, Cópia de <nome original do relatório> e, em seguida, clique em **OK**.

   ![criar uma cópia do relatório](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/studio_reports_save_as.png)
3. Faça o check-in do novo relatório e aguarde a conclusão do cálculo antes de prosseguir.

   Observação: Após a conclusão do cálculo, a cópia do relatório pode aparecer em uma coleção de relatórios completamente diferente.
4. Faça o check-out e remova as permissões da cópia de <original report>. Na guia **Relatório**, clique em **Permissões**, selecione **Todos** e clique em **OK**.

   ![Alterar permissões](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/studio_reports_change_permissions.png)
5. Faça o check-in do relatório e aguarde a conclusão do cálculo.
6. Verifique qualquer *um* dos relatórios filhos anexados a <Original Report> e clique em **Delete (Excluir** ).
7. Faça o check-in do relatório e aguarde a conclusão do cálculo.

   Observação: Ao trabalhar com relatórios OOTB, a exclusão de um dos relatórios filhos faz com que o relatório pai e o(s) outro(s) relatório(s) filho(s) desapareçam.
8. Verifique a cópia que você criou na etapa anterior. Crie outra cópia do Copy of <original report> e, em seguida, renomeie o relatório para o nome <original Report>. Por fim, faça o check-in do relatório e aguarde a conclusão do cálculo.
9. Após a conclusão do cálculo, o relatório original é exibido:
   - Na coleção original do relatório
   - E com todos os relatórios adicionais de crianças que não foram explicitamente excluídos
10. Para remover o restante dos relatórios filhos, execute as seguintes etapas, nesta ordem, para cada relatório filho:
    - Confira o relatório da criança.
    - Excluir.
    - Check-in.
    - Aguarde a conclusão do cálculo após cada check-in antes de passar para o próximo relatório.
    - Repita esse processo até que todos os relatórios filhos sejam excluídos.

Agora você tem o relatório original que não tem nenhum relatório filho:

![Relatórios](../../resources/images/studio_images/studioimages/studio_reports_auto%20calculate_sui.jpg)

## Reverter para o estado OOTB (Out-of-the-Box)

Para relatórios OOTB que foram intencionalmente personalizados, não é necessário reverter ou definir o relatório de volta para a versão original, portanto, o processo de migração está concluído. Nesse caso, vá para a seção Personalizar relatórios migrados a seguir.

Se o estado final desejado para o relatório que você planeja migrar precisar ser definido como a versão original do relatório sem personalizações, conclua as seguintes etapas adicionais de migração. Talvez seja necessário fazer isso porque o estado final que você deseja para o relatório é a versão OOTB ou porque você deseja ver a versão mais recente do relatório antes de decidir quais personalizações devem ser recriadas. Nesse caso, siga estas etapas:

1. Faça uma personalização no relatório (por exemplo, adicione um componente de tabela em branco na parte superior do relatório) e, em seguida, verifique as alterações.
2. Vá para a página de instalação de componentes desse relatório e reverta o relatório OOTB.
3. Quando o cálculo da reversão é concluído, o relatório é restaurado para o estado original sem a personalização feita anteriormente.

## Personalizar relatórios migrados

Quando houver apenas uma cópia do relatório sem cópias de relatórios filhos, você poderá reaplicar todas as permissões e personalizações necessárias na cópia final do relatório migrado.

**Somente para permissões** : Para adicionar permissões ao relatório recém-migrado, consulte [Trabalhar com permissões de relatório](control-access-reports-11755.htm "(Abre em uma nova guia ou janela)").

**Para outras personalizações** :

- Se você identificar que mais de um relatório é necessário para atender a todos os requisitos, determine o menor número de relatórios que precisa criar para atender a todos os requisitos.
- Se as permissões de função forem usadas para criar relatórios para diferentes funções, em que o relatório de cada função é personalizado, uma opção é usar a visibilidade do componente para ajudar a recriar um relatório em que diferentes funções tenham visibilidade para visualizar diferentes conjuntos de componentes quando você navegar para o mesmo relatório. Nesse caso, adicione um grupo de relatórios por função que contenha os componentes que devem estar visíveis para essa função. Cada grupo é então configurado para ser visível apenas para uma função, de modo que esses grupos possam ser sobrepostos uns sobre os outros na superfície do relatório. Isso permite que a função do usuário determine qual grupo de relatórios e quais componentes ele vê.

Observação: Se um usuário tiver duas das funções para as quais os grupos são visíveis, ele verá os componentes da função que está no topo da pilha de grupos.
