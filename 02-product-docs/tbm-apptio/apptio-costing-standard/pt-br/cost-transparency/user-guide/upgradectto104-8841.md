---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Atualizar o padrão de cálculo de custos para o modelo v104"
breadcrumb: []
source_path: "cost-transparency/user-guide/upgradectto104-8841.html"
images:
  - "resources/images/ct_images/8841_1.png"
  - "resources/images/ct_images/8841_10.png"
  - "resources/images/ct_images/8841_11.png"
  - "resources/images/ct_images/8841_12.png"
  - "resources/images/ct_images/8841_13.png"
  - "resources/images/ct_images/8841_14.png"
  - "resources/images/ct_images/8841_15.png"
  - "resources/images/ct_images/8841_16.png"
  - "resources/images/ct_images/8841_17.png"
  - "resources/images/ct_images/8841_18.png"
  - "resources/images/ct_images/8841_19.png"
  - "resources/images/ct_images/8841_2.png"
  - "resources/images/ct_images/8841_20.png"
  - "resources/images/ct_images/8841_21.png"
  - "resources/images/ct_images/8841_22.png"
  - "resources/images/ct_images/8841_23.png"
  - "resources/images/ct_images/8841_24.png"
  - "resources/images/ct_images/8841_25.png"
  - "resources/images/ct_images/8841_26.png"
  - "resources/images/ct_images/8841_27.png"
  - "resources/images/ct_images/8841_28.png"
  - "resources/images/ct_images/8841_29.png"
  - "resources/images/ct_images/8841_3.png"
  - "resources/images/ct_images/8841_30.png"
  - "resources/images/ct_images/8841_31.png"
  - "resources/images/ct_images/8841_32.png"
  - "resources/images/ct_images/8841_4.png"
  - "resources/images/ct_images/8841_5.png"
  - "resources/images/ct_images/8841_6.png"
  - "resources/images/ct_images/8841_7.png"
  - "resources/images/ct_images/8841_8.png"
  - "resources/images/ct_images/8841_9.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Atualizar o padrão de cálculo de custos para o modelo v104

Este documento descreve os motivos por trás da atualização da interface do usuário (UI) do Costing Standard e as etapas recomendadas para atualizar o conteúdo do aplicativo Apptio do modelo v103 para a versão mais recente do modelo do aplicativo.

Observação: Aplica-se a: Costing Standard em TBM Studio 12.3 e posterior, com o modelo v104 e posterior ([Saiba mais](../reports-v104/ctreportcollections104-plus.html) )

**VEJA TAMBÉM** :

- Para entender a diferença entre os modelos v103 e v104, vá para [Comparar os relatórios de transparência de custos v104 e v103](../reports-v104/comparev103v104reports.html).
- Para entender como os relatórios são mapeados para o modelo v104, vá para [Mapeamento dos relatórios de transparência de custos do modelo v103 para v104](../reports-v104/mappingctreports103to104.html).
- Para obter uma planilha que lista todos os conjuntos de dados que precisam ser atualizados para v104, vá para [Template v103 para v104 Data Updates](template103to104dataupdates-9027.html).

## Objetivos

A interface de usuário do Costing Standard foi redesenhada para fazer o seguinte:

- Simplificar a navegação do relatório em Costing Standard
- Simplificar e separar relatórios complexos
- Melhor suporte à configuração incremental
- Segmentar produtos em uma seleção de nível superior (por exemplo, separar os relatórios Vendor Insights de Costing Standard)
- Suporte à taxonomia da TBM v2 como padrão (a taxonomia da TBM v1 ainda é suportada)
- Suporte à conformidade com a Seção 508
- Melhorar o desempenho de relatórios conhecidos como "caros"

## Coleções de relatórios no modelo v104

Os relatórios do site Costing Standard foram organizados nas seguintes coleções de relatórios no Modelo v104:

- Aplicativos
- Linha de base para testes
- Unidades de negócios
- Dimensões dos dados
- Qualidade de dados
- Infraestrutura e nuvem
- Finanças de TI
- Projetos
- Recursos
- Serviços
- Visão geral da TBM
- Fornecedores

