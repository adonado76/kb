---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Notas de lançamento de 2025"
breadcrumb:
  - "Planning"
  - "Notas sobre a liberação"
source_path: "it-planning/release-notes/whats-new-2025.html"
images:
  - "resources/images/it_planning_images/3.84-ibm.jpg"
  - "resources/images/it_planning_images/3.86a.jpg"
  - "resources/images/it_planning_images/3.86b.jpg"
  - "resources/images/it_planning_images/3.88-1.jpg"
  - "resources/images/it_planning_images/3.88-2.jpg"
  - "resources/images/it_planning_images/3.88-3.jpg"
  - "resources/images/it_planning_images/5.5a.png"
  - "resources/images/it_planning_images/5.5b.png"
  - "resources/images/it_planning_images/5.5c.png"
  - "resources/images/it_planning_images/pln-3.89.png"
  - "resources/images/it_planning_images/release-notes/3.84-1.jpg"
  - "resources/images/it_planning_images/release-notes/3.84.jpg"
  - "resources/images/it_planning_images/release-notes/3.91.png"
  - "resources/images/it_planning_images/release-notes/384-1.jpg"
  - "resources/images/it_planning_images/release-notes/5.13.2.png"
  - "resources/images/it_planning_images/release-notes/5.6a.png"
  - "resources/images/it_planning_images/release-notes/5.7a.png"
  - "resources/images/it_planning_images/release-notes/5.7b.png"
  - "resources/images/it_planning_images/release-notes/5.7c.png"
  - "resources/images/it_planning_images/release-notes/5.8a1.png"
  - "resources/images/it_planning_images/release-notes/5.8b.png"
  - "resources/images/it_planning_images/release-notes/5.8c.png"
  - "resources/images/it_planning_images/release-notes/5.8d.png"
  - "resources/images/it_planning_images/release-notes/ml-1.png"
  - "resources/images/it_planning_images/release-notes/ml-2.png"
  - "resources/images/it_planning_images/th-lp.png"
  - "resources/images/it_planning_images/th-menu.png"
  - "resources/images/it_planning_images/thimg.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Notas de lançamento de 2025

## Lançamento 5.14 Sandbox: 22 a 26 de dezembro de 2025 | Principal: 29 de dezembro de 2025 a 2 de janeiro de 2026

**Os planos de previsão agora suportam mais períodos reais**

Os planos de previsão agora oferecem maior flexibilidade ao trabalhar com dados reais. Anteriormente, os planos de previsão estavam limitados a um máximo de 12 períodos reais, independentemente da duração total do plano. Com esta atualização, os planos de previsão podem incluir todos os períodos reais disponíveis dentro do prazo do plano, permitindo um contexto histórico mais preciso e melhores previsões em horizontes de planejamento mais longos.

