---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Compilação e implantação"
breadcrumb:
  - "TBM Studio"
  - "Administração"
source_path: "studio/new-uc/admin/build-deploy.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Compilação e implantação

**Tipo de conteúdo:** Conceitual / Guia prático

**Público-alvo:** Administradores, usuários avançados

**Pré-requisitos:** Conhecimento dos ambientes de desenvolvimento, teste e produção

O ciclo de vida de compilação e implantação no TBM Studio gerencia o fluxo das alterações desde o desenvolvimento, passando pela fase de teste, até a produção. Compreender esse ciclo de vida é essencial para manter um ambiente de produção estável e, ao mesmo tempo, possibilitar o desenvolvimento iterativo.

## Compreendendo os ambientes

A TBM Studio utiliza três ambientes para gerenciar o fluxo das alterações, desde o desenvolvimento até os usuários finais.

|  |  |
| --- | --- |
| **Meio ambiente** | **Descrição** |
| **Desenvolvimento** | Onde são feitas as alterações de configuração. Os check-ins acionam cálculos de desenvolvimento que processam transformações e métricas. As alterações são validadas aqui antes de serem transferidas para o ambiente de teste. |
| **Preparação** | Ambiente de validação de pré-produção. Calcula os exercícios e gera relatórios após a conclusão do cálculo de desenvolvimento. Utilizado para verificar as alterações antes de implementá-las na produção. |
| **Produção** | Ambiente de produção ao qual os usuários corporativos têm acesso. As alterações só chegam ao ambiente de produção por meio de uma promoção explícita a partir do ambiente de teste. A promoção é quase instantânea. |

## Fluxo de trabalho de check-out e check-in

No TBM Studio, todos os elementos (tabelas, métricas, perspectivas, modelos) são documentos que devem ser retirados para edição. Quando você faz o check-out de um documento, ele fica bloqueado para que outras pessoas não possam editá-lo ao mesmo tempo.

**Para retirar um documento:**

- Selecione o documento no Explorador de Projetos
- Na guia Página inicial, no grupo Documento, clique **em Retirar**
- Aparece um ícone de check-out ao lado do nome do documento, e o nome é exibido em laranja

## Melhores práticas para o check-in:

- Revise os dados antes de enviá-los para verificar o conteúdo e a formatação
- Clique em “Salvar” após modificar qualquer documento
- Resolva todos os erros antes de fazer o check-in
- Valide os relatórios que utilizam os dados modificados
- Coordene as atualizações com os membros da equipe para evitar cálculos em fila

**Dica:** *Estabeleça uma política de contato diário da equipe para coordenar o contato uma ou duas vezes por dia (por exemplo, na hora do almoço e no final do dia). Isso reduz os conflitos na fila de cálculos e garante que todos vejam os mesmos dados.*

## Monitoramento da fila de cálculos

A Fila de Cálculos mostra o status das compilações em todos os ambientes. Use-o para acompanhar o andamento dos cálculos, identificar compilações na fila e visualizar o histórico de cálculos.

**Para acessar a fila de cálculos:**

- Vá para **Compilação > Fila de cálculos**

**Indicadores de status da compilação:**

- **Em espera** - A compilação está na fila e aguardando processamento
- **Calculando** - Compilação em andamento (mostra cálculos concluídos em relação ao total)
- **Concluído** - A compilação foi concluída (mostra o tempo decorrido desde a conclusão e a duração)

## Bloquear e enviar para produção

Para implementar as alterações na produção, você deve primeiro bloquear o ambiente de teste para impedir novas alterações e, em seguida, promover a compilação do ambiente de teste para a produção.

**Para enviar para produção:**

- Certifique-se de que todos os cálculos de preparação pendentes estejam concluídos
- Vá até **Build > Lock** para bloquear o ambiente de teste
- Clique em **“Promover agora”** para implementar em produção
- Verificar os relatórios na produção após a implementação

**Observação:** *A migração para o ambiente de produção no TBM Studio R12 é praticamente instantânea. Os usuários verão os dados atualizados assim que a promoção for concluída.*

## Trabalhando com ramificações

A ramificação cria uma cópia completa do seu projeto, permitindo o desenvolvimento paralelo sem afetar o projeto principal (trunk). Os ramos são úteis para alterações de configuração de longa duração, correções de emergência e arquivamento de estados anteriores.

**Quando usar branches:**

- **Configuração de longa duração** — Grandes alterações que levam semanas para serem concluídas, enquanto o carregamento de dados operacionais continua no tronco
- **Produção de hotfixes** - Corrija problemas de produção sem interromper o trabalho de desenvolvimento em andamento
- **Arquivar estados anteriores** - Preservar e acessar estados históricos do projeto (por exemplo, exercícios fiscais anteriores)

**Limitações da filial:**

- Máximo de 5 ramificações por ambiente
- Cada ramificação utiliza os mesmos recursos que o projeto principal
- Os cálculos das ramificações são colocados na fila junto com os cálculos do tronco (exceto ramificações de hotfix)
- Um branch não pode ser fechado se sua compilação estiver em uso na produção

**Dica:** *Para melhorar o desempenho da ramificação, defina o período de tempo adequado, ajustando as datas de início e término do projeto para incluir apenas os períodos necessários. Isso reduz significativamente o tempo de cálculo.*

## Reverter alterações

O recurso de reversão permite restaurar um projeto para um estado de configuração anterior. Use o recurso de reversão quando uma alteração confirmada causar problemas que precisem ser rapidamente revertidos.

**Aviso:** *a reversão é uma operação de grande importância. Todos os check-ins realizados após o ponto selecionado serão descartados. Certifique-se de compreender o impacto antes de prosseguir e considere usar um branch para preservar o trabalho, se necessário.*

**Para reverter uma configuração:**

- Vá para **Compilação > Histórico de check-ins**
- Clique com o botão direito do mouse no check-in que deseja restaurar e selecione **"Reverter para"**
- Insira um motivo descritivo para a reversão
- Clique em **"Reverter o check-in"**
- Após a conclusão da reversão, atualize as áreas de trabalho clicando em **Página inicial > Atualizar área de trabalho**

## Promoções programadas e recorrentes

O TBM Studio oferece suporte a promoções programadas para fluxos de trabalho de implantação automatizados. Você pode configurar atualizações e promoções recorrentes para automatizar a implementação de dados editáveis em tabelas e outras alterações.

**Para configurar promoções programadas:**

- Vá até **Compilação > Opções de promoção**
- Configure **as atualizações recorrentes** para definir a programação das compilações de teste
- Configure **promoções recorrentes** para automatizar a implantação em produção
