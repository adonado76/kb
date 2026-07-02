---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "API URL para cargar y editar datos de usuarios en sistemas anteriores a la Administración de Acceso Mejorado"
breadcrumb: []
source_path: "studio/studio/apis/studio_api_url_upload_edit.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# API URL para cargar y editar datos de usuarios en sistemas anteriores a la Administración de Acceso Mejorado

**Se aplica a** : v11.x, v12.0, v12.1

Utilice el sitio URL descrito a continuación para cargar en bloque los datos de los usuarios y editar los datos de los usuarios existentes en los sistemas anteriores aEnhanced Access Administration

## URL

Utilice el siguiente URL para cargar una tabla de usuarios en Apptio :

`https://[instance].apptio.com/biit/api/v1/[domain]/users/[userid]`

Por ejemplo, si tu empresa se llama **abcempresa** y quieres automatizar tu instancia dev, usarías:

`https://[abccompany-dev].apptio.com/biit/api/v1/[abccompany.com]/users/[user@abccomany.com]user@abccomany.com]`

A continuación se describen los atributos utilizados en URL.

| Atributo | Descripción |
| --- | --- |
| Dominio | El dominio del cliente (e. g.: customer.com ) |
| nombre de usuario | El ID de la cuenta a crear, formado como una dirección de correo electrónico (e. g.: joe@customer.com ) |

Para actualizar un usuario con la API, realice un envío HTTP de pares parámetro-valor a la dirección URL. A continuación se describen los parámetros que se pueden pasar.

| Parámetro | Descripción |
| --- | --- |
| contraseña | La nueva contraseña a establecer para el usuario. **NOTA** : Establecer una contraseña de SSO, en cualquier caso, hará que el usuario se convierta en un usuario de Single Sign-On(SSO). |
| contraseñaantigua | La contraseña antigua a establecer para el usuario. Obligatorio para actualizar su propia contraseña. Opcional para administradores. |
| nombre completo | El nombre completo del usuario. |
| roles | Una lista separada por comas de los roles que se aplican a este usuario. Los usuarios no disponibles en AdminDB serán eliminados. |
| últimoproyecto | Una cadena domain:project que especifica el proyecto que se utilizará como último proyecto del usuario. |
| último período | Una cadena mes:año que especifica el periodo a utilizar como último periodo de tiempo seleccionado por el usuario. |
| contraseña de un solo uso | Indica si la contraseña que estás configurando es de un solo uso. Valores: Verdadero, Falso. |

## Códigos de devolución

| Código | Descripción |
| --- | --- |
| 200 | Conseguir el éxito |
| 202 | Actualización completada con éxito |
| 201 | Creación con éxito |
| 400 | Cadena API incorrecta |
| 500 | Error interno del servidor |

## Respuestas

Las respuestas se devuelven en JavaScript Object Notation (JSON). Las respuestas correctas incluirán el nombre de usuario, el nombre completo, los roles y si el usuario está configurado para SSO. A continuación figura un ejemplo de respuesta:

```
{
"username":"newUser@customer.com",
"roles":"Admin",
"issso":true,
"fullname":"Joe User"
}
```

Las respuestas que se devuelven en caso de error, simplemente devuelven el mensaje que describe el error. A continuación se muestra un ejemplo de intento de obtener información sobre un usuario que no existe.

```
{
"message":"user newUser@customer.com does not exist"
}
```

## Ejemplos de rizos

Los siguientes ejemplos utilizan Curl para interactuar con la API de usuario Apptio. El argumento -data-url-encode a Curl le indica que el siguiente argumento de la línea de comandos es un parámetro/valor que debe enviarse a Apptio.

Crear usuario:

```
curl -k -u 'api@customer.com:password' --data-urlencode "password=Password" --data-urlencode "fullname=Joe User" --data-urlencode "Roles=Admin" 
https://customer.apptio.com/biit/api/v1/customer.com/users/joe@customer.com//customer.apptio.com/biit/api/v1/customer.com/users/joe@customer.com
```

Editar usuario:

```
curl -k -u 'api@customer.com:password' --data-urlencode "fullname=Joe The Plumber" 
https://customer.apptio.com/biit/api/v1/customer.com/users/joe@customer.com//customer.apptio.com/biit/api/v1/customer.com/users/joe@customer.com
```

Obtener usuario:

```
curl -k -u 'api@customer.com:password' 
https://customer.apptio.com/biit/api/v1/customer.com/users/joe@customer.com//customer.apptio.com/biit/api/v1/customer.com/users/joe@customer.com
```
