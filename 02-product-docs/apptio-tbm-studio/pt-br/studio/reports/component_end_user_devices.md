---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Configure os dispositivos do usuário final"
breadcrumb: []
source_path: "studio/reports/component_end_user_devices.html"
images:
  - "resources/images/studio_images/eud-1.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configure os dispositivos do usuário final

Conclua estas etapas para começar a usar os dispositivos de usuário final:

## Instale o componente Dispositivos do usuário final

1. Criar um projeto em TBM Studio.
2. Navegue até Project > Enable Features (Projeto > Ativar recursos) e verifique se Templates and Modules (Beta) está ativado pelo administrador de suporte do Apptio ou pelo CSM do Apptio.

   Observação: Para as versões R12.10.0 a R12.10.7, a opção **Templates and Modules (Beta)** deve ser ativada. Quando essa opção estiver ativada, você poderá instalar o componente "Dispositivos do usuário final". A partir da versão R12.10.8, os dispositivos de usuário final são GA e esse componente está disponível sem nenhuma habilitação de recurso.
3. Navegue até Project > Components, role para baixo até a lista de recursos disponíveis e instale End User Devices no projeto.
   - Para clientes com formato de data (dd/MM/aaaa), vá para editar as configurações do projeto e verifique se "Locale" está definido como "United Kingdom" (Reino Unido).
   - Para clientes com formato de data (MM/dd/aaaa), vá para editar as configurações do projeto e verifique se "Locale" está definido como "United States".
4. Existem basicamente três conjuntos de dados necessários para configurar os dispositivos do usuário final. Prepare seus dados em formato tabular para as seguintes tabelas em seu projeto:
   - Active Directory dados
   - Dados trabalhistas
   - Dados dos dispositivos do usuário final
5. Mapeie essas tabelas para as seguintes tabelas mestre. Para obter mais informações, consulte [Upload de dados](../data%20studio/upload-data.html) e [Map Columns](../data%20studio/mapcolumns.html).

| Tabela criada | Mesa principal (presente em Mesas) |
| --- | --- |
| Active Directory dados | EUI Active Directory Dados mestre |
| Dados trabalhistas | Dados mestre de mão de obra da EUI |
| Dados dos dispositivos do usuário final | Entrada de dispositivo do usuário final |

As tabelas a seguir são criadas automaticamente quando o componente é instalado e podem ser vistas na lista **Tabelas** :

- Entrada de termo EOL e EOW do dispositivo
- Estimativa do dispositivo Entrada de custo de atualização
- Entrada de definição de status do dispositivo do usuário final em estoque
- Dispositivo do usuário final Versão do sistema operacional Entrada de referência
- Entrada de isenção de usuário final

Você deve fazer upload de dados para essas tabelas. Para obter mais informações, consulte [Upload de dados](../data%20studio/upload-data.html).

Observação: faça upload de dados para as tabelas mestre de entrada quando houver alterações ou quando houver uma atualização mensal. Isso garante que os relatórios sejam precisos.

## Detalhes do componente

| Nome da Tabela | Tipo |
| --- | --- |
| Active Directory | Tabela de entrada (tabela a ser criada e dados a serem carregados) |
| DISPOSITIVOS DO USUÁRIO FINAL | Tabela de entrada (tabela a ser criada e dados a serem carregados) |
| DADOS TRABALHISTAS | Tabela de entrada (tabela a ser criada e dados a serem carregados) |
| Entrada de termo EOL e EOW do dispositivo | Tabela de entrada |
| Estimativa do dispositivo Entrada de custo de atualização | Tabela de entrada |
| Entrada de definição de status do dispositivo do usuário final em estoque | Tabela de entrada |
| Dispositivo do usuário final Versão do sistema operacional Entrada de referência | Tabela de entrada |
| Entrada de isenção de usuário final | Tabela de entrada |
| Termo EOL e EOW do dispositivo | Mesa Master |
| Estimativa do dispositivo Custo de atualização | Mesa Master |
| Definição do status do dispositivo do usuário final em estoque | Mesa Master |
| Referência da versão do sistema operacional do dispositivo do usuário final | Mesa Master |
| Isenção de usuário final | Mesa Master |
| Insights do usuário final Dados mestre | Mesa Master |
| Entrada de dispositivo do usuário final | Mesa Master |
| EUI Active Directory Dados mestre | Mesa Master |
| Dados mestre de mão de obra da EUI | Mesa Master |
| Referência da versão do sistema operacional do usuário final | Mesa Master |
| Sequência de ordenação de relatórios EOL EOW | Referência/Tabela de consulta |
| Ajudante de período EOL e EOW | Referência/Tabela de consulta |
| Faixa etária do usuário final Tablematch | Referência/Tabela de consulta |
| Sequência de relatórios | Referência/Tabela de consulta |
| Insights do usuário final Pre Master Staging | Tabela normal/Tabela de transição |
| Insights do usuário final Pré-dados mestre | Tabela normal/Tabela de transição |
| Referência editável das percepções do usuário final | Mesa transformada |

