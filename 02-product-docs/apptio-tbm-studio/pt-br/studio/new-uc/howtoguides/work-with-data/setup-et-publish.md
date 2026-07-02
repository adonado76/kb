---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Configurar a publicação de tabelas editáveis"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Trabalhar com dados"
  - "Entrada manual de dados"
source_path: "studio/new-uc/howtoguides/work-with-data/setup-et-publish.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configurar a publicação de tabelas editáveis

**Objetivo:** Configurar como os dados inseridos pelo usuário nas tabelas editáveis são transferidos para as tabelas de transformação e, por fim, para o seu modelo de custos, incluindo publicações manuais, programadas e automatizadas.

**Quando usar**

- Depois de criar tabelas editáveis que precisam alimentar tabelas de transformação
- Ao definir intervalos de atualização automática de dados
- Para cenários de previsão ou planejamento colaborativo
- Para permitir que os usuários da área de negócios atualizem os dados de entrada do modelo sem a intervenção do departamento de TI

**Por que isso é importante** : as tabelas editáveis existem fora do fluxo de transformação padrão. A publicação transfere os dados inseridos pelo usuário para tabelas de transformação, onde podem ser utilizados em cálculos e alocações. Sem uma configuração de publicação adequada, as atualizações feitas pelos usuários permanecem isoladas e não afetam o modelo.

## Pré-requisitos

- Uma tabela editável (em branco ou preenchida) já criada com colunas definidas
- Compreensão de quando os dados devem ser atualizados (conforme necessidade, diariamente, semanalmente, mensalmente)
- Saber quais períodos exigem dados
- Permissões de administrador ou criador para agendamento

## Tempo estimado

15 a 25 minutos

## R. Crie uma tabela de transformação a partir da sua tabela editável

1. **Criar a tabela de transformação**
   - Acesse **Data Studio**
   - Na guia **Página inicial**, selecione **Novo > Tabela**
   - Digite um nome para a tabela de transformação (por exemplo, "Transformação de categorias de fornecedores")
   - Clique **em OK**
2. **Selecione “Tabela editável” como fonte**
   - Na janela pop-up “**Criar tabela** ”, selecione o bloco **“Tabela editável”**
   - No menu suspenso “**Tabela editável** ”, selecione o nome da sua tabela editável
3. **Escolha o método de publicação inicial**
   - **Método de envio:** Selecione **“Substituir”** (as novas publicações substituem completamente os dados existentes — opção mais comum)
   - Selecione uma **programação de publicação recorrente** no menu suspenso ou use "Padrão - Sem atualização recorrente"
   - Clique **em OK**
4. **Salvar e fazer o check-in**
   - Clique em **“Salvar”** na guia **“Página inicial”**
   - Clique em **"Fazer check-in"**

## B. Publicar manualmente a partir do TBM Studio

Use este método quando quiser controlar exatamente quando os dados são atualizados.

1. **Acesse sua tabela de transformação**
   - No **Project Explorer**, localize a tabela de transformação derivada da sua tabela editável
   - Consulte a tabela, se necessário
2. **Acesse a etapa “Tabela editável”**
   - Clique em **Etapas > Tabela editável** no pipeline
   - Você verá marcadores de tempo para cada período definido no seu projeto
3. **Publicar por um período específico**
   - Clique com o botão direito do mouse no período que deseja atualizar (por exemplo, “janeiro de 2025”)
   - Selecione **“Atualizar este período”**
   - O sistema publica os dados atuais da tabela editável referentes a esse período
4. **Verifique e faça o check-in**
   - Clique na etapa **“Tabela”** e verifique se os dados aparecem corretamente
   - Clique em **"Fazer check-in"**

## C. Publicar manualmente a partir de relatórios

Os usuários com permissões adequadas podem publicar alterações em tabelas editáveis diretamente a partir dos relatórios.

**Pré-requisitos:** O usuário precisa ter **acesso ao ambiente de desenvolvimento** e **ao ambiente de teste** (não é necessário ter acesso ao TBM Studio ou acesso de administrador).

**Fluxo de trabalho do usuário:**

