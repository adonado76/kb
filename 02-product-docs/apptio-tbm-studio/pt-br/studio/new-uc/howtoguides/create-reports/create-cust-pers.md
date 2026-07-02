---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Criar perspectivas personalizadas"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Criar relatórios"
  - "Personalização de relatórios"
source_path: "studio/new-uc/howtoguides/create-reports/create-cust-pers.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Criar perspectivas personalizadas

**Objetivo:** Criar uma perspectiva personalizada que organize os campos selecionados para os usuários corporativos, tornando a elaboração de relatórios mais fácil e consistente.

**Quando usar:** Use perspectivas personalizadas quando quiser:

- Forneça aos analistas um conjunto selecionado de campos comumente utilizados
- Reúna campos de várias tabelas em um único local de fácil acesso
- Restringir campos a tabelas específicas para obter resultados previsíveis nos relatórios de produção
- Ocultar a complexidade técnica dos usuários de negócios que criam relatórios

**Pré-requisitos:**

- Função de Usuário Avançado ou Administrador (ou função personalizada com permissão para Editar Modelos)
- Acesso ao Report Studio no modo de edição
- Identificar quais campos os analistas utilizam com mais frequência

**Tempo estimado:** 15 a 30 minutos por perspectiva

## Entendendo as perspectivas personalizadas

O Explorador de Projetos no Report Studio exibe várias seções padrão: Tabelas, Métricas e Tempo. Embora essas seções ofereçam acesso a todos os dados disponíveis, elas podem ser um pouco confusas — especialmente para analistas de negócios que precisam apenas de um subconjunto de campos.

As perspectivas personalizadas resolvem esse problema, permitindo que você crie grupos de campos selecionados. Pense em uma perspectiva personalizada como uma lista de “favoritos” que contém exatamente o que seus usuários precisam. Uma vantagem é que você pode adicionar campos de várias tabelas diferentes e vincular cada campo à sua tabela de origem. Isso permite criar relatórios que contenham dados de várias tabelas em diferentes níveis do seu modelo.

**Conceitos-chave:**

- **Os usuários avançados** têm acesso a todas as seções: Tabelas, Métricas, Tempo e Perspectivas
- **Os analistas** veem apenas as perspectivas personalizadas e a seção "Tempo", o que simplifica a visualização
- Todos os analistas têm acesso a todas as perspectivas personalizadas — não é possível criar conjuntos de perspectivas diferentes para grupos distintos de analistas
- As perspectivas personalizadas aparecem em ordem alfabética na parte superior da área Perspectivas

## Passo a passo: Criar uma perspectiva personalizada

1. No **Explorador** de Projetos, localize a seção **Perspectivas**.
2. Clique com o botão direito do mouse na seção **Perspectivas** e selecione **Adicionar nova perspectiva**.
3. Na caixa de diálogo **Criar Perspectiva**, insira um nome descritivo para a perspectiva (por exemplo, “Análise Financeira de TI” ou “Revisão Mensal de Custos”) e clique **em OK**.

**Dica:** *Escolha nomes que transmitam claramente aos seus analistas o objetivo da perspectiva.*

## Passo a passo: como adicionar campos a uma perspectiva personalizada

Você pode adicionar campos a uma perspectiva usando qualquer um destes métodos:

**Método 1: Arraste a partir do Explorador de Projetos**

1. Localize um campo na seção **Tabelas**, **Métricas** ou **Tempo** do **Explorador** de Projetos.
2. Arraste o campo para o cabeçalho **“Perspectivas”** no **Explorador** de Projetos.
3. Quando solicitado, selecione a perspectiva de destino e clique em **OK**.
4. Preencha a caixa de diálogo “**Publicar campo** ” (veja as opções de campo abaixo).
5. Clique em **Publicar**.

**Método 2: Arrastar a partir da configuração do componente**

1. Ao configurar um componente de relatório, localize um campo útil no painel **Configuração** do Componente.
2. Arraste o campo para a barra de título da seção Perspectivas.
3. Preencha a caixa de diálogo **“Publicar campo”** e clique em “**Publicar** ”.

**Método 3: Clique com o botão direito do mouse em “Configuração do componente”**

