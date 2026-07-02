---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Definindo alertas de compromisso"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Guia para a gestão de compromissos"
source_path: "product/setting_commitment_alerts.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Definindo alertas de compromisso

## Propósito

Os Alertas de Compromisso reduzem o monitoramento manual notificando-o quando os compromissos estão se aproximando da expiração ou quando a utilização cai abaixo de um limite definido por você. Este documento explica como configurar, interpretar e agir em relação aos alertas, além de nuances específicas do fornecedor.

## Noções básicas de alerta

Oferecemos suporte a dois tipos de alertas de compromisso:

**Expiração** - Notifica os usuários sobre os próximos compromissos a expirar. Na frequência de "expiração dentro de" escolhida, o site Cloudability determinará se um compromisso está expirando durante o período de tempo especificado.

**Utilization Threshold (Limite de utilização** ) - Notifica os usuários sobre compromissos que exibem uma utilização abaixo de um limite especificado. No "período de retrospectiva" e no "limite" escolhidos, o site Cloudability executa o algoritmo de utilização do Portfólio de Compromissos para determinar se algum compromisso existente atende aos critérios especificados.

Para configurar alertas, navegue até o portfólio de compromissos e selecione o botão de alertas no canto superior direito. Os alertas são facilitados por meio de uma notificação por e-mail. Observe que há um relatório de e-mail personalizado separado para cada um dos dois tipos de alerta. Os alertas avaliam todo o seu portfólio de tipos compatíveis com credenciais válidas; eles não são segmentados pela guia do fornecedor ou pelo tipo selecionado quando você abre o painel. (Por exemplo, ao definir um alerta na guia “ AWS ”, ele será aplicado em Azure e GCP ).

A notificação por e-mail ocorrerá de acordo com a frequência de envio especificada e o horário selecionado. Observe que a hora está em UTC. Observe que, para ambos os tipos de alerta, você pode decidir enviar o alerta na frequência especificada, mesmo que nenhum compromisso atenda aos critérios especificados.

## Fornecedor Nuance

- Azure Os Planos de Poupança não suportam um lookback de 90 dias. Em vez disso, o alerta tem como padrão o período mais longo disponível, 30 dias.
- GCP não oferece a granularidade de dados necessária para determinar a utilização de um compromisso específico. Em vez disso, fornecemos alertas de limite de utilização no grupo de compromisso. Para obter mais informações sobre os grupos de compromisso d GCP, consulte a documentação da carteira de compromissos.

## Configuração de alertas passo a passo

1. Navegue até Optimize → Commitment Portfolio.
2. Clique em Alertas (canto superior direito).
3. Em Commitment Alerts (Alertas de compromisso):

   **Expiration**
   1. Alternar entre ON/OFF
   2. Definir prazo de validade (por exemplo, 7, 14, 30, 60, 90 dias)
   3. (Opcional) Marque Enviar mesmo que não haja nenhuma expiração

   **Limite de utilização**
   1. Alternar entre ON/OFF
   2. Definir o período de lookback (rolando N dias)
   3. (Opcional) Marque Enviar mesmo que nenhum valor esteja abaixo do limite

   **Frequência**
   1. Escolha a frequência de avaliação e o horário de envio do e-mail
4. Clique em Submit para se inscrever.
5. Para desativar, abra o painel e clique em Cancelar assinatura para o alerta relevante.

## Interpretação dos alertas de e-mail

*E-mail de expiração*

**O que você verá:**

Compromisso(s) que estão expirando dentro da janela selecionada, juntamente com identificadores e detalhes de tempo.

**Ações recomendadas:**

- Validar a cobertura e a utilização no portfólio de compromissos.
- Compreender a consideração da carga de trabalho atual e futura para avaliar a renovação.
- Imediatamente após a expiração, avalie suas recomendações para determinar se novas compras de compromissos são apropriadas.

*E-mail de limite de utilização*

**O que você verá:**

Compromissos abaixo do limite de utilização, juntamente com seus detalhes de uso avaliados.

**Ações recomendadas:**

- Investigar o escopo (zonal vs. regional), configurações de compartilhamento e mudanças na carga de trabalho
- Considerar trocas/conversíveis ou reduzir os tamanhos/termos de compras futuras
- Reavaliar a estratégia de compromisso para entender por que ocorreu a subutilização frequente e como evitá-la no futuro.

## Boas Práticas

- **Seleção do limite** : Comece com 90-95% e refine de acordo com o ponto de equilíbrio e a volatilidade histórica do tipo.
- **Janela de retrospectiva** : 7-14 dias equilibra ruído vs. capacidade de resposta. Use de 30 a 90 dias para um uso mais estável.
- **Operar para sinalizar, não para ruído** : Investigue a baixa utilização durante um longo período de tempo. Quedas em um único dia podem refletir mudanças de uso benignas ou sazonais que ainda podem valer a pena cobrir com um compromisso.
- **Combine com painéis de controle** : Acompanhe a cobertura, a utilização, a taxa de economia e o custo restante para contextualizar os picos de alerta.

## Principais conclusões

- Configure os alertas de expiração e de limite de utilização em Commitment Portfolio → Alerts.
- Defina um lookback e um limite alinhados ao ponto de equilíbrio e à volatilidade; escolha a frequência e o tempo de envio.
- Use os e-mails como um sinal para investigar.
- Esteja ciente dos limites de retroatividade do Azure e das avaliações em nível de grupo do GCP.

**Tópico dos pais:** [Guia para gerenciamento de compromissos](../product/guide_to_commitment_management.html)
