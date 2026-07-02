---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Apptio Scripts de demonstração da API"
breadcrumb: []
source_path: "studio/studio/apis/studio_demo_scripts.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Apptio Scripts de demonstração da API

## Introdução

Nota:

Na versão 12.9 e superior, inclua os seguintes valores de cabeçalho em todas as chamadas de API para a API da plataforma.

tipo de aplicativo="Flagship"

versão do aplicativo="NA"

Isso inclui chamadas de API que fazem upload ou download em Costing Standard ou em outros projetos de plataforma. Esses cabeçalhos são adicionais aos cabeçalhos de API existentes que você já pode estar usando.

Apptio suporta três APIs:

- A [API da plataforma Apptio](../../admin/the-apptio-api.html "Aplica-se a: TBM Studio 12.0 e posterior")
- A [API Enhanced Access Administration](../../../frontdoor/home.html)
- A [API Datalink (Classic)](../../../datalink-classic/datalink/datalink_api_sample_scripts.html)

Este documento fornece scripts de demonstração da API da plataforma Apptio em uma ou duas linguagens de script comumente usadas, bem como instruções sobre como configurar os scripts de demonstração para teste. Ele também fornece aos usuários uma orientação sobre a mecânica de uso da API para que eles possam aplicar o aprendizado em suas próprias soluções com script.

Datalink (Classic) usa a API Apptio para transportar dados. A API Apptio também pode ser usada de forma independente para operações de upload ou download de dados (por exemplo, operações em lote), que o site Datalink (Classic) não suporta prontamente. O uso da API é mais complexo e geralmente requer algum conhecimento de script ou programação para ser implementado e mantido. Portanto, é recomendável usar o site Datalink (Classic) , a menos que você tenha necessidades e recursos avançados para implementar e manter a implementação da API.

A API Apptio é diferente da API Datalink (Classic) : A API Apptio é usada para fazer upload para as tabelas do projeto Apptio ou download das tabelas do projeto Apptio (inclusive aquelas em relatórios), e é o que o Datalink (Classic) usa nos bastidores. A API Datalink (Classic) é usada para automatizar a execução do conector do agente Datalink
(Classic) . Para saber mais sobre a API Datalink
(Classic) , consulte [os scripts de amostra da API Datalink](../../../datalink-classic/datalink/datalink_api_sample_scripts.html) .

O script anexado a este artigo foi testado nas seguintes versões específicas. No entanto, ele também deve funcionar com outras versões:

- r11.8.3.5
- r12.3.2

## Operações básicas

O primeiro script de demonstração tem o nome de ApptioAPI\_Demo\_Basic\_v2.ps1. Ele foi escrito no Windows PowerShell,, que está amplamente disponível nos sistemas Windows, pode aproveitar as bibliotecas.NET e pode ser usado por softwares, como o SQL Server Management Studio, para implementar o carregamento e a extração do SQL Server. Esse assunto será abordado com mais detalhes em versões futuras deste documento.

O script está anexado e comentado. O uso é o seguinte. Isso é exibido se o script for executado sem argumentos:

Você precisa especificar -up ou -down.

Uso (usando chaves de API):

```
ApptioAPI_Demo_Basic_v2.ps1 -help
ApptioAPI_Demo_Basic_v2.ps1 -down [-APIURL "valid API URL"]
[-downtimeperiod "Apptio time period"]
[-downloadfolder "folder to download to"] [-downfile "file name"]
ApptioAPI_Demo_Basic_v2.ps1 -up [-v1] [-upfile "path to file to upload"]
[-apptiohost "https://domain-r12.apptio.com"]
[-domain "domain.com"] [-project "Project Name"] [-table "Table Name"]
[-uptimeperiod "Apptio time period"] [-transformation overwrite | append]
```

Uso (usando autenticação de nome de usuário/senha):

```
ApptioAPI_Demo_Basic_v2.ps1 -help
ApptioAPI_Demo_Basic_v2.ps1 -user "username@domain.com" -pass "password"
-down [-APIURL "valid API URL"]
[-downtimeperiod "Apptio time period"]
[-downloadfolder "folder to download to"] [-downfile "file name"]
ApptioAPI_Demo_Basic_v2.ps1 -user "username@domain.com" -pass "password"
-up [-v1] [-upfile "path to file to upload"]
[-apptiohost "https://domain-r12.apptio.com"]
[-domain "domain.com"] [-project "Project Name"] [-table "Table Name"]
[-uptimeperiod "Apptio time period"] [-transformation overwrite | append]
```

