---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Passos para habilitar relatórios OOTB (NX) modernizados na instância do cliente"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "ApptioIBM Report Studio (Novo)"
  - "Configuração e personalização"
source_path: "studio/report-studio/ootb-report-pp.html"
images:
  - "resources/images/studio_images/pp-s2.png"
  - "resources/images/studio_images/pp-s3a.png"
  - "resources/images/studio_images/pp-s5a.png"
  - "resources/images/studio_images/pp-s5b.png"
  - "resources/images/studio_images/pp-screenshot.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Passos para habilitar relatórios OOTB (NX) modernizados na instância do cliente

Este documento descreve as **etapas necessárias para habilitar os relatórios OOTB modernizados (Nova Experiência (NX))** em uma instância do cliente. Esses relatórios oferecem maior visibilidade, melhores insights e uma experiência mais intuitiva, mantendo o uso dos **mesmos conjuntos de dados do Classic TBM Studio**.

1. **Verificar pré-requisitos**

   Antes de ativar qualquer relatório, certifique-se de que o ambiente do cliente atenda aos **requisitos obrigatórios relativos ao modelo e à versão do servidor**.

   - **Versões necessárias**
     - **Versão do modelo:** V120
     - **Versão do servidor:** 12.11.22 ou superior

     Essas versões são **obrigatórias** para habilitar os relatórios OOTB modernizados.
2. **Direcione o modelo do cliente para a versão de conteúdo V120 (não é necessária atualização)**

   Se o cliente **ainda não** estiver apontando para a versão de conteúdo V120, **não** será necessário realizar uma atualização completa do modelo. Você pode verificar a versão do conteúdo no TBM Studio, na guia “Projeto” > “Configurações do projeto”. Na janela pop-up, há um campo chamado “Versão do componente” que indica qual é a versão atual do modelo de conteúdo.

   ![janela pop-up de edição das configurações do projeto](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pp-s2.png)

   - **O que é necessário**
     - **Configure** temporariamente a instância do cliente para a versão de conteúdo V120 na seção “**Componentes do** relatório”, utilizando o menu suspenso “Versão do componente” (navegue pelo TBM Studio > guia “Projeto” > “Configurações do projeto”; na janela pop-up, você encontrará um campo chamado “Versão do componente”)
     - Esta etapa é necessária porque **os novos componentes de relatório do Modernized OOTB (NX) só ficam visíveis quando a versão do conteúdo está definida como “ V120 ”**
   - **Principais esclarecimentos**
     - **Não é necessária nenhuma atualização do modelo**
     - Trata-se **apenas** de uma alteração no índice de conteúdo, não de uma atualização estrutural
     - Depois de acessar V120, os clientes podem **instalar as coleções de relatórios necessárias**
   - **Reverter a versão do conteúdo (opcional)**
     - Depois que os componentes necessários do relatório NX estiverem instalados, o cliente **poderá reverter para a versão original do conteúdo**, se desejar
     - **Não há nenhum risco em fazer isso**
   - **Aviso importante**
     - Os componentes do relatório NX instalados **permanecerão disponíveis** mesmo após a reversão
     - Todas **as tabelas, modelos e relatórios** instalados permanecem intactos
     - Não há perda de dados nem impacto funcional devido à reversão da versão do conteúdo

     Observação: Se não for definida temporariamente **a versão** de conteúdo V120, os novos componentes NX **não** ficarão visíveis na lista de componentes.
   - **Documentação de referência**

     Caso seja necessária mais orientação, os clientes podem consultar a documentação oficial do Apptio :

     - Instalação de novas soluções de cálculo de custos do Apptio em projetos com modelos antigos

       https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=configuration-installing-new-apptio-costing-solutions-older-template-projects
