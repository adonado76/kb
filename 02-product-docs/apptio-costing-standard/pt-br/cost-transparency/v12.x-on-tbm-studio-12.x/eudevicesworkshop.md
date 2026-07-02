---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Workshop de dispositivos para usuários finais"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/eudevicesworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Workshop de dispositivos para usuários finais

## Preparação dos dados dos dispositivos do usuário final

1. Se ainda não tiver feito isso, carregue os dados dos dispositivos do usuário final, como:
   - Computadores de mesa
   - Dispositivos móveis
   - Qualquer dispositivo de usuário final
2. Seguindo as Apptio práticas padrão, categorize cada conjunto de dados brutos na categoria 01 - Dados brutos.
3. Se apropriado, aplique um filtro de data aos dados dos dispositivos do usuário final.

## Sobre os identificadores de dispositivos do usuário final

O identificador do conjunto de dados mestre de dispositivos de usuário final é o identificador de objeto por padrão. Você deve ter alguma forma de identificar cada dispositivo de usuário final e usá-lo como identificador de objeto.

## Sobre as chaves dos dispositivos do usuário final

Algumas das chaves do conjunto de dados mestre do usuário final são geradas pelo sistema e outras são definidas pelo usuário. Qualquer chave gerada pelo sistema não deve ser alterada. As teclas predefinidas são:

Chave de dispositivos de usuário ITRT\_End
:   Uma chave gerada pelo usuário usada para alocar custos do objeto Torre de recursos de TI para o objeto Dispositivos do usuário final.

Chave de dispositivos de usuário final\_de\_comunicação
:   Uma chave gerada pelo usuário usada para alocar custos do objeto Communications (Comunicações) para o objeto End User Devices (Dispositivos do usuário final).

Chave de dispositivos de rede\_dispositivos do usuário final
:   Uma chave gerada pelo usuário usada para alocar custos do objeto Dispositivos de rede para o objeto Dispositivos do usuário final.

Chave de serviços\_dispositivos do usuário final
:   Uma chave gerada pelo usuário usada para alocar custos do objeto Dispositivos do usuário final para o objeto Serviços.

Chave de dispositivos de usuário Server\_End
:   Uma chave gerada pelo usuário para alocar instâncias de servidor usadas para hospedar instâncias de VDI

## Mapear dados para os dados mestre dos dispositivos do usuário final

Mapeie seus dados de dispositivos de usuário final para o conjunto de dados de dados mestre de dispositivos de usuário final. Em 12.7, agora você pode aproveitar a função Column Map em seu conjunto de dados brutos para mapear para os dados mestre dos dispositivos do usuário final ([Map Columns](https://community.apptio.com/docs/DOC-10561 "(Abre em uma nova guia ou janela)") )

## Relatórios de dispositivos de usuário final

Atualmente, não há relatórios que se iluminam após a adição de dados ao conjunto de dados de dados mestre de dispositivos de usuário final.

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
