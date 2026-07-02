---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Integração da transparência de custos (legado)"
breadcrumb:
  - "Planning"
  - "Integrações"
  - "Conecte-se ao site Apptio Costing"
source_path: "it-planning/planning/integrate-ct.html"
images:
  - "resources/images/icons/icon-settings_20x20.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Integração da transparência de custos (legado)

Se a sua organização executa tanto o Apptio Costing Standard quanto um aplicativo Apptio Planning , é possível integrá-los para compartilhar dados.

A integração do Costing Standard com um aplicativo Apptio Planning permite que você realize o seguinte:

- Importe dados de referência de Costing Standard para seu aplicativo Apptio Planning
- Importe dados reais mensais do site Costing Standard para seu aplicativo Apptio Planning
- Publique planos e previsões orçamentárias do seu aplicativo Apptio Planning para Costing Standard

Para obter mais informações, consulte [Solução de problemas de erros de upload de dados de planejamento](troubleshooting.html)

## Ativar a integração

As tarefas desta seção só podem ser executadas por usuários atribuídos à função Admin. Consulte Permissões e funções do Frontdoor.

Um painel aprimorado do Cost Transparency Integration (CTI), introduzido na versão de planejamento 2.78, é um espaço independente em que os usuários administradores podem executar todas as tarefas do Cost Transparency Integration em um único painel de controle. O painel oferece gerenciamento centralizado e importação e exportação com um clique com Costing Standard. Para saber mais, consulte [Cost Transparency Integration Panel](cti_panel.html "O painel atualizado da Integração da Transparência de Custos (CTI), introduzido na versão de planejamento 2.78, é um espaço independente em que os usuários administradores podem executar todas as tarefas da Integração da Transparência de Custos em um único painel de controle. O novo painel oferece gerenciamento centralizado e importação e exportação com um clique, com transparência de custos.").

Em Costing Standard, instale o componente Apptio ITPF Integration. Isso instala automaticamente todos os modelos dos conjuntos de dados de referência necessários para integrar os produtos. Se estiver usando Assets and Vendor, será necessário instalar também os componentes Apptio ITPF Asset e Apptio ITPF Vendor. Para saber mais, consulte [Instalar os componentes de integração do ITPF](../../cost-transparency/configuration/installitpfintegration.html "Três componentes estão disponíveis como parte do módulo Costing Standard Foundation para conectar o Costing Standard (CT) ao IT Planning Foundation (ITPF).") na ajuda do site Costing Standard .

Você pode integrar o Costing Standard usando um dos seguintes métodos de autenticação:

Autenticação por token ( R12+ ) (recomendado)
:   Esse método determina a instância Costing Standard e o domínio do projeto com base nas configurações do ambiente. O ambiente Enhanced Access Administration e o token de autenticação do usuário são incluídos na solicitação.

    Qualquer usuário com permissões **ManagePlans**, **CTIConfig** e **ReadOnlyApi** (permissões incluídas na função padrão Admin) pode se autenticar para publicar planos e importar dados do site Costing Standard.

    Se você se autenticar usando **a autenticação de token ( R12+** ), também deverá escolher um **ambiente**. Isso permite que você use a mesma instância ou projeto Costing Standard para as instâncias de planejamento principal e sandbox ao exportar dados planejados ou importar dados reais e/ou de referência de e para Costing Standard. Por exemplo, você pode importar informações de dados reais e de referência da mesma instância ou projeto do Costing Standard para a área restrita de planejamento e para as instâncias principais ou de produção.
