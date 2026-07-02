---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Tutorial da API: Download e upload da tabela v.12 Costing Standard usando a ferramenta Postman"
breadcrumb: []
source_path: "studio/studio/apis/studio_tutorial.html"
images:
  - "resources/images/studio_images/studioimages/studio_11_800x683.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tutorial da API: Download e upload da tabela v.12 Costing Standard usando a ferramenta Postman

## Requisitos

- Uma conta de usuário em Enhanced Access Administration configurada com chaves de API. Para obter mais informações, consulte [Enhanced Access Administration API: Visão geral das chaves de API e perguntas frequentes](/docs/SSFG2DK/frontdoor/admin-guide/eaa-api/overview-api-keys-faq.html).
  - A conta de usuário deve estar no domínio de autenticação Enhanced Access Administration , onde reside o aplicativo Costing Standard (CT).
  - A chave deve receber acesso ao ambiente apropriado após ser criada. Clique no link **Grant Access (Conceder acesso)** ao lado do nome da chave.
  - O usuário deve ter uma função de Power User para acesso ao CT e, possivelmente, privilégios de Datalink
    (Classic) Admin se a mesma conta for usada em ambos os aplicativos. Se a função de usuário avançado não for padrão ou tiver sido modificada, certifique-se de que as permissões estejam definidas para a função como Permitir acesso a ambientes e Permitir exportação.
- O aplicativo Costing Standard com o acesso do usuário (mencionado acima) ao ambiente.
- O aplicativo Postman para este exemplo. Aplicativos semelhantes, como o SoapUI,, podem ser usados com os mesmos princípios.

## Usuário em Enhanced Access Administration

![tela de usuários](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_11_800x683.png)

## Configurar um ambiente Postman

Esse procedimento permite que você salve variáveis de ambiente no Postman. Isso é útil para encadear diferentes solicitações em apoio aos testes, de modo que você não precise copiar e colar o Apptio -opentoken repetidamente.

Para configurar o ambiente:

