---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Dimensionamento correto do ROI"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
source_path: "product/jira-for-rightsizing.html"
images:
  - "images/rightsizing_roi_1.png"
  - "images/rightsizing_roi_2.png"
  - "images/rightsizing_roi_3.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Dimensionamento correto do ROI

O Rightsizing ROI permite que você acompanhe as recomendações de rightsizing, desde a oportunidade até a conclusão, e gere relatórios sobre o impacto de seus esforços de rightsizing. Você pode criar tíquetes manualmente ou por meio de políticas automatizadas que permitem rastrear essas recomendações, analisar oportunidades abertas e fechadas, comentar sobre essas oportunidades e gerar relatórios sobre as economias obtidas como resultado.

O Rightsizing ROI permite que você configure políticas para criar automaticamente problemas e solicitações enquanto acompanha as recomendações. Você também pode usá-lo para visualizar a economia real resultante da aplicação dessas recomendações de otimização de recursos.

O Rightsizing ROI tem três opções de tíquetes:

- Uma integração do Jira Cloud usando a extensão do Jira Service Management para criar problemas e solicitações do Jira e usar a sincronização bidirecional do status do tíquete do Jira para manter seus projetos sincronizados.

- Uma integração com o ServiceNow usando um script gerado pelo Cloudability para incidentes e solicitações do ServiceNow, usando também a sincronização bidirecional do status do tíquete do ServiceNow para manter seus projetos sincronizados.

- Funcionalidade autônoma de rastreamento de tíquetes contida no próprio site Cloudability.

## Antes de começar

**Se quiser usar a funcionalidade de emissão de tíquetes na nuvem do ServiceNow ou do Jira, você precisará configurar essas integrações primeiro. Consulte os guias de configuração abaixo para obter mais informações**

Integração com o Jira

- Saiba mais sobre [a integração com o Jira – Configuração](../admin/connect-jira-cloud.html)

ServiceNow integração

- Saiba mais sobre [a integração ServiceNow - Configuração](../admin/connect-servicenow-integration.html)

Usando o ROI do dimensionamento de direitos: Criação de tíquetes

Os tíquetes podem ser criados no Rightsizing ROI de duas maneiras.

Criação manual de tíquete - Ao visualizar qualquer recomendação nas páginas de recomendação do Rightsizing, você pode criar um tíquete diretamente pela interface do usuário, clicando no botão Mais opções, no lado direito da recomendação.

A partir daí, você pode selecionar o sistema de tíquetes que deseja utilizar e um tíquete de ROI de dimensionamento de direitos é criado e vinculado ao sistema de sua escolha com os detalhes relevantes.

![](../../../../03-media/cloudability-premium/images/rightsizing_roi_1.png)

**Criação de tíquetes por meio de política automatizada** - As políticas automatizadas oferecem uma maneira escalonável de criar tíquetes em relação às oportunidades apresentadas pelo mecanismo de redimensionamento Cloudability. As políticas podem ser executadas em intervalos definidos e criar tíquetes para as oportunidades até o número selecionado de resultados, para que suas equipes se concentrem apenas nas maiores oportunidades.

## Como configurar uma política

1. Navegue até **Settings > Rightsizing Policies**.

1. Selecione o botão **Adicionar uma política**. **A** aba “Criar uma política” é aberta.![direcionamento-adicionar-política-captura-de-tela](../../../../03-media/cloudability-premium/images/rightsizing_roi_2.png)

1. Insira seus critérios de política:

- **Nome** : Digite um nome para sua apólice.

- **limite de economia de 30 dias** : Insira a economia mínima de custos que você precisa em 30 dias.

- **Serviço de nuvem** : Selecione o recurso de nuvem que você deseja incluir.

- **Base de custo** : Escolha a base de custo a ser usada no cálculo do limite.

- **Ações** : Marque as caixas para incluir ações de rightsizing.

- **Resultados máximos** :insira os resultados máximos adicionados de cada execução programada.

- **Exibir** : Selecione o filtro para seus recursos.

- **Tipo de integração** : Selecione o tipo de integração de ROI para essa política.

- **Projeto** : Para o Jira, selecione o projeto em que os tíquetes criados são exibidos.

- **Tarefa** : Em ServiceNow,, selecione o tipo de tarefa em que os tíquetes criados são exibidos.

- Tipo de solicitação: Para o Jira, selecione o tipo de problema (Jira) ou o tipo de solicitação (Jira Service Management).

- **Programar** : Selecione a recorrência.

- **Dias da semana:** Se a política for executada semanalmente, selecione o dia em que você deseja que ela seja executada.

- **Terminar após** : Escolha a data de término da apólice.

1. Selecione o botão **Create (Criar** ) para criar a política ou selecione o botão **Create and Run (Criar e executar** ) para criar uma política e executá-la.

Para ativar a criação automática de tíquetes, você deve criar e configurar uma política.

## Dimensionamento do ROI: Compreensão e triagem de seus problemas e tíquetes

Os problemas, as solicitações ou os tíquetes de incidentes criados pela política são todos visíveis na exibição de tabela do Painel de dimensionamento no Rightisizing ROI, bem como diretamente no projeto JIRA configurado ou na fila ServiceNow.

