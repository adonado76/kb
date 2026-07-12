---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "data-sharing"
title: "Publicação do plano de programação"
breadcrumb: []
source_path: "data-sharing/scheduling-the-data-shares.html"
images:
  - "resources/images/icons/icon-delete.png"
  - "resources/images/icons/icon_details.png"
  - "resources/images/icons/pencil-icon.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Publicação do plano de programação

## Capacidade de agendamento do ADM

Um recurso de agendamento em Automated Data Management (ADM) foi criado para automatizar o compartilhamento de dados entre :

- Apptio Planning dados de planos (orçamento e previsão) em Apptio Costing
- Cloudability em Apptio Costing.

Esse recurso permitirá opções flexíveis para agendar trabalhos para publicar dados do Plano e do Cloudability no Apptio Costing e um local centralizado para gerenciar o compartilhamento de dados entre o portfólio de produtos do Apptio.

Os usuários administradores agora podem criar cronogramas diários, semanais e mensais usando a integração Automated Data Management para publicar dados do Plano e Cloudability de qualquer plano ativo em estado Novo, Aberto ou Final para Apptio Costing (Transparência de custos). Além disso, eles também podem selecionar o período específico em Apptio Costing para o qual os dados devem ser publicados.

![Capacidade do Sceduler](../resources/images/data%20sharing_images/adm-scheduler-capability.png)

## Pré-requisito

- O IT Planning, Automated Data Management e o TBM Studio devem estar no mesmo ambiente.

  ![Planejamento de TI, Automated Data Management, TBM Studio](../resources/images/data%20sharing_images/same-env.png)
- Certifique-se de que a permissão DataOrchestrationServiceFeatureFullAccess esteja ativada na função que gerenciará as programações do Automated Data Management . Por padrão, as funções Admin, Apptio Admin e Apptio Partner têm essa permissão ativada.
- [Conexão](data_sharing_connections.html) com o projeto TBM Studio estabelecida em Automated Data Management
- Automated Data Management deve ser ativado em Apptio Planning
- Apptio Planning [as entidades](data_sharing_entity_mapping.html) são criadas e configuradas em Automated Data Management

  ![Pré-requisito](../resources/images/data%20sharing_images/adm-prerequisite1.png)

  ![Pré-requisito](../resources/images/data%20sharing_images/adm-prerequisite2.png)

Nota:

Consulte o [guia de configuração do ADM](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=costing-configure-automated-data-management "(Abre em uma nova guia ou janela)") para configurar a integração entre Apptio Costing e Apptio
Planning.

## Configuração do planejamento para o cálculo de custos

Navegue até a página Cronograma da entidade para criar, editar ou excluir cronogramas para publicar um plano no cálculo de custos. O processo de criação de programação gera vários trabalhos com base nas entidades selecionadas e aplica a mesma configuração de programação para cada tipo/entidade de item de planejamento. No entanto, o usuário tem a flexibilidade de gerenciar as publicações no cálculo de custos separadamente para cada tipo de entidade/item de linha, se necessário.

Automated Data Management mantém o mapeamento 1:1 entre o tipo de item de linha Apptio Planning e a entidade Automated Data
Management para o nome do conjunto de dados em Apptio Costing. O nome do conjunto de dados pode ser alterado em Automated Data Management com base na configuração dos clientes.

Observação: os acionadores manuais estão disponíveis para publicações adhoc de dados do plano e do site Cloudability para o cálculo de custos.