Dica: os dispositivos do usuário final são compatíveis com várias moedas.

## Configurar definições para o modelo de dispositivos de usuário final

1. Crie tabelas de entrada e carregue os dados regularmente (de preferência mensalmente) e mapeie todos os dados conforme necessário para as tabelas mestre existentes. Consulte [Instalar o componente Dispositivos do usuário final](#ConfigureEndUserDevices__InstalltheEndUserDevicescomponent) para obter mais informações.
2. Mapeie os dados de mão de obra e de diretório no EUI Labor Master Data e no EUI Active Directory Master Data, respectivamente. Consulte [Instalar o componente Dispositivos do usuário final](#ConfigureEndUserDevices__InstalltheEndUserDevicescomponent) para obter mais informações.
3. Configure suas tabelas de entrada para tabelas mestre usando as fórmulas listadas abaixo. Se a etapa Fórmulas não for exibida, adicione-a usando a opção Adicionar etapa.

   Dica: as fórmulas listadas abaixo são apenas dados de referência. Você pode atualizar as fórmulas de acordo com seus dados específicos e padrões do setor.

   Para clientes com formato de data dd/MM/aaaa
   :   - Atualize a seguinte coluna para **Active Directory** :

         | Nome da coluna | Tipo | Formato | Fórmula |
         | --- | --- | --- | --- |
         | Carimbo de data e hora do último logon | Data | dd/MM/aaaa | =DateFormat($\_,"dd/MM/yyyy") |
       - Crie e atualize as seguintes colunas para **Dispositivos de usuário final** :

         | Nome da coluna | Tipo | Formato | Fórmula |
         | --- | --- | --- | --- |
         | Unidade de negócios | Rótulo |  | =Lookup(Employee ID,EUI Labor Master Data,Employee ID,Business Unit) |
         | Proprietário da unidade de negócios | Rótulo |  | =Lookup(Employee ID,EUI Labor Master Data,Employee ID,Business Unit Owner) |
         | CC Check | Rótulo |  | =Lookup(Employee ID,EUI Labor Master Data,Employee ID,Cost Center) |
         | Centro de custos | Rótulo |  | =IF( {CC Check}!="",Lookup(Employee ID,EUI Labor Master Data,Employee ID,Cost Center Description)&" ("&Lookup(Employee ID,ACME LAB,Employee ID,Cost Center)&")","") |
         | Proprietário do centro de custo | Rótulo |  | =Lookup(ID do funcionário, dados mestre de mão de obra da EUI, ID do funcionário, proprietário do centro de custo) |
         | Departamento | Rótulo |  | =Lookup(Employee ID,EUI Labor Master Data,Employee ID,Cost Center Description) |
         | Contagem de Dispositivo | Numérico |  | =1 |
         | Inventário em estoque | Rótulo |  | =Lookup(Inventory Status,End User Device In Stock Status Definition,In Stock Status List,In Stock Status List) |
         | S.O. | Rótulo |  | =Lookup(Asset ID,EUI Active Directory Master Data,Asset ID,OS) |
         | Versão de S.O. | Rótulo |  | =Lookup(Asset ID,EUI Active Directory Master Data,Asset ID,OS Version) |
         | Tabela de fontes | Rótulo |  | ="End User Devices Raw" (Dispositivos do usuário final brutos) |
         | Nome de usuário HR | Rótulo |  | =Lookup(Employee ID,EUI Labor Master Data,Employee ID,Employee Name) |
         | Data de aquisição | Data | dd/MM/aaaa | =DateFormat($\_,"dd/MM/yyyy") |
         | Data do fim da vida útil | Data | dd/MM/aaaa | =DateFormat($\_,"dd/MM/yyyy") |
         | Data de atualização | Data | dd/MM/aaaa | =DateFormat($\_,"dd/MM/yyyy") |
         | Nome do usuário | Rótulo |  | =if($\_!="",$\_,If( {User Name HR} ="" AND {In Stock Inventory} ="", "ID do funcionário não encontrado", {User Name HR} )) |
         | Data de término da garantia | Data | dd/MM/aaaa | =DateFormat($\_,"dd/MM/yyyy") |
         | Data de início da garantia | Data | dd/MM/aaaa | =DateFormat($\_,"dd/MM/yyyy") |

         ![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/eud-1.png)

         ![imagem](../../resources/images/studio_images/eud-2_913x453.png)
       - Atualize as seguintes colunas para **Labor Data** :

         | Nome da coluna | Tipo | Formato | Fórmula |
         | --- | --- | --- | --- |
         | Centro de custo e ID | Rótulo |  | =Descrição do centro de custo&&Centro de custo |
         | Data de Término | Data | dd/MM/aaaa | =DateFormat($\_,"dd/MM/yyyy") |
         | Data de Início | Data | dd/MM/aaaa | =DateFormat($\_,"dd/MM/yyyy") |

         ![imagem](../../resources/images/studio_images/eud-3_913x458.png)

   Para clientes com formato de data MM/dd/yyyy
   :   - Atualize a seguinte coluna para **Active Directory** :

         | Nome da coluna | Tipo | Formato | Fórmula |
         | --- | --- | --- | --- |
         | Carimbo de data e hora do último logon | Data | MM/dd/aaaa | =DateFormat($\_,"MM/dd/yyyy") |
       - Crie e atualize as seguintes colunas para **Dispositivos de usuário final** :

         | Nome da coluna | Tipo | Formato | Fórmula |
         | --- | --- | --- | --- |
         | Unidade de negócios | Rótulo |  | =Lookup(Employee ID,EUI Labor Master Data,Employee ID,Business Unit) |
         | Proprietário da unidade de negócios | Rótulo |  | =Lookup(Employee ID,EUI Labor Master Data,Employee ID,Business Unit Owner) |
         | CC Check | Rótulo |  | =Lookup(Employee ID,EUI Labor Master Data,Employee ID,Cost Center) |
         | Centro de custos | Rótulo |  | =IF( {CC Check}!="",Lookup(Employee ID,EUI Labor Master Data,Employee ID,Cost Center Description)&" ("&Lookup(Employee ID,ACME LAB,Employee ID,Cost Center)&")","") |
         | Proprietário do centro de custo | Rótulo |  | =Lookup(ID do funcionário, dados mestre de mão de obra da EUI, ID do funcionário, proprietário do centro de custo) |
         | Departamento | Rótulo |  | =Lookup(Employee ID,EUI Labor Master Data,Employee ID,Cost Center Description) |
         | Contagem de Dispositivo | Numérico |  | =1 |
         | Inventário em estoque | Rótulo |  | =Lookup(Inventory Status,End User Device In Stock Status Definition,In Stock Status List,In Stock Status List) |
         | S.O. | Rótulo |  | =Lookup(Asset ID,EUI Active Directory Master Data,Asset ID,OS) |
         | Versão de S.O. | Rótulo |  | =Lookup(Asset ID,EUI Active Directory Master Data,Asset ID,OS Version) |
         | Tabela de fontes | Rótulo |  | ="End User Devices Raw" (Dispositivos do usuário final brutos) |
         | Nome de usuário HR | Rótulo |  | =Lookup(Employee ID,EUI Labor Master Data,Employee ID,Employee Name) |
         | Data de aquisição | Data | MM/dd/aaaa | =DateFormat($\_,"MM/dd/yyyy") |
         | Data do fim da vida útil | Data | MM/dd/aaaa | =DateFormat($\_,"MM/dd/yyyy") |
         | Data de atualização | Data | MM/dd/aaaa | =DateFormat($\_,"MM/dd/yyyy") |
         | Nome do usuário | Rótulo |  | =if($\_!="",$\_,If( {User Name HR} ="" AND {In Stock Inventory} ="", "ID do funcionário não encontrado", {User Name HR} )) |
         | Data de término da garantia | Data | MM/dd/aaaa | =DateFormat($\_,"MM/dd/yyyy") |
         | Data de início da garantia | Data | MM/dd/aaaa | =DateFormat($\_,"MM/dd/yyyy") |

         ![imagem](../../resources/images/end%20user%20devices%20-%20configuration%20guide/component%20end%20user%20devices_1.png)
       - Atualize as seguintes colunas para **Labor Data** :

         | Nome da coluna | Tipo | Formato | Fórmula |
         | --- | --- | --- | --- |
         | Centro de custo e ID | Rótulo |  | =Descrição do centro de custo&&Centro de custo |
         | Data de Término | Data | MM/dd/aaaa | =DateFormat($\_,"MM/dd/yyyy") |
         | Data de Início | Data | MM/dd/aaaa | =DateFormat($\_,"MM/dd/yyyy") |

         ![imagem](../../resources/images/end%20user%20devices%20-%20configuration%20guide/component%20end%20user%20devices_2_762x592.png)
4. Mapeie **os dados dos dispositivos do usuário final** para a **entrada do dispositivo do usuário final**, anexando-os. Para obter mais informações, consulte [Anexar dados](../data%20studio/append-data.html).

   ![imagem](../../resources/images/end%20user%20devices%20-%20configuration%20guide/component%20end%20user%20devices_3_821x505.png)
5. Se as colunas tiverem coluna de data, verifique o formato e defina o formato de data para todas as tabelas de dados mestre ou, ao fazer upload de dados, certifique-se de definir o tipo de dados de substituição dessas colunas para o formato necessário.
6. Se houver algumas datas codificadas no conjunto de tabelas mestre, altere o formato de acordo com suas necessidades.
7. Verifique os dados pré-mestre do End User Insights para confirmar se todos os dados são provenientes da **entrada do dispositivo do usuário final**.
8. Verifique o **End User Insights Pre Master Staging** para confirmar se todos os dados e fórmulas são provenientes dos **dados do End User Insights Pre Master**.
9. Verifique o **End User Insights Master Data** para confirmar o fluxo de dados do **End User Insights Pre Master Staging**.

   ![imagem](../../resources/images/end%20user%20devices%20-%20configuration%20guide/component%20end%20user%20devices_4.png)
10. Verifique **o modelo do End User Insights** para ver se a maioria dos custos está sendo alocada corretamente.

    ![imagem](../../resources/images/end%20user%20devices%20-%20configuration%20guide/component%20end%20user%20devices_5.png)

    Observação: O custo na captura de tela serve apenas como referência.

    ![imagem](../../resources/images/end%20user%20devices%20-%20configuration%20guide/component%20end%20user%20devices_6.png)

    Observação: O custo na captura de tela serve apenas como referência.
11. Verifique se **os relatórios OOTB dos dispositivos do usuário final** estão mostrando os números desejados.

## Fluxo de configuração dos dispositivos do usuário final

![imagem](../../resources/images/end%20user%20devices%20-%20configuration%20guide/component%20end%20user%20devices_7.png)

## Estúdio de relatórios

Depois de instalar os Dispositivos do usuário final, **o Report Studio** exibe um bloco Dispositivos do usuário final na página inicial. Você pode usar isso para navegar até os **relatórios de Dispositivos do usuário final**.

A seguir, um rápido resumo dos relatórios de Dispositivos do usuário final:

![imagem](../../resources/images/end%20user%20devices%20-%20configuration%20guide/component%20end%20user%20devices_9.png)

[Saiba mais sobre os relatórios de Dispositivos do usuário final](end_user_dev_dashboard.html)