## Tipos de relatórios

As coleções de relatórios do site v104 são organizadas de acordo com os seguintes tipos de relatórios:

- Os relatórios de revisão fornecem uma visão geral gráfica dos principais itens em uma área, como os 10 aplicativos ou categorias com o maior gasto.
  - Exemplo: Revisão financeira
  - Exemplo: Revisão do projeto
- Os relatórios de portfólio fornecem métricas de todos os itens em uma área.
  - Exemplo: Portfólio de projetos
- Os relatórios de análise ou lista oferecem uma visualização tabular de cada área para localizar rapidamente um valor específico.
  - Exemplo: Análise financeira
  - Exemplo: Lista de projetos
- Outros relatórios são adicionados a uma coleção para lidar com casos de uso de insight exclusivos de uma área.
  - Exemplo: Projetos em risco
  - Exemplo: Impacto da desativação de aplicativos

## Expectativas de atualização para o modelo v104

Devido à amplitude das alterações na interface do usuário e na navegação subjacente, é importante que **todos os componentes existentes DEVEM ser atualizados**. Da mesma forma, a navegação da página de destino para os relatórios de nível superior pode ser interrompida. Além disso, os links de um relatório para um relatório em outra área podem ser interrompidos (por exemplo, um link do relatório do portfólio de serviços para um relatório de projeto relacionado a um serviço específico)

## Identificação do modelo v103

Você pode determinar se o seu aplicativo está usando o modelo v103 consultando a página inicial Costing Standard ou a lista de coleções de relatórios Costing Standard .

Se a página **inicial** for semelhante à página abaixo, você tem o Template v103. Procure seções como IT Finance e IT Management, cada uma com três links abaixo.

![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_1.png)

Como alternativa, consulte o menu Relatórios. Na barra de navegação, clique no menu **Relatórios** e veja a lista de coleções de relatórios. Se você vir Gerenciamento de TI, você tem o Template v103.

![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_2.png)

Dica: Para entender a diferença entre os modelos, acesse [os relatórios Compare v104 e v103 Cost Transparency](../reports-v104/comparev103v104reports.html).

## Atualize para os componentes mais recentes

As etapas a seguir são necessárias para atualizar o aplicativo do modelo v103 para v104 e posteriores. Conclua estas etapas *depois de* fazer o upgrade de sua plataforma de TBM Studio 12.3 ou 12.4 ou posterior.

## Etapa 1: Criar uma filial

Execute o processo de upgrade em uma filial separada, em vez de em um ambiente **de desenvolvimento** pessoal.

1. Antes de criar a ramificação, conclua e verifique todas as alterações em seu projeto principal.
2. Na guia **Projeto**, clique em **Criar filial**.

   A caixa de diálogo **Criar filial** é aberta.
3. Digite um novo nome de filial, por exemplo, "Upgrade da versão 104"

   ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_3.png)
4. Clique em **OK**.

   A caixa de diálogo **Fila de cálculo** é aberta. Aguarde a conclusão dos cálculos.

   ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_4.png)

## Etapa 2: Abra a nova filial

Faça upgrade do projeto em uma ramificação separada ([Saiba mais](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=step-2-open-new-branch "(Abre em uma nova guia ou janela)") ).

1. Na guia **Project (Projeto** ), clique no menu suspenso **Trunk (Tronco** ).
2. Selecione a ramificação desejada, por exemplo, Upgrade da versão 104.

   ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_5.png)

   Depois de selecionar uma ramificação, você verá a ramificação ativa na barra de menus.

   ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_6.png)
3. Sempre que retornar ao site TBM Studio, verifique se você está no ramo de upgrade correto antes de prosseguir. Caso contrário, e **o Tronco** for exibido, você precisará selecionar novamente a ramificação Upgrade da versão 104.

   **CUIDADO** : Não faça alterações no projeto principal (por exemplo, Tronco) durante o curso das atividades de atualização na ramificação de atualização separada. Se você fizer isso, todas as alterações feitas no tronco principal serão perdidas após a mesclagem do ramo de atualização.

## Etapa 3: Alterar a versão do componente

1. Na guia **Projeto**, clique em **Configurações do projeto**.

   A caixa de diálogo **Editar configurações do projeto** é aberta.
2. Em **Versão do componente**, selecione a versão desejada, por exemplo, **Versão 104**.

   ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_7.png)
3. Clique em **Salvar**.
4. Marque a alteração e insira uma descrição, como "Configurações do projeto: alterar para v104 "

## Etapa 4: Analise os componentes a serem atualizados

Confirme se as novas versões dos componentes estão disponíveis e, em seguida, atualize-as:

1. Na guia **Projeto**, clique em **Componentes**.

   A caixa de diálogo **Configuração de componentes** é aberta.
2. Exibir a lista de componentes instalados.

   Uma seta no canto inferior direito de cada componente instalado indica que uma versão atualizada do conteúdo desse componente está disponível.

   ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_8.png)
3. Instale e atualize todos os componentes para a nova versão do modelo, v104 e posteriores. Execute a Etapa 5 para cada componente a ser atualizado.

## Etapa 5: Faça upgrade de componentes individuais e verifique as alterações

1. Na caixa de diálogo **Configuração de componentes**, clique duas vezes em um componente específico (por exemplo, CTF - Fonte de custos).

   Uma caixa de diálogo de componentes é aberta.

   ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_9.png)
2. Role para baixo, abaixo da lista de relatórios incluídos, até a seção **Upgrade disponível**.
   1. Uma caixa azul indica que não foram feitas personalizações em nenhum item do componente.
   2. Uma caixa amarela indica que foram encontradas personalizações nos dados, métricas calculadas ou relatórios.

      ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_10.png)

      **OBSERVAÇÃO** : Ocasionalmente, a caixa amarela permanece após você reverter todas as personalizações. Para continuar, clique no botão Upgrade na caixa amarela.
3. Se houver personalizações, clique em **View Conflicts (Exibir conflitos** ) ou role até a parte inferior da página.
4. Reverter todos os relatórios personalizados e métricas calculadas.

   ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_11.png)
5. Para conjuntos de dados personalizados, reverta os conjuntos de dados personalizados para os seguintes componentes relacionados à nuvem:
   1. CTF - Provedor de serviços em nuvem
   2. CTF- Amazon Web Services
   3. CTF- Azure

      **RECOMENDAÇÃO** : Faça uma captura de tela de seus mapeamentos atuais para ajudar no remapeamento dos campos de marcação.

   **CUIDADO** : Não reverta os conjuntos de dados de nenhum outro componente. Se você reverter as alterações do conjunto de dados, será necessário reanexar e mapear novamente os arquivos de origem para os conjuntos de dados mestre.
6. Clique em **Upgrade**.

   O aplicativo levará alguns minutos para processar a atualização. Depois que a tela do componente for atualizada e retornar à página de **configuração do componente**, você poderá continuar. Confirme se a seta de atualização não é mais exibida.

   ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_12.png)
7. Se você reverteu as alterações do conjunto de dados para os relatórios do Cloud, remapeie os arquivos de origem para os dados mestre, como segue:
   1. No Project Explorer, clique em **Tables (Tabelas** ).
   2. Clique em **Dados mestre**.
   3. Anexar.
   4. Mapeie as colunas de origem para as colunas de dados mestre apropriadas.

      **OBSERVAÇÃO** : use a captura de tela feita na etapa anterior para verificar os mapeamentos.
8. Após a conclusão do upgrade, você deve alterar manualmente os conjuntos de dados que não foram revertidos. Para v104, consulte a lista cumulativa de [atualizações de dados do modelo v103 para v104](template103to104dataupdates-9027.html) para identificar quais alterações são necessárias.
9. Faça o check-in de todas as alterações relacionadas ao upgrade de componente único, uma de cada vez, da seguinte forma:

   **CUIDADO** : se você não seguir essas etapas para fazer o check-in dos componentes um de cada vez, poderá ocorrer um erro que o fará perder o trabalho e reiniciar a atualização desde o início.
   1. Selecione **Projetos** e clique em **Check-in**.

      A caixa de diálogo **Check-in** é aberta.
   2. Selecione **Todos os itens** no painel esquerdo (padrão).
   3. Digite uma descrição dos itens no painel **Mensagem**.

      **OBSERVAÇÃO** : insira uma descrição útil, como "Fonte de custos: reverter alterações no conjunto de dados, componente atualizado" Isso é fundamental para as atividades de mesclagem de ramificações mais adiante neste processo de atualização. Revise [a Etapa 9: mesclar alterações no projeto principal (Tronco)](#upgradectto104-8841__Step9MergechangesintothemainprojectTrunk) para entender por que isso é importante.

      ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_13.png)
   4. Clique em **Check In**.
   5. Continue com a Etapa 6.

## Etapa 6: Faça upgrade de todos os outros componentes na ramificação Upgrade

Todos os componentes instalados precisam ser atualizados para a nova versão do modelo. Recomenda-se que você comece com os componentes de nível inferior (por exemplo, componentes CTF-, depois aplicativos CT etc.). No entanto, não é necessário seguir uma ordem exata. Para este exemplo, os componentes instalados são para uma configuração de base de CT no modelo v103.

Observação: Se você abrir o projeto Costing Standard durante o processo de atualização, perceberá que alguns dos links de navegação estão quebrados na ramificação de atualização. Isso será resolvido quando todos os componentes tiverem sido atualizados.

Repita as etapas 4 e 5 para continuar atualizando todos os outros componentes. A ordem a seguir é recomendada; no entanto, talvez você não tenha todos esses componentes instalados em seu ambiente:

- Componente de **revisão da TBM** :
  1. Desativar o componente.
  2. Verifique a alteração, "Revisão da TBM: desabilitar componente"
- **ATUM v2.0** componente:
  1. Desativar o componente.
  2. Verifique na alteração, " ATUM v2.0: disable component."
- **CTF- Componente de fonte de custo** :
  1. Reverter qualquer métrica calculada ou personalizações de relatórios.
  2. Atualize o componente.
  3. Reajuste os arquivos de origem para o conjunto de dados mestre de origem de custos, se você reverteu as alterações do conjunto de dados.
  4. Verifique a alteração, "CTF- Cost Source: reverter métricas calculadas, atualizar componente"
- **CT- Componente de qualidade** :
  1. Reverter qualquer métrica calculada ou personalizações de relatórios.
  2. Atualize o componente.
  3. Verifique a alteração, "CT- Quality: upgrade component"
- Componente **CTF-Trabalho** :
  1. Reverter qualquer métrica calculada ou personalizações de relatórios.
  2. Atualize o componente.
  3. Remapeie os arquivos de origem para o conjunto de dados mestre da mão de obra, se você reverteu as alterações no conjunto de dados.
  4. Verifique a alteração, "CT- Labor: upgrade component"
- Componente de **torres CTF-IT** :
  1. Reverter qualquer métrica calculada ou personalizações de relatórios.
  2. Atualize o componente.
  3. Remapeie os arquivos de origem para o conjunto de dados mestre da Torre de Recursos de TI.
  4. Verifique a alteração, "CTF- IT Towers: reverter métricas calculadas, atualizar componente"
- Componente **CTF-Time Tracking** :
  1. Reverter qualquer métrica calculada ou personalizações de relatórios.
  2. Atualize o componente.
  3. Remapeie os arquivos de origem para o conjunto de dados mestre de controle de tempo, se você reverteu as alterações do conjunto de dados.
  4. Verifique a alteração, "CTF- Controle de tempo: componente de atualização"
- Componente **CTF-Projetos** :
  1. Reverter qualquer métrica calculada ou personalizações de relatórios.
  2. Atualize o componente.
  3. Remapeie os arquivos de origem para o conjunto de dados mestre de projetos, se você reverteu as alterações do conjunto de dados.
  4. Verifique a alteração, "CTF-Projetos: componente de atualização"
- Componente **CTF-Cloud Service** :
  1. Reverter qualquer conjunto de dados, métrica calculada ou personalização de relatório.
  2. Atualize o componente.
  3. Verifique a alteração, "CTF- Cloud Service: reverter métricas calculadas, atualizar componente"
