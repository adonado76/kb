---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Guia prático: Configurar tabelas publicadas"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Trabalhar com dados"
  - "Exportação de dados"
source_path: "studio/new-uc/howtoguides/work-with-data/htg-config-pt.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Guia prático: Configurar tabelas publicadas

**Objetivo:** Criar e configurar uma tabela publicada que permita que sistemas externos consultem dados do modelo de custos

**Quando usar:** Quando for necessário fornecer um conjunto de dados estável e atualizado automaticamente para ferramentas externas de BI, data warehouses ou outros projetos de Cálculo de Custos e Planejamento

**Pré-requisitos:**

- TBM Studio versão 12.11.3 ou posterior
- Permissões de administrador para criar e modificar tabelas publicadas
- Um modelo de custos completo com dados calculados
- (Opcional) Uma tabela de relatório existente a ser convertida

**Tempo estimado:** 15 a 20 minutos

## Como interpretar tabelas publicadas

As tabelas publicadas são entidades de exportação específicas no TBM Studio, distintas dos relatórios e das tabelas de transformação. Elas resolvem um problema comum: antes das Tabelas Publicadas, os usuários precisavam criar relatórios bloqueados para exportar dados, o que sobrecarregava o processo de cálculo de preparação e complicava o gerenciamento de permissões.

As tabelas publicadas oferecem várias vantagens:

- Elimine a necessidade de gerenciar permissões de relatórios para a exportação de dados
- Permitir a exportação assim que o cálculo de desenvolvimento for concluído
- Fornecer um esquema estável no qual os sistemas externos possam confiar
- Eliminar a dependência da interface de relatórios para a saída de dados

Importante: as tabelas publicadas refletem apenas os valores do modelo implantado — elas não exibem valores preliminares dos ramos de desenvolvimento. Os dados são atualizados sempre que um cálculo no ambiente de teste ou de produção é concluído com sucesso.

## Método 1: Criar uma nova tabela publicada

Siga estas etapas para criar uma tabela publicada do zero:

1. Vá até a guia **Início** e selecione **Novo**.
2. Selecione **“Tabela publicada”** no menu.
3. Na caixa de diálogo que aparece:
   - Digite um **nome** descritivo para a tabela (por exemplo, "Resumo de custos mensais - PowerBI"" )
   - Selecione uma **categoria** para organizar a tabela no Explorador de Projetos
   - Clique **em OK**
4. Localize a tabela recém-criada no Explorador de Projetos, na categoria especificada.
5. Configure a tabela publicada definindo seu conteúdo de dados:
   - Selecione o objeto do modelo de origem ou a tabela de transformação
   - Escolha quais colunas incluir
   - Aplique as regras de formatação ou conversão necessárias

Observação: O processo de configuração é semelhante ao da configuração de uma tabela de relatório. Para obter instruções detalhadas sobre as opções de configuração de tabelas, consulte a seção “Tabelas em relatórios” da documentação do Report Studio (Seção 5.3 ).

- Faça o check-in das suas alterações para incluir a Tabela Publicada no seu projeto.

## Método 2: Criar a partir de uma tabela de relatório existente

Se você já tiver uma tabela de relatório configurada com os dados que deseja exportar, poderá convertê-la diretamente em uma tabela publicada:

1. Acesse o relatório que contém a tabela que você deseja exportar.
2. Clique com o botão direito do mouse na tabela do relatório.
3. Selecione **“Criar tabela publicada”** no menu de contexto.
4. Na caixa de diálogo:
   - Digite um **nome** para a nova tabela publicada
   - Selecione uma **categoria**
   - Clique **em OK**
5. A nova tabela publicada aparece no Explorador de Projetos e herda a configuração da tabela do relatório original.

Dica: Esse método é ideal quando você já aperfeiçoou a seleção e a formatação das colunas de uma tabela de relatório — assim, você não precisa recriar essa configuração.

## Configurar as definições de pré-cálculo

Por padrão, as tabelas publicadas são pré-calculadas durante o processo de compilação, garantindo que os dados estejam prontos imediatamente quando solicitados. Você pode ajustar esse comportamento:

1. No Project Explorer, verifique a tabela publicada.
2. Selecione a guia **“Tabela publicada”** para visualizar suas propriedades.
3. Localize a configuração “**Ativo** ”:
   - **Marcado (padrão):** O sistema pré-calcula a tabela durante as compilações. Os dados ficam disponíveis imediatamente após a chamada da API URL.
   - **Desmarcado:** O sistema não realiza o cálculo prévio. A API continua funcionando, mas a primeira solicitação aciona um cálculo, o que pode atrasar a resposta.
4. Salve suas alterações.

**Quando desativar o pré-cálculo:** considere desativar o pré-cálculo para tabelas publicadas que raramente são acessadas ou utilizadas apenas para resolução de problemas. Isso reduz o tempo de compilação das suas exportações principais.

## Recuperar o endereço da API ( URL ) de uma tabela publicada

Após a configuração, obtenha o endereço URL que os sistemas externos usarão para acessar os dados:

1. No Explorador de Projetos, clique com o botão direito do mouse na **Tabela** Publicada.
2. Selecione **“Mostrar API” ( URL )** no menu de contexto.
3. Copie o endereço URL da caixa de diálogo.
4. Use este URL em:
   - DataLink conexões para extração programada de dados
   - Scripts personalizados para acesso programático
   - Configurações de fontes de dados da ferramenta de BI

Dica: A API URL permanece estável desde que o nome da tabela publicada não seja alterado. Se você renomear a tabela publicada, atualize todos os sistemas que a utilizam com o novo URL.

## Resultados esperados

Após concluir estas etapas:

- Sua tabela publicada aparece no Explorador de Projetos na categoria atribuída a ela
- Os dados são atualizados automaticamente após cada cálculo bem-sucedido no ambiente de teste ou de produção
- Sistemas externos podem recuperar dados usando a API URL nos formatos CSV ou JSON
- O esquema permanece estável, a menos que você modifique explicitamente a configuração da tabela publicada

## Armadilhas comuns

**Dados que não aparecem na tabela publicada** — as tabelas publicadas refletem apenas os valores do modelo implantado. Se você estiver trabalhando em um ramo de desenvolvimento, os dados não aparecerão até que você promova as alterações e execute um cálculo.

**Primeira solicitação lenta** — Se o pré-cálculo estiver desativado, a primeira solicitação de API aciona o cálculo. No caso de grandes conjuntos de dados, isso pode levar bastante tempo. Ativar o pré-cálculo para tabelas publicadas acessadas com frequência.

**Alterações no esquema que prejudicam sistemas a jusante** - Quando você modifica as seleções de colunas em uma tabela publicada, os sistemas a jusante podem deixar de funcionar corretamente. Comunique as alterações no esquema a todos os usuários dos dados antes de realizar as modificações.

**Erros que impedem a atualização** - Se as tabelas de transformação de origem apresentarem erros ou incompatibilidades de dados, a atualização da tabela publicada falhará. Verifique os registros de cálculo e resolva primeiro os problemas na origem.

**Tópico principal:** [Exportação de dados](../../../../studio/new-uc/howtoguides/work-with-data/data-export.html)