1. [Crie um novo ambiente **Postman**](https://learning.postman.com/docs/postman/variables-and-environments/variables/ "(Abre em uma nova guia ou janela)").

   ![novo ambiente](../../../resources/images/studio_images/studioimages/studio%2012.png)
2. Defina as variáveis de ambiente apropriadas. Nas imagens a seguir, usamos env, pub, secret e token.

- **env** - Está em branco no início - será preenchido posteriormente.
- **pub** - O componente público de sua chave de API.
- **secret** - O componente secreto de sua chave de API.
- **token** - Está em branco no início - será preenchido posteriormente.

![ambiente de edição](../../../resources/images/studio_images/studioimages/studio%2013.png)

## Obter um Opentoken do Frontdoor

Para obter a documentação sobre esse exemplo, consulte [Enhanced Access Administration API: Autenticação por meio de chaves de API](https://community.apptio.com/docs/DOC-10522 "(Abre em uma nova guia ou janela)").

Postar solicitação URL : [https://frontdoor.apptio.com/service/apikeylogin](https://frontdoor.apptio.com/service/apikeylogin "(Abre em uma nova guia ou janela)")

Cabeçalhos:

- Aceitar: application/json
- Tipo de conteúdo: application/json

![obter chaves de API](../../../resources/images/studio_images/studioimages/studio%2014_800x289.png)

Corpo (**OBSERVAÇÃO** : defina o corpo para o formato bruto selecionando o botão de rádio adequado):

`{"keyAccess":"{{pub}}","keySecret":"{{secret}}"}`

![imagem](../../../resources/images/studio_images/studioimages/studio%2015_800x266.png)

Em **Testes**, defina o seguinte. Isso definirá o valor de sua variável de ambiente **Token** quando o POST for executado:

`pm.environment.set("token",
pm.cookies.get('apptio-opentoken'));`

![imagem](../../../resources/images/studio_images/studioimages/studio%2016_800x256.png)

Clique em **Salvar** e, em seguida, clique em **Enviar** para esse POST. Agora você deve ver o endereço Apptio -opentoken nos cookies:

![imagem](../../../resources/images/studio_images/studioimages/studio%2017_800x531.png)

E em suas variáveis de ambiente:

![imagem](../../../resources/images/studio_images/studioimages/studio%2018.png)

## Uso de nome de usuário/senha para autenticação

O uso de chaves de API é o método preferencial de autenticação por motivos de segurança. No entanto, se estiver usando um nome de usuário e uma senha em vez de chaves de API, será necessário criar variáveis de ambiente para o ID do usuário e a senha. Em seguida, o corpo terá uma aparência semelhante à do exemplo a seguir.

![imagem](../../../resources/images/studio_images/studioimages/studio%2019.png)

Para obter mais informações, consulte [API do Frontdoor: Autenticação básica usando um nome de usuário e senha](https://community.apptio.com/docs/DOC-10529 "(Abre em uma nova guia ou janela)").

## Obter a ID do ambiente

A chamada para obter uma ID de ambiente não é necessária se você já souber qual é a ID. O ID não é alterado, a menos que um aplicativo como a configuração do CT Enhanced Access Administration seja modificado. Para obter mais informações, consulte [API do Frontdoor: Obter informações sobre o ambiente do usuário](https://community.apptio.com/docs/DOC-10459 "(Abre em uma nova guia ou janela)").

**OBSERVAÇÃO** : não se esqueça de substituir seu nome de domínio pelo espaço reservado **yourdomain.com** e seu nome de ambiente Enhanced Access Administration (normalmente **main** ) pelo espaço reservado **yourfrontdoorenv** no seguinte URL :

Solicitação GET URL : [https://frontdoor.apptio.com/api/environment/yourdomain.com/yourfrontdoorenv](https://frontdoor.apptio.com/api/environment/yourdomain.com/yourfrontdoorenv "(Abre em uma nova guia ou janela)")

Cabeçalhos:

- tipo de conteúdo: application/json
- aplicativo aberto: {{token}}

![imagem](../../../resources/images/studio_images/studioimages/studio%2020.png)

Use o seguinte nos **testes** :

```
var jsonData = pm.response.json();

pm.environment.set("env", jsonData.id);
```

Clique em **Salvar** e depois em **Enviar**. Você deverá ver o ID do ambiente no corpo:

![imagem](../../../resources/images/studio_images/studioimages/studio%2021.png)

E nas variáveis de seu ambiente:

![imagem](../../../resources/images/studio_images/studioimages/studio%2022.png)

## Carregar uma tabela

Para obter mais informações, consulte os exemplos em Introdução à [API da](../../admin/the-apptio-api.html "Aplica-se a: TBM Studio 12.0 e posterior") [plataforma APIPlatform](../../admin/the-apptio-api.html "Aplica-se a: TBM Studio 12.0 e posterior").

Cabeçalhos:

- tipo de conteúdo: application/json
- aplicativo aberto: {{token}}
- ambiente atual do aplicativo: {{env}}

![imagem](../../../resources/images/studio_images/studioimages/studio%2023.png)

Em Body (Corpo), especifique o arquivo a ser carregado:

![imagem](../../../resources/images/studio_images/studioimages/studio%2024.png)

Clique em **Salvar** e, em seguida, clique em **Enviar**. Se tudo estiver configurado corretamente, você deverá obter um json no corpo da resposta, semelhante a este exemplo.

![imagem](../../../resources/images/studio_images/studioimages/studio%2025.png)

## Baixar uma tabela

Para obter mais informações, consulte os exemplos em Introdução à [API da plataforma](../../admin/the-apptio-api.html "Aplica-se a: TBM Studio 12.0 e posterior").

Observação: Certifique-se de substituir os valores adequados à sua situação no seguinte exemplo URL :

URL da solicitação GET: consulte a seção Tabela da [API: Baixando dados](studio_api_download_data.html "Aplica-se a: TBM Studio v11.x, v12.0, v12.1, v12.2 e posterior") [da API: Baixando dados](studio_api_download_data.html "Aplica-se a: TBM Studio v11.x, v12.0, v12.1, v12.2 e posterior") para obter detalhes sobre como obter uma URL da API da tabela.

Cabeçalhos:

- tipo de conteúdo: texto/valores separados por tabulação
- aplicativo aberto: {{token}}
- ambiente atual do aplicativo: {{env}}

![imagem](../../../resources/images/studio_images/studioimages/studio%2026.png)

## Baixar uma tabela de relatórios

URL de solicitação GET: consulte [API: Baixando dados](studio_api_download_data.html "Aplica-se a: TBM Studio v11.x, v12.0, v12.1, v12.2 e posterior") [API: Baixando dados](studio_api_download_data.html "Aplica-se a: TBM Studio v11.x, v12.0, v12.1, v12.2 e posterior") para obter detalhes sobre como obter uma URL reportAPI.

Cabeçalhos:

- tipo de conteúdo: texto/valores separados por tabulação
- aplicativo aberto: {{token}}
- ambiente atual do aplicativo: {{env}}

![imagem](../../../resources/images/studio_images/studioimages/studio%2027.png)

Para obter mais informações sobre a API, consulte [Platform APIPlatform](../../admin/the-apptio-api.html "Aplica-se a: TBM Studio 12.0 e posterior") [API](../../admin/the-apptio-api.html "Aplica-se a: TBM Studio 12.0 e posterior").