| **Entidade ADM** | **Apptio Planning Tipo de item** | **Apptio Costing Nome padrão do conjunto de dados** | Gatilho manual |
| --- | --- | --- | --- |
| Orçamento financeiro | Tipo de item de linha financeira em um tipo de plano de orçamento | Apptio PlanningF Orçamento | Plano > Despesas > guia Resumo > Ações > Publicar finanças na transparência de custos... |
| Orçamento trabalhista | Tipo de item de linha de trabalho em um tipo de plano de orçamento | Apptio PlanningF Orçamento trabalhista | Plano > Despesas > guia Mão de obra > Ações > Publicar mão de obra na transparência de custos... |
| Orçamento de ativos | Linha de imobilizado Tipo de item em um tipo de plano de orçamento | Apptio PlanningF Orçamento de ativos | Plano > Despesas > guia Ativos > Ações > Publicar ativos na transparência de custos... |
| Orçamento do contrato | Tipo de item de linha de contrato em um tipo de plano de orçamento | Apptio PlanningF Orçamento do contrato | Plano > Despesas > guia Contratos > Ações > Publicar contratos na transparência de custos... |
| Orçamento de atividades trabalhistas | Tipo de item da linha Atividade de trabalho em um tipo de plano de orçamento | Apptio PlanningF Orçamento de atividades trabalhistas | Plano > Despesas > guia Atividade de mão de obra > Ações > Publicar atividade de mão de obra na transparência de custos... |
| Previsão financeira | Tipo de item de linha financeira em um tipo de plano de previsão | Apptio PlanningF Previsão financeira | Plano > Despesas > guia Resumo > Ações > Publicar finanças na transparência de custos... |
| Previsão de mão de obra | Linha de trabalho Tipo de item em um tipo de plano de previsão | Apptio PlanningF Previsão de mão de obra | Plano > Despesas > guia Mão de obra > Ações > Publicar mão de obra na transparência de custos... |
| Previsão de ativos | Tipo de item de linha do ativo em um tipo de plano de Previsão | Apptio PlanningF Previsão de ativos | Plano > Despesas > guia Ativos > Ações > Publicar ativos na transparência de custos... |
| Previsão de contratos | Tipo de item de linha do contrato em um tipo de plano de previsão | Apptio PlanningF Previsão de contrato | Plano > Despesas > guia Contratos > Ações > Publicar contratos na transparência de custos... |
| Previsão de atividade trabalhista | Tipo de item de linha Atividade de Trabalho em um tipo de plano de Previsão | Apptio PlanningF Previsão de atividade trabalhista | Plano > Despesas > guia Atividade de mão de obra > Ações > Publicar atividade de mão de obra na transparência de custos... |

## Criar cronograma para planejamento

1. Vá para **Enhanced Access Administration** e selecione **Automated Data Management**
2. Selecione **Entity Schedule** no painel esquerdo
3. Selecione **Add Schedule** ( ApptioOne Planning é selecionado por padrão na opção Producer)
4. Digite o nome do cronograma no campo **Nome do cronograma**

   ![Adicionar cronograma](../resources/images/data%20sharing_images/add-schedule1.png)
5. Selecione o **Plan Name (Nome do plano** ) no menu suspenso para criar a programação
6. Selecione as **entidades** que deseja criar o cronograma (dependendo do orçamento ou plano de previsão selecionado, as entidades disponíveis serão atualizadas)

   ![Adicionar cronograma](../resources/images/data%20sharing_images/add-schedule2.png)
7. Defina o período de tempo no CT que você deseja publicar
   - Mês atual: Esse valor dinâmico mudará à medida que você avançar no tempo. Eg.when Se o mês de julho for selecionado, os dados do plano e do site Cloudability serão publicados no mês de julho no TBM Studio.
   - Mês anterior: Esse valor dinâmico será alterado à medida que você avançar no tempo. Por exemplo, Se essa opção for escolhida, quando o mês atual for julho, os dados do Plano e do Cloudability serão publicados no TBM Studio para o mês de junho.
   - Mês inicial do ano fiscal: esse valor dinâmico mudará à medida que você avançar no tempo. Por exemplo, quando julho for definido como o início do ano fiscal, os dados do Plano e do site Cloudability serão publicados para o mês de julho em TBM Studio.
   - Personalizar: O plano será publicado no mês da data selecionada. Essa opção é usada quando o início do ano fiscal do plano é diferente do início do ano fiscal no TBM Studio
8. Selecione **Next (Avançar** ) para configurar a cadência da programação
9. Selecione o **Schedule Type** (diário, semanal ou mensal)
10. Selecione a **data de início** e a **data de término** da programação. Se **No End Date** for selecionado, o campo **End Date** será desativado
11. Defina a frequência para acionar o trabalho
    - Selecione uma ou várias vezes ao dia
    - Selecione uma ou várias vezes por semana
    - Selecione um ou vários dias do mês
