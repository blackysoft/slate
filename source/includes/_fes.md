# Firma electrónica simple

## Firma de documento individual

Firma electrónicamente un documento en formato PDF, recibido en formato `base64`.

> Empleado con id = 3 va a firmar el documento con id = 1453, en ambiente de pruebas:

<aside class="notice">
    El largo de los campos <b>documento</b> (request) y <b>documento_firmado</b> (response) dependerá del tamaño del archivo PDF enviado y recibido respectivamente, por lo que el largo del texto, tanto del request como del response, podría ser muy extenso.
</aside>

```python
#TO-DO
```

```shell
curl -X POST \
   -H "ApiKey: xxxxxxxxxxxxxxxx" \
   -d \
    '{
      "empleado_id": "3"
      "id_doc_firma": "1453",
      "sandbox": "true",
      "documento": "JVBERi0xLjcKKCjQgMCBvYmoKPDwKL0JpdHNQZXJD........ydHhyZWYKMTc1NzQ0CiUlRU9GCg=="
    }' \
 'https://api.gael.cloud/v2/fes/firma_documento'
```

```javascript
//TO-DO
```

> El ejemplo anterior retorna el siguiente JSON:

```json
{
  "cantidad_firmas": 1,
  "mensaje": "Documento firmado exitosamente",
  "codigo_paquete_fes": "FES-5154",
  "firmas_restantes": 485,
  "es_adicional": false,
  "documento_firmado": "JVBERi0xLjcKCjQgMCBvYmoKPDwKL0JpdHNQZXJD........ydHhyZWYKMTc1NzQ0CiUlRU9GCg=="
}
```

### HTTPS Request

<aside class="api-endpoint">
    <div class="endpoint-data">
        <i class="label label-post">POST</i>
        <h6>https://api.gael.cloud/v2/fes/firma_documento</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Descripción | Default
--------- | ------- | ----------- | ----------- | -----------
<b>empleado_id</b> | Opcional | `int` | *Id del empleado firmante del documento*| `null`
<b>usuario_id</b> | Opcional | `int` | *Id del usuario firmante del documento*| `null`
<b>id_doc_firma</b> | Obligatorio | `int` | *Id del documento a firmar* | `null`
<b>sandbox</b> | Opcional | `bool` | *Indica si el request se realizará a un ambiente productivo o de pruebas* | `false`
<b>documento</b> | Obligatorio | `string` | Cadena de carateres en `base64`. Documento a firmar, en PDF. |`null`
