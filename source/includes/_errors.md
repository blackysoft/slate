# Manejo de errores

## Códigos de error

La API de GAEL utiliza los siguientes códigos de error HTTP:

Código | Significado
---------- | -------
<b>400</b> | Bad Request - La solicitud contiene información errónea
<b>401</b> | Unauthorized - Tu ApiKey no es válida o no la estás enviando correctamente según la sección [Autenticación](#autenticacion)
<b>403</b> | Forbidden - Baneo permanente por uso indebido de api
<b>404</b> | Not Found - El endpoint solicitado no existe
<b>422</b> | Unprocessable Entity - Existe un error de lógica (negocio)
<b>429</b> | Too Many Requests - IP baneada por demasiados [requests seguidos](#rate-limiting)
<b>500</b> | Internal Server Error - Error interno del servidor. Intenta nuevamente más tarde.
<b>503</b> | Service Unavailable - Api temporalmente fuera de servicio. Intenta nuevamente más tarde.

## Objeto "error"

```python
#TO-DO
```

```shell
# Vamos a enviar una ApiKey incorrecta en el header
curl "https://api.gael.cloud/v2/cuenta/login" \
  -H "ApiKey: Api_Key_Incorrecta"
```

```javascript
//TO-DO
```

> Si ocurre un error, la api retornará un objeto JSON similar a este:

```json
{
  "error": {
    "type": "auth_error",
    "code": 1001,
    "message": "ApiKey no válida"
  }
}
```

Si la api retorna cualquier estado que no sea **200 OK**, retornará además un objeto en formato JSON con mayor información acerca del error.

El objeto **error** esta compuesto de la siguiente manera: `error: { type: type, code: code, message: msg }` 

Parámetro  | Tipo | Descripción
--------- | ------- | -----------
**type** | `string` | *Tipo de error* (`internal_error, auth_error, bad_request_error, logic_error, provider_error, rate_limiting_error`)
**code** | `int` | *Código interno del error*
**message** | `string` | *Mensaje descriptivo del error*