- **CTF- Amazon Web Services** component:
  1. Reverter qualquer conjunto de dados, métrica calculada ou personalização de relatório.
  2. Atualize o componente.
  3. Verifique a alteração, "CTF- Amazon Web Services : componente de atualização"
- **CTF- Azure** component:
  1. Reverter qualquer conjunto de dados, métrica calculada ou personalização de relatório.
  2. Atualize o componente.
  3. Verifique a alteração, "CTF- Azure : componente de atualização"
- Componente **CT Apps-Applications** :
  1. Reverter qualquer métrica calculada ou personalizações de relatórios.
  2. Atualize o componente.
  3. Remapeie os arquivos de origem para o conjunto de dados mestre de aplicativos, caso tenha revertido as alterações no conjunto de dados.
  4. Verifique a alteração, "Aplicativos CT - Aplicativos: reverter métricas calculadas, atualizar componente"
- **CT - Componente Unidades de Negócios** :
  1. Reverter qualquer métrica calculada ou personalizações de relatórios.
  2. Atualize o componente.
  3. Reajuste os arquivos de origem para o conjunto de dados mestre da unidade de negócios, se você reverteu as alterações do conjunto de dados.
  4. Verifique a alteração, "CT- Unidades de negócios: reverter métricas calculadas, atualizar componente"

## Etapa 7: Revise o aplicativo atualizado na ramificação de upgrade

1. Na guia **Projeto**, clique em **Componentes**.

   A caixa de diálogo **Configuração de componentes** é aberta.
2. Verifique se as compilações foram concluídas.

   Você verá uma lista dos check-ins individuais.

   ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_14.png)
3. Na barra de navegação, selecione **Transparência de custos** no menu Aplicativo.

   ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_15.png)
4. Selecione o ramo de upgrade (por exemplo, **Upgrade da versão 104** ).

   A nova página inicial é aberta.

   ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_16.png)

   **OBSERVAÇÃO** : se **a TBM Review** aparecer na barra de menus e a nova página de destino não for exibida, você precisará alterar a página de destino de **TBM Review** para **Service Costing** usando o conjunto de dados params, como segue:
   1. Retornar para **TBM Studio**.
   2. Na guia **Project (Projeto** ), abra a seção **Tables (Tabelas** ) no painel esquerdo.
   3. Pesquise por "params"
   4. Clique em **Params**.
   5. Confira o documento.
   6. Clique na etapa **Upload** transform.
   7. Clique em **Params.csv** e selecione **Download**.
   8. Abra o Excel.
   9. Altere o valor da coluna “InitialReport” para ".View:tab:Service Costing"
   10. Clique em **Salvar**.
   11. Clique em **Params.csv** e selecione **Overwrite**.
   12. Selecione o arquivo salvo e carregue-o em Apptio.
   13. Clique na etapa de transformação **da tabela**.
   14. Verifique se o valor **InitialReport** o valor foi alterado para ".View:tab:Service Costing"
   15. Clique em **Salvar**.
   16. Verifique a mudança.

## Etapa 8: Compare os relatórios do site v103 com os relatórios da nova versão do modelo

1. Abra o projeto Costing Standard em um navegador.
2. Selecione **Tronco** para visualizar os relatórios do Template v103.

   ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_17.png)
3. Abra o projeto Costing Standard em outro navegador.
4. Selecione a ramificação do novo modelo (por exemplo, **Upgrade da versão 104** ) para visualizar os relatórios atualizados.
5. Revisar relatórios lado a lado.

   ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_18.png)
6. Se desejar, aplique novamente as alterações específicas do cliente aos relatórios diretamente na filial para a nova versão do modelo (por exemplo, Upgrade da versão 104).

   **RECOMENDAÇÃO** : Evite fazer alterações em relatórios prontos para uso para que você possa minimizar o esforço envolvido em atualizações futuras.

   **RECOMENDAÇÃO** : se for necessário fazer personalizações de relatórios, aplique-as aos relatórios prontos para uso depois de concluir a Etapa 7, mesclar as alterações de upgrade. Isso minimizará o tempo que você terá para trabalhar na ramificação de atualização da versão 104. Lembre-se: NÃO faça alterações (exceto cargas de dados) no projeto principal (Trunk) depois de criar a ramificação de upgrade.