É possível fornecer combinações dos argumentos opcionais e executá-los sem modificações. No entanto, se quiser usar apenas os sinalizadores "-up" e "-down", você poderá editar o script para modificar as variáveis necessárias. A seguir, uma explicação das variáveis, o que elas contêm e o que você pode precisar fazer para a configuração.

## Argumentos de autenticação

Os argumentos a seguir oferecem suporte à autenticação de chaves de API. Esse é o método preferido para uso em ambientes v12.

*-pubkey "xxxxxxxx-xxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"*

Esse argumento fornece uma chave pública de chave de API válida. Consulte [API de administração de acesso aprimorado: Visão geral das chaves da API e Perguntas frequentes](../../../frontdoor/admin-guide/eaa-api/overview-api-keys-faq.html) para obter mais informações sobre como obter uma chave pública.

*-segredo "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"*

Esse argumento fornece uma chave secreta de chave de API válida. Consulte [API de administração de acesso aprimorado: Visão geral das chaves da API e Perguntas frequentes](../../../frontdoor/admin-guide/eaa-api/overview-api-keys-faq.html) para obter mais informações sobre como obter uma chave pública.

*-envid "xxxxxxxx-xxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"*

Esse argumento fornece uma ID de ambiente v12 válida. Consulte [API de administração de acesso avançado: Atualizar informações de ambiente de um usuário](../../../frontdoor/admin-guide/eaa-api/api-get-user-environment.html) para obter informações sobre como obter essa ID usando a API. Você também pode solicitá-lo em Apptio Support ou em seu CSM ou CSE.

Os argumentos a seguir oferecem suporte à autenticação por nome de usuário/senha. Isso é para compatibilidade com versões anteriores de ambientes r11 e não deve ser usado em ambientes v12.

*-usuário " user@domain.com " -pass "senha"*

Esses argumentos especificam uma conta de usuário que tem acesso ao projeto que contém os dados a serem baixados e a senha dessa conta. Lembre-se de que, se você criar uma nova conta para dar suporte a isso, precisará editar a conta após a criação para desmarcar a caixa de seleção **Single-Use Password**, ou a API poderá não responder.

## Argumentos para download

*-APIURL "API válida URL "*

Esse argumento especifica uma API válida, entre aspas, Apptio URL. Isso pode ser obtido em quase tudo no site Apptio clicando no ícone de exportação, que aparece da seguinte forma:

![](../../../resources/images/studio_images/studioimages/studio%2028.png)

Esse ícone aparece na guia r11 Data (Dados) do studio em associação com qualquer visualização Transform Table (Tabela de transformação) ou Raw Table (Tabela bruta), ou por meio do botão Export (Exportar) de TBM Studio em r12 quando uma tabela é selecionada.

Nos relatórios, você pode acessá-lo clicando com o botão direito do mouse na base de uma tabela (por exemplo, na área da linha de totais).

*-downtimeperiod " Apptio time period"*

Esse argumento especifica um período de tempo corretamente formatado em Apptio para fazer o download (por exemplo, Aug:FY2016 ). Isso substituirá qualquer período de tempo que esteja na APIURL.

*[-downloadfolder "pasta para a qual fazer o download"]*

Esse argumento especifica a pasta para os dados baixados.

*[-filename "nome do arquivo"]*

Esse argumento especifica o nome do arquivo para o qual os dados são baixados.

## Argumentos de upload

`[-v2]`

Esse argumento especifica o uso da API v2 URL para upload. Isso é opcional e só é necessário em situações específicas.

`[-upfile "path to file to upload"]`

Esse argumento especifica o caminho para um arquivo que deve ser carregado.

`[-apptiohost "https://domain-dev.apptio.com"]`

Esse argumento especifica a instância do host Apptio onde reside o projeto para o qual o arquivo está sendo carregado.

`[-domain "domain.apptio.com"]`

Esse argumento especifica o domínio de sua empresa.

`[-project "Project Name"]`

Esse argumento especifica o nome do projeto no qual o arquivo será carregado.

`[-table "Table Name"]`

Esse argumento especifica o nome da tabela na qual os dados devem ser carregados.

`[-uptimeperiod "Apptio time period"]`

Esse argumento especifica um período de tempo Apptio corretamente formatado no qual fazer o upload (por exemplo, Aug:FY2016 ).

`[-transformation overwrite | append]`

Esse argumento especifica se a tabela deve ou não ser substituída ou anexada.

## Baixar scripts de demonstração

Clique [aqui](../../../resources/apptio_api_demo_scripts.zip) para fazer o download dos scripts de demonstração da API Apptio.