Para obter mais detalhes, consulte a documentação de ajuda sobre [Criação de planos](https://www.ibm.com/docs/en/SSKZJE8/it-planning/planning/create-plan.html "(Abre em uma nova guia ou janela)").

**API de importação de planos**

Introduzimos APIs de importação de planos que permitem a importação programática de dados de planos dentro do planejamento do Apptio. Essas APIs permitem a ingestão automatizada de dados de planos de ferramentas de terceiros, scripts de automação e outros sistemas, fornecendo uma maneira padronizada de importar planos.

**Ferramentas Importantes**

- **Importar dados de despesas do plano:** O ponto final POST importa dados do plano para todos os tipos de despesas suportados (como Mão de obra, Atividade de mão de obra, Contratos, Ativos e Outros) usando a opção Atualizar ou Substituir.
- **Arquivo de ajuda sobre erros de importação do plano de exportação:** O endpoint GET exporta um arquivo de ajuda no formato CSV que contém os erros de importação dos dados do plano, permitindo que os usuários analisem e resolvam as falhas de importação.

Para obter mais detalhes, consulte a documentação de ajuda [Plan APIs](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=apis-plan-api "(Abre em uma nova guia ou janela)").

**Correções de erros**

- Adicionada uma opção para atualizar automaticamente a página Status da integração de custos do Apptio quando houver atualizações disponíveis, eliminando a necessidade de atualizações manuais da página.
- Corrigimos um problema em que as variações na comparação de planos não eram exibidas, mesmo quando o usuário tinha permissões idênticas em ambos os planos.
- Atualização do texto de ajuda na caixa de diálogo de finalização do plano para comunicar claramente o comportamento esperado após a finalização do plano.

## 5.13.2 - Todos os ambientes: 24 de dezembro de 2025

Controle de acesso no nível do plano: melhorias na publicação em massa

Aprimoramos as permissões em nível de plano para facilitar aos administradores e proprietários do processo orçamentário o gerenciamento e a aplicação de permissões de usuário em todos os planos.

**Qual era o problema?**

Anteriormente, o gerenciamento de permissões no nível do plano não tinha uma maneira eficiente de publicar essas permissões em todos os planos ou sincronizá-las de volta para as Permissões globais de objetos de custo. Isso muitas vezes exigia atualizações manuais, aumentava o risco de inconsistências entre os planos e dificultava garantir que os usuários tivessem o acesso correto em escala.

**O que foi melhorado**

Os administradores e proprietários do processo orçamentário agora podem selecionar uma ou mais linhas de permissão em Configurações do plano > Permissões do usuário e publicá-las em massa em todos os planos ou nos Dados de referência. No menu de overflow, selecione:

- **Publicar permissões selecionadas para todos os planos**
- Aplica as permissões de usuário selecionadas em todos os planos
- As permissões existentes para usuários e departamentos correspondentes são atualizadas.
- São adicionadas permissões para novos usuários em departamentos correspondentes.
- **Publicar permissões selecionadas para dados de referência**
- Publica as permissões selecionadas nos dados de referência de Permissões de Objeto de Custo, mantendo as permissões globais sincronizadas com as alterações no nível do plano.

![](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/5.13.2.png)

## 5.13 - Sandbox: 8 a 12 de dezembro de 2025 | Principal: 15 a 19 de dezembro de 2025

**Horizonte de planejamento ampliado: agora até 10 anos**

Agora você pode criar planos com duração de até 10 anos, ampliando o máximo anterior de 6 anos. Esta melhoria proporciona maior flexibilidade para o planejamento financeiro estratégico de longo prazo, previsão de investimentos plurianuais e modelagem de cenários.

**O que está mudando?**

- Agora você pode selecionar um plano com duração **de** até 10 anos ao criar um novo plano.
- Todas as visualizações de despesas, gráficos resumidos e comparações entre planos são totalmente compatíveis com o prazo estendido de 10 anos.
- Opções adicionais de layout para controlar a granularidade por mês, trimestre e ano na tabela Despesas estarão disponíveis em uma versão futura.

  Para obter mais detalhes, consulte [Criando planos](../planning/create-plan.html).

**Editar linhas externas**

Agora, gerenciar itens externos ficou muito mais fácil com recursos completos de edição no produto — sem necessidade de exportar, modificar offline e reimportar.

**Novidades**

- **Edite ou exclua linhas externas diretamente na interface do usuário** em **Despesas → Nova visualização**, sem usar o fluxo de trabalho de exportação/importação.
- **Disponível para usuários com a permissão** “ ExternalLineEdit ” (Acessar e modificar o orçamento), incluída por padrão para administradores e proprietários do processo orçamentário.
- **Habilite o modo de edição** para uma única linha externa ou para todas as linhas externas de uma só vez, para atualizações mais rápidas e eficientes.
- **Exclua linhas externas individualmente ou em massa**, removendo a restrição anterior que exigia a exclusão de todas as linhas de uma só vez.
- **Importar itens externos permanece** disponível para adicionar novos itens externos.

  Para obter mais detalhes, consulte [Itens externos](../planning/ext-li.html "Os itens externos permitem que você gerencie dados do plano originários de sistemas externos e os traga para o planejamento d Apptio, para fins de visibilidade e análise, sem permitir que os usuários finais os editem.").

**Plan APIs**

Introduzimos novas **APIs de planos** que permitem o acesso programático a planos e dados de planos no Planejamento d Apptio. Essas APIs permitem integrações mais profundas com ferramentas de BI, scripts de automação e sistemas downstream, fornecendo uma maneira padronizada de recuperar planos e exportar despesas do plano.

**Ferramentas Importantes**

- **Recuperar todos os planos disponíveis para um usuário** - Use o novo endpoint GET /planning/api/v1/plans para obter uma lista dos planos aos quais o usuário autenticado tem acesso, incluindo IDs e nomes dos planos.
- **Exportar dados de despesas do plano via API** - O endpoint POST /planning/api/v1/plans/{planId }/expenses/export permite exportar dados do plano (resumo, mão de obra, contratos, ativos, etc.) no formato CSV para processamento externo.

  Para obter mais detalhes, consulte [Plan APIs](../planning/plan-api.html "As APIs REST do Planning do Apptio oferecem acesso programático e seguro a planos, dados de planejamento, metadados e artefatos relacionados no Planning d Apptio. Essas APIs foram projetadas para oferecer suporte à automação e às integrações de sistemas em casos de uso relacionados a planejamento, previsão, análise, governança e troca de dados.").

**Nova interface do usuário do perfil da empresa**

O design atualizado apresenta um visual mais limpo e intuitivo, que organiza as configurações por área de recurso, ajudando você a navegar mais facilmente por várias configurações e descobrir facilmente os recursos e funcionalidades que podem ser ativados ou desativados.

**Correções de erros**

- Corrigimos um problema em que o texto no menu suspenso Favoritos não ficava totalmente visível.
- Quando a opção Exibir atualizações está ativada, as colunas Última atualização e Modificado por são exibidas automaticamente e fixadas no lado esquerdo para melhor visibilidade.
- Corrigimos um problema que fazia com que a criação do plano falhasse quando os dados carregados excediam os limites de caracteres. Os dados que excedem os limites permitidos agora são automaticamente truncados e uma mensagem de aviso é exibida para que os usuários possam decidir se desejam continuar com o upload.

## 5.12 - 1º de dezembro de 2025

Controle de acesso no nível do plano

Apptio O planejamento agora oferece suporte ao controle de acesso por nível de plano, permitindo que os administradores gerenciem o acesso dos usuários por plano. Esta melhoria proporciona maior flexibilidade e segurança, garantindo que os direitos de visibilidade e edição sejam definidos em cada plano individualmente.

**O que está mudando**

1. **Nova página de permissões de usuário no nível do plano** - Cada plano agora inclui uma página **de permissões de usuário** em Plano > Configurações. Os administradores podem conceder acesso a departamentos específicos diretamente no nível do plano, substituindo a dependência anterior das permissões globais de objetos de custo. A nova página Permissões do usuário no nível do plano também inclui pesquisa e filtragem para facilitar o gerenciamento. As atualizações das permissões do usuário serão registradas no Histórico de alterações.
2. **As permissões globais de objetos de custo agora servem como modelo** - As permissões globais não controlam mais o acesso automaticamente. Em vez disso:
   1. **Novo plano (sem linha de base):** as permissões globais de objeto de custo são copiadas para o plano no momento da criação.
   2. **Novo plano (com linha de base):** as permissões de usuário do plano de linha de base são copiadas para o novo plano.

   Importante:
   - Agora, os usuários devem receber acesso **explicitamente no nível do plano**.
   - As permissões globais de objetos de custo, por si só*, não* fornecem acesso aos planos.
   - Em uma versão futura, adicionaremos uma opção para copiar permissões das Permissões Globais de Objetos de Custo ou do plano de linha de base ao criar um novo plano.

   Para aplicar em massa as permissões globais existentes a um plano, os administradores podem:
   1. Exportar a partir das permissões globais de objetos de custo (Configuração > Permissões de objetos de custo)
   2. Importe o arquivo ` CSV ` na página “Permissões do usuário” do plano (Plano > Configurações > Permissões do usuário)

   Uma opção de sincronização automatizada entre as permissões globais de objetos de custo e as permissões de usuário no nível do plano será disponibilizada em uma versão futura.

**Comportamento comparativo**

- Se um usuário não tiver acesso aos mesmos departamentos nos dois planos que estão sendo comparados, os dados dos departamentos restritos serão ocultados (ícone de olho exibido).
- Para os campos de dados confidenciais de Despesas > Mão de obra, as comparações só exibirão valores quando o usuário tiver acesso a dados confidenciais em *ambos* os planos.

**Comportamento de atualização**

- Os planos existentes manterão seu acesso atual.
- Durante a atualização, as permissões no nível do plano serão preenchidas automaticamente com base nas configurações atuais de Permissão de Objeto de Custo.

Para obter mais detalhes, consulte a documentação de ajuda sobre [permissões de objetos de custo](../planning/manage-cost-object.html).

Campos de hiperlink

Agora você pode criar colunas personalizadas do tipo Link no Apptio Planning, permitindo anexar URLs — como tickets do Jira, documentação ou recursos externos — diretamente aos seus itens de linha para navegação rápida.

- Adicione colunas do tipo Link na configuração do seu esquema.
- Clicar em um link o abre em uma nova guia do navegador.
- Os campos de link são totalmente compatíveis com a Nova Visualização e aparecem como somente leitura na Visualização Antiga.

Esse aprimoramento ajuda você a manter referências externas vinculadas aos seus dados de planejamento para facilitar o rastreamento e agilizar a navegação. Para obter mais detalhes, consulte a documentação da Ajuda sobre [os tipos de atributos suportados](../planning/manage_schema.html "Os esquemas definem a estrutura dos dados no planejamento d Apptio. Eles especificam as tabelas, os campos e as relações que determinam como as informações são armazenadas, vinculadas e exibidas nas guias de despesas, como Mão de obra, Contratos, Ativos e Finanças.").

Correções de erros

- Corrigimos um problema em que a data de início da extensão do contrato na nova visualização começava na data de término do contrato, em vez de no dia seguinte.

## 5.11 - 17 de novembro de 2025

Menu suspenso aprimorado para departamentos e projetos

Agora é mais fácil navegar pelos planos com os novos aprimoramentos do menu suspenso.

**Menu suspenso do departamento:**

- Selecione vários departamentos em todos os níveis hierárquicos
- Edite despesas em vários departamentos ao mesmo tempo (quando a seleção múltipla é usada)
- Edite as despesas de todos os departamentos pertencentes à sua empresa na visualização “Todos os departamentos”
- Indicadores visuais claros para departamentos somente para visualização
- Veja rapidamente as contagens dos departamentos em nível de grupo

**Menu suspenso do projeto:**

- Expanda ou recolha as hierarquias do projeto para uma navegação mais rápida
- Nova opção “Valor em branco” no menu suspenso Projeto para filtrar despesas não relacionadas ao projeto
- Indicadores visuais claros para departamentos somente para visualização
- Veja rapidamente as contagens de projetos em nível de grupo

Comparações de planos agora disponíveis para todos os anos (incluindo planos de 6 anos)

Removemos uma limitação anterior que impedia a adição de comparações de planos com duração de 6 anos. Agora você pode adicionar comparações entre todos os anos do seu plano — incluindo planos de 6 anos e planos plurianuais.

Capacidade expandida de dimensões personalizadas

Agora você pode definir até 40 dimensões personalizadas, um aumento em relação ao limite anterior de 13, o que lhe dá muito mais flexibilidade para modelar e segmentar seus dados.

Novas melhorias na visualização

**Ações do fluxo de trabalho movidas para a interface do usuário de nível superior**

Na Nova Visualização, as ações Enviar, Aprovar/Devolver e Abrir/Finalizar agora estão acessíveis diretamente na página Despesas, em vez de estarem localizadas no menu de reticências.

**Duplicar várias linhas na nova visualização**

Agora você pode selecionar e duplicar várias linhas de uma só vez na Nova Visualização.

- Use a seleção da caixa de seleção para escolher várias linhas.
- Clique no ícone Duplicar para copiá-los.
- As linhas duplicadas são inseridas diretamente abaixo das originais, com todos os valores copiados, exceto os campos gerados pelo sistema.

Esse aprimoramento torna mais rápido e fácil replicar várias linhas, economizando tempo e reduzindo o esforço manual.

Correções de erros

- As pastas do Plano no menu Plano agora aparecem por padrão em um estado recolhido.
- Corrigido um problema que impedia a eliminação de pastas de planos vazias.
- Corrigido um problema em que os menus suspensos na Nova Visualização exigiam um clique duplo para serem expandidos. O menu suspenso agora se expande com um único clique, em consonância com o comportamento da Visualização Antiga.
- Corrigimos um problema em que o campo Duração nos Contratos exibia um valor incorreto. Agora mostra corretamente a duração do contrato em meses, com duas casas decimais.

## 5.10 - 27 de outubro de 2025

Marcar planos como “Ativos”

Os administradores agora podem [marcar os planos como Ativos](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=plans-tag-as-active "(Abre em uma nova guia ou janela)") para identificar e priorizar facilmente os planos mais importantes.

- **Marcar como ativo:** marque os planos como ativos ao criar um novo plano ou na página Planos.
- **Navegação mais fácil:** os planos ativos são exibidos com uma etiqueta “Ativo” e aparecem sempre no topo do menu suspenso Plano.
- **Padrões do usuário:** Ao fazer login, os usuários são direcionados por padrão para um plano ativo (se houver vários, o mais recente será selecionado).
- **Planos arquivados:** os planos arquivados não podem ser marcados como ativos; se um plano ativo for arquivado, sua marcação será removida automaticamente.

Isso torna mais rápido e fácil encontrar e trabalhar com os planos mais importantes.

Visualização de itens atualizados agora suportada para visualizações de departamentos em grupo

O recurso Exibir itens atualizados foi aprimorado para oferecer suporte a cenários em que os usuários visualizam um grupo ou vários departamentos simultaneamente.

Anteriormente, a opção Exibir itens atualizados só funcionava ao visualizar um único departamento. Com esta versão, o recurso agora funciona quando departamentos agrupados são selecionados, permitindo que os usuários identifiquem alterações em um escopo mais amplo.

Nova visualização - Comparações adicionadas a contratos, ativos e atividades de mão de obra

Agora você pode adicionar comparações nas guias Contratos, Ativos e Atividade de mão de obra usando a Nova Visualização.

Anteriormente, as comparações estavam disponíveis apenas nas guias Resumo, Trabalho e Outros. Com essa melhoria, agora você pode analisar e comparar dados em todas as guias, obtendo uma visão mais completa de seus planos e permitindo insights mais profundos sobre tendências e variações de custos.

Nova visualização - Melhorias no comportamento da pesquisa do menu Filtro

Aprimoramos o comportamento do menu de filtros quando os usuários realizam uma pesquisa para tornar a filtragem mais intuitiva e alinhada com o comportamento comum das planilhas (por exemplo, Excel). Anteriormente, ao inserir uma consulta de pesquisa, todos os itens — incluindo aqueles que não correspondiam à pesquisa — permaneciam selecionados por padrão. Isso muitas vezes causava confusão e resultados de filtragem inesperados.

**O que mudou**

- **Filtragem de pesquisa mais inteligente:** quando um usuário digita uma consulta de pesquisa na caixa de filtro, a opção Selecionar tudo é automaticamente desmarcada e apenas os itens que correspondem à pesquisa permanecem selecionados. Para selecionar todos os resultados correspondentes, use a opção Selecionar todos os resultados da pesquisa.
- **Comportamento de seleção preciso:** quaisquer alterações feitas após a pesquisa — como marcar ou desmarcar itens — agora serão aplicadas apenas aos itens atualmente visíveis nos resultados. Se desejar, você pode selecionar **Adicionar seleção atual ao filtro** para adicionar os novos resultados da pesquisa ao filtro aplicado existente.
- **Tratamento de seleção vazia:** ao desmarcar todos os itens, agora será exibido corretamente um conjunto de resultados vazio.
- **Limpar pesquisa Redefinir:** Limpar a consulta de pesquisa restaura a lista completa com todos os itens selecionados por padrão.

Correções de erros

- Corrigimos um problema em que adicionar comparações de planos causava um erro para clientes que usavam calendários de 13 períodos.
- Corrigimos um problema em que as entradas de data na Nova Visualização eram sempre impostas no formato MM/DD/AAAA, ignorando a configuração regional do usuário. Os campos de data agora seguem corretamente o formato regional de data do usuário.
- Corrigido um problema em que a filtragem por Nome da Categoria da Conta não retornava resultados corretos quando várias Categorias de Conta compartilhavam o mesmo nome.
- Resolvido um problema em que o sistema não exibia uma mensagem de aviso quando os dados necessários estavam faltando em uma coluna oculta marcada como campo obrigatório.

## 5.9 - 6 de outubro de 2025

Nova visualização - Editar enquanto agrupado na tabela de despesas

Agora você pode adicionar, excluir e duplicar linhas na Nova Exibição, mesmo quando ela estiver no modo agrupado. Anteriormente, o agrupamento limitava as ações de edição, exigindo que você desagrupasse antes de fazer alterações. Com esta atualização, você pode editar diretamente no modo agrupado, tornando mais rápido e eficiente o gerenciamento de suas despesas sem interromper seu fluxo de trabalho.

Correções de erros

- Corrigimos um problema em que o filtro de item de linha exibia os valores Código e Nome quando eles eram idênticos. O filtro agora mostra apenas o Código na lista de opções se o Código e o Nome forem iguais.
- Corrigido um problema em que os atributos personalizados configurados como *Numéricos* não exibiam os totais na linha Total. A linha Total agora agrega e exibe corretamente os valores para dimensões do tipo numérico.
- Resolvido um problema em que a atualização dos dados de referência em um plano podia remover involuntariamente os fatores de variação e as explicações existentes.
- Corrigido um problema em que os atributos personalizados do tipo *Data* não respeitavam a configuração de localidade do usuário. Os valores de data agora são exibidos no formato correto com base na configuração regional definida.
- Corrigimos um problema em que a Nova Visualização permitia que os usuários inserissem mais de 255 caracteres no campo Código Externo. Embora o campo tenha sido salvo, posteriormente ele apresentaria um erro. O código externo agora está corretamente limitado a 255 caracteres.
- Corrigimos um problema em que a importação de dados para a guia Atividade de mão de obra às vezes marcava recursos como duplicatas quando eles eram atribuídos a vários centros de custo. A causa principal foi que o processo de importação avaliou o Recurso antes da Função de Trabalho do Projeto e do Centro de Custos do Recurso, ao contrário da sequência de entrada manual na interface do usuário. O processo de importação agora segue a mesma sequência da interface do usuário, garantindo consistência e evitando erros de duplicatas falsas quando um recurso está associado a vários centros de custo.
- Corrigido um problema em que clicar no espaço vazio entre as opções de filtro não selecionava corretamente o valor mais próximo do clique do mouse.
- Corrigimos um problema em que as comparações entre um plano orçamentário e um plano de previsão não carregavam e resultavam em um erro.
- Resolvido um problema em que a página Resumo não carregava quando a opção Agrupar por era aplicada.
- Corrigido um problema em que o botão Desbloquear não era exibido para usuários administradores no nível do departamento folha.
- Corrigido um problema em que expandir um grupo com um valor vazio/nulo no Planejamento ocultava seus itens de linha. Os itens de linha agora são exibidos corretamente quando agrupados por uma coluna que contém valores em branco.
- Resolvido um problema na Análise de Variação em que a expansão dos agrupamentos de Objetos de Custo não carregava como esperado.

## 5.8 - 22 de setembro de 2025

**Pastas do plano**

Mantenha seu espaço de trabalho organizado à medida que o número de planos aumenta. Com as Pastas de Planos, você pode agrupar planos relacionados, simplificar a navegação e gerenciá-los com mais eficiência.

![](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/5.8a1.png)

**Principais recursos:**

- Os administradores podem criar uma estrutura de pastas simples, de um único nível, para agrupar planos
- Os planos e pastas são automaticamente ordenados em ordem alfabética para facilitar a navegação
- Arquive, desarquive ou exclua pastas inteiras (com todos os seus planos) em uma única ação
- A estrutura da pasta agora é refletida no menu suspenso Plano em todo o aplicativo

**Tornar o campo Moeda somente leitura**

A coluna Moeda na tabela Despesas agora pode ser configurada como Acesso Restrito a partir do Esquema. Quando ativado, apenas usuários com a **EditRestrictedDimensions** permissão podem modificar os valores monetários dos itens de linha.

![](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/5.8b.png)

**Atualizar dados reais – Seleção de vários meses**

A atualização dos dados reais agora é mais flexível. No modal Atualizar dados reais, você pode:

- Use o menu suspenso de seleção múltipla para escolher vários meses de uma só vez
- Selecione rapidamente todos os meses disponíveis com a nova opção “Selecionar tudo”

![](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/5.8c.png)

**Adicionar linha em nova visualização**

Atualizamos a forma como você adiciona linhas na tabela Nova Visualização > Despesas para melhor se alinhar com a visualização antiga.

Os usuários agora podem:

- Adicione uma nova linha usando a linha vazia na parte inferior da tabela
- Use as ações do menu do botão direito do mouse para inserir uma linha acima ou abaixo

Veja os campos obrigatórios destacados diretamente na tabela, incluindo campos ocultos que devem ser preenchidos

![](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/5.8d.png)

**Correções de erros**

- A opção Exportar tudo agora inclui corretamente as colunas Mês, mesmo quando elas estão ocultas na tabela.
- As colunas de porcentagem nas tabelas de despesas agrupadas agora exibem os valores agregados corretos em vez de 0% ou NULL. Se todas as linhas compartilharem a mesma porcentagem, o grupo mostrará essa porcentagem. Se as linhas contiverem porcentagens diferentes, o grupo mostrará a contagem exclusiva de valores.
- Os nomes dos projetos agora são importados corretamente ao usar a configuração de idioma japonês.
- A Gestão de Despesas agora usa como padrão o mês atual do calendário no ano fiscal ativo ao navegar. Anteriormente, os locatários com calendários fiscais diferentes de janeiro a dezembro não estavam sendo processados corretamente.
- Apptio BI Agora respeita corretamente as permissões do objeto de custo do Planning, garantindo que os usuários possam visualizar dados financeiros confidenciais (por exemplo, remuneração base) quando o acesso é provisionado no Planning.
- O botão Enviar todas as alterações e finalizar agora funciona conforme o esperado. Quando selecionado, todos os objetos de custo pendentes são automaticamente aprovados e o plano é finalizado.
- Corrigimos um problema em que os filtros de coluna na página Despesas não consideravam corretamente caracteres especiais ou pontuação nos valores.

## 5.7 - 8 de setembro de 2025

**Identificadores baseados em código para fornecedor, localização, função e dimensões personalizadas**

Fornecedor, localização, função e dimensões personalizadas agora usarão o código em vez do nome como identificador exclusivo.

Essa alteração permite que os nomes sejam atualizados sem afetar o identificador exclusivo, reduzindo o risco de incompatibilidades de dados quando os nomes são alterados.

**Impacto:**

- **Importação de dados do plano:** você deve importar o código em vez do nome para fornecedor, localização, função e dimensões personalizadas. Isso também se aplica a conjuntos de dados que fazem referência a essas dimensões, como Taxas de mão de obra, Regras de alocação de mão de obra e Itens de despesas.
  - As importações do plano aceitarão campos de fornecedor, localização, função e dimensão personalizada usando [Nome da dimensão] (por exemplo, fornecedor) ou [Nome da dimensão] Código (por exemplo, código do fornecedor). Como o Código será igual ao Nome, os arquivos de importação de planos existentes continuarão a funcionar sem alterações.
- **Exportação de dados do plano:** Ao exportar dados, os campos Código e Nome podem ser exportados como colunas separadas ao usar *Exportar tudo* ou *Exportar layout*. Por exemplo, a dimensão Fornecedor será exportada como **Fornecedor** (para Código) e **Nome do Fornecedor** (para Nome).
  - Observação: *a exportação para reimportação* exportará o código para “Fornecedor”, “Localização” e “Função”
- **Apptio Integração de custos:** se você estiver integrando com o Apptio Costing por meio da Cost Transparency Integration (CTI) ou do Automated Data Manager (ADM), revise e atualize sua configuração em Data Studio para garantir que o campo **Código** esteja mapeado corretamente. Os planos publicados em Apptio Costing agora exportarão **o código** do fornecedor, localização, função e dimensões personalizadas. Se suas transformações utilizarem esses campos, verifique se seus mapeamentos estão corretos.
- **Apptio Conjuntos de dados de custos:** os conjuntos de dados prontos para uso que oferecem suporte à integração com o Apptio Planning foram atualizados para oferecer suporte a identificadores baseados em código. Esta atualização está disponível em Apptio Costing Release r12.11.16.

Observação: as dimensões existentes serão migradas automaticamente copiando o valor atual do Nome para a nova coluna Código para Fornecedor, Localização, Função e dimensões personalizadas, garantindo que as tabelas de integração existentes continuem funcionando. Se já existir um atributo personalizado chamado “Código”, ele será renomeado para “ Code2 ”.

![identificador da base de código](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/5.7a.png)

Nos menus suspensos da tabela Despesas, os valores das dimensões agora serão exibidos como **Código – Nome** (por exemplo, “ LOC001 – Nova York”). Se o Código e o Nome forem iguais, o menu suspenso mostrará apenas o Código para evitar valores duplicados.

![formato do nome de código](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/5.7b.png)

**Agrupamento aprimorado na nova visualização**

As colunas agrupadas aparecem em uma única coluna com hierarquia clara, totais e grupos classificáveis. Você também pode arrastar colunas para o painel Agrupar por para aplicar ou reorganizar rapidamente o agrupamento.

![agrupamento aprimorado](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/5.7c.png)

**Novos guias de treinamento no aplicativo**

O Centro de Treinamento no Aplicativo ficou ainda melhor com dois novos guias passo a passo:

- **Planos de edição** – Aprenda a atualizar e gerenciar dados de despesas em seus planos.
- **Comparando planos e analisando variações** – Descubra como comparar planos e interpretar as principais diferenças para tomar melhores decisões.

Acesse os guias diretamente no produto, sem necessidade de logins ou abas adicionais.

**Correções de erros**

- Corrigimos um problema em que os gráficos de cascata de gastos exibiam todas as barras em azul, em vez de usar as cores corretas de variação positiva/negativa.
- Atualização da lógica da interface do usuário para exibir apenas o KPI de cobranças nas páginas Resumo, Painel e Despesas quando a atividade de mão de obra estiver habilitada no perfil da empresa.
- Resolvido um problema que impedia a importação automática de valores reais para o Gerenciamento de Gastos através do Gerenciador de Dados Automatizado (ADM) quando o período dos valores reais estava encerrado no Gerenciamento de Gastos. Isso garante que os períodos fechados sejam respeitados, mantendo a integridade dos dados durante as importações.

## 5.6 - 4 de agosto – 17 de agosto de 2025

**Atualize para um PostgreSQL**

Estamos atualizando todos os ambientes principais para o PostgreSQL como parte do lançamento do 5.6. Esta atualização oferece melhor desempenho, escalabilidade e suporte de plataforma a longo prazo. Seu ambiente será atualizado no dia designado para a atualização durante a Semana 1 (4 a 10 de agosto) ou Semana 2 (11 a 17 de agosto) do período de lançamento. As atualizações são processadas em ordem alfabética, com os ambientes restantes concluídos na Semana 2.

Nenhuma ação é necessária por parte da sua equipe. Recomendamos validar seus fluxos de trabalho principais após a atualização para garantir que tudo continue funcionando conforme o esperado.

**O que está mudando:**

- **Migração do backend:** Apptio O planejamento está passando do banco de dados atual para PostgreSQL.
- **Desempenho aprimorado:** os usuários podem esperar tempos de carregamento mais rápidos e interações mais responsivas, especialmente em planos grandes.
- **Melhor escalabilidade:** a nova infraestrutura suportará volumes de dados maiores e necessidades crescentes de planejamento.

Se você tiver alguma dúvida ou preocupação, entre em contato com seu gerente de sucesso do cliente.

Observação: os clientes federais serão atualizados entre agosto e dezembro.

**Visualização atualizada dos itens da linha**

A visualização atualizada dos itens de linha melhora a visibilidade das alterações recentes entre as versões, facilitando aos usuários a revisão, o acompanhamento e o gerenciamento eficiente das atualizações ao longo do processo de planejamento. Uma nova opção na página Despesas permite que os usuários alternem entre a visualização de todos os itens ou filtrados para mostrar apenas os itens atualizados desde o último envio ou instantâneo. A coluna Ação indica o tipo de alteração feita: Nova, Atualizada ou Excluída.

Nota:

- Os itens importados serão marcados como novos, com carimbo de data/hora e nome de usuário da pessoa que importou os dados.
- Os dados financeiros gerados refletirão os últimos valores atualizados do item de origem (por exemplo, mão de obra, atividade de mão de obra, contratos ou ativos) que provocaram a alteração.
- Itens excluídos ou atualizados devido à Atualização de dados de referência e Atualização de valores reais não serão incluídos.
- Os planos criados a partir de uma linha de base herdarão os valores da última atualização do plano original.

Esse recurso torna mais rápido e fácil identificar o que mudou, quem fez a alteração e quando — ajudando as equipes a colaborar e validar as atualizações do plano com confiança.

![atualizando itens de linha](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/5.6a.png)

**Fluxos de trabalho de aprovação multinível**

O novo Fluxo de Trabalho de Aprovação em Vários Níveis oferece uma abordagem flexível e assíncrona para gerenciar aprovações, projetada para dar suporte a processos de planejamento e cadeias de revisão mais complexos. Esse aprimoramento permite que os departamentos definam caminhos de aprovação exclusivos e introduz novos níveis de permissão para melhorar o controle e a colaboração durante o planejamento.

**Principais recursos:**

- **Roteamento multinível configurável**
  - Configure cadeias de aprovação personalizadas para cada departamento.
  - Defina até 10 níveis de aprovação sequenciais.
  - Cada nível pode incluir usuários específicos responsáveis pela revisão e aprovação.
- **Aprovações departamentais assíncronas**
  - Os departamentos atuam de forma independente por meio de suas cadeias de aprovação definidas.
  - Permite o planejamento e as aprovações paralelas entre equipes.
- **Novo nível de permissão “Editar”**
  - Permite que os usuários façam alterações nos planos sem poder enviá-los para aprovação.
  - Útil para colaboradores ou contribuidores que não devem acionar alterações no fluxo de trabalho de aprovação.
  - A permissão “Editar” está disponível para fluxos de trabalho de aprovação multinível e aprovação hierárquica.

![fluxo de trabalho multinível](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/ml-1.png)

![fluxo de trabalho multinível](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/ml-2.png)

**Comparação: fluxos de trabalho de aprovação hierárquicos vs. multiníveis**

|  |  |  |
| --- | --- | --- |
|  | **Aprovações hierárquicas** | **Aprovações em vários níveis** |
| **Caminho de aprovação** | Segue a hierarquia do departamento, progredindo nível por nível através dos departamentos superiores. | Definido de forma personalizada por departamento, com aprovações sequenciais fluindo em ordem ( L1 → L2 → L3, etc.). |
| **Níveis de aprovação** | Vários proprietários podem ser atribuídos por departamento ou grupo de departamentos, sendo necessária apenas uma aprovação para avançar. | Suporta até 10 níveis de aprovação por departamento. Vários aprovadores podem ser designados por nível, sendo necessário apenas um para aprovar. |
| **Envio em grupo** | Suporta envios do Departamento do Grupo, onde o envio de um Grupo automaticamente envia e aprova todos os Departamentos filhos juntos. | Não aplicável. |
| **Fluxo de planejamento** | Requer planejamento e envio sincronizados (os departamentos filhos devem enviar antes que o grupo pai possa avançar). | Suporta planejamento e revisão assíncronos. Os departamentos podem enviar e avançar de forma independente através da cadeia de aprovação. |
| **Comportamento de rejeição** | Rejeitar envia o plano de volta um nível na hierarquia. O proprietário em cada nível deve continuar recusando-se a repassar isso para o departamento subordinado. | Rejeitar um departamento o envia de volta ao início do fluxo de trabalho, exigindo que o departamento o reenvie ao Nível 1 |
| **Ignorar nós** | Apoiado por deixar o Proprietário sem atribuição em um nível, transferindo as aprovações para o Proprietário do nível imediatamente superior. | Não aplicável. |
| **Permissões de usuário** | Permissão para editar nível: • **Proprietário:** pode editar, enviar e aprovar ou devolver planos. Recebe notificações por e-mail quando os planos são aprovados ou devolvidos.  • **Editar e enviar** – É possível editar e enviar planos.  • **Editar** – Pode editar planos, mas não pode enviá-los.  • **Somente visualização** – Pode visualizar planos, mas não pode editar ou enviar. | Editar permissões de nível:  • **Proprietário:** pode editar e enviar planos. Recebe notificações por e-mail quando os planos são aprovados ou devolvidos.  • **Editar e enviar** – É possível editar e enviar planos.  • **Editar** – Pode editar planos, mas não pode enviá-los.  • **Somente visualização** – Pode visualizar planos, mas não pode editar ou enviar.  Permissão de nível de aprovação:  • **Nível de aprovação:** defina um nível de aprovação (1–10) para definir a posição do usuário no fluxo de trabalho de aprovação. |

Consulte **[Visão geral dos fluxos de trabalho de aprovação](../planning/about-approval-workflows.html "Os fluxos de trabalho de aprovação no Apptio Planning controlam como os planos enviados passam pelas etapas de revisão e aprovação, garantindo que os planos sejam encaminhados às partes interessadas apropriadas para aprovação. Esses fluxos de trabalho oferecem flexibilidade para se alinhar à estrutura e ao processo de governança da sua organização.")** para obter mais detalhes e instruções de configuração.

**Correções de erros**

- Corrigido um problema na Nova Visualização em que inserir texto no campo Descrição na guia Trabalho resultava em um erro e o valor não era salvo.
- Modo de tela cheia aprimorado na página Novas despesas para aproveitar melhor a altura vertical total do navegador.
- Corrigido um problema em que a publicação automática do ADM ( Data Management ) para o TBM Studio falhava devido ao desalinhamento do período fiscal.
- Resolvido um problema em que os usuários não conseguiam adicionar valores a campos marcados como obrigatórios para entrada de dados.

## 5.5 - 28 de julho de 2025

**Configuração da precisão decimal**

Os administradores agora podem configurar o número de casas decimais exibidas no Planejamento d Apptio, com suporte para até 8 casas decimais. Essa configuração controla como os valores numéricos aparecem na interface do usuário para todos os usuários.

![imagem para decimal](../../../../../03-media/apptio-planning/resources/images/it_planning_images/5.5a.png)

![imagem em resumo](../../../../../03-media/apptio-planning/resources/images/it_planning_images/5.5b.png)

Além disso, os usuários agora podem especificar a precisão decimal no momento da exportação para maior flexibilidade. Todos os cálculos e armazenamento de dados continuam a usar precisão total, independentemente das configurações de exibição.

![formatos de exportação](../../../../../03-media/apptio-planning/resources/images/it_planning_images/5.5c.png)

**Correções de erros**

- Resolvido um problema em que o recurso Exportar tudo ignorava as opções de exportação selecionadas pelo usuário.

## 5.4 - 14 de julho de 2025

**Versão de manutenção**

Esta versão contém atualizações de manutenção do sistema e correções de bugs.

**Correções de erros**

- Para melhorar a clareza e a usabilidade, atualizamos o rótulo do menu “Agrupamentos” em Nova Visualização para “Grupos por Data” Essa alteração se baseia no feedback dos usuários, que destacaram a confusão em torno da localização dos agrupamentos por mês, trimestre e ano. A etiqueta atualizada reflete melhor o objetivo do menu, facilitando a localização e o trabalho com dados baseados em tempo, incluindo os agrupamentos Total do plano, Acumulado no ano e Previsão restante.
- Resolvido um problema em que a dimensão do item de linha real para o código do projeto fazia referência incorretamente ao objeto de custo em vez do ID/código do projeto.
- Resolvido um problema no relatório Planning Apptio BI, em que a adição de filtros na hierarquia de contas resultava em um erro 500.
- Resolvido um problema em que valores numéricos com mais de 15 dígitos eram exportados para o Excel como texto devido à formatação automática do Excel, levando a totais incorretos.
- Corrigido um problema em que o filtro de intervalo de datas não limitava o agrupamento por meses/trimestres ao ano selecionado, exibindo dados de todos os anos.

## 5.3 - 23 de junho de 2025

Observação: esta versão se aplica apenas aos clientes do Postgres Beta.

**Comportamento aprimorado do menu suspenso do departamento**

O menu suspenso Departamento agora exibe dinamicamente apenas os departamentos aos quais o usuário tem acesso, com base em suas permissões de objeto de custo. Esta melhoria simplifica a navegação e proporciona uma visibilidade mais clara dos resumos de custos para todos os departamentos pertencentes ao usuário.

- Os usuários administradores continuarão a ver toda a hierarquia do departamento.
- Os usuários não administradores verão apenas os departamentos para os quais têm permissões de visualização ou edição.
- Selecionar “Todos os departamentos” ou um nível de departamento agrupado exibirá dados de despesas somente para leitura em todos os departamentos aos quais o usuário tem acesso.

**Correções de erros**

- Resolvido um problema em que um plano de previsão não incluía valores monetários da guia “Outros” do orçamento de referência.
- Corrigimos um problema em que os usuários não conseguiam duplicar linhas com códigos externos na Nova Visualização.
- Corrigimos um problema em que o filtro “Projeto” apresentava um erro “Falha ao carregar filtros” em determinados planos.
- Resolvido um problema em que o campo Centro de Custos não era preenchido automaticamente na guia Atividade de Trabalho ao selecionar um Projeto sem um centro de custos padrão. O campo deve agora assumir como padrão o centro de custos padrão do Departamento nesses casos.
- Corrigido um problema em que um erro era exibido incorretamente ao adicionar um item de linha vinculado a um projeto com um centro de custo padrão enviado. Nenhum erro deve ocorrer neste cenário.

## 5.2 - 9 de junho de 2025

**PostgresSQL Migração de banco de dados**

Estamos atualizando a infraestrutura de Apptio Planning banco de dados do site PostgreSQL, para uma plataforma moderna e escalável, projetada para oferecer desempenho mais rápido, maior confiabilidade e uma experiência de usuário mais robusta.

**O que está mudando:**

- **Migração do backend:** Apptio Planning está mudando do banco de dados atual para PostgreSQL.
- **Desempenho aprimorado:** os usuários podem esperar tempos de carregamento mais rápidos e interações mais responsivas, especialmente em planos grandes.
- **Melhor escalabilidade:** a nova infraestrutura suportará volumes de dados maiores e necessidades crescentes de planejamento.
- **Fundação para IA e automação:** esta atualização permite melhorias futuras, como previsões baseadas em IA e fluxos de trabalho inteligentes.

**Correções de erros**

- Corrigimos um problema em que o gráfico Tendência de gastos na página Painel exibia os valores reais do plano completo, em vez de filtrar apenas os projetos e departamentos aos quais o usuário tem acesso.
- Resolvido um problema que fazia com que os valores do filtro Descrição se sobrepusessem visualmente, dificultando a leitura ou seleção ao aplicar filtros.
- Resolvido um problema em que usuários sem permissão para visualizar dados confidenciais encontravam um erro na página Nova despesa quando a remuneração base era marcada como confidencial. Com essa correção, a remuneração base ficará devidamente oculta para usuários não autorizados.

## 3.93 - 3 de junho de 2025

Versão de manutenção

Esta versão contém atualizações de manutenção do sistema e correções de bugs.

**Correções de erros**

- Resolvido um problema em que a dimensão do projeto renomeada no Planejamento Integrado de Investimentos revertia para o nome padrão quando publicada. Apptio Costing

## 3.92 - 12 de maio de 2025

Atenção: Esta será a versão final antes do Apptio Planning 5.0.

Para obter detalhes sobre as mudanças no ciclo de lançamento e na infraestrutura da plataforma, acesse: [Próximas mudanças no Apptio Planning ciclo de lançamento e na infraestrutura da plataforma](https://community.ibm.com/community/user/discussion/upcoming-changes-to-apptio-plannings-release-cycle-and-platform-infrastructure "(Abre em uma nova guia ou janela)")

**Centro de treinamento no aplicativo**

O centro de treinamento no aplicativo é uma experiência de aprendizagem integrada diretamente no Apptio Planning. Ele fornece orientações passo a passo e personalizadas na interface do produto, sem necessidade de logins separados ou portais de ajuda externos. Projetado para simplificar a integração e apoiar o aprendizado contínuo, o guia ajuda os usuários a acessar o treinamento certo no momento em que precisam, promovendo uma adoção mais rápida e maior produtividade.

Os guias atuais incluem:

- Apptio Planning Visão geral
- Acessando planos
- Operações básicas da tabela de despesas
- Envio de planos
- Verificando o status do plano
- Comparando planos
- Relatórios e análises

O centro de treinamento no aplicativo está disponível para **todos Apptio Planning os usuários**, e continuaremos a expandi-lo com novos tópicos no futuro. Para saber mais, veja este [vídeo](https://youtu.be/5B-FxNzE_mo "(Abre em uma nova guia ou janela)").

Selecione o ícone do Centro de Treinamento para acessar os guias de treinamento:

![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/thimg.png)

![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/th-menu.png)

**Agora em versão beta: Assistente Apptio para IBM Apptio Planning**

Temos o prazer de apresentar o Assistente Apptio — uma ferramenta de suporte com tecnologia de inteligência artificial que ajuda os usuários a obter respostas para perguntas sobre IBMApptio Planning e instruções relacionadas. Este assistente foi projetado para melhorar a experiência do usuário, fornecendo ajuda sob demanda, especialmente para novos usuários que estão navegando na plataforma.

O assistente pode ser ativado para usuários específicos e é ideal para pessoas que são novas no Apptio Planning.

**O que esperar como testador beta**

Os participantes devem se programar para os seguintes compromissos de tempo:

- Uma chamada inicial de 30 minutos para revisar o programa de testes
- ~1 hora para interagir com o assistente e fazer perguntas relacionadas ao produto ou ao TBM
- Uma sessão de feedback de 1 hora para compartilhar sua experiência
- E-mails ocasionais de acompanhamento da equipe de IA da Apptio

**Interessado em participar?**

Inscreva-se aqui: [Formulário de inscrição para a versão beta](https://forms.monday.com/forms/a4fa2efe897704ff5cbe58649f5d6c1b?r=use1 "(Abre em uma nova guia ou janela)")

![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/th-lp.png)

**Correções de erros**

- Corrigimos um problema em que os campos obrigatórios na guia Trabalho não eram destacados automaticamente.

## 3.91 - 28 de abril de 2025

Funcionalidade de exportação aprimorada

Esta versão aprimora o recurso Exportar com a introdução de uma opção abrangente “Exportar tudo”, permitindo que os usuários exportem todas as dimensões e atributos no esquema do plano.

Principais melhorias:

- Nova opção “Exportar tudo ”: exporta um conjunto de dados completo, incluindo todas as dimensões e atributos no esquema do plano.
- Opções de exportação renomeadas:
  - “Exportar apenas layout” agora é “Exportar layout” para maior clareza.
  - A opção existente “Exportar tudo” agora é “Exportar para reimportar”, indicando que inclui apenas os campos editáveis necessários para a reimportação.
- Dicas de ferramentas para maior clareza : cada opção de exportação inclui dicas detalhadas para explicar sua finalidade.

Comportamento de exportação:

- Exportar tudo: exporta o esquema completo do plano, incluindo todas as dimensões e atributos.
- Exportar layout : exporta o último layout salvo, incluindo todas as colunas e filtros visíveis.
- Exportar para reimportar : exporta todos os campos editáveis em um formato adequado para reimportar dados.

Observação: a publicação de dados do plano por meio do CTI ou ADM continuará usando o formato “Exportar para reimportar” (anteriormente conhecido como formato “Exportar tudo”). Em uma versão futura, a publicação do plano será atualizada para incluir o esquema completo do plano.

Novas colunas “Última atualização” e “Modificado por” para itens de linha do plano

Adicionamos uma coluna Última atualização e Modificado por a todas as tabelas de itens do plano, incluindo Mão de obra, Atividade de mão de obra, Contratos, Ativos e Finanças. As colunas Última atualização e Modificado por mostram a data, a hora e o nome de usuário do último usuário que editou cada item da linha. O carimbo de data/hora se ajusta automaticamente às suas configurações regionais para uma experiência personalizada.

Observação: ao criar um plano a partir de uma linha de base, as informações sobre a data da última atualização e o usuário que fez a modificação serão transferidas para o novo plano.

![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/3.91.png)

Correções de erros

- Resolvido um problema em que a atualização dos valores reais em um plano aberto ou a criação de um plano a partir de uma linha de base gerava incorretamente itens de linha de previsão com custo financeiro zero, levando a linhas desnecessárias. Agora, apenas itens com valores financeiros são incluídos.
- Melhoria no desempenho da importação de dados do plano de atividades de trabalho quando o calendário de trabalho é utilizado.

## 3.90 - 14 de abril de 2025

Versão de manutenção

Esta versão contém atualizações de manutenção do sistema e correções de bugs.

Correções de erros

- Corrigido um erro em que o filtro Projeto não funcionava para usuários administradores.
- Resolvido um problema de desempenho que afetava o carregamento da página Despesas para usuários com permissões de nível Todos os projetos no Integrated Investment Planning.
- Resolvido um bug em que abrir um mês no Gerenciamento de Gastos inadvertidamente abria vários meses e os revertia para o status “NOVO”.
- Resolvido um problema em que a Análise de Variação exibia variações incorretas do plano após alterações feitas na hierarquia do Departamento.

## 3.89 - 31 de março de 2025

Comentário sobre a variação das exportações

Esta versão adiciona a capacidade de exportar comentários sobre variações como um arquivo.csv diretamente do relatório Análise de Variações. Com essa melhoria, os clientes podem acessar com eficiência todos os fatores de variação e explicações em um formato estruturado. Os dados exportados podem ser integrados perfeitamente ao TBM Studio ou outras ferramentas de BI para análises e relatórios mais aprofundados.

![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/pln-3.89.png)

Correções de erros

- Resolvido um problema na visualização Despesas, em que o ícone de reverter não ficava visível quando Trabalho > Remuneração base era substituído.
- Corrigido um problema em que os dados reais do projeto não eram atualizados após a modificação dos detalhes do projeto na lista de projetos.
- Corrigido um problema de desempenho que afetava o carregamento da página Despesas para usuários com permissões de nível Todos os projetos no Integrated Investment Planning.
- Resolvido um problema na Análise de Variação em que eram exibidos dados financeiros incorretos para departamentos inexistentes numa comparação de previsões.
- Corrigido um problema em que ocorria um erro na Análise de Variação quando um usuário fornecia um fator de variação sem adicionar um comentário.
- Resolvido um problema em que a abertura de um mês no Gerenciamento de Gastos inadvertidamente abria vários meses e os revertia para o status “NOVO”.

## 3.88 - 17 de março de 2025

Dimensões de acesso restrito

Esta versão introduz a capacidade dos administradores designarem dimensões específicas como “Acesso restrito”, garantindo que apenas usuários autorizados possam modificá-las. Esta melhoria ajuda a manter a integridade dos dados e evita alterações não intencionais.

Principais melhorias

- Nova configuração de “Acesso restrito ”: os administradores podem marcar dimensões específicas como Acesso restrito na caixa de diálogo Editar atributo do sistema dentro do Esquema.
- Permissões granulares : Somente usuários com a nova permissão EditRestrictedDimensions podem editar essas dimensões.

  ![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.88-1.jpg)
- Exibição somente leitura : os usuários sem essa permissão verão as dimensões de acesso restrito como somente leitura na tabela Despesas.
- Nova dica de ferramenta : uma dica de ferramenta aparecerá ao passar o mouse sobre os campos de acesso restrito, indicando que a dimensão é somente leitura.

  ![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.88-2.jpg)
- Comportamento de importação :
  - Os usuários com permissão de " EditRestrictedDimensions " podem importar e modificar dimensões de acesso restrito.
  - Os usuários sem permissão de " EditRestrictedDimensions " (Acessar e alterar) terão as dimensões de acesso restrito automaticamente ignoradas durante a importação, preservando os valores existentes.
  - Uma mensagem de aviso notificará os usuários quando as dimensões de acesso restrito forem ignoradas durante a importação.
- Histórico de alterações : as alterações nas dimensões de acesso restrito são rastreadas no Histórico de alterações.
- Permissões : uma nova permissão EditRestrictedDimensions foi introduzida e atribuída às funções de administrador e proprietário do processo orçamentário no Frontdoor.

Configuração aprimorada do limite de variação com operador AND/OR

Esta atualização introduz um tipo de operação “AND/OR” nas configurações de variação, proporcionando aos usuários maior flexibilidade ao definir limites de variação. Os usuários agora podem escolher entre:

- E – A variação deve atender aos limites de valor absoluto e porcentagem.
- OU – A variação deve atender aos limites de valor absoluto ou porcentagem.

  ![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.88-3.jpg)

Links da comunidade atualizados

Os links de recursos da comunidade foram atualizados para seus novos locais na plataforma da comunidade IBM.

Correções de erros

- Os valores periódicos FTE exportados agora são arredondados corretamente e limitados a duas casas decimais.

## 3.87 - 3 de março de 2025

Apenas versão de manutenção

Esta versão contém atualizações de manutenção do sistema e correções de bugs.

Correções de erros

- Otimizamos a lógica de cálculo da Delegação para evitar a degradação do desempenho ao adicionar itens de linha.
- Resolvido um problema no Apptio BI em que um usuário não conseguia acessar a fonte de dados “Planejamento” em Gerenciamento de fontes de dados.
- Removida a dimensão duplicada do projeto na integração de custos d Apptio quando Integrated Investment Planning está ativada. (Requer o padrão Apptio ).
- Resolvido um problema em que as dimensões de data eram exibidas como “ NaN ” quando os itens de linha eram agrupados na Nova Visualização.
- Corrigido um problema em que as configurações de agrupamento na Nova Visualização não persistiam como esperado.

## 3.86 - 17 de fevereiro de 2025

Análise de variância aprimorada

Esta versão amplia os recursos de análise de variação, permitindo que os usuários administradores comparem previsões com planos (orçamentos ou previsões) nos estados Aberto e Novo para qualquer período selecionado, como variação anual.

Principais melhorias

- Os usuários agora podem configurar análises de variação entre Previsão e Plano (Orçamento ou Previsão) para períodos de tempo flexíveis, permitindo um acompanhamento e planejamento financeiro mais abrangente.
- Todos os planos ativos nos estados Aberto e Novo estão agora disponíveis no menu suspenso Comparar com o plano ao configurar a análise de variação. No entanto, observe que os proprietários do centro de custos não terão acesso à análise de variação ao comparar com um plano no novo estado.
- A coluna Categoria da conta foi adicionada à tabela Análise de variação, permitindo uma melhor categorização e acompanhamento dos dados financeiros.

  ![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.86a.jpg)
- Anteriormente, a análise de variação limitava-se à comparação entre previsões e resultados reais, mas esta melhoria proporciona maior flexibilidade para analisar o desempenho financeiro em diferentes cenários.

  Observação: ao comparar com os Períodos de Previsão, os usuários administradores podem selecionar “Atualizar Análise de Variação ” para atualizar os cálculos de variação, garantindo que os valores de variação reflitam as últimas atualizações da previsão. Esta opção está disponível em “...” menu na página Análise de Variação.

  ![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.86b.jpg)

Extensões de contrato variáveis para contratos externos

Expandimos o recurso Ajustes de extensão de contrato variável para oferecer suporte a contratos externos, que são usados para importar itens de linha de contrato como somente leitura.

- Configure ajustes de prorrogação de contrato composto para contratos externos.
- Defina porcentagens de ajuste exclusivas para cada extensão de contrato.

Ao incorporar esses ajustes, você pode obter uma modelagem financeira mais precisa, levando em consideração fatores como inflação e variações nas taxas ao longo de ciclos de planejamento plurianuais. Para saber mais, veja [aqui](../planning/vrbl-cntc-ext-adj.html "Apptio O planejamento permite estender contratos além da data de término original, com recursos diferentes dependendo se você está usando a Visualização Antiga ou a Nova Visualização.").

## 3.85 - 3 de fevereiro de 2025

Total restante previsto nos planos de previsão

Esta versão apresenta um novo recurso na Nova Visualização que permite aos usuários ativar ou desativar a coluna Previsão Remanescente nos Planos de Previsão. A Previsão restante fornece uma soma de todos os períodos de previsão no primeiro ano do plano, oferecendo uma visão rápida e consolidada dos valores previstos restantes.

Correções de erros

- Corrigimos um problema em que as configurações do filtro não eram mantidas ao alternar entre as guias na página Despesas.
- Corrigimos um problema nos relatórios do Apptio BI em que os dados de FTE (equivalente a tempo completo) da atividade laboral eram exibidos incorretamente quando agrupados por intervalos trimestrais, semestrais ou anuais. Esta correção se aplica a Integrated Investment Planning.
- Resolvido um problema em que a importação de permissões de objetos de custo não acionava um erro para nomes de usuário inexistentes no Frontdoor.
- Corrigido um problema em que os dados do plano exportados não seguiam as configurações de formatação numérica definidas.
- Resolvido um problema em que o valor do atributo Boolean Cost Center era exibido incorretamente como “false” nas comparações de planos.
- Corrigido um problema em que o Centro de Custos não era preenchido automaticamente na guia Mão de obra após a criação de um novo item de linha.
- Corrigido um problema em que o ADM ( Data Management ) carregava dados de previsão no ano fiscal errado para calendários fiscais com datas de início diferentes de janeiro.
- Corrigimos um problema em que o recurso de comentários ficava desativado ao usar a configuração de localidade japonesa.
- Resolvido um problema em que o campo “Tipo de contrato” não era salvo ao adicionar uma nova linha na guia Contratos ao usar as configurações de idioma japonês.

## 3.84 - 20 de janeiro de 2025

Ajustes variáveis de extensão de contrato

Esta versão apresenta o recurso Ajustes de Extensão de Contrato Variável, proporcionando maior flexibilidade na modelagem dos custos do contrato. Com essa funcionalidade, você pode:

- Aplicar o ajuste de extensão composta em cada renovação do contrato.
- Prorrogar o contrato por um período inferior à duração do plano, em vez do comportamento padrão atual de sempre prorrogar o contrato pela duração total do plano.
- Defina diferentes porcentagens de ajuste de extensão para cada renovação de contrato.
- Forneça comentários para apoiar cada ajuste de renovação

Esse recurso permite uma modelagem mais precisa, levando em consideração mudanças financeiras específicas, como inflação ou ajustes de taxas, em ciclos de planejamento plurianuais.

Observação : esse recurso está disponível apenas quando a Nova Visualização está ativada.

![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/3.84.jpg)

![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/3.84-1.jpg)

Para saber mais, consulte [Ajuste de extensão de contrato variável](../planning/vrbl-cntc-ext-adj.html "Apptio O planejamento permite estender contratos além da data de término original, com recursos diferentes dependendo se você está usando a Visualização Antiga ou a Nova Visualização.").

KPIs de despesas do projeto

Esta versão apresenta novos KPIs de despesas do projeto disponíveis quando Integrated Investment Planning o recurso está ativado, além de dicas de ferramentas adicionadas a todos os KPIs para melhorar a usabilidade:

- Total do projeto : exibe o total combinado das despesas operacionais ( OpEx ) e de capital ( CapEx ) associadas a um projeto. Isso é calculado como a soma dos itens financeiros em que o ID do projeto não é nulo.
- Total de encargos : mostra o total de créditos aplicados das despesas com atividades de mão de obra do projeto, calculado como a soma dos itens em que o tipo de custo = encargos.

Esses KPIs estão acessíveis nas páginas Despesas > Resumo, Painel e Resumo. Além disso, o KPI Total de Encargos está incluído em Despesas > Atividade de Mão de Obra. Com a adição de dicas de ferramentas, os usuários agora podem visualizar explicações detalhadas para cada KPI diretamente na interface, aumentando a clareza e a usabilidade.

![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/384-1.jpg)

IBM Planning Analytics Integração

Temos o prazer de anunciar a integração do IBM Planning Analytics com o IBM Apptio, permitindo uma conectividade perfeita entre essas plataformas para aprimorar o planejamento e a análise financeira. Essa integração bidirecional permite que os usuários unifiquem seus processos de planejamento, alinhem dados financeiros e tomem decisões mais precisas e baseadas em dados em toda a organização.

Principais características :

- Sincronize automaticamente os dados financeiros entre IBM Planning Analytics e IBM Apptio para garantir uma visão consistente dos orçamentos, previsões e resultados reais.
- Combine os recursos de gestão financeira de TI d Apptio com as ferramentas de planejamento e previsão d IBMPlanning Analytics para obter processos de planejamento mais abrangentes e integrados.
- Reduza o esforço manual e os erros com a troca automatizada de dados, garantindo que os planos financeiros estejam sempre atualizados.

Para habilitar os conectores de dados IBM Planning Analytics, consulte o guia de configuração no link abaixo.

[IBM Planning Analytics Guia de configuração de integração](https://www.ibm.com/docs/en/apptio-platform/datalink/saas?topic=connectors-configure-planning-analytics-connection "(Abre em uma nova guia ou janela)")

Observação : essa integração requer um software como serviço (nuvem) IBM Planning Analytics.

![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.84-ibm.jpg)

Correções de erros

- Resolvido um problema em que os usuários administradores não conseguiam visualizar colunas marcadas como confidenciais após atribuir permissões de objeto de custo com restrições de visualização.
- Corrigimos um problema com a linha de base do Plano de Previsão, em que a seleção de um mês de início da previsão no Ano 2 fazia com que o plano de linha de base falhasse ao copiar linhas para todos os anos.
- Corrigimos um problema em Despesas > Contratos, onde os valores padrão não eram preenchidos ao adicionar uma nova linha de contrato com as dimensões “Data de início” ou “Data de término” ocultas.
- Resolvido um problema com a importação de dados reais em que o fornecimento de um código de projeto em vez de um código de objeto de custo resultava em um objeto de custo inválido e um erro de mapeamento do centro de custo.
- Migrou a caixa de diálogo Criar análise de variação para a interface de usuário moderna. Observação: esta atualização é apenas uma melhoria visual, sem alterações funcionais.
- Resolvido um problema em que a importação de listas com caracteres especiais adicionava aspas duplas indesejadas aos valores de texto.