12. Selecione **a hora** e **o fuso horário** para acionar o trabalho
13. Selecione **Criar cronograma**

## Editar planejamento

1. Vá para **Enhanced Access Administration** e **Automated Data Management**
2. Selecione o menu **Entity Schedule** no painel esquerdo
3. Selecione o ícone de lápis (![Editar ícone](../../../../03-media/apptio-planning/resources/images/icons/pencil-icon.png)) para editar a programação
4. Editar os detalhes do plano e da programação conforme necessário
5. Selecione **Salvar cronograma**

   ![Salvar cronograma](../resources/images/data%20sharing_images/edit-schedule-new.png)

## Excluir cronograma

1. Vá para **Enhanced Access Administration** e **Automated Data Management**
2. Selecione o menu **Entity Schedule** no painel esquerdo
3. Selecione o ícone de lápis (![Editar ícone](../../../../03-media/apptio-planning/resources/images/icons/pencil-icon.png)) para excluir a programação
4. Selecione o ícone Excluir (![Excluir ícone](../../../../03-media/apptio-planning/resources/images/icons/icon-delete.png)) e, em seguida, selecione **Excluir** na janela pop-up de confirmação

## Verificação de status

1. Vá para **Enhanced Access Administration** e **Automated Data Management**
2. Selecione o menu **Entity Schedule** no painel esquerdo
3. Selecione o ícone de notas (![Ícone de notas](../../../../03-media/apptio-planning/resources/images/icons/icon_details.png)) para ver os detalhes sobre *o status do Schedule* e *o Run History*

   ![Status do planejamento](../resources/images/data%20sharing_images/status-schedule.png)

## Criação de cronograma para Cloudability

1. Vá para **Enhanced Access Administration** e selecione **Automated Data Management**
2. Selecione **Cronograma da Entidade** > **Detalhes da Entidade** no menu à esquerda
3. Clique no botão **Add Schedule**.
4. Digite o **Schedule Name**.
5. Selecione o **tipo de agendamento** (diário, semanal ou mensal).

   Inserir

   | **Frequência** | **Melhor para** | **Exemplo de caso de uso** |
   | --- | --- | --- |
   | Diária | Monitoramento de custos em tempo real | FinOps equipes que acompanham as despesas diárias |
   | Semanal | Cadência regular de relatórios | Revisões semanais de custos com as partes interessadas |
   | Mensalmente | Acompanhamento do orçamento | Relatórios financeiros mensais |
   | Personalizado | Necessidades comerciais específicas | Alinhado com os ciclos de faturamento |
6. Selecione a **data de início** e a **data de término** da programação. Se **No End Date (Sem data de término** ) for selecionado, o campo **End Date (Data de término** ) será desativado.
7. Selecione os valores apropriados nos campos **Hora** e **Fuso horário** para acionar o trabalho.
8. Selecione **Next** para configurar a cadência da programação.
9. Clique no botão **Create Schedule**.

Observação: Algumas práticas recomendadas que devem ser levadas em conta durante o agendamento

- Defina a programação para horários fora do pico, de preferência no início da manhã.
- Certifique-se de que a programação esteja alinhada com seu fuso horário local.
- Permitir tempo suficiente para o processamento de dados antes do início das operações comerciais.

Importante: As restrições de sistema a seguir são aplicáveis:

- Só é permitido um agendamento ativo por ambiente.
- Cada fornecedor de nuvem pode ter apenas um plano de execução por programação.

**Tópico principal:** [Conectar-se ao Apptio Cálculo de custos](../it-planning/planning/adm/adm_capabilities.html "Apptio O planejamento integra-se ao Apptio cálculo de custos usando o ADM ( Data Management Automated Design Management). O ADM é um serviço de plataforma compartilhada projetado para fornecer uma experiência de troca de dados unificada, segura e escalável entre Apptio aplicativos.")