7. Depois de verificar se os relatórios usam a versão do modelo que você deseja, vá para a Etapa 9 para mesclar as alterações em seu projeto principal.

**DICA** : Consulte [os relatórios de transparência de custos do modelo v103 a v104](../reports-v104/mappingctreports103to104.html) para entender onde os relatórios v103 e as informações relacionadas aparecem em v104.

## Etapa 9: mesclar alterações no projeto principal (Trunk)

Dica: Consulte as [práticas recomendadas de ramificação, hotfix e ramificação](https://community.apptio.com/docs/DOC-5472 "(Abre em uma nova guia ou janela)") no Product Central.

1. Retornar para **TBM Studio**.
2. Selecione o ramo de upgrade (por exemplo, Upgrade da versão 104).
3. Na guia **Projeto**, clique em **Check-in History**.
4. Role para baixo até a parte inferior da lista e clique no primeiro item acima das entradas de bootstrap, por exemplo, Configurações do projeto: altere para v104 check-in.

   **OBSERVAÇÃO** : Você pode selecionar itens adicionais para fazer o check-in como uma única mesclagem, mas não selecione mais do que 5 itens de uma só vez.

   **CUIDADO** : Mesclar mais de 5 itens em um único check-in pode fazer com que o aplicativo falhe.
5. Clique com o botão direito do mouse no item de linha e selecione **Mesclar alterações na ramificação**.

   Para as capturas de tela deste exemplo, usaremos o item de mesclagem CT-Apps Application.
6. Selecione **Tronco** como o destinatário da mesclagem.

   ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_19.png)

   A caixa de diálogo **Mesclar conjuntos de modificações** é aberta.
7. Selecionar todos os itens para mesclagem (padrão).

   **OBSERVAÇÃO** : Não desmarque nenhum item individual. Todos os itens são mesclados, estejam eles selecionados ou não.
8. Clique em **OK**.

   ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_20.png)

   **RECOMENDAÇÃO** : rastreie manualmente as etapas mescladas à medida que você atualiza os componentes, pois a caixa de diálogo Check-in History não indicará quais itens foram mesclados. Se você tentar fazer o check-in de um item duas vezes e a seguinte mensagem for exibida, clique em **Cancelar** e, em seguida, prossiga com um componente diferente.

   ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_21.png)
9. Depois de concluída, a janela poderá mudar para **Tronco**.
10. Mude para **Trunk** para verificar o item mesclado em seu projeto.
11. Para verificar se a alteração foi propagada para o ambiente de desenvolvimento:
    1. Na barra de navegação, selecione o ambiente **In Development**.
    2. Clique na guia **Projeto**.
    3. Clique em **Components (Componentes** ).
    4. Verifique se o componente não exibe mais a seta de atualização, como neste exemplo, para o componente Aplicativo CT-Apps.

       ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_22.png)
12. No menu Environment (Ambiente) da barra de navegação, selecione **Staging (Preparação** ).
13. Na guia **Projeto**, verifique se o ícone Bloqueado está acinzentado (não bloqueado).

    Você precisa fazer isso apenas uma vez.
14. Clique em **Components (Componentes** ) e observe que o componente CT Apps Applications (Aplicativos do CT) exibe a seta de atualização para v103.
15. No menu Ambiente da barra de navegação, selecione **Em desenvolvimento** e clique em **Check-in**.

    A caixa de diálogo **Check-in** é aberta.

    **OBSERVAÇÃO** : se o ícone **Check In** estiver esmaecido, talvez seja necessário aguardar alguns minutos para que os documentos sejam processados e, em seguida, ir para o ambiente **de teste**, voltar para o ambiente **de desenvolvimento** e tentar novamente.
16. Selecionar todos os itens no painel esquerdo (padrão).

    Isso deve ser limitado aos itens mesclados.
17. Digite uma descrição dos itens no painel **Mensagem**.

    **RECOMENDAÇÃO** : use uma descrição útil, como "Merge - CTF- Cost Source: reverter alterações no conjunto de dados, componente atualizado"
