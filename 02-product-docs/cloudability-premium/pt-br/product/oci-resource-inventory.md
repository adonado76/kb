---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Inventário de Recursos da OCI"
breadcrumb:
  - "Cloudability Premium"
  - "Insights"
  - "Inventário de recurso"
source_path: "product/oci-resource-inventory.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Inventário de Recursos da OCI

O recurso Inventário de recursos OCI do Cloudability permite que você produza uma lista oficial dos recursos de nuvem OCI que existiam e foram cobrados durante um período específico de relatório. Você tem a flexibilidade de criar essa lista a partir de recursos que abrangem várias contas e escolher entre diferentes medidas (dimensões e métricas) para exibir os detalhes relevantes para elas. Atualmente, essas informações estão disponíveis apenas para recursos **de máquinas virtuais** — unificam faturamento, utilização e metadados descritivos para oferecer uma visão mais abrangente do inventário.

## Introdução

O recurso de relatórios do Inventário de Recursos OCI deve estar habilitado para sua organização do Cloudability. Você deve entrar em contato com seu TAM/CSM/ponto de contato da conta em IBM Cloudability para fazer isso. Depois de ativado, aguarde 2 a 3 dias úteis para que os dados comecem a aparecer nos seus relatórios de inventário.

Medidas de relatórios de inventário

- As medidas são categorizadas como dimensões, métricas e tags (as tags incluem dimensões de tag d Cloudability, grupos de contas e mapeamentos de negócios). Você pode incluir até 20 colunas em um relatório individual.
- Para o serviço OCI Virtual Machine, um conjunto específico de medidas é suportado.
- Você pode filtrar seus respectivos relatórios de inventário usando qualquer uma das medidas disponíveis neste recurso.

KPIs clicáveis para filtragem rápida

Para cada serviço, os KPIs serão exibidos na parte superior do relatório para fornecer informações resumidas importantes, como Recursos totais e Instâncias sem marcação. Você pode clicar e filtrar o relatório de inventário com base nesses KPIs para detalhar os dados específicos do relatório que você está procurando.

Janelas de datas para relatórios de inventário

Você pode escolher o período no seletor de datas para o qual deseja visualizar os dados de inventário de cada serviço. O intervalo máximo permitido para seleção é de 31 dias. Ao ativar esse recurso, os dados do inventário de recursos serão preenchidos retroativamente até o início do mês atual. Com o tempo, os dados de inventário estarão disponíveis em uma janela móvel de três meses. A qualquer momento, você poderá acessar os dados do inventário de recursos do mês atual, juntamente com os dois meses anteriores.

Filtragem estatística usando o filtro de exibição

A partir dos dados de inventário gerados para um serviço e período de tempo específicos, agora você pode optar por exibir um subconjunto desses dados, seja o número x superior ou a porcentagem x de recursos com base em sua métrica preferida de custo ou utilização.

Por exemplo: o Inventário de Recursos exibe 1000 registros para o serviço Compute por um período de sete dias. Você pode filtrar ainda mais essa exibição, optando por visualizar apenas os 25% principais desses recursos, com base no custo (total). A aplicação deste filtro retornaria os 250 principais recursos com base no custo (total), classificados do mais alto para o mais baixo.

Exportando relatórios

C licar em Exportar no canto superior direito da tabela do relatório exportará todas as colunas de inventário selecionadas com qualquer filtro aplicado. No entanto, para exportar os dados completos do inventário para o mês e serviço selecionados com todas as colunas suportadas, clique no botão Exportar no canto superior direito do menu suspenso Filtros na barra de ferramentas da guia.

Relatórios de inventário de recursos de economia

Você pode salvar um relatório com suas seleções de data, serviço e filtro e compartilhar esse relatório com outros usuários da organização, concedendo a eles permissões de “Somente visualização” ou “Editar”. No canto superior direito da barra de ferramentas da interface do usuário do Inventário de Recursos, você pode ver um ícone de elipse com três pontos. Ao clicar nele, será aberto o menu Ações do Relatório com essas opções.

