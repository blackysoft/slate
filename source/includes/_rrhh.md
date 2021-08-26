# Recursos humanos

## Comprobante de vacaciones

Obtiene el comprobante de vacaciones de una solicitud específica en formato PDF o HTML

> Obtener el comprobante de vacaciones para la solicitud id = 26

```python
#TO-DO
```

```shell
#El siguiente ejemplo retorna el comprobante de vacaciones en formato PDF
curl "https://api.gael.cloud/v2/rrhh/vacaciones_comprobante?id=26&formato=pdf" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET \
  --output comprobante_vacaciones.pdf

#El siguiente ejemplo retorna el comprobante de vacaciones en formato HTML
curl "https://api.gael.cloud/v2/rrhh/vacaciones_comprobante?id=26&formato=html" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET
```

```javascript
//TO-DO
```

### HTTPS Request

<aside class="api-endpoint">
    <div class="endpoint-data">
        <i class="label label-get">GET</i>
        <h6>https://api.gael.cloud/v2/rrhh/vacaciones_comprobante</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- 
<b>id</b> | Obligatorio | `int` | *Id de la solicitud de vacaciones * | `null`
<b>formato</b> | Obligatorio | `string` | `pdf` `html` | *Formato del comprobante* | `null`

## Certificado de antigüedad laboral

Obtiene el certificado de antigüedad laboral para un tercero específico, en formato PDF o HTML

> Obtener el certificado de antigüedad laboral para el tercero id = 43

```python
#TO-DO
```

```shell
#El siguiente ejemplo retorna el comprobante de vacaciones en formato PDF
curl "https://api.gael.cloud/v2/rrhh/certificado_laboral?tercero_id=43&formato=pdf" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET \
  --output certificado_antiguedad_laboral.pdf

#El siguiente ejemplo retorna el comprobante de vacaciones en formato HTML
curl "https://api.gael.cloud/v2/rrhh/certificado_laboral?tercero_id=43&formato=html" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET
```

```javascript
//TO-DO
```

### HTTPS Request

<aside class="api-endpoint">
    <div class="endpoint-data">
        <i class="label label-get">GET</i>
        <h6>https://api.gael.cloud/v2/rrhh/certificado_laboral</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- 
<b>tercero_id</b> | Obligatorio | `int` | *Id del tercero * | `null`
<b>formato</b> | Obligatorio | `string` | `pdf` `html` | *Formato del comprobante* | `null`