---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "API URL para carregar e editar dados de usuários em sistemas pré-Enhanced Access Administration"
breadcrumb: []
source_path: "studio/studio/apis/studio_api_url_upload_edit.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# API URL para carregar e editar dados de usuários em sistemas pré-Enhanced Access Administration

**Aplica-se a** : v11.x, v12.0, v12.1

Use o site URL descrito abaixo para fazer upload em massa de dados de usuários e editar dados de usuários existentes em sistemas anteriores aoEnhanced Access Administration

## URL

Use o seguinte URL para fazer upload de uma tabela de usuário para Apptio :

`https://[instance].apptio.com/biit/api/v1/[domain]/users/[userid]`

Por exemplo, se sua empresa se chama **abccompany** e você deseja automatizar sua instância de desenvolvimento, você usaria:

`https://[abccompany-dev].apptio.com/biit/api/v1/[abccompany.com]/users/[user@abccomany.com]user@abccomany.com]`

Os atributos usados no site URL estão descritos abaixo.

| Atributo | Descrição |
| --- | --- |
| domínio | O domínio do cliente (e. g.: customer.com ) |
| nome do usuário | A ID da conta a ser criada, formada como um endereço de e-mail (por exemplo, g.: joe@customer.com ) |

Para atualizar um usuário com a API, faça uma postagem HTTP de pares de valores de parâmetros no site URL acima. Os parâmetros que podem ser passados estão descritos abaixo.

| Parâmetro | Descrição |
| --- | --- |
| Senha | A nova senha a ser definida para o usuário. **OBSERVAÇÃO** : A definição de uma senha de SSO, em qualquer caso, fará com que o usuário se torne um usuário de Single Sign-On (SSO). |
| senha antiga | A senha antiga a ser definida para o usuário. Necessário ao atualizar sua própria senha. Opcional para administradores. |
| nome completo | O nome completo do usuário. |
| funções | Uma lista separada por vírgulas de funções que se aplicam a esse usuário. Os usuários que não estiverem disponíveis no site AdminDB serão removidos. |
| último projeto | Uma cadeia de caracteres domain:project que especifica o projeto a ser usado como o último projeto do usuário. |
| último período | Uma cadeia de caracteres mês:ano especificando o período a ser usado como o último período de tempo selecionado pelo usuário. |
| senha de usuário único | Designa se a senha que você está definindo é uma senha de uso único. Valores: True, False. |

## Códigos de retorno

| Código | Descrição |
| --- | --- |
| 200 | Obter sucesso |
| 202 | Atualização bem-sucedida |
| 201 | Criação bem-sucedida |
| 400 | String de API incorreta |
| 500 | Erro interno do servidor |

## Respostas

As respostas são retornadas em JavaScript Object Notation (JSON). As respostas bem-sucedidas incluirão o nome de usuário, o nome completo, as funções e se o usuário está definido para SSO. Veja abaixo um exemplo de resposta:

```
{
"username":"newUser@customer.com",
"roles":"Admin",
"issso":true,
"fullname":"Joe User"
}
```

As respostas que são retornadas em caso de erro simplesmente retornam a mensagem que descreve o erro. Abaixo está um exemplo de uma tentativa de obter informações sobre um usuário que não existe.

```
{
"message":"user newUser@customer.com does not exist"
}
```

## Exemplos de cachos

Os exemplos a seguir usam o Curl para interagir com a API de usuário Apptio. O argumento -data-url-encode para o Curl informa que o próximo argumento na linha de comando é um par de parâmetro/valor que deve ser enviado para Apptio.

Criar usuário:

```
curl -k -u 'api@customer.com:password' --data-urlencode "password=Password" --data-urlencode "fullname=Joe User" --data-urlencode "Roles=Admin" 
https://customer.apptio.com/biit/api/v1/customer.com/users/joe@customer.com//customer.apptio.com/biit/api/v1/customer.com/users/joe@customer.com
```

Editar usuário:

```
curl -k -u 'api@customer.com:password' --data-urlencode "fullname=Joe The Plumber" 
https://customer.apptio.com/biit/api/v1/customer.com/users/joe@customer.com//customer.apptio.com/biit/api/v1/customer.com/users/joe@customer.com
```

Obter usuário:

```
curl -k -u 'api@customer.com:password' 
https://customer.apptio.com/biit/api/v1/customer.com/users/joe@customer.com//customer.apptio.com/biit/api/v1/customer.com/users/joe@customer.com
```
