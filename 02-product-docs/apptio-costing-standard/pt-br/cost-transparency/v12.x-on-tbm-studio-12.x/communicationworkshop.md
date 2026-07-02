---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Workshop de comunicação"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/communicationworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Workshop de comunicação

## Preparação de seus dados de comunicação

1. Se ainda não tiver feito isso, carregue seus dados de comunicação, incluindo:
   - Comunicações
2. Seguindo as Apptio seguindo as práticas padrão, categorize cada conjunto de dados brutos na categoria de Comunicações
3. Se apropriado, aplique um filtro de data aos seus dados de comunicação.

## Sobre os identificadores de comunicação

O identificador do conjunto de dados mestre de comunicações é o identificador de objeto por padrão. Você deve ter alguma forma de identificar cada dispositivo de comunicação e usá-lo como identificador de objeto.

## Sobre as teclas de comunicação

Algumas das chaves do conjunto de dados mestre de comunicações são geradas pelo sistema e outras são definidas pelo usuário. Qualquer chave gerada pelo sistema não deve ser alterada. As teclas predefinidas são:

- Chave ITRT\_Communications
- Chave de dispositivos de usuário final\_de\_comunicações
- Chave Communications\_Servers
- Chave Communications\_Services

## Mapear dados para dados mestre de comunicação

Mapeie seus dados de comunicações para o conjunto de dados de dados mestre de comunicações. A maior parte do mapeamento é autoexplicativa neste ponto. Em 12.7, agora você pode aproveitar a função Column Map em seu conjunto de dados brutos para mapear para os dados mestre de comunicações ([Map Columns](https://community.apptio.com/docs/DOC-10561 "(Abre em uma nova guia ou janela)") )

## Relatórios de comunicação

Atualmente, não há relatórios que se iluminam após a adição de dados ao conjunto de dados de dados mestre de comunicações.

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
