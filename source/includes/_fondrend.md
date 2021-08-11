# Fondos por rendir

## Reporte de fondos por rendir

Obtener el reporte del fondo por rendir indicado

> Obtener el reporte del fondo por rendir con ID = 1234

```python
#TO-DO
```

```shell
#El siguiente ejemplo retorna el reporte del fondo por rendir en formato PDF
curl "https://api.gael.cloud/v2/fondrend/reporte?id=1234&formato=pdf" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET \
  --output reporte_fondrend.pdf

#El siguiente ejemplo retorna el reporte del fondo por rendir en HTML
curl "https://api.gael.cloud/v2/fondrend/reporte?id=1234&formato=html" \
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
        <h6>https://api.gael.cloud/v2/fondrend/reporte</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- 
<b>id</b> | Obligatorio | `int` | *Id del fondo por rendir* | `null`
<b>formato</b> | Obligatorio | `string` | `pdf` `html` | *Formato del reporte* | `null`