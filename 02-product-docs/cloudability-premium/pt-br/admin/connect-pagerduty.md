---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Conectar o Pagerduty"
breadcrumb:
  - "Cloudability Premium"
  - "Obtendo dados em Cloudability"
source_path: "admin/connect-pagerduty.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conectar o Pagerduty

As informações a seguir ajudarão você a conectar seus serviços do Pagerduty ao Cloudability.

Etapas para a integração

Pagerduty

1. No menu Configuração, selecione Serviços.
2. Se você estiver criando um novo serviço para sua integração, na página Serviços, selecione Adicionar novo serviço.
3. Se você estiver adicionando sua integração a um serviço já existente, na página Serviços, selecione o nome do serviço ao qual deseja adicionar a integração. Em seguida, selecione a aba Integrações e clique em Nova integração.
4. No menu “Tipo de integração ”, selecione “ Cloudability ” e preencha o campo “Nome da integração ”.
5. Se você estiver criando um novo serviço para sua integração, em Configurações gerais, insira um nome para o seu novo serviço no campo Nome. Em seguida, em Configurações de Incidente, especifique a Política de Escalonamento, a Urgência da Notificação e o Comportamento do Incidente para o seu novo serviço.
6. Selecione “Adicionar serviço ” ou “Adicionar integração ” para salvar sua nova integração. Você será redirecionado para a página Integrações do seu serviço.
7. Copie a Chave de integração da sua nova integração. Isso será utilizado no procedimento a seguir.

Cloudability 

1. No site Cloudability, acesse Configurações > Credenciais do fornecedor > Adicionar fonte de dados > PagerDuty. O painel “Adicionar conta do PagerDuty ” é exibido.

   Ou

   No site Cloudability, acesse Configurações > Credenciais do fornecedor > PagerDuty. Selecione Adicionar um novo serviço. O painel “Adicionar um novo serviço” é aberto
2. Insira os detalhes nos campos Nome da integração e Chave de integração.

Agora você está pronto para usar o Pagerduty nas áreas compatíveis do aplicativo Cloudability. Por exemplo, você pode configurar alertas sobre anomalias para serem enviados para PagerDuty:

1. Acesse a página Detecção de anomalias.
2. Selecione ALERTAS e configure as definições de alerta do PagerDuty.

Detecção de Problemas

O que o Cloudability pode fazer com minha chave de integração no Pagerduty?

Nós os integramos com v2 da API de Eventos do Pagerduty. A API de Eventos v2 é uma API assíncrona altamente confiável e de alta disponibilidade que capta eventos de ferramentas de monitoramento. Os eventos enviados a esta API são encaminhados para um serviço do Pagerduty e processados. Isso pode resultar na criação de um novo alerta ou incidente, ou na atualização ou resolução de um já existente. Anteriormente, a API de Eventos também era usada para integrar o Pagerduty a sistemas de emissão de bilhetes e a várias outras ferramentas de software. Hoje, recomendamos o uso da API síncrona de incidentes para integrar sistemas de tickets ou outros sistemas de registro ao Pagerduty

Portanto, as chaves de integração permitem apenas o envio de alertas para um serviço.
