---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Conecte-se ao Datadog - Dados de custo e uso"
breadcrumb:
  - "Cloudability Premium"
  - "Obtendo dados em Cloudability"
  - "Conecte-se ao Datadog - Dados de utilização"
source_path: "admin/connect-datadog-cost-usage_data.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conecte-se ao Datadog - Dados de custo e uso

Você pode conectar sua conta do Datadog ao Cloudability para permitir a ingestão de dados de custo e uso. Se você já credenciou uma conta Datadog para trazer dados de utilização para nosso recurso de redimensionamento, você pode editar essa conta existente para trazer também dados de custo. Basta selecionar custo na seção de relatórios da página de credenciamento e adicionar a chave de API e a chave de aplicativo.

Observação: pode levar até 24 horas para que seus dados iniciais de custo e uso apareçam no site Cloudability. Durante esse período, uma mensagem indica que o processo ainda não foi concluído.

Resumo da integração

Datadog nos permite voltar e obter os dados de custos dos últimos 15 meses. Se a fatura for finalizada, você verá os custos atribuídos ao primeiro dia do mês. Se a fatura não tiver sido finalizada, você verá os custos diários associados aos produtos e serviços que adquiriu. Isso significa que, em geral, você verá dados diários do mês atual e do último mês, até a data em que a fatura foi finalizada.

Nossas integrações respeitam os princípios de menor privilégio, nos quais projetamos os conectores para trabalhar com o menor nível de permissão necessário para que possamos extrair os dados relevantes para o site Cloudability.

Observação: se você estiver adquirindo o Datadog por meio de um marketplace de provedores de nuvem e adicionando dados de custo e uso para o Datadog com essa integração, os custos serão exibidos duas vezes nos relatórios do Cloudability. Por exemplo, se você adquiriu o Datadog através do AWS Marketplace, você teria:

Os itens de linha de alto nível por mês para AWS

Os itens com custos detalhados Datadog e “ AWS Marketplace” listado como “Vendedor”

Você precisará configurar filtros ou exibições para ocultar seus custos do Marketplace. Os custos de marketplace são excluídos do faturamento.

Antes de começar

Antes de começar, verifique o seguinte:

- Você é um administrador do Cloudability.
- Você tem permissões de administrador no console Datadog.

  - Recomendamos **que** um administrador crie um novo usuário e reduza o nível desse novo usuário **de** administrador **para** usuário somente leitura para fins desta integração.
  - Se você é um administrador existente do Datadog configurando essa integração, recomendamos que crie um novo login através da criação de um novo usuário, usando um endereço de e-mail diferente (diferente daquele usado para sua função de administrador). Rebaixe este usuário para **um** usuário somente leitura.

Etapas para a integração

Recomendamos que um administrador crie um novo usuário e faça o downgrade desse novo usuário de usuário administrador para usuário Read-Only para os fins dessa integração.

Se você é um administrador existente do Datadog configurando essa integração, recomendamos que crie um novo login através da criação de um novo usuário, usando um endereço de e-mail diferente (diferente daquele usado para sua função de administrador). Faça downgrade desse usuário para um usuário Read-Only.

Crie novas chaves em Datadog

No console do Datadog :

1. Convide um novo membro como um usuário administrador para a integração.

   Consulte a [seção Funções e Permissões de Usuário do Datadog](https://docs.datadoghq.com/account_management/users/ "(Abre em uma nova guia ou janela)") para obter mais informações.
2. Faça login como o usuário administrador recém-criado.
3. Navegue até Integrações > APIs > Nova chave de API.
4. Crie uma nova chave de API.
5. Vá para a seção Nova chave de aplicativo e crie uma nova chave de aplicativo.

Adicione suas chaves Datadog a Cloudability

1. Em Cloudability, navegue até Settings > Vendor Credentials.
2. Selecione a guia “ Datadog ”.
3. Selecione Sim, estou pronto para confirmar que você possui suas chaves Datadog.
4. Copie e cole a nova chave de API e a chave de aplicativo no campo relevante.
5. Insira seu limite de API em Rate Limit. para 300, que é o limite de taxa padrão.

   Observação: as tags ainda não são compatíveis com Datadog

   Caso você precise de uma lista branca de IPs, os seguintes intervalos de IPs darão acesso a Cloudability :

   - 185.115.88.0/22
   - 103.195.128.0/22

**Tópico principal:** [Conecte-se ao Datadog - Dados de utilização](../admin/connect-datadog-premium.html)
