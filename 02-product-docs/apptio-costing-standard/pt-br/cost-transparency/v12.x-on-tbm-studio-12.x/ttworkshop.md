---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Workshop de controle de horas"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/ttworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Workshop de controle de horas

## Preparação de seus dados de controle de tempo

1. Se ainda não tiver feito isso, carregue seus dados de controle de tempo, incluindo:
   - Lista de tarefas
   - Horas trabalhadas por funcionário
2. Seguindo as Apptio as práticas padrão, categorize cada conjunto de dados brutos na categoria de controle de tempo:
3. Se for o caso, aplique um filtro de data aos seus dados de controle de tempo:

## Sobre o identificador de controle de tempo

O identificador do objeto de controle de tempo é predefinido e não deve ser alterado. Ele inclui:

- Identificação do trabalho
- ID de Tarefa
- ID de Projeto

## Sobre as teclas de controle de tempo

As chaves do conjunto de dados mestre de controle de ponto são todas geradas pelo sistema e não devem ser alteradas.

| Chave | A chave de campo é baseada em | Lógica |
| --- | --- | --- |
| **Chave de controle de tempo de trabalho** | Identificação do trabalho | Anexar o texto Labor\_Time Tracking com o ID do trabalho |
| **Chave do projeto\_de controle de horas** | ID de Projeto | Anexar o texto Time Tracking\_Project com o ID do projeto |
| **Controle de horas\_IT Tower Key** | Torre de recursos de TI  Subtorre de recursos de TI | Anexar o texto Time Tracking\_IT Tower Key com IT Resource Tower e IT Resource Sub Tower |

Ao mapear o ID do funcionário para o ID do trabalho, o sistema fará automaticamente uma conexão entre os objetos de trabalho e de controle de horas. Quando essa conexão for estabelecida, o custo desse funcionário fluirá para o objeto de controle de horas, mas será mais granular, pois agora o funcionário será dividido com base nas atividades em relação às quais ele está registrando horas.

## Colunas computadas comuns necessárias para o controle de horas

Muitas vezes, não há uma única lista de tarefas e todos os metadados sobre essas tarefas. Talvez você precise extrair dados de um ou mais sistemas. Desde que o ID da tarefa seja o mesmo entre os vários sistemas, é possível usar a função LOOKUP para converter informações relacionadas à tarefa, como horas reais ou horas planejadas, em um único conjunto de dados (como a lista original de tarefas de um projeto).

## Mapear dados para dados mestre de controle de tempo

Mapeie seus dados de controle de tempo para o conjunto de dados mestre de controle de tempo. A maior parte do mapeamento deve ser autoexplicativa neste ponto. Não há requisitos incomuns de mapeamento. Em 12.7, agora você pode aproveitar a função Column Map em seu conjunto de dados brutos para mapear para os dados mestre de controle de tempo ([Map Columns](https://community.apptio.com/docs/DOC-10561 "(Abre em uma nova guia ou janela)") )

## Revisar o objeto de controle de tempo nos modelos

| Modelo | Ações |
| --- | --- |
| Custo | Certifique-se de que os valores estejam fluindo para o objeto de controle de tempo.  Do trabalho ao controle de horas, aloque usando a referência baseada em dados. Você também pode alocar do Time Tracking para as Torres de TI, conforme necessário.  No Controle de horas, você pode alocar para projetos com base na ID do projeto. O ideal é alocar usando a Referência baseada em dados. Se não for possível usar uma Referência baseada em dados, discuta suas opções com seu consultor. |
| Orçamento | Certifique-se de que os valores estejam fluindo para o objeto de controle de tempo.  Do trabalho ao controle de horas, aloque usando a referência baseada em dados. Você também pode alocar do Time Tracking para as Torres de TI, conforme necessário[ VM1 ].  No Controle de horas, você pode alocar para projetos com base na ID do projeto. O ideal é alocar usando a Referência baseada em dados. Se não for possível usar uma Referência baseada em dados, discuta suas opções com seu consultor. |
| CapEx | Certifique-se de que os valores estejam fluindo para o objeto de controle de tempo.  Do objeto Trabalho para o objeto Controle de horas, faça a alocação usando a Referência baseada em dados. Do controle de tempo aos projetos, faça a alocação usando a referência baseada em dados.  Se não for possível usar uma Referência baseada em dados, discuta suas opções com seu consultor. |
| Orçamento CapEx | Certifique-se de que os valores estejam fluindo para o objeto de controle de tempo[ VM2 ].  Do objeto Trabalho para o objeto Controle de horas, faça a alocação usando a Referência baseada em dados. Do controle de tempo aos projetos, faça a alocação usando a referência baseada em dados.  Se não for possível usar uma Referência baseada em dados, discuta suas opções com seu consultor |

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