1. Clique com o botão direito do mouse em um campo no painel **Configuração** do Componente.
2. Selecione **Publicar**.
3. Preencha a caixa de diálogo **“Publicar campo”** e clique em “**Publicar** ”.

## Opções da caixa de diálogo “Publicar campo”

Ao publicar um campo, você configura várias opções importantes:

|  |  |
| --- | --- |
| **Campo** | **Descrição** |
| Nome | O nome de exibição do campo. Se for associar a um objeto, considere incluir o nome do objeto para maior clareza. |
| Tipo de dados | Controla a formatação básica. Escolha entre Moeda, Número, Porcentagem, etc. |
| Fixar ao objeto | Quando marcada, garante que o campo se aplique apenas ao objeto específico selecionado durante a publicação. Prática recomendada: Sempre bloqueie os campos nos relatórios de produção. |
| Representa um código de hierarquia | Aplica-se apenas a cortadores. Quando marcado, o campo cria agrupamentos hierárquicos com base nos caracteres da pesquisa. |
| Mostrar todas as linhas na consulta baseada em tempo | Quando marcada, exibe todas as linhas nas tabelas baseadas em tempo, mesmo que alguns períodos tenham valores nulos. Necessário para cálculos que utilizem PreviousYear,, YearToDate, e funções de tempo semelhantes. |
| Descrição | Exibido como uma dica de ferramenta quando os usuários passam o mouse sobre o campo. Forneça explicações claras para ajudar os analistas a compreender os dados. |
| Notas | Informações visíveis apenas para outros usuários avançados nesta caixa de diálogo — úteis para documentar decisões sobre a configuração dos campos. |

## Passo a passo: Organizar campos com grupos

Agrupe campos relacionados dentro de uma perspectiva para uma melhor organização:

1. Clique com o botão direito do mouse dentro de uma perspectiva personalizada e selecione “**Adicionar novo grupo** ”.
2. Digite um nome para o grupo (por exemplo, “Métricas de Custos” ou “Dimensões da Unidade de Negócios”).
3. Arraste os campos de outras partes da perspectiva para dentro do grupo.

Para remover um campo de um grupo, arraste-o para uma área vazia dentro da perspectiva personalizada.

Dica: os grupos são especialmente úteis para filtros hierárquicos. A ordem dos campos dentro de um grupo determina a hierarquia do filtro.

## Passo a passo: Criar uma perspectiva exclusiva para administradores

Às vezes, é necessário disponibilizar visualizações para usuários avançados e administradores que os analistas não devem ver:

1. Crie uma nova perspectiva conforme descrito acima.
2. Ao nomear a perspectiva, coloque o nome entre parênteses — por exemplo, **(Campos de administração)** ou **(Métricas técnicas)**.
3. Clique em **OK**.

As perspectivas cujos nomes estão entre parênteses são visíveis apenas para usuários com funções de administrador.

## Gerenciamento de perspectivas personalizadas

**Renomear uma perspectiva:** clique com o botão direito do mouse no nome da perspectiva e selecione **Renomear**.

**Excluir um campo:** clique com o botão direito do mouse no campo dentro da perspectiva e selecione “**Excluir campo** ”.

**Excluir uma perspectiva:** clique com o botão direito do mouse na barra de título da perspectiva e selecione **Excluir**.

**Editar um campo publicado:** clique com o botão direito do mouse no campo e selecione **Editar** para modificar suas propriedades.

## Armadilhas comuns

- **Campos desbloqueados geram resultados inconsistentes:** se você não vincular um campo ao seu objeto, ele poderá ser aplicado a qualquer objeto selecionado no momento no relatório, resultando em dados inesperados.
- **A falta de descrições confunde os analistas:** reserve um tempo para escrever descrições úteis — os analistas podem não conhecer o seu modelo de dados.
- **Um número excessivo de campos vai contra o objetivo:** seja seletivo. Uma perspectiva com 100 campos não é muito melhor do que a visualização de tabelas em formato bruto.
- **Opção de consulta baseada no tempo:** Se você estiver publicando métricas calculadas que fazem referência a outros períodos, marque a opção “Mostrar todas as linhas na consulta baseada no tempo” para garantir que os dados sejam exibidos na íntegra.

**Tópico principal:** [Personalização de relatórios](../../../../studio/new-uc/howtoguides/create-reports/report-cust.html)
