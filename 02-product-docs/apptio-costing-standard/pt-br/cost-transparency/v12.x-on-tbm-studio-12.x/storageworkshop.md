---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Oficina de armazenamento"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/storageworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Oficina de armazenamento

## Preparação de seus dados de armazenamento

1. Se ainda não tiver feito isso, carregue seus dados de armazenamento, incluindo:
   - Dispositivos de armazenamento
     - Matrizes (exemplo)
     - Backup em fita (exemplo)
   - Armazenamento
     - LUNS (exemplo)
2. Seguindo as Apptio práticas padrão, categorize cada conjunto de dados brutos na categoria de Armazenamento.
3. Se apropriado, aplique um filtro de data aos seus dados de armazenamento.

## Sobre os identificadores de armazenamento

O identificador do conjunto de dados mestre dos dispositivos de armazenamento é a ID do dispositivo de armazenamento. Você deve ter alguma maneira de identificar cada dispositivo de armazenamento e usá-lo como ID do dispositivo de armazenamento.

O identificador do conjunto de dados mestre de armazenamento é a ID de armazenamento. Um dispositivo de armazenamento pode conter vários hosts de armazenamento. Esse identificador deve ser o ID dos hosts de armazenamento separados.

## Sobre as chaves de armazenamento

Algumas das chaves do conjunto de dados mestre de dispositivos de armazenamento são geradas pelo sistema e outras são definidas pelo usuário. Qualquer chave gerada pelo sistema não deve ser alterada. A lógica recomendada para as teclas definidas pelo usuário está na tabela abaixo.

| Chave | A chave de campo é baseada em | Lógica |
| --- | --- | --- |
| **Chave ITRT\_Storage** | Definido pelo usuário | A lógica recomendada é anexar Asset\_Resource - "Storage" e Sub-Tower |
| **Chave Asset\_Storage** | Definido pelo usuário | Chave opcional que permite uma referência baseada em dados entre ativos fixos e dispositivos de armazenamento |
| **Chave Devices\_Storage** | ID do dispositivo de armazenamento  Local | Anexar a ID do dispositivo de armazenamento e o local |
| **Chave de dispositivos de rede\_dispositivos de armazenamento** | Definido pelo usuário | A lógica recomendada é anexar Network Devices\_Storage Devices (Dispositivos de rede/Dispositivos de armazenamento) com a ID do dispositivo de armazenamento |

Algumas das chaves do conjunto de dados mestre de armazenamento são geradas pelo sistema e outras são definidas pelo usuário. Qualquer chave gerada pelo sistema não deve ser alterada. A lógica recomendada para as teclas definidas pelo usuário está na tabela abaixo.

| Chave | A chave de campo é baseada em | Lógica |
| --- | --- | --- |
| **Chave do servidor de armazenamento** | Definido pelo usuário | A lógica recomendada é anexar a Storage\_Server Key à ID do dispositivo de armazenamento |
| **Chave Devices\_Storage** | ID do dispositivo de armazenamento  Local | Anexar a ID do dispositivo de armazenamento e o local |
| **Chave do aplicativo de armazenamento** | Definido pelo usuário | A lógica recomendada é anexar a Storage\_Server Key à ID do aplicativo |
| **Chave do servidor de armazenamento** | Definido pelo usuário | A lógica recomendada é anexar a Storage\_Server Key à ID do servidor |

## Colunas computadas comuns necessárias para armazenamento

Além das chaves definidas pelo usuário mencionadas acima, não há nenhuma coluna computada específica que precise ser criada. Isso varia de acordo com os seus dados, mas normalmente você precisará descobrir os recursos que estão usando o armazenamento e alocar diretamente para esses itens de infraestrutura. Atributos suplementares ajudam na geração de relatórios, como estatísticas de capacidade e utilização.

## Mapear dados para dispositivos de armazenamento e dados mestre de armazenamento

Mapeie os dados de seu dispositivo de armazenamento para o conjunto de dados mestre de dispositivos de armazenamento. A maior parte do mapeamento deve ser autoexplicativa neste ponto.

Se você definir seu identificador como o ID do dispositivo de armazenamento, mapeie =1 para o campo Unidades reais. Se você não tiver dados de dispositivo de armazenamento orçados, poderá definir o campo Budgeted Units como =1 também. Em 12.7, agora você pode aproveitar a função Column Map em seu conjunto de dados brutos para mapear para os dados mestre dos dispositivos de armazenamento ([Map Columns](https://community.apptio.com/docs/DOC-10561 "(Abre em uma nova guia ou janela)") )

Mapeie seus dados de armazenamento para o conjunto de dados mestre de armazenamento. A maior parte do mapeamento deve ser autoexplicativa neste ponto.

Se você definir seu identificador como o nome do host de armazenamento, mapeie =1 para o campo Unidades reais. Se você não tiver dados de armazenamento orçados, poderá definir o campo Unidades orçadas como =1 também. Em 12.7, agora você pode aproveitar a função Column Map em seu conjunto de dados brutos para mapear para os dados mestre de armazenamento ([Map Columns](https://community.apptio.com/docs/DOC-10561 "(Abre em uma nova guia ou janela)") )

## Analise os objetos de armazenamento nos modelos

| Modelo | Ações |
| --- | --- |
| **Custo** | Verifique se os valores estão fluindo para os dispositivos de armazenamento e objetos de armazenamento.  De Torres de Recursos de TI a Dispositivos de Armazenamento, aloque usando a Referência Baseada em Dados, ponderada por Unidades Mestre de Dispositivos de Armazenamento Data.Actual (essa é a configuração padrão). As chaves que unem as Torres de recursos de TI e os Dispositivos de armazenamento são a Asset\_Resource Key no lado das Torres de recursos de TI e a ITRT\_Storage Key no lado dos Dispositivos de armazenamento.  De Dispositivos de armazenamento a Armazenamento, alocação usando a Referência baseada em dados (essa é a configuração padrão). A chave que une os dois conjuntos de dados é a Devices\_Storage Key. |
| **Orçamento** | Verifique se os valores estão fluindo para os dispositivos de armazenamento e objetos de armazenamento.  De Torres de Recursos de TI a Dispositivos de Armazenamento, aloque usando a Referência Baseada em Dados, ponderada por Unidades Mestre de Dispositivos de Armazenamento Data.Budgeted (essa é a configuração padrão). As chaves que unem as Torres de recursos de TI e os Dispositivos de armazenamento são a Asset\_Resource Key no lado das Torres de recursos de TI e a ITRT\_Storage Key no lado dos Dispositivos de armazenamento.  De Dispositivos de armazenamento a Armazenamento, alocação usando a Referência baseada em dados (essa é a configuração padrão). A chave que une os dois conjuntos de dados é a Devices\_Storage Key. |

## Revisar relatórios de armazenamento

Os relatórios a seguir são atualizados após a configuração do objeto Storage:

- TCO de armazenamento
- Infra - TCO de armazenamento - Detalhe
- Infra - TCO de armazenamento - Detalhe da LUN
- Infra - Resumo - Armazenamento
- Revisão da infraestrutura
- Validade do armazenamento
- Aplicativo Infra
- Infraestrutura de aplicativos - detalhes de armazenamento
- Dimensões dos dados - Armazenamento
- Qualidade de dados - Recursos de TI
- Qualidade dos dados - Armazenamento

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