- **Salvar como relatório:** Usando esta opção, você pode salvar uma cópia do seu relatório. Esta opção é útil se alguém compartilhou um relatório com você com acesso “Somente visualização” e você deseja fazer alterações nesse relatório criando sua própria cópia dele. Outro caso de uso do Salvar como relatório é para o Relatório padrão. O Relatório Padrão não pode ser modificado e você precisará selecionar a opção “Salvar como Relatório” para salvar quaisquer alterações feitas no Relatório Padrão.
- **Salvar relatório:** Esta opção é usada para salvar quaisquer alterações feitas no relatório que você criou ou que foi compartilhado com você com permissão para “Editar”
- **Compartilhar relatório:** Com essa opção, você pode compartilhar seus relatórios com outros usuários da sua organização, concedendo a eles permissões de “Somente visualização” ou “Editar”.
- **Excluir relatório:** Você pode excluir seu relatório clicando em Excluir relatório.
- **Tratamento do intervalo de datas em relatórios salvos:** Os relatórios salvos com intervalos de datas não contínuos e fora do intervalo permitido (superiores a 3 meses) serão carregados com o intervalo de datas redefinido para o padrão de 7 dias. Também será exibida uma mensagem de aviso ao usuário informando que o intervalo de datas foi reiniciado. Esse comportamento garante que os relatórios salvos continuem acessíveis mesmo quando os intervalos de datas armazenados ultrapassarem o limite permitido.

Nota:

- O número máximo de relatórios que serão exibidos no menu suspenso Relatórios salvos é 100.
- Quando um relatório é compartilhado com um usuário, nenhuma notificação por e-mail será enviada.
- O Inventário de Recursos suporta um máximo de 3 meses de dados, ou seja, o mês até à data + os últimos 2 meses. Assim, os dados acabariam por expirar nos relatórios quando ultrapassassem esse período de retenção.

Utilizando o inventário de recursos

1. Para acessar o Inventário de Recursos OCI, navegue até Insights > Inventário de Recursos e clique na guia OCI.

1. Selecione o serviço no menu suspenso Serviços (atualmente apenas Máquina Virtual) para o qual deseja visualizar seu inventário de recursos.
2. Selecione o intervalo de datas para o qual deseja visualizar os dados do inventário de recursos. Você pode optar por visualizar até 31 dias de dados, no máximo. Os dados exibidos serão classificados por Custo (Total)em ordem decrescente por padrão.
3. Clique em qualquer um dos KPIs com a barra azul à esquerda para filtrar seus relatórios com base nesse KPI específico.
4. Clique no botão de configurações da tabela no canto superior direito da tabela de inventário de recursos para configurar as medidas e tags que você deseja exibir como colunas na tabela.

As medidas e tags selecionadas são exibidas como colunas na tabela.

1. Clique em Filtros para aplicar quaisquer filtros ao seu relatório de inventário.
2. Use o  Exibir  menu suspenso acima da tabela Detalhes do inventário de recursos para especificar a porcentagem superior ou inferior das linhas a serem exibidas na tabela e para classificar a tabela em ordem decrescente pelo custo preferencial ou métrica de utilização.
3. Clique no botão Exportar no canto superior direito da tabela Detalhes do inventário de recursos para exportar todas as colunas exibidas na tabela filtradas pelas suas configurações de filtro. Para exportar todos os dados de inventário do mês e serviço selecionados com todas as colunas suportadas, clique no botão Exportar, à direita do menu suspenso Filtros na barra de ferramentas da guia.

Medidas de recursos indicando "Não disponível"

Para alguns recursos, você pode perceber que algumas medidas, como Data de lançamento, Estado e Tamanho, entre outras, aparecem como Não disponível no relatório Inventário de recursos. Isso significa que Cloudability não conseguiu obter dados para essas medidas específicas devido a um dos seguintes motivos:

- Você pode não ter feito a credenciação avançada para a conta à qual o(s) recurso(s) específico(s) pertence(m).
- A vida útil do(s) recurso(s) pode ter sido muito curta para capturar os dados para essas medidas.
- As métricas de utilização desses recursos podem aparecer como “0” (zero) no relatório.

| Computação OCI | |
| --- | --- |
| Total de recursos | Número total de e VM s (incluindo instantâneos/backups) para o período selecionado. |
| Total de instâncias | Número total de instâncias do VM (excluindo instantâneos/backups) para o período selecionado. |
| Instanças inativas do VM | Número de instâncias do VM que estão em um desses estados: “terminando”, “parando”, “parado” ou “terminado” |
| Custo (total) | Custo total calculado pela taxa não combinada |
| Total de capturas instantâneas | Número total de instantâneos (backups) do VM para o período selecionado. |
| Instâncias não marcadas do VM | Número de instâncias que não possuem tags. |

**Tópico principal:** [Inventário de recursos](../product/resource-inventory.html)
