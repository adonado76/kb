---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Adicionar componentes editáveis aos relatórios"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Criar relatórios"
  - "Relatórios avançados"
source_path: "studio/new-uc/howtoguides/create-reports/add-et-rep.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Adicionar componentes editáveis aos relatórios

**Objetivo:** Incorporar tabelas editáveis nos relatórios para viabilizar fluxos de trabalho de entrada de dados pelo usuário final, permitindo que os usuários insiram ou modifiquem dados diretamente na interface do relatório, sem a necessidade de acessar o TBM Studio.

**Quando usar:** Quando os usuários precisam inserir ou atualizar dados como mapeamentos de mão de obra, atributos de centros de custo, lançamentos orçamentários ou explicações de variações.

**Tempo estimado:** 15 a 25 minutos

## Entendendo os componentes editáveis

As tabelas editáveis nos relatórios criam uma camada de entrada de dados que alimenta as tabelas de transformação do TBM Studio e, por fim, o modelo de custos. Eles oferecem suporte a cenários como:

- Mapeamentos de pessoal (atribuição de funcionários a soluções, categorias ou grupos de custos)
- Atributos do centro de custo (adição de metadados ou classificações)
- Explicações sobre os desvios orçamentários (incluindo comentários dos responsáveis pelos centros de custo)
- Correções diretas nos dados (permitindo edições controladas nos dados de origem)

**Pré-requisitos**

- Uma tabela editável já existente criada em Data Studio (consulte a seção 3.1.3 para saber como criar tabelas editáveis)
- Um relatório para adicionar o componente editável ao
- Permissões adequadas (os usuários precisam de acesso ao ambiente de desenvolvimento e ao ambiente de teste para publicar as alterações)

## Passos

**Passo 1: Adicione o componente de tabela editável**

1. Abra o relatório de destino no Report Studio e dê uma olhada nele.
2. Na guia Relatório, clique em Tabela editável. Um componente de tabela editável é adicionado ao relatório, e o painel de configuração do componente é aberto.
3. No menu suspenso do seletor de tabelas, na parte superior do painel Configuração do componente, selecione a tabela editável que deseja exibir.

**Passo 2: Configurar as colunas visíveis**

1. Arraste as colunas do Explorador de Projetos para a área Colunas Incluídas do painel Configuração do Componente.
2. Organize as colunas na ordem de exibição desejada arrastando-as para cima ou para baixo na lista.
3. As colunas não incluídas permanecem disponíveis na tabela editável, mas ficam ocultas na visualização do relatório.

Dica: exiba apenas as colunas que os usuários precisam ver e editar. As colunas ocultas mantêm seus dados e não são afetadas pelas edições feitas pelo usuário nas colunas visíveis.

**Etapa 3: Configurar o comportamento de edição**

1. Clique com o botão direito do mouse no componente de tabela editável e selecione Propriedades.
2. Na guia Edição de dados, configure:
   - **Ativar adição de linhas:** permite que os usuários adicionem novas linhas (para tabelas editáveis em branco)
   - **Ativar exclusão de linhas:** permite que os usuários excluam linhas (apenas para tabelas editáveis em branco)
   - **Ativar duplicação de linha:** permite que os usuários dupliquem linhas existentes
   - **Ativar transporte:** copia automaticamente os valores numéricos para a célula seguinte ao pressionar a tecla Tab entre as células
3. Clique em OK para salvar a configuração.

**Passo 4: Adicionar a funcionalidade de upload (opcional)**

Para permitir que os usuários importem dados pelo Excel:

1. Role até o final do componente de tabela editável no relatório.
2. As opções “Abrir no Excel” e “Clicar ou arrastar o arquivo” aparecem automaticamente para componentes de tabela editáveis.
3. Os usuários podem baixar os dados atuais para o Excel, fazer alterações e enviar o arquivo modificado.

**Passo 5: Salvar e fazer o check-in**

1. Posicione e redimensione o componente de tabela editável conforme necessário.
2. Salve e verifique o relatório.

## Fluxo de trabalho do usuário para entrada de dados

Depois de configurar um componente editável, os usuários finais seguem este fluxo de trabalho:

1. Acesse o relatório que contém a tabela editável.
2. Clique nas células para editar os valores diretamente. As colunas com menu suspenso exibem os valores permitidos.
3. Clique em Salvar para salvar as alterações localmente (as alterações ficam armazenadas no lado do cliente até serem publicadas).
4. Clique em “Publicar” na parte inferior do relatório para salvar as alterações na tabela de transformação subjacente.
5. Digite uma descrição e clique em “Publicar” para concluir a publicação.

Aviso: A publicação confirma TODAS as edições pendentes em toda a tabela editável, e não apenas nas linhas filtradas visíveis na tela. Se a segurança por linha estiver ativada, os usuários só verão e poderão editar as linhas para as quais têm autorização, mas as linhas ocultas serão mantidas durante a publicação.

## Colunas especiais para controle de auditoria

As tabelas editáveis incluem colunas especiais de auditoria que você pode mostrar ou ocultar:

- **Coluna.pk:** A coluna da chave primária. Mostre isso para garantir a consistência nas operações de copiar/colar e na classificação.
- **Coluna "Nome de usuário":** mostra quem fez a última alteração em cada linha.
- **.EditDate coluna:** Mostra quando foi feita a última alteração em cada linha.

Para exibir essas colunas: passe o mouse sobre o cabeçalho da coluna, clique com o botão direito do mouse e selecione “Mostrar” no menu.

## Concorrência e bloqueio

As tabelas editáveis aplicam bloqueio no nível das células para evitar conflitos:

- Quando um usuário começa a editar uma célula, essa célula fica bloqueada para os outros usuários
- O bloqueio permanece até que o usuário salve ou cancele
- Outros usuários podem editar diferentes células da mesma tabela simultaneamente

## Resultados esperados

- As células editáveis são destacadas quando os usuários clicam nelas
- As colunas com menu suspenso exibem os valores permitidos configurados
- Os erros de validação são exibidos como avisos ou erros próximos às células afetadas
- Os botões “Salvar” e “Publicar” aparecem na parte inferior do componente

## Armadilhas comuns

- **Os usuários não podem adicionar/excluir linhas:** apenas tabelas editáveis em branco permitem a adição e a exclusão de linhas. As tabelas editáveis enriquecidas (derivadas de tabelas de transformação) não permitem a exclusão de linhas, pois essas linhas provêm da transformação de origem.
- **As alterações não aparecem no modelo:** os usuários devem publicar as alterações, não apenas salvá-las. As alterações salvas permanecem apenas no lado do cliente até serem publicadas.
- **Erros de validação impedindo a publicação:** as linhas inválidas não podem ser publicadas. Os usuários devem corrigir os erros de validação antes que a publicação possa ser concluída.

## Tarefas relacionadas

- Criar tabelas editáveis (Seção 3.1.3 )
- Configurar listas suspensas para colunas editáveis (Seção 3.1.3 )
- Configure agendas de publicação recorrentes (Seção 6.1 )
- Configurar a segurança no nível da linha (Seção 4.4 )

**Tópico principal:** [Relatórios avançados](../../../../studio/new-uc/howtoguides/create-reports/adv-rep.html)
