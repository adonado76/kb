---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Workshop de rede"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/networkworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Workshop de rede

## Preparando seus dados de rede

A rede varia muito de acordo com o cliente, pois a definição significa coisas diferentes para empresas diferentes. Algumas empresas não se importam com relatórios de rede adicionais e, portanto, serão usadas apenas para calcular o custo dos serviços. Outras empresas terão dispositivos de rede, centrais de contato etc. Portanto, se esses dados existirem, instale o componente, calcule o custo dos itens, atribua os custos diretamente à infraestrutura onde for possível e envie o restante para os serviços que utilizam redes.

1. Se ainda não tiver feito isso, carregue seus dados de rede, incluindo (varia muito de acordo com o cliente):

   - Dispositivos de rede
   - Dados de uso da rede
2. Seguindo as Apptio práticas padrão, categorize cada conjunto de dados brutos na categoria de Dispositivos de rede.
3. Se apropriado, aplique um filtro de data aos dados de sua rede.

## Sobre os identificadores de rede

O identificador do conjunto de dados mestre de dispositivos de rede é o nome do dispositivo por padrão. Você deve ter alguma maneira de identificar cada dispositivo de rede e usá-lo como nome do dispositivo.

## Sobre as chaves de rede

Algumas das chaves do conjunto de dados mestre de dispositivos de rede são geradas pelo sistema e outras são definidas pelo usuário. Qualquer chave gerada pelo sistema não deve ser alterada. As teclas predefinidas são:

- Chave ITRT\_Network Devices (Dispositivos de rede ITRT)
- Dispositivos de rede\_chave de mainframe
- Dispositivos de rede\_chave física
- Chave de dispositivos de rede\_dispositivos de armazenamento
- Chave de dispositivos de rede DC\_Network

## Mapear dados para os dados mestre da rede

Mapeie seus dados de dispositivos de rede para o conjunto de dados mestre de dispositivos de rede. A maior parte do mapeamento é autoexplicativa neste ponto. Em 12.7, agora você pode aproveitar a função Column Map em seu conjunto de dados brutos para mapear para os dados mestre dos dispositivos de rede (Map Columns)

## Relatórios de rede

Atualmente, não há relatórios que se iluminam após a adição de dados ao conjunto de dados mestre de dispositivos de rede.

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
