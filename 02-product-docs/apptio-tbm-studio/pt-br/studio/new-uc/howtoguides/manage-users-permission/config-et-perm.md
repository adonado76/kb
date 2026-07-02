---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Configurar permissões para tabelas editáveis"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Gerenciar usuários e permissões"
  - "Controle de acesso"
source_path: "studio/new-uc/howtoguides/manage-users-permission/config-et-perm.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configurar permissões para tabelas editáveis

|  |  |
| --- | --- |
| **Objetivo** | Controle quais usuários ou funções podem editar, enviar ou excluir dados em tabelas editáveis |
| **Tempo estimado** | 15 a 20 minutos por tabela editável |
| **Pré-requisitos** | Tabela editável criada; função de administrador ou usuário avançado; usuários e funções configurados |

## Quando utilizar este procedimento

Utilize permissões de tabela editável quando diferentes usuários ou funções precisarem ter diferentes níveis de acesso de edição às tabelas de entrada de dados. Isso é especialmente importante em cenários de entrada de dados distribuída, nos quais os gerentes de centros de custo, os proprietários de aplicativos ou outras partes interessadas mantêm suas próprias partes dos dados de mapeamento ou de referência.

## Tipos de permissões para tabelas editáveis

As tabelas editáveis suportam vários tipos de permissão:

|  |  |
| --- | --- |
| **Permissão** | **O que controla** |
| Permissão para fazer upload | Quais funções podem fazer upload de arquivos de dados na tabela editável |
| Mostrar permissão de histórico | Quais funções têm permissão para visualizar o histórico de alterações da tabela |
| Permissão para excluir todas as linhas | Quais funções podem excluir todas as linhas da tabela editável (quando ativada) |

## Passos

## Opção A: Configurar permissões básicas baseadas em funções

1. No **Explorador** de Projetos, acesse o relatório que contém a tabela editável.
2. Dê uma olhada no relatório.
3. Na tabela editável exibida no relatório, abra as **Propriedades avançadas** da tabela (clique com o botão direito do mouse > Propriedades > Avançado).
4. Configure as seguintes permissões conforme necessário:
   - **Permissão para fazer upload:** Selecione as funções que podem fazer upload de dados
   - **Permissão para exibir histórico:** Selecione as funções que podem visualizar o histórico de alterações
   - **Permissão para excluir todas as linhas:** Selecione as funções que podem realizar a exclusão em massa (se habilitada)
5. Clique em **Aplicar** para salvar suas alterações.
6. Confira o relatório.

## Opção B: Configurar acesso avançado a usuários/tabelas (Componente de upload de tabelas)

Para um controle detalhado sobre quais usuários podem acessar quais tabelas por meio de um componente de upload de tabelas nos relatórios:

1. Crie uma tabela editável para definir mapeamentos de acesso com as seguintes colunas:
   - **Tabela:** O nome da tabela editável
   - **Função:** (Opcional) A função que tem acesso
   - **Usuário:** (Opcional) O endereço de e-mail específico do usuário que tem acesso
2. Preencha a tabela de mapeamento de acesso. Por exemplo:

   |  |  |  |
   | --- | --- | --- |
   | **Tabela** | **Função** | **Usuário** |
   | Contratos Acme | Usuário avançado |  |
   | Contabilidade Geral da Acme |  | bob@acme.com |
   | Mapeamento da Estrutura Organizacional da Acme IT |  | roxanne@acme.com |
3. No seu relatório, adicione o componente “**Carregamento de tabela** ”.
4. Clique no botão **"Config"** no componente "Carregamento de tabela".
5. Altere o **tipo de configuração** para “**Avançado** ”.
6. No campo **Tabela**, insira o nome da sua tabela editável de mapeamento de acesso.
7. Clique em **Aplicar** e salve o relatório.

Agora, os usuários verão apenas as tabelas às quais têm acesso no menu suspenso “Carregamento de tabelas”.

## Opção C: Aplicar segurança no nível da linha a tabelas editáveis

Para casos em que os usuários devem ver e editar apenas suas próprias linhas em uma tabela editável (por exemplo, gerentes de centro de custo editando os dados de seus próprios centros de custo):

1. Configure as tabelas de mapeamento do RLS conforme descrito na seção anterior (“Implementar a segurança no nível da linha”).
2. Habilite o RLS na tabela editável adicionando uma etapa de RLS no pipeline de transformação.
3. Quando os usuários acessarem a tabela editável por meio de um relatório, eles verão apenas as linhas que correspondem às suas permissões RLS.
4. Os usuários só podem editar células nas linhas que conseguem ver.

Importante: Quando um usuário publica uma tabela editável filtrada pelo RLS, as linhas ocultas são mantidas. A operação de publicação não exclui linhas que o usuário não consegue visualizar.

## Resultados esperados

- Os usuários veem apenas as tabelas editáveis às quais têm permissão de acesso
- As funções de upload, histórico e exclusão estão disponíveis apenas para funções autorizadas
- Com o RLS ativado, os usuários visualizam e editam apenas as linhas para as quais têm autorização
- A publicação preserva as linhas ocultadas pelo RLS

## Armadilhas comuns

- **Conflitos de edição simultânea:** quando o usuário A começa a editar uma célula, o usuário B fica impedido de acessá-la até que A salve ou cancele a edição. Planeje os horários de inserção de dados para equipes distribuídas, a fim de minimizar conflitos.
- **Erros de validação que impedem a publicação:** dados inválidos (regras de validação não atendidas) não podem ser publicados. Certifique-se de que os usuários compreendam os requisitos de validação antes da inserção dos dados.
- **Exclusão de linhas de tabelas enriquecidas:** os usuários não podem excluir linhas de tabelas editáveis enriquecidas, pois essas linhas são baseadas na tabela de transformação de origem.

## Tarefas relacionadas

- [Criar tabelas editáveis](../work-with-data/create-blank-et.html)
- [Configurar regras de validação para tabelas editáveis](../work-with-data/config-dd-valid.html)
- [Configurar agendas de publicação de tabelas editáveis](../work-with-data/setup-et-publish.html)

**Tópico principal:** [Controle de acesso](../../../../studio/new-uc/howtoguides/manage-users-permission/access-control-intro.html)
