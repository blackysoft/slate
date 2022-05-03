# Ventas / Ingresos

## Reporte Ventas / Ingresos

Muestra un informe del registro de Venta o de Ingreso asociado en formato `PDF` o `HTML`

> Obtener el reporte asociado al registro Venta/Ingreso con id = 62541

```python
#TO-DO
```

```shell
#El siguiente ejemplo retorna el reporte en formato PDF
curl "https://api.gael.cloud/v2/venting/reporte?id=62541&formato=pdf" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET \
  --output reporte_venting.pdf

#El siguiente ejemplo retorna el reporte en formato HTML
curl "https://api.gael.cloud/v2/venting/reporte?id=62541&formato=html" \
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
        <h6>https://api.gael.cloud/v2/venting/reporte</h6>
    </div>
</aside>


### Parámetros

Parámetro | Requerido | Tipo | Formato | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- | ----------- 
<b>id</b> | Obligatorio | `int` |  | *Id del registro de entrada a consultar* | `null`
<b>formato</b> | Obligatorio | `string` | `pdf` `html` | *Formato del reporte* | `null`

## Crear Registro Venta

Crea transacción de venta / ingreso y obtiene el id de la transacción creada y de sus detalles relacionados

> Para crear un registro, necesitas enviar la información en el body del request de la siguiente manera:

```python
#TO-DO
```

```shell
  curl -X POST \
   -H "ApiKey: xxxxxxxxxxxxxxxx" \
   -H "Content-Type: application/json" \
   -d \
    '{
        "ttrans_id": 4,
        "empresa_id": 1,
        "status_id": 1,
        "usuario_id": 1,
        "tercero_id": 25749,
        "ucontrol_id": 5897,
        "categoria_id": null,
        "periodo": "0522",
        "operacion_id": 13,
        "mext": false,
        "total_afecto": 1763190.00,
        "total_exento": 0,
        "total_retencion": 0,
        "total_iva": 335006.00,
        "total_final": 2098196.00,
        "curr_id": 0,
        "tasa_cambio": 1,
        "notas": "Asociada a cotización XYZ",
        "detalles": {
          "data": [
            {
              "detalle": "Detalle 1",
              "cantidad": 1,
              "veces": 1,
              "precio_unit": 1100110.00,
              "descuento_unit": 0,
              "exento": false,
              "producto_id": 0
            },
            {
              "detalle": "Detalle 2",
              "cantidad": 1,
              "veces": 1,
              "precio_unit": 6565.00,
              "descuento_unit": 0,
              "exento": false,
              "producto_id": 0
            },
            {
              "detalle": "Detalle 3",
              "cantidad": 1,
              "veces": 1,
              "precio_unit": 656515.00,
              "descuento_unit": 0,
              "exento": false,
              "producto_id": 0
            }
          ]
        }
      }' \
  'https://api.gael.cloud/v2/venting/crear'
```

```javascript
//TO-DO
```

> El ejemplo anterior retorna el siguiente JSON:

```json
{
  "nvid": 22506,
  "detalles": [
    {
      "nvdetid": 21257
    },
    {
      "nvdetid": 21258
    },
    {
      "nvdetid": 21259
    }
  ]
}
```

### HTTPS Request

<aside class="api-endpoint">
    <div class="endpoint-data">
        <i class="label label-post">POST</i>
        <h6>https://api.gael.cloud/v2/venting/crear</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Formato | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- | -----------
<b>ttrans_id</b> | Obligatorio | `int` | | *Tipo de transacción*| `null`
<b>empresa_id</b> | Obligatorio | `int` |  | *Id de la empresa* | `null`
<b>status_id</b> | Obligatorio | `int` |  | *Estado de la transacción* | `1`
<b>usuario_id</b> | Obligatorio | `int` |  | *Propietario de la transacción* | `null`
<b>tercero_id</b> | Obligatorio | `int` |  | *Cliente asociado* | `null`
<b>ucontrol_id</b> | Obligatorio | `int` |  | *Unidad de control asociada* | `null`
<b>categoria_id</b> | Opcional | `int` |  | *Categoría asociada* | `null`
<b>periodo</b> | Obligatorio | `string` | `YYMM` | *Período* | `null`
<b>operacion_id</b> | Obligatorio | `int` |  | *Operación para cálculo* | `null`
<b>mext</b> | Opcional | `bool` |  | *Si es en moneda extranjera* | `false`
<b>total_afecto</b> | Opcional | `float` |  | *Valor total afecto* | `0`
<b>total_exento</b> | Opcional | `float` |  | *Valor total exento* | `0`
<b>total_retencion</b> | Opcional | `float` |  | *Valor total retención* | `0`
<b>total_iva</b> | Opcional | `float` |  | *Valor total IVA* | `0`
<b>total_final</b> | Opcional | `float` |  | *Valor total final* | `0`
<b>curr_id</b> | Opcional | `int` |  | *ID de moneda extranjera* | `0`
<b>tasa_cambio</b> | Opcional | `float` |  | *Tasa de cambio de moneda extranjera* | `1`
<b>notas</b> | Opcional | `string` | `(255)` | *Notas o instrucciones adicionales* | `null`

El parámetro **ttrans_id** admite los siguientes valores:

* `ttrans_id=4` **Nota de Venta**

El parámetro **status_id** admite los siguientes valores:

* `status_id=1` **Guardado (Sin Emitir)**

### Parámetros Detalles
Parámetro | Requerido | Tipo | Formato | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- | -----------
<b>detalle</b> | Obligatorio | `string` | `(250)` | *Descripción del item* | `null`
<b>cantidad</b> | Obligatorio | `int` |  | *Cantidad* | `0`
<b>veces</b> | Opcional | `int` |  | *Veces* | `1`
<b>precio_unit</b> | Obligatorio | `float` |  | *Precio unitario* | `null`
<b>descuento_unit</b> | Opcional | `float` | `%` | *Descuento unitario* | `0`
<b>exento</b> | Opcional | `bool` |  | *Item es exento* | `false`
<b>producto_id</b> | Opcional | `int` |  | *Producto asociado* | `0`

<aside class="notice">
    El valor total de cada detalle <b>no es necesario</b> ya que se calcula automáticamente en base a las cantidades y precios unitarios
</aside>