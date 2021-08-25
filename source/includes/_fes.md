# Firma electrónica simple

## Firma de documento individual

Firma electrónicamente un documento en formato PDF, recibido en formato `base64`.

> Firmar documento para usuario con id = 17, para el tipo de documento "Liquidación de sueldo", en ambiente de pruebas:

<aside class="notice">
    Este endpoint deberá recibir <b>obligatoriamente</b>, id_usuario o id_empleado, uno a la vez, <b>nunca juntos</b>.
</aside>
<aside class="notice">
    El largo de los campos <b>documento</b> y <b>documento_firmado</b> dependerá del tamaño del archivo PDF enviado y recibido respectivamente, por lo que el largo del texto, tanto del request como del response, podría ser muy extenso.
</aside>

```python
#TO-DO
```

```shell
curl -i -X POST \
   -H "ApiKey:XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX" \
   -H "Content-Type:application/json" \
   -d \
    '{
      "id_empleado": "1",
      "tipo_documento": "1",
      "documento": "JVBERi0xLjcKCjQgMCBvYmoKPDwKL0JpdHNQZXJDb21wb25lbnQg..........R4cmVmCjk0MzIwCiUlRU9GCg==",
      "sandbox": "true"
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
  "codigo_paquete_fes": "AXC5154",
  "firmas_restantes": 485,
  "es_adicional": false,
  "documento_firmado": "JVBERi0xLjcKCjQgMCBvYmoKPDwKL0JpdHNQZXJD........ydHhyZWYKMTc1NzQ0CiUlRU9GCg=="
}
```

### HTTPS Request

<aside class="api-endpoint">
    <div class="endpoint-data">
        <i class="label label-get">POST</i>
        <h6>https://api.gael.cloud/v2/fes/firma_documento</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- 
<b>id_usuario</b> | Opcional* | `int` | *Id del usuario a consultar. No se envía junto a id_empleado.* | `null`
<b>id_empleado</b> | Opcional* | `int` | *Id del empleado a consultar. No se envía junto a id_usuario.* | `null`
<b>tipo_documento</b> | Obligatorio | `int` | *Tipo de documento a firmar*| `null`
<b>documento</b> | Obligatorio | `string` | Cadena de carateres en `base64`.Documento a firmar, en PDF. |`null`
<b>sandbox</b> | Opcional | `bool` | *Indica si el request se realizará a un ambiente productivo o de prueba* | `false`

El parámetro **tipo_documento** admite los siguientes valores:

* `tipo_documento=1` **Liquidaciones de sueldo**
* `tipo_documento=2` **Certificados de vacaciones**
* `tipo_documento=3` **Contrato de trabajo**
* `tipo_documento=4` **Anexo de contrato de trabajo**
* `tipo_documento=5` **Certificado de antigüedad laboral**