1. Abra um relatório que contenha a tabela editável
2. Faça as alterações desejadas nos dados
3. Clique em **Salvar** para salvar as alterações na tabela editável
4. Clique em **“Publicar”** na parte inferior do relatório
5. Confirme a ação de publicação na janela pop-up de aviso
6. Insira uma descrição na janela modal **de check-in**
7. Clique em **"Fazer check-in"**

Importante: Ao publicar a partir de um relatório, TODAS as alterações editáveis na tabela são publicadas, e não apenas as linhas visíveis na visualização atual do relatório. Se vários usuários estiverem editando seções diferentes, a publicação feita por um usuário atualiza todas as alterações.

## D. Configurar agendas de publicação automática

A publicação automática permite atualizações regulares e automáticas dos dados.

1. **Ativar o recurso de publicação recorrente** (se ainda não estiver ativado)
   - Acesse a guia **Projeto** > **Ativar recursos** ( 12.11.7 ) ou **Configurações do projeto** ( 12.11.8 +)
   - Selecione **“Ativar publicação recorrente” para as tabelas de transformação**
   - Clique **em OK**
2. **Acessar a configuração de publicação recorrente**
   - Vá até a guia "**Build** " > **"Publicação recorrente"**
   - Você verá duas guias: **“Transformar tabela”** e **“Agendamentos recorrentes”**
3. **Criar uma nova programação**
   - Selecione a guia **“Agendamentos recorrentes”**
   - Clique **em “Adicionar programação”**
4. **Configurar as definições da programação**
   - **Nome da programação:** Insira um nome descritivo (por exemplo, “Mapeamento de mão de obra – Diário”)
   - **Recorrência:** Selecione a frequência (a cada hora, diariamente, semanalmente ou mensalmente)
   - **Período de publicação:** Selecione o período para o qual os dados serão publicados (Mês atual, Mês anterior, Período específico, etc.)
   - **Ativar:** marque esta opção para ativar a programação
   - **Promover automaticamente para produção** ( 12.11.10 +): Marque esta opção para promover automaticamente os dados publicados para a produção
5. **Salvar e atribuir a programação**
   - Clique **em Salvar**
   - Vá para a guia **“Transformar tabela”**
   - Localize sua tabela de conversão e atribua a nova programação

## Resultados esperados

Após configurar a publicação:

- **Publicação manual:** os dados da tabela editável são transferidos para as tabelas de transformação quando você aciona explicitamente a publicação
- **Publicação baseada em relatórios:** os usuários corporativos podem atualizar os dados de entrada do modelo sem precisar acessar o Studio
- **Publicação programada:** os dados são atualizados automaticamente em intervalos definidos
- **Promoção automática** (se ativada): transfere o fluxo para a produção sem intervenção manual

## Armadilhas comuns

|  |  |
| --- | --- |
| **Problema** | **Solução** |
| **Os dados publicados não aparecem na tabela de transformação** | Verifique se o período que você está visualizando corresponde ao período em que você publicou. Marque tanto a tabela editável quanto a tabela de transformação. Certifique-se de que não haja erros nos dados da tabela editável. |
| **A programação não está funcionando como esperado** | Verifique se a caixa de seleção “Ativar” está marcada na programação. Verifique a data e a hora da última publicação — se aparecer “Inicial”, a programação ainda não foi executada. Verifique se a hora de início e o fuso horário estão corretos. |
| **A edição simultânea por vários usuários causa a sobrescrita de dados** | Esse é o comportamento esperado — a última publicação prevalece. Implementar a gestão: atribuir diferentes usuários a diferentes seções. Utilize a segurança no nível da linha para distribuir as responsabilidades de edição. |
| **A promoção automática envia dados incorretos para o ambiente de produção** | Desativar a promoção automática para tabelas que exigem validação manual. Implemente regras de validação de dados para detectar erros antes da publicação. |

## O que vem a seguir

Após configurar a publicação:

- [Criar relatórios para entrada de dados](../create-reports/report-basic.html)
- [Aplicar segurança no nível da linha](htg-arls.html)
- [Integrar com o modelo de custos](../build-cost-model/model-basics.html)
- Configurar a governança de promoções (Seção 6.1 )

**Tópico principal:** [Entrada manual de dados](../../../../studio/new-uc/howtoguides/work-with-data/manual-data-entry.html)