Cada ingresso contém:

- Uma visão geral da recomendação.

- Um link para os detalhes da recomendação em Cloudability.

- Rótulos dos principais atributos do recurso.

![Ícone de notas](../../../../03-media/cloudability-premium/images/rightsizing_roi_3.png)

## Exibir recomendações no painel Rightsizing

Em Cloudability, os tíquetes criados pela política são exibidos no painel Rightsizing ROI. Ele exibe os seguintes indicadores-chave de desempenho (KPIs) agregados:

- **Economia em potencial:** Oportunidades de economia em potencial de todos os tíquetes não resolvidos.

- **Economia realizada** : Economia realizada para todos os tíquetes resolvidos, normalizada para uma taxa de economia de 30 dias.

- **Gráfico de economia realizada:** O gráfico mostra um detalhamento dos tíquetes acionados e a economia realizada associada por data em que foram acionados. O Rightsizing ROI não tenta acumular economias ao longo do tempo, mas mostra a taxa de economia de 30 dias para as ações nas datas, para que você possa ver a taxa na qual as equipes estão implementando mudanças/resoluções.

**Ingressos individuais**

O painel Rightsizing também exibe os detalhes de cada tíquete criado por sua política:

- **Serviço de nuvem** : O provedor e o serviço de nuvem.

- **Nome do recurso** : O nome do recurso da nuvem.

- **ID do recurso** : um identificador exclusivo para um recurso específico do site AWS.

- **Ticket** : O tíquete associado a esse recurso.

- **Digite** : Jira, ServiceNow, ou Cloudability.

- **Status** : O status atual do tíquete.

- **Atribuído** a: O proprietário do bilhete.

- **Criado** : A data em que o tíquete foi criado.

- **Fechado :** A data em que o tíquete foi resolvido ou "N/A" se o tíquete ainda estiver ativo.

- **Resolução** : O status da resolução do tíquete.

- **Potencial de economia:** Potencial de economia para o tíquete identificado pela recomendação.

- **Economia realizada:** Economia realizada com base no novo tipo de instância.

- **Detalhes** : Os detalhes da recomendação.

**Observação** : Revise as recomendações de Rightsizing para cada serviço usando a visualização de 30 dias. A partir daí, observe as oportunidades de economia de custos para obter insights sobre como estabelecer o valor limite.

**Observação** : a detecção de alterações de recursos é atualmente compatível com os tipos de recursos de computação, armazenamento e banco de dados.

## Exclusão de tíquetes de ROI do dimensionamento

Para excluir um tíquete no Rightsizing ROI, clique no painel de detalhes do tíquete que você deseja excluir. Selecione o botão de mais opções no canto superior direito e selecione excluir. Confirme sua intenção de excluir o tíquete. **A exclusão de tíquetes de ROI do Rightsizing não pode ser desfeita.**

## Perguntas frequentes sobre o ROI do redimensionamento

**Existe uma maneira de ver quem lhe atribuiu um tíquete de Rightsizing?**

Não, se o tíquete for alocado por meio da interface Cloudability.

**Em quanto tempo as economias realizadas aparecerão no ROI do rightsizing? Ele desaparece ou fica lá para sempre?**

Os dados de economia realizada no recurso Rightsizing ROI não são excluídos; eles permanecem em Cloudability para sempre. É um registro histórico da mudança que foi feita e do dinheiro que foi economizado.

**Como são calculadas as economias realizadas?**

No momento em que a recomendação é rastreada pela primeira vez, o site Cloudability armazena informações sobre o recurso em seu estado atual. Quando ocorre uma alteração no recurso, o valor da economia realizada é calculado com base nos custos de 30 dias do estado original do recurso menos os custos de 30 dias do novo estado do recurso. Como o uso futuro é desconhecido, o valor da economia realizada é calculado como (tipo de recurso atual \* taxa \* 24 horas \* 30 dias) - (tipo de recurso anterior \* taxa \* 24 horas \* 30 dias) como uma estimativa de uso. O valor da economia realizada reflete a mudança que foi realmente feita e não é diretamente influenciado pelo que pode ter sido recomendado.

**Qual é o número máximo de políticas que podem ser criadas?**

Até 30 apólices. No entanto, se você usar uma integração de terceiros (como o Jira Cloud ou o Service Now), poderá contornar esse limite usando esses serviços para fazer a triagem dos tíquetes e das solicitações com base nas informações de recursos fornecidas. Por exemplo, as tags de recursos são incluídas nos tíquetes criados.

**Qual é o número máximo de tíquetes que podem ser criados por execução de política?**

Até 100 tíquetes por rodada. No entanto, o limite é restringido pelo número de tíquetes abertos. Um tíquete "aberto" é atualmente definido como qualquer tíquete que não tenha um valor de "economia realizada".

**O site Cloudability oferece suporte a exibições com filtros baseados no mapeamento de negócios no ROI?**

Não, o Rightsizing não oferece suporte à filtragem por mapeamento de negócios.