18. Clique em **Check In**.

    ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_23.png)

    Aguarde a conclusão da compilação.

    ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_24.png)
19. Verifique se a alteração esperada da etapa de mesclagem de ramificação é aplicada ao ambiente de preparação.

    Neste exemplo, na guia **Projeto**, clique em **Componentes** para verificar se o site v104 está ativo.

    ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_25.png)
20. Retorne ao ramo de upgrade (por exemplo, Upgrade da versão 104) para prosseguir com o próximo item a ser mesclado.

    **Problemas conhecidos:**

- **Mensagem de erro** - O primeiro item mesclado deve ser a **alteração das Configurações do projeto para v104** (ou qualquer versão para a qual você esteja atualizando). Depois de mesclar o item, você poderá ver uma mensagem de erro, "Erro do servidor: Entre em contato com o administrador"

  **Solução** - Saia do navegador, abra-o novamente e prossiga com a etapa de check-in no Trunk. Depois que a alteração do branch de upgrade for feita e propagada para o Staging, você não verá mais a mensagem de erro.
- **Informações conflitantes na barra de navegação** - Ao alternar entre o Tronco e a ramificação do novo modelo (como a atualização da versão 104), a nova ramificação de atualização pode aparecer na barra de navegação enquanto o histórico de check-in é do Tronco. Se isso ocorrer, siga estas etapas:
  1. Feche a caixa de diálogo **Check In History** e talvez todas as outras caixas de diálogo.
  2. Mudar para **Tronco**.
  3. Volte para a ramificação de **upgrade da versão 104**.
  4. Reabra o **histórico de check-in**.
  5. Prossiga com a mesclagem na próxima etapa.
- **Mesclando componentes desabilitados**. Após uma etapa mesclada para um componente desativado, os itens da mesclagem anterior ainda poderão ser listados no painel esquerdo.

  **Solução**. Digite a descrição apropriada para o que acabou de ser mesclado (por exemplo, Merge - ATUM 2.0 component disabled). Quando o cálculo for concluído, você poderá verificar as alterações esperadas no Staging.

## Etapa 10: Mesclar todos os outros componentes