3. **Instalar os componentes modernizados do NX**

   Assim que o ambiente estiver ativo:

   - Versão do modelo **V120**
   - Versão do servidor **12.11.22 ou superior**

   Os componentes do relatório podem ser ativados usando **qualquer** uma das seguintes opções:

   **Opção A: Função de acesso de gravação Admin/TBM Studio**
   - Um usuário com **a função de administrador d Apptio ou do TBM Studio com acesso de gravação** pode ativar diretamente os componentes. Isso pode ser feito seguindo o Passo 2 para ativar primeiro a versão do modelo para a versão mais recente do conteúdo. Após isso, os usuários podem acessar a guia “Projetos” e instalar os componentes NX recém-disponibilizados.

     ![ativar modelos e módulos](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pp-s3a.png)

   **Opção B: Gerente de Sucesso do Cliente (CSM)**
   - O cliente pode solicitar ao seu **CSM designado** que ative os componentes em seu nome.
4. **Identificar coleções e componentes de relatórios disponíveis**

   A tabela a seguir lista as **coleções de relatórios** e **os principais componentes de relatórios** disponíveis nesta versão.

   - **Coleções e componentes de relatórios NX modernizados**
   - **Finanças**
   - **CTF – Relatórios de Origem de Custos do NX**
     - Análise Financeira
     - Financial Review – CapEx
     - Análise financeira
   - **Mainframe**
   - **BI – Relatórios do Mainframe Insights NX**
     - Custo total de propriedade (TCO) de mainframes
     - Análise de mainframe
     - Aplicativos de mainframe
     - Utilização de mainframes
     - Consumo de recursos do mainframe
     - Fatura de consumo de uso do mainframe
   - **Custo total de propriedade (TCO) e uso da IA**
   - **Relatórios de TCO e uso de IA no NX**
     - Custo total de propriedade (TCO) e uso da IA
   - **Fornecedores**
   - **CTF – Relatórios de fornecedores NX**
     - Avaliação do fornecedor
     - Dedução do custo do fornecedor
     - Lista de fornecedores
   - **Mão de Obra**
   - **CTF – Relatórios Labor NX**
     - Revista do Trabalho
     - Análise da mão de obra
     - Exclusão dos custos de mão de obra
   - **Aplicativos**
   - **Aplicativos CT – Relatórios NX**
     - Análise da candidatura
     - Lista de aplicativos
     - Aplicativos novos e descontinuados
     - Análise de infraestrutura por aplicação
   - **Serviços**
   - **Aplicativos de TC – Serviços Relatórios NX**
     - Lista de serviços
     - Avaliação do serviço
   - **Custo total de propriedade (TCO) da nuvem pública**
   - **Relatórios de TCO da Nuvem Pública NX**
     - Custo total de propriedade (TCO) da nuvem pública
5. **Instalar os componentes do NX Report no TBM Studio**
   1. Acesse o **TBM Studio,** conforme mencionado na etapa 3.
   2. Vá para a seção **Componentes**
   3. Localize os **componentes** necessários do relatório NX
   4. **Instale** os componentes desejados

   Após a instalação, os componentes aparecerão na lista de **Componentes Disponíveis** no TBM Studio.

   A captura de tela abaixo mostra os componentes marcados com uma estrela como novos componentes disponíveis para instalação.

   ![instalar componentes](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pp-s5a.png)

   Ao clicar em qualquer componente, serão exibidas a descrição e os detalhes sobre ele. Após clicar no botão de instalação, o usuário poderá instalar os componentes, e os relatórios ficarão disponíveis no New Report Studio, que é o botão azul mencionado na captura de tela.

   ![componente de relatórios do Apps BX](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pp-s5b.png)
6. **Acesse o Novo Studio de Relatórios**
   1. Após a instalação do componente, clique no **link/botão azul** na parte superior da tela
   2. Esta ação direciona o usuário para o **New Reporting Studio**
7. **Acesso e uso dos relatórios modernizados do NX**
   - Os componentes de relatório instalados aparecerão como **pastas de coleção** no New Reporting Studio
   - Os usuários podem:
     - Selecione a **coleção** desejada
     - Acesse **os relatórios principais** individuais
     - Use **os caminhos de detalhamento** integrados para obter insights mais aprofundados

     Captura de tela mostrando como ficará após a instalação do componente:

     ![página do visualizador de relatórios](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pp-screenshot.png)

   Importante:
   - Os relatórios OOTB modernizados utilizam os **mesmos conjuntos de dados** já disponíveis no **TBM Studio Classic**
   - Não é necessária nenhuma configuração ou importação adicional de dados
   - Depois que os componentes do Modernized NX Report forem instalados e registrados, os usuários finais poderão visualizar essas coleções de relatórios e os próprios relatórios em sua instância.

