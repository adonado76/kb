---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Guia prático 1: Como aplicar segurança no nível da linha às tabelas"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Trabalhar com dados"
  - "Segurança de dados"
source_path: "studio/new-uc/howtoguides/work-with-data/htg-arls.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Guia prático 1: Como aplicar segurança no nível da linha às tabelas

## Objetivo

Configure a segurança por linha em uma tabela de transformação para que os usuários vejam apenas as linhas para as quais têm autorização.

## Quando usar

Quando for necessário restringir a visibilidade dos dados com base em limites organizacionais (por exemplo, unidade de negócios, centro de custo, região, departamento) ou ao implementar restrições de dados em ambientes multilocatários.

## Tempo estimado

30 a 45 minutos para a configuração inicial; 10 a 15 minutos para mesas adicionais

## Pré-requisitos

- Uma tabela de transformação que foi modelada (possui uma etapa de modelagem)
- Tabelas de mapeamento enviadas para o projeto de Segurança em Nível de Linha (consulte o Guia Prático 2)
- Permissões adequadas para editar tabelas e o projeto de segurança no nível da linha

## Passo 1: Acesse o projeto de segurança em nível de linha

1. Abra o menu **Configurações** (ícone de engrenagem na barra de navegação superior).
2. Clique em “**Configurar segurança no nível da linha** ”.
3. O projeto "Segurança em Nível de Linha" é iniciado. Este é um projeto específico que armazena todas as tabelas de mapeamento do seu domínio.

Dica: O projeto Row-Level Security é instalado automaticamente quando sua instância do Apptio é criada. Ele atende a todos os projetos do seu domínio, portanto, as tabelas de mapeamento criadas aqui podem ser utilizadas em vários projetos.

## Passo 2: Verifique se suas tabelas de mapeamento existem

Antes de configurar o RLS nas suas tabelas de dados, certifique-se de que as tabelas de mapeamento estejam definidas:

1. No projeto Segurança em Nível de Linha, acesse o **Explorador de Projetos**.
2. Localize sua(s) tabela(s) de mapeamento. Você deverá ver tabelas que contêm os IDs dos usuários e os itens aos quais cada usuário tem acesso.
3. Se as tabelas de mapeamento não existirem, consulte **o Guia Prático 2: Controlar o acesso com mapeamento de usuários** para criá-las antes de prosseguir.

Uma tabela de mapeamento típica para acesso por unidade de negócios pode ter a seguinte aparência:

|  |  |
| --- | --- |
| **ID de Usuário** | **Unidade de negócios** |
| bob@acme.com | BU 2 |
| rachel@acme.com | BU 1 |
| rachel@acme.com | BU 3 |
| tom@acme.com | BU 1 |

Observação: Rachel tem acesso a duas unidades de negócios, por isso ela aparece duas vezes na tabela de mapeamento.

## Passo 3: Abra a tabela para proteger

1. Acesse o projeto em que você está trabalhando (não o projeto de Segurança por Linha).
2. No **Explorador** de Projetos, localize a tabela que você deseja proteger.
3. Verifique a tabela, caso ainda não tenha sido verificada.
4. Clique duas vezes para abrir a tabela no editor de transformação.

## Etapa 4: Inserir uma etapa de segurança no nível da linha

1. No painel do pipeline de transformação (lado esquerdo), clique com o botão direito do mouse no local onde deseja adicionar a etapa RLS.
2. Selecione **Inserir etapa** > **Segurança no nível da linha**.
3. O painel de configuração da Segurança por Linha é exibido.

Dica: Ao adicionar uma etapa de segurança no nível da linha, uma etapa de modelo será adicionada automaticamente, caso ainda não exista. Apenas as tabelas modeladas e as tabelas editáveis podem ter a segurança no nível da linha aplicada a elas.

## Passo 5: Configurar o filtro de segurança

O filtro RLS possui quatro campos que definem a regra de segurança. Configure cada campo da seguinte forma:

