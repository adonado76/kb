---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Guia prático 2: Controle de acesso com mapeamento de usuários"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Trabalhar com dados"
  - "Segurança de dados"
source_path: "studio/new-uc/howtoguides/work-with-data/htg-cacc.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Guia prático 2: Controle de acesso com mapeamento de usuários

## Objetivo

Crie e gerencie tabelas de mapeamento que definem quais usuários podem acessar quais dados, permitindo controles de segurança granulares no nível da linha.

## Quando usar

Antes de implementar o RLS em qualquer tabela de dados. Utilize também ao adicionar novos usuários ao sistema, quando houver mudanças nas estruturas organizacionais ou ao implementar diferentes níveis de acesso (por exemplo, acesso regional versus global).

## Tempo estimado

20 a 30 minutos para a configuração inicial; 5 a 10 minutos para as atualizações

## Pré-requisitos

- Acesso ao projeto Segurança em Nível de Linha
- Lista de usuários e suas permissões de acesso
- Compreensão das dimensões de dados que você deseja filtrar (por exemplo, unidades de negócios, centros de custo)

## Passo 1: Planeje a estrutura da sua tabela de mapeamento

Antes de criar tabelas, planeje sua estratégia de controle de acesso:

- **Identifique o critério de filtragem:** em qual(is) coluna(s) dos seus dados você vai filtrar? Exemplos comuns: Unidade de Negócios, Centro de Custos, Região, Departamento.
- **Determinar os padrões de acesso:** alguns usuários terão acesso restrito, enquanto outros terão acesso total? Algum usuário precisa ter acesso a vários valores?
- **Decida como organizar as tabelas:** pode ser necessário criar várias tabelas de mapeamento para diferentes cenários de acesso (por exemplo, uma para usuários padrão e outra para usuários com “acesso total”).

Uma tabela de mapeamento requer apenas duas colunas:

|  |  |  |
| --- | --- | --- |
| **Coluna** | **Descrição** | **Exemplo** |
| ID de Usuário | O e-mail de login do usuário. Deve corresponder exatamente ao nome de usuário na tabela Usuários. | bob@acme.com |
| Item | O valor ao qual o usuário tem acesso, tal como aparece nas suas tabelas de dados. | BU 2 |

Dica: você não precisa se preocupar com o nome da tabela ou dos nomes das colunas nesta fase. Ao configurar os filtros RLS, você selecionará a tabela e as colunas apropriadas nos menus suspensos.

## Passo 2: Crie seu arquivo de tabela de mapeamento

Prepare sua tabela de mapeamento como um arquivo do CSV ou Excel fora do TBM Studio:

1. Abra seu aplicativo de planilha (Excel, Planilhas Google, etc.).
2. Crie colunas para o ID do usuário e os itens aos quais os usuários têm acesso.
3. Insira uma linha para cada mapeamento entre usuário e item. Se um usuário tiver acesso a vários itens, inclua várias linhas para esse usuário.
4. Salve o arquivo no formato d CSV ou Excel.

**Exemplo: Tabela de acesso padrão da unidade de negócios**

|  |  |
| --- | --- |
| **ID de Usuário** | **Unidade de Negócios** |
| bob@acme.com | BU 2 |
| rachel@acme.com | BU 1 |
| rachel@acme.com | BU 3 |
| tom@acme.com | BU 1 |
| tom@acme.com | BU 2 |
| tom@acme.com | BU 3 |

*Neste exemplo, Bob vê apenas os dados da BU 2, Rachel vê os da BU 1 e da BU 3, e Tom vê os dados das três unidades de negócios.*

**Exemplo: Tabela de acesso total (para usuários que devem ter acesso a tudo)**

|  |  |
| --- | --- |
| **ID de Usuário** | **É o administrador** |
| sally@acme.com | Sim |
| director@acme.com | Sim |

*Esta tabela separada é utilizada com a lógica OR nos filtros RLS para conceder acesso total sem a necessidade de listar todos os valores possíveis de BU.*

## Etapa 3: Carregar a tabela de mapeamento no projeto RLS

1. Abra o menu **Configurações** e clique em **Configurar segurança no nível da linha**.
2. No projeto Segurança em Nível de Linha, clique em **Novo** > **Tabela**.
3. Digite um nome descritivo para a tabela (por exemplo, “Acesso à Unidade de Negócios” ou “Permissões do Centro de Custos”).
4. Selecione **“Carregar arquivo”** e escolha o arquivo do tipo “ CSV ” ou Excel que você preparou.
5. Verifique a detecção de colunas. Certifique-se de que as colunas “ID do usuário” e “Item” estejam corretamente identificadas.
6. Clique em **Criar** para enviar a tabela.

## Passo 4: Verifique o envio

1. Abra a tabela carregada no Explorador de Projetos.
2. Verifique os dados para garantir que todos os IDs de usuário e itens estejam corretos.
3. Verifique se os tipos de dados das colunas estão corretos (normalmente, Etiqueta/Texto para ambas as colunas).
4. Marque a tabela para disponibilizá-la para a configuração do RLS.

## Alternativa: Carregar tabelas de mapeamento através de DataLink

Para organizações com muitos usuários ou alterações frequentes de permissões, é possível automatizar as atualizações da tabela de mapeamento usando o DataLink (versão clássica):

1. Acesse sua instância do DataLink (Clássico).
2. Selecione o agente e o conector desejados.
3. Na seção "**Projeto** ", digite "Usuários" para selecionar o projeto "Segurança em nível de linha".
4. Conclua a configuração da mesma forma que faria para qualquer execução do ` DataLink `.

## Passo 5: Atualizar as tabelas de mapeamento quando houver alterações no Access

As permissões de acesso dos usuários mudam com o tempo. Veja como fazer a manutenção das suas tabelas de mapeamento:

**Adicionar um novo usuário:**

- Adicione uma ou mais novas linhas à tabela de mapeamento com o e-mail do usuário e os itens autorizados.
- Se estiver usando o envio de arquivos, reenvie o arquivo completo e atualizado.

**Alterar o acesso de um usuário:** modifique as linhas correspondentes a esse usuário (adicione novas linhas de itens e remova as antigas) e faça o upload novamente.

**Remover o acesso de um usuário:** Remova todas as linhas desse usuário da tabela de mapeamento.

## Resultados esperados

- As tabelas de mapeamento aparecem no Explorador de Projetos do projeto de Segurança em Nível de Linha.
- As tabelas contêm mapeamentos precisos entre usuários e itens.
- As tabelas estão disponíveis para seleção ao configurar etapas do RLS em tabelas de dados.

## Problemas comuns e solução de problemas

**Incompatibilidade de ID de usuário:** os IDs de usuário devem corresponder exatamente aos nomes de usuário na tabela Usuários. Verifique se há erros ortográficos, espaços em excesso ou diferenças de maiúsculas e minúsculas.

**Inconsistência nos valores dos itens:** os valores dos itens devem corresponder exatamente aos valores nas suas tabelas de dados. Se seus dados contiverem “Unidade de Negócios 1”, mas a tabela de mapeamento tiver “BU 1”, o RLS não funcionará corretamente.

**Usuários com acesso total ausentes:** Se você adicionar novos itens (por exemplo, uma nova unidade de negócios), os usuários aos quais foi concedido acesso por meio da tabela de mapeamento padrão não verão automaticamente os novos dados, a menos que você atualize suas entradas. Considere usar uma tabela separada com "acesso total" para usuários que devem ter acesso a todos os dados em todos os momentos.

**Tópico principal:** [Segurança de dados](../../../../studio/new-uc/howtoguides/work-with-data/data-security.html)