## Perguntas frequentes: Relatórios OOTB (NX) modernizados

**Seção A: Perguntas frequentes gerais – Relatórios OOTB NX (modernizados)**

1. O que são relatórios OOTB (NX) modernizados?

   Os relatórios OOTB (New Experience – NX) modernizados são **relatórios prontos para uso de última geração,** projetados para oferecer:
   - Melhor visibilidade
   - Interface de usuário mais limpa e moderna
   - Informações mais detalhadas
   - Navegação simplificada com experiências de detalhamento

   Eles são desenvolvidos com base no **modelo de dados existente do TBM** e utilizam os mesmos conjuntos de dados que os relatórios do TBM Studio Classic.
2. Em que os relatórios do NX diferem dos relatórios padrão do Classic?

   A NX informa:
   - São **fáceis de usar e baseados em insights**
   - Consolide relatórios grandes e complexos em visualizações específicas
   - Oferecer navegação detalhada em vez de relatórios estáticos com várias páginas
   - Aderir aos **padrões modernos de relatórios e experiência do usuário** do site Apptio

   Os relatórios clássicos continuam sendo suportados, mas os relatórios NX representam o **futuro da geração de relatórios**.
3. Os relatórios NX substituem os relatórios clássicos prontos para uso?

   Nº **Os relatórios NX coexistem com os relatórios clássicos**. Os clientes podem:
   - Continue usando os relatórios clássicos
   - Explore e adote os relatórios do NX no seu próprio ritmo

   Com o tempo, os relatórios do NX passarão a ser a principal forma de geração de relatórios.
4. Os relatórios do NX já estão disponíveis para o público em geral (GA)?

   Sim. Os relatórios do NX são lançados como **versão estável**. Isso significa que:
   - Os recursos podem sofrer alterações
   - O feedback é incorporado de forma ativa
   - As atualizações podem ser lançadas com frequência
5. Quais áreas funcionais são abrangidas pelos relatórios do NX?

   Os relatórios NX estão disponíveis em 8 componentes para o Lote 1, incluindo:
   - Finanças
   - Mainframe
   - Custo total de propriedade (TCO) e uso da IA
   - Fornecedores
   - Mão de Obra
   - Aplicativos
   - Serviços
   - Custo total de propriedade (TCO) da nuvem pública

**Seção B: Perguntas frequentes sobre implementação e capacitação**

1. Quais são os pré-requisitos para ativar os relatórios do NX?

   O cliente deve estar em:
   - **Versão do modelo:** V120
   - **Versão do servidor:** 12.11.22 ou superior

   Esses são obrigatórios para ativar os relatórios do NX.
2. É necessária uma atualização completa do modelo para habilitar os relatórios do NX?

   Nº **Não é necessária uma atualização completa do modelo**. Os clientes precisam apenas **apontar** temporariamente para a versão de conteúdo V120 para tornar os componentes NX visíveis.
3. Por que precisamos indicar a versão do conteúdo V120?

   Os componentes do relatório NX estão incluídos na **versão de conteúdo V120**. Sem redirecionar para V120:
   - Os componentes NX **não aparecerão** na lista de componentes
   - A instalação não é possível
4. É possível reverter a instalação após instalar os componentes do NX?

   Sim. Os clientes podem voltar à versão original do conteúdo após a instalação. **Não** há risco:
   - Os componentes do NX instalados continuam disponíveis
   - Tabelas, modelos e relatórios permanecem intactos
   - Sem perda de dados nem impacto no sistema