1. **Primeiro campo (Coluna a filtrar):** Selecione a coluna da sua tabela de dados que contém os valores a serem filtrados. Por exemplo, se você estiver filtrando por unidade de negócios, selecione a coluna "BU" ou "Unidade de Negócios".
2. **Segundo campo (intersecções):** Selecione a tabela de mapeamento do projeto de Segurança em Nível de Linha que define as permissões de acesso dos usuários.
3. **Terceiro campo (coluna Item):** Selecione a coluna na tabela de mapeamento que contém os valores que os usuários têm permissão para visualizar (por exemplo, a coluna “Unidade de Negócios” na tabela de mapeamento).
4. **Quarto campo (onde está o usuário):** Selecione a coluna na tabela de mapeamento que contém os IDs dos usuários (por exemplo, “ID do usuário” ou “E-mail”).

Essa configuração cria uma regra: *"Mostrar linhas nas quais o valor da [Coluna] da tabela de dados corresponda à [Coluna Item] da tabela de mapeamento para o ID do usuário atual na [Coluna ID do usuário]."*

## Passo 6: Adicionar regras adicionais (opcional)

Pode ser necessário definir várias regras para lidar com diferentes cenários de acesso. Por exemplo, talvez você queira que determinados usuários (como diretores financeiros) tenham acesso a todos os dados, independentemente da unidade de negócios.

1. Clique em **“Adicionar entrada”** para criar uma regra adicional.
2. Configure a nova entrada seguindo o mesmo padrão de quatro campos.
3. As entradas múltiplas utilizam a lógica **OR** : se qualquer entrada for verdadeira para um usuário, ele verá a linha.

**Exemplo:** Para permitir que os usuários com "acesso total" tenham visibilidade de todas as linhas, crie uma segunda tabela de mapeamento (por exemplo, "BU Acesso Total") com o indicador "É administrador" definido como "Sim" para esses usuários. Adicione uma coluna de fórmula à sua tabela de dados com o valor "Sim" e, em seguida, crie uma entrada RLS que associe essa coluna à coluna "É administrador", na qual o usuário aparece na tabela de Acesso Total.

## Passo 7: Teste a configuração de segurança

Antes de salvar, verifique se a configuração do RLS está funcionando corretamente:

1. Na etapa RLS, localize o campo “**Filtrar pré-visualização** ”.
2. Digite o endereço de e-mail de um usuário (por exemplo, " bob@acme.com ") para ver quais dados ele teria acesso.
3. Verifique o painel de visualização para confirmar se apenas as linhas esperadas aparecem.
4. Teste vários usuários, incluindo usuários com acesso restrito, usuários com várias autorizações de acesso e (se configurado) usuários com acesso total.

Dica: O recurso de representação é útil para testes em relatórios. Você pode visualizar o relatório na perspectiva de um usuário específico para verificar se o RLS está funcionando corretamente.

## Passo 8: Salvar e fazer o check-in

1. Clique em **Salvar** para salvar as alterações na tabela.
2. Verifique a tabela para disponibilizar a configuração do RLS nos ambientes de teste e produção.

## Resultados esperados

- A tabela agora apresenta uma etapa RLS visível no fluxo de transformação.
- Os usuários que visualizam relatórios que incluem essa tabela veem apenas as linhas que correspondem às suas permissões de acesso.
- As agregações nos relatórios (somas, contagens, médias) refletem apenas os dados filtrados pelo usuário.
- O filtro de pré-visualização mostra o subconjunto de dados esperado para cada usuário de teste.

## Problemas comuns e solução de problemas

**O usuário não vê nenhum dado:**

- Verifique se o ID do usuário na tabela de mapeamento corresponde exatamente ao e-mail de login do usuário (distingue maiúsculas de minúsculas).
- Verifique se os valores na coluna “item” da tabela de mapeamento correspondem exatamente aos valores da sua tabela de dados.

**O usuário vê todos os dados (sem filtragem):**

- Verifique se a tabela possui uma etapa "Modelo". O RLS só funciona em tabelas modeladas.
- Verifique se a etapa RLS está configurada corretamente e se todos os quatro campos estão preenchidos.

**RLS não aplicado às tabelas relacionadas:**

- Lembre-se de que o RLS não é herdado. Cada tabela que exija segurança deve ter seu próprio nível de RLS configurado.

**Tópico principal:** [Segurança de dados](../../../../studio/new-uc/howtoguides/work-with-data/data-security.html)
