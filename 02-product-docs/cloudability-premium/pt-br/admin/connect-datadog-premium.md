---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Conecte-se ao Datadog - Dados de utilização"
breadcrumb:
  - "Cloudability Premium"
  - "Obtendo dados em Cloudability"
source_path: "admin/connect-datadog-premium.html"
images:
  - "images/datadog-integration-azure.jpg"
  - "images/datadog-integration-readonly.jpg"
  - "images/vc_ss10.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conecte-se ao Datadog - Dados de utilização

Se você usa o Datadog para monitorar seus recursos, pode aproveitar a integração do Cloudability com o Datadog para ajudar a reduzir gastos desnecessários, otimizando o uso de recursos. Cloudability Suporta totalmente [Datadog várias contas organizacionais](https://docs.datadoghq.com/account_management/multi_organization/ "(Abre em uma nova guia ou janela)").

Cloudability usa suas credenciais do Datadog para coletar métricas de utilização e gerar recomendações precisas de redimensionamento para os seguintes tipos de recursos de computação em nuvem em todas as suas contas organizacionais do Datadog :

- AWS EC2
- Computação do Azure
- GCP GCE

Além disso, oferecemos suporte aos seguintes recursos do Datadog :

[Residência de dados na União Europeia ( datadoghq.eu )](https://www.datadoghq.com/about/latest-news/press-releases/eu-region-germany/ "(Abre em uma nova guia ou janela)")

[Datadog várias contas organizacionais](https://docs.datadoghq.com/account_management/multi_organization/ "(Abre em uma nova guia ou janela)")

Usar um produto de monitoramento de desempenho de aplicativos (APM), como o Datadog, facilita a geração e a coleta das métricas necessárias de utilização de recursos (como métricas de memória convidada, que podem ser difíceis de instrumentar em escala) para obter uma visão precisa de como o recurso está sendo utilizado, levando a uma recomendação precisa de redimensionamento. Saiba mais sobre a Datadog e seus produtos [aqui](https://www.datadoghq.com/ "(Abre em uma nova guia ou janela)").

Observação: a integração utilizará a Chave API e a Chave do nome do aplicativo para autenticar a conta dos clientes do Cloudability Premium.

Benefícios

- Recomendações aprimoradas: os dados de utilização fornecidos pelo Datadog oferecem maior precisão, pois a amostragem métrica ocorre com maior frequência quando comparada ao provedor nativo. Como resultado, podemos aproveitar essa maior precisão para descobrir oportunidades adicionais de economia de custos de 15 a 20% em relação às métricas padrão da plataforma.
- Maior cobertura: ao concluir a integração do Datadog Azure, você se beneficiará de uma cobertura mais fácil e ampliada dos recursos da máquina virtual, recebendo recomendações de redimensionamento e oportunidades de economia de custos correspondentes.

Antes de começar

Chaves de API e de aplicativo

Para integrar sua conta Datadog à plataforma Cloudability, você precisa dos seguintes itens:

- Datadog Chave API
- Chave do aplicativo

Se você tiver várias organizações Datadog, será necessário criar uma chave API e uma chave de aplicativo por organização. Cloudability requer apenas uma única chave API e chave de aplicativo por conta organizacional Datadog

Observação: O Datadog possui três tipos de chaves de aplicativo que determinam o nível de acesso:

- Administrador
- Standard
- Somente leitura

Cloudability suporta todos os três tipos, mas as chaves somente leitura têm as seguintes limitações:

- As chaves somente leitura impedem que o site Cloudability obtenha metadados, como o nome da chave, para as chaves.
- As chaves somente leitura impedem que o site Cloudability possa realizar a eliminação da duplicação. Por exemplo, no caso em que um usuário adiciona várias chaves somente leitura da mesma conta organizacional Datadog, precisamos apenas de uma única API e chave de aplicativo por conta, mas não podemos eliminar a duplicidade, pois as chaves somente leitura não nos fornecem acesso aos dados necessários para realizar essa verificação. Em outras palavras, Cloudability não sabe que essas credenciais somente leitura são da mesma conta.

Se você adicionar uma chave de aplicativo somente leitura às suas credenciais Cloudability, os metadados, como o nome da chave e o proprietário, serão mostrados como Não disponível.

![captura de tela da integração do datadog](../../../../03-media/cloudability-premium/images/datadog-integration-readonly.jpg)

Etapas para a integração

Recomendamos rebaixar o usuário administrador para usuário somente leitura para os fins dessa integração, a fim de seguir as práticas recomendadas de segurança e privacidade das informações.

Se você já é um administrador e precisa ser o líder dessa integração, convide-se como um novo usuário usando um endereço de e-mail diferente daquele definido atualmente como usuário administrador e crie as chaves. Depois disso, faça o downgrade para um usuário somente leitura.

Crie novas chaves em Datadog

No console do Datadog :

1. Convide um novo membro como um usuário administrador para a integração.

   Consulte a [seção Funções e Permissões de Usuário do Datadog](https://docs.datadoghq.com/account_management/users/ "(Abre em uma nova guia ou janela)") para obter mais informações.
2. Faça login como o usuário administrador recém-criado.
3. Navegue até Integrações > APIs > Nova chave de API.
4. Crie uma nova chave de API.
5. Vá para a seção Nova chave de aplicativo e crie uma nova chave de aplicativo.

Adicione suas chaves Datadog a Cloudability

Repita as etapas abaixo para todas as suas contas organizacionais do Datadog.

1. Em Cloudability, navegue até Configurações > Credenciais do fornecedor > Adicionar fonte de dados > Datadog. O painel Adicionar conta do Datadog é exibido.

   Ou

   Em Cloudability, navegue até Configurações > Credenciais do fornecedor > Datadog. Selecione Add a Credential (Adicionar uma credencial ). O painel Adicionar uma credencial é aberto.
2. Selecione a Datadog guia.
3. Selecione Sim, estou pronto para confirmar que você possui suas chaves Datadog.
4. Copie e cole a nova chave de API e a chave de aplicativo no campo relevante.
5. Insira seu limite de API em Rate Limit.

   Observação: essa integração exigirá cerca de 300 solicitações de API por hora, já que o site Cloudability precisa coletar os dados de um mês em até 24 horas. 300 solicitações de API por hora por organização é a taxa padrão definida pelo site Datadog.

   Se você usar a API Datadog para outros fins, recomendamos que entre em contato com o suporte do Datadog para solicitar um aumento no número de solicitações de API que você pode fazer.

   Em geral, recomendamos aumentar esse número para 600 a 900 solicitações de API por hora por organização. Este é um pedido simples e gratuito para Datadog, e você pode fazer referência a Cloudability em seu pedido.

   Cloudability lista todas as suas credenciais Datadog na mesma página:![captura de tela da lista do datadog](../../../../03-media/cloudability-premium/images/vc_ss10.jpg)

Cloudability integração com Datadog para Azure Compute

Após concluir as etapas de integração acima, finalize a [integração da assinatura Datadog](https://docs.datadoghq.com/integrations/azure/?tab=azurecliv20#setup "(Abre em uma nova guia ou janela)") para cada assinatura que contenha máquinas virtuais. Este procedimento inclui a instalação do agente Datadog em cada máquina virtual.

Cloudability integração com Datadog para GCP GCE ( Google Compute Engine )

Para obter mais informações sobre a configuração e a instalação do Datadog no Google Cloud Platform, consulte [https://docs.datadoghq.com/integrations/google\_cloud\_platform/#setup](https://docs.datadoghq.com/integrations/google_cloud_platform/#setup "(Abre em uma nova guia ou janela)")

Como confirmar o sucesso

Dentro de 24 horas após a conclusão da integração do Datadog Azure, você verá recomendações de redimensionamento baseadas nas métricas de utilização do Datadog. A coluna Fonte de dados agora exibirá Datadog se a recomendação foi informada por dados de utilização de Datadog.

![captura de tela da integração do datadog azure](../../../../03-media/cloudability-premium/images/datadog-integration-azure.jpg)

- **[Conecte-se ao Datadog - Dados de custo e uso](../admin/connect-datadog-cost-usage_data.html)**