Repita a Etapa 9 para continuar mesclando até 5 ramificações de upgrade individuais (de uma só vez) e os check-ins subsequentes do Tronco (em desenvolvimento) na mesma ordem recomendada na [Etapa 6: Atualize todos os outros componentes na ramificação de upgrade](#upgradectto104-8841__Step6UpgradeallothercomponentsintheUpgradebranch) :

- Mesclar 1 (até 5 itens de mesclagem)
  1. **Configurações do projeto** : Altere para a nova versão do modelo, como v104.

     **OBSERVAÇÃO** Esse deve ser o primeiro item na primeira mesclagem.

     Verifique no Trunk se as configurações do projeto foram alteradas no desenvolvimento e na preparação.
  2. **Revisão da TBM** : Desativar o componente.

     Verifique no Trunk se o componente TBM Review não está mais instalado para Desenvolvimento e Preparação.
  3. **ATUM v2.0** : Desativar o componente.

     Verifique no Trunk se o componente ATUM v.2.0 não está mais instalado para desenvolvimento e preparação.
  4. **CTF - Origem do custo** : Reverter as métricas calculadas e atualizar o componente.

     Verifique no Tronco se nenhuma seta de atualização é exibida no componente CTF- Cost Source em Desenvolvimento e preparação.
  5. **Parâmetros** : Alterar para a página inicial do Service Costing.

     Acesse o aplicativo Costing Standard . Você deverá ver a nova página de destino da versão selecionada. ([Saiba mais](../reports-v104/comparev103v104reports.html) )

     **OBSERVAÇÃO** : esta etapa só é necessária se você tiver instalado o componente TBM Review disponível em v103.
- Mesclar 2 (até 5 itens de mesclagem)
  1. **CT- Qualidade** : Atualize o componente.

     Verifique no Trunk se não há nenhuma seta de atualização no componente CT-Quality em Development and Staging.
  2. **CT- Trabalho** : Atualizar o componente.

     Verifique no Trunk se não há nenhuma seta de atualização no componente CTF- Labor em Development and Staging.
  3. **CTF - Torres de TI** : Reverter as métricas calculadas e atualizar o componente.

     Verifique no Trunk se não há uma seta para cima no componente CTF- IT Towers em Development and Staging.
  4. **CTF - Controle de tempo** : Atualize o componente.

     Verifique no Trunk se não há nenhuma seta de atualização no componente CTF- Time Tracking em Development and Staging.
  5. **CTF- Projetos** : Atualizar o componente.

     Verifique no Trunk se não há nenhuma seta de atualização no componente CTF-Projetos em Desenvolvimento e Preparação.
- Mesclar 3 (até 5 itens de mesclagem)
  1. **CTF - Serviço de nuvem** : Reverter as métricas calculadas e atualizar o componente.

     Verifique no Trunk se não há nenhuma seta de atualização no componente CTF- Cloud Services em Desenvolvimento e Preparação.
  2. **CTF- Amazon Web Services** : Atualize o componente.

     Verifique no Trunk se há uma seta de noupgrade no componente CTF- AWS em Desenvolvimento e Preparação.
  3. **CTF- Azure** : Atualize o componente.

     Verifique no Trunk se não há nenhuma seta de atualização no componente CTF- Azure em Development and Staging.
  4. **Aplicativos CT - Aplicativos** : Reverta as métricas calculadas e atualize o componente.

     Verifique no Trunk se não há nenhuma seta de atualização no componente Aplicativos em Desenvolvimento e Preparação.
  5. **CT- Unidades de negócios** : Reverter as métricas calculadas e atualizar o componente.

     Verifique no Trunk se não há nenhuma seta de upgrade no componente CT- Business Units em Development and Staging.

## Etapa 11: Validar os relatórios do v104 no projeto principal (Tronco)

1. Abra o projeto Costing Standard em um navegador.
2. Selecione **Tronco** para visualizar os relatórios atualizados.
3. Abra o projeto Costing Standard em um segundo navegador.
4. Selecione o ramo **de upgrade da versão 104** para comparar.

   ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_26.png)
5. Comparar e revisar relatórios lado a lado.

   ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_27.png)
6. Se desejar, aplique novamente as alterações específicas do cliente aos relatórios diretamente na ramificação principal (por exemplo, Tronco).

   **RECOMENDAÇÃO** : Evite fazer alterações nos relatórios prontos para uso para minimizar o esforço envolvido em futuras atualizações.

## Etapa 12: Atualizar o ambiente de produção

Depois de concluir a verificação dos relatórios, envie o aplicativo atualizado para a produção.

1. Ir para **TBM Studio**.
2. Selecione o ambiente **de teste**.
3. Na guia **Projeto**, clique em **Bloquear**.

   Uma breve mensagem pop-up indicará que o ambiente está bloqueado. O ambiente agora está pronto para ser promovido à produção.

   ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_28.png)
4. Na guia **Projetos**, clique em **Opções de promoção** e siga um destes procedimentos:
   1. Clique em **Promote Now (Promover agora** ). A atualização é enviada para a produção imediatamente.
   2. Clique em **Promote Later (Promover mais tarde** ) para programar quando o upgrade será publicado na produção.

      ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_29.png)
5. Na guia **Project (Projeto** ), clique em **Calculation Queue (Fila de cálculo)** para verificar a compilação de produção.
6. Compare os números de compilação dos ambientes de desenvolvimento, preparação e produção.

   ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_30.png)

## Etapa 13: Fechar o tronco de mesclagem

1. Selecione o ramo da nova versão do modelo (como Upgrade da versão 104).
2. Na guia **Projeto**, clique em **Fechar filial**.

   A caixa de diálogo **Confirmar fechamento** é aberta.
3. Clique em **OK** para fechar a ramificação.

   ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_31.png)
4. Confirme que Tronco não é mais exibido na barra de navegação.

   ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_32.png)
5. **RECOMENDAÇÃO** : feche a ramificação de upgrade o mais rápido possível. A ramificação consome a mesma quantidade de recursos que o projeto principal do tronco. O fechamento da ramificação de upgrade liberará recursos e melhorará o desempenho geral.