5. Quem pode habilitar os componentes do NX Report?

   Os componentes do NX Report podem ser ativados da seguinte forma:
   - **Função de acesso de gravação** no Admin/TBM Studio
   - Ou **o Gerente de Sucesso do Cliente (CSM) designado** para o cliente
6. Onde os usuários acessam os relatórios do NX após a instalação?

   Após a instalação:
   - Clique no **link/botão azul** na parte superior da tela
   - Isso direciona os usuários para o **Novo Reporting Studio**
   - Os relatórios são exibidos como **coleções,** com navegação e caminhos de detalhamento
7. Os relatórios do NX precisam de novas fontes de dados ou de nova importação?

   Nº Os relatórios do NX utilizam os **mesmos conjuntos de dados já disponíveis no Classic TBM Studio**. Sem adicional:
   - Configuração de dados
   - Ingestão de dados
   - Mapeamento

     é necessário.

**Seção C: Perguntas frequentes sobre uso e comportamento**

1. Os relatórios do NX podem ser usados imediatamente após a instalação?

   Sim. Depois que os componentes forem instalados e registrados:

   - As coleções de relatórios ficam visíveis
   - Os usuários finais podem começar a usar os relatórios imediatamente
2. Os relatórios do NX são baseados em funções?

   Segue abaixo o acesso aos relatórios do NX:

   - Funções de usuário existentes
   - Permissões do projeto

     Não é necessário nenhum gerenciamento de acesso separado.
3. Os relatórios do NX permitem a exploração detalhada?

   Sim. Os relatórios NX são elaborados com:

   - Informações resumidas
   - Detalhamentos contextuais
   - Caminhos de navegação simplificados

**Seção D: Perguntas frequentes sobre personalização (Importante para os clientes)**

1. Qual é a prática recomendada para relatórios do NX prontos para uso?

   **Não personalize os relatórios padrão do NX.** Manter os relatórios inalterados garante:
   - Acesso automático às melhorias
   - Compatibilidade com versões futuras
   - Menores custos de manutenção
2. O que acontece se eu personalizar um relatório padrão do NX?

   Se um relatório NX pronto para uso for personalizado:
   - As futuras atualizações **não** serão aplicadas
   - O relatório passa a ser **gerenciado pelo cliente**
   - As novas funcionalidades e correções não serão aplicadas
3. Os relatórios personalizados do NX receberão atualizações em versões futuras?

   Nº As melhorias são aplicadas **apenas aos relatórios NX padrão, sem modificações**.
4. Como os clientes podem receber as últimas atualizações do relatório NX?

   Os clientes devem:
   1. **Reverter as personalizações** nos relatórios padrão afetados
   2. Entre em contato com o seu **CSM ou com o suporte da IBM Apptio**
   3. Atualize a instância para a versão desejada
5. Como faço para reverter personalizações nos relatórios padrão do NX?
   1. Acesse o **TBM Studio → guia Projeto**
   2. Selecionar **componentes**
   3. Ir para **Componentes instalados**
   4. Abra o componente personalizado
   5. Role até **os elementos personalizados**
   6. Clique no ícone **"Reverter"** para cada relatório personalizado
   7. ( *Apenas os relatórios precisam ser revertidos* )
   8. Clique **em Check-in**
6. Preciso reverter tudo no componente?

   Nº Apenas **os elementos personalizados do relatório** devem ser revertidos para receber as melhorias no nível do relatório.
7. E se a personalização for absolutamente necessária?

   Melhores práticas:
   - **Copiar o relatório padrão**
   - Personalize o relatório copiado
   - Mantenha o relatório NX padrão inalterado

     Isso permite a personalização **sem perder futuras melhorias**.

## Principais conclusões

- Evite personalizar relatórios prontos para uso
- Os relatórios personalizados não recebem melhorias
- Reverta as personalizações antes das atualizações
- Entrar em contato com o CSM ou com o Suporte

Acesse o [NX Reports](/docs/SSI71A/cost-transparency/get-started/costing-guide-nav.html#base_file_name__nrs)

**Tópico principal:** [Configuração e personalização](../../studio/report-studio/config-custom.html)