:   [Integrar usando autenticação de token ( R12+ )](#IntegratewithCostTransparency__Integrat)

Autenticação da conta de serviço
:   A autenticação da conta de serviço não é mais compatível com o site Costing Standard v12.9.0 ou posterior.

    Esse método determina a instância Costing Standard e o domínio do projeto a partir das configurações inseridas pelo usuário para esse tipo específico de integração. As credenciais da conta de serviço são transmitidas como um cabeçalho de autenticação "básico" do HTTP.

    Se o seu aplicativo Costing Standard for executado em TBM Studio v.11, você deverá usar a autenticação da conta de serviço.

    [Integrar usando a autenticação da conta de serviço](#IntegratewithCostTransparency__Integrat2)

## Integrar usando autenticação de token ( R12+ )

1. No menu Apptio Planning , selecione **Settings** e, em seguida, selecione **Cost Transparency Integration**.
2. No painel Cost Transparency Integration , selecione **Configure (Configurar** ).
3. Em General, digite o seguinte:

   Método de autenticação
   :   Selecione a autenticação de token ( R12+ ).

   Meio ambiente
   :   Selecione o Ambiente no menu suspenso.

   Instância
   :   Digite a instância Costing Standard .

   Domínio do projeto
   :   Digite o domínio do projeto Costing Standard .

   Importar de
   :   Selecione uma das seguintes opções:
       - Desenvolvimento
       - Produção

         Se você importar da **Produção**, terá que aguardar a conclusão dos cálculos para que os dados sejam exibidos.

   Recursos habilitados
   :   Selecione uma das seguintes opções:

       - **Integração de planos** : permite exportar planos e previsões orçamentárias para Costing Standard. Na lista **Export Format (Formato de exportação** ), selecione uma das seguintes opções:
         - Publicar **meses para todos os anos fiscais como colunas em uma única linha** : publicar cabeçalhos de coluna mensais usando o formato de data período número ano fiscal. Por exemplo, P1 FY2018.
         - **Publicar meses para todos os anos fiscais como linhas individuais** : inclui uma coluna **Data** para o mês e o ano fiscal e uma coluna **Valor** com o valor apropriado para esse período e ano fiscal. Essa opção também usa o formato de número de período do ano fiscal.
       - **Resultados** : permite a importação de resultados mensais de Costing Standard
       - **Dados de referência** : permite a importação de dimensões padrão e personalizadas, como centros de custo e um plano de contas. Se optar por integrar dados de referência, verifique se os nomes dos conjuntos de dados de referência na seção Planning Costing Standard correspondem ao que foi carregado em Costing Standard.
       - **Configurações de exportação** - Configure **as configurações de exportação** para definir o comportamento padrão de exportação para todos os conjuntos de dados do plano. As configurações de exportação permitem controlar como os dados do plano são publicados, incluindo a seleção do formato de exportação, a escolha da moeda padrão ou original, a definição do formato da data e da precisão decimal, a aplicação de filtros de dados confidenciais e a configuração de se os meses são publicados como linhas ou colunas (editado)
4. Selecione Salvar.

## Integrar usando a autenticação da conta de serviço

1. No menu Apptio Planning , selecione **Settings** () e, em seguida, selecione **Cost Transparency Integration**.
2. No painel Cost Transparency Integration , selecione **Configure (Configurar** ).
3. Em General, digite o seguinte:

   Método de autenticação
   :   Selecione Conta de serviço.

   Nome do usuário
   :   Digite o nome de usuário que deseja usar para se autenticar em HTTP.

   Senha
   :   Digite a senha que você deseja usar para se autenticar em HTTP.

   Recursos habilitados
   :   Selecione uma das seguintes opções:
       - **Integração de planos** : permite exportar planos e previsões orçamentárias para Costing Standard. Na lista **Export Format (Formato de exportação** ), selecione uma das seguintes opções:
         - Publicar **meses para todos os anos fiscais como colunas em uma única linha** : publicar cabeçalhos de coluna mensais usando o formato de data período número ano fiscal. Por exemplo, P1 FY2018.
         - **Publicar meses para todos os anos fiscais como linhas individuais** : inclui uma coluna **Data** para o mês e o ano fiscal e uma coluna **Valor** com o valor apropriado para esse período e ano fiscal. Essa opção também usa o formato de número de período do ano fiscal. Por exemplo, P1 FY2018.
       - **Resultados:** permite a importação de resultados mensais do site Costing Standard.
       - **Dados de referência** : permite a importação de dimensões padrão e personalizadas, como centros de custo e um plano de contas. Se optar por integrar dados de referência, verifique se os nomes dos conjuntos de dados de referência na seção Planning Costing Standard correspondem ao que foi carregado para Costing Standard
4. Selecione Salvar.

## Importar dados reais de Costing Standard

1. Selecione ![img](../../../../../03-media/apptio-planning/resources/images/icons/icon-settings_20x20.png).
2. Selecione **Cost Transparency Integration**.
3. Selecione **Importar dados reais**.
4. Selecione o Período inicial e o Período final dos dados que você deseja importar.
5. Selecione **Importar**.

A importação funciona em segundo plano.

Para ver o andamento do processo de importação, na janela A importação de dados reais foi enfileirada, selecione Status.

- Se a opção **Importar da transparência de custos** não estiver disponível ou se a importação falhar, é possível que o site Cost Transparency Integration não esteja configurado corretamente. Entre em contato com o contato de suporte designado ou com o administrador.
- Se a sua organização usa várias moedas, você deve usar a mesma tabela de taxas de câmbio reais para o aplicativo Apptio Planning e Costing Standard. Consulte [Suporte para várias moedas](support-multiple-currencies.htm "(Abre em uma nova guia ou janela)").

## Publicar planos para Costing Standard

Antes de publicar um conjunto de dados em Costing Standard a partir de seu aplicativo Apptio Planning , certifique-se de que o conjunto de dados exista em Costing Standard.

1. Selecione ![img](../../../../../03-media/apptio-planning/resources/images/icons/icon-settings_20x20.png).
2. Selecione **Cost Transparency Integration**.
3. Selecione **Publicar**.
4. No menu suspenso, selecione o plano que deseja publicar.
5. Selecione os tipos de itens de linha que você deseja publicar.
6. Selecione **Publicar**.

A publicação funciona em segundo plano.

Para ver o andamento do processo de publicação, na janela Seu plano foi colocado na fila para publicação, selecione Status.

- Se Project Financial Planning está habilitado, o **Publicar Financeiro para Costing Standard** a ação será movida da página **Todos os departamentos** > **Despesas** > **Resumo** para a página **Todas as seções do plano** > **Razão**. Isso publicará todos os itens de linha financeiros diretos, indiretos e de cobrança em Costing Standard.
- Se a opção **Publish to Costing Standard** não estiver disponível, ou se a publicação falhar, seu Cost Transparency Integration pode não estar configurado corretamente. Entre em contato com o contato de suporte designado ou com o administrador.
- Se sua organização utiliza várias moedas, Apptio Planning os aplicativos podem publicar até 72 meses de dados em uma única ação de publicação (consulte [Suporte para várias moedas](support-multiple-currencies.htm "(Abre em uma nova guia ou janela)")).

## Importar dados de referência de Costing Standard

As tarefas desta seção só podem ser executadas por usuários atribuídos à função Admin. Consulte Permissões e funções do Frontdoor.

Os dados de referência devem ser consistentes para que todos os recursos de relatório funcionem corretamente. Consulte [Gerenciar dados de referência](manage-reference-data.html "(Abre em uma nova guia ou janela)"). Inicialmente, os formatos de dados do aplicativo Apptio Planning e do Costing Standard não são exatamente iguais. Antes de continuar, considere as seguintes diferenças de dados:

| Tabela | O que procurar |
| --- | --- |
| Contas | Os dados de referência da conta em Costing Standard não incluem:   - Grupo de contas - Subgrupo de contas - Fixo/Variável - Discricionário/não discricionário   Essas dimensões aparecem em vários relatórios no Planejamento. Você deve incluir essas dimensões além das informações padrão da conta. |
| Departamento | Os dados de referência do departamento em Costing Standard não incluem:   - Proprietário - Proprietário do orçamento   Essas dimensões aparecem em vários relatórios no Planejamento. Você deve incluir essas dimensões além das informações padrão da listagem do departamento. |

Siga estas etapas para importar dados de referência do site Costing Standard. Quando você importa dados de referência, o conjunto de dados de referência mais recente é importado, independentemente da configuração de data ativa em Costing Standard.

1. Selecionar ![img](../../../../../03-media/apptio-planning/resources/images/icons/icon-settings_20x20.png)
2. Selecione **Cost Transparency Integration**.
3. Selecione **Importar dados de referência**.
4. Em Categories and Import Values (Categorias e valores de importação), selecione os conjuntos de dados que deseja importar.
5. Selecione **Importar**.

A importação funciona em segundo plano.

Para ver o andamento do processo de importação, na janela Import of Reference Data has been queued (A importação de dados de referência foi enfileirada), selecione **Status**.

**Tópico principal:** [Conecte-se ao Cálculo de Custos d Apptio](../../it-planning/planning/adm/adm_capabilities.html "Apptio O planejamento integra-se ao Apptio cálculo de custos usando o ADM ( Data Management Automated Decision Making). O ADM é um serviço de plataforma compartilhada projetado para fornecer uma experiência de troca de dados unificada, segura e escalável entre Apptio aplicativos.")
