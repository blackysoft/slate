# Compras / Egresos

## Lista de registros

Lista todas las compras y egresos presentes en el módulo de salidas de Gael Gestión, excepto transacciones asociadas a remuneraciones y costos internos.

Solamente podrás consultar:

* Órdenes de compra (`ttrans_id: 1`)
* Órdenes de egreso (`ttrans_id: 2`)
* Rendiciones de compra (`ttrans_id: 18`)
* Rendiciones de egreso (`ttrans_id: 19`)

> Obtener todas las órdenes de compra autorizadas para la empresa con el id = 1

```python
#TO-DO
```

```shell
curl "https://api.gael.cloud/v2/comegr/lista" \
  -H "Content-Type: application/json" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET  \
  --data '{"empresa_id": 1, "ttrans_id": 1, "estado_id": 4 }'
```

```javascript
//TO-DO
```

> El ejemplo anterior retorna el siguiente JSON:

```json
{
  "count": 1,
  "data": [
    {
      "id": 13265,
      "correlativo": "C-0047-21",
      "ttrans_id": 1,
      "creado_por_id": 14,
      "creado_por_nombre": "Andrés Colombino",
      "creado_fecha": "2021-03-10T14:03:26.257Z",
      "estado_id": 4,
      "empresa_id": 1,
      "empresa_nombre": "Empresa XYZ",
      "area_id": 0,
      "area_nombre": null,
      "unegocio_id": 3,
      "unegocio_nombre": "Gastos de administración y venta",
      "ucontrol_id": 6,
      "ucontrol_nombre": "Gastos Generales",
      "categoria_id": 51,
      "categoria_nombre": "Arriendos",
      "operacion_id": 10,
      "operacion_nombre": "Compra Afecta en Otra Moneda",
      "tercero_id": 2177,
      "tercero_nombre": "Sociedad Alto Norte",
      "tercero_rut": "76132765-1",
      "presu_id": 0,
      "presu_nombre": null,
      "valor_iva": 185944,
      "valor_costo": 978652,
      "valor_final": 1164596,
      "rechazada": false,
      "emit_fecha": "2021-04-01T12:35:13.000Z",
      "per_cont": "2102"
    }
  ]
}
```

### HTTPS Request

`GET https://api.gael.cloud/v2/comegr/lista`

### Parámetros

Parámetro | Requerido | Tipo | Formato | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- | ----------- 
<b>empresa_id</b> | Opcional | `int` |  | *Id de la empresa a consultar* | `null`
<b>ttrans_id</b> | Opcional | `int` |  | *Tipo de transacciones a consultar* | `null`
<b>estado_id_desde</b> | Opcional | `int` | | *Estado desde a consultar* | `null`
<b>estado_id_hasta</b> | Opcional | `int` | | *Estado hasta a consultar* | `null`
<b>fech_emit_desde</b> | Opcional | `date` | `DD-MM-YYYY` | *Fecha emisión desde a consultar* | `null`
<b>fech_emit_hasta</b> | Opcional | `date` | `DD-MM-YYYY` | *Fecha emisión hasta a consultar* | `hoy`
<b>area_id</b> | Opcional | `int` | | *Id de la unidad de negocio* | `null`
<b>unegocio_id</b> | Opcional | `int` |  | *Id de la unidad de negocio* | `null`
<b>ucontrol_id</b> | Opcional | `int` |  | *Id de la unidad de control* | `null`
<b>categoria_id</b> | Opcional | `int` |  | *Id de la categoría* | `null`
<b>operacion_id</b> | Opcional | `int` |  | *Id de la operación* | `null`
<b>tercero_id</b> | Opcional | `int` |  | *Id del proveedor* | `null`

<aside class="notice">
    Los parámetros se pueden combinar para filtrar la información según consideres necesario.
</aside>

## Detalle Registro

Entrega detalle más completo de la transacción a consultar

Se entregará la siguiente información:

* Detalle de la transacción
* Glosas que componen la transacción
* Pagos y Documentos asociados a la transacción

> Obtener detalle de la transacción con el id = 13262

```python
#TO-DO
```

```shell
curl "https://api.gael.cloud/v2/comegr/detalle" \
  -H "Content-Type: application/json" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET  \
  --data '{"id": 13262}'
```

```javascript
//TO-DO
```

> El ejemplo anterior retorna el siguiente JSON:

```json
{
  "count": 1,
  "data": {
    "id": 13262,
    "correlativo": "C-0038-21",
    "ttrans_id": 1,
    "ttrans_nombre": "Orden de Compra",
    "creado_por_id": 14,
    "creado_por_nombre": "Andrés Colombino",
    "creado_fecha": "2021-03-10T13:03:10.907Z",
    "estado_id": 7,
    "empresa_id": 1,
    "empresa_nombre": "Empresa Pulenta",
    "area_id": 0,
    "unegocio_id": 3,
    "unegocio_nombre": "Gastos de administración y venta",
    "ucontrol_id": 6,
    "ucontrol_nombre": "Gastos Generales",
    "categoria_id": 141,
    "categoria_nombre": "Dominios",
    "operacion_id": 10,
    "operacion_nombre": "Compra Afecta en Otra Moneda",
    "tercero_id": 32,
    "tercero_nombre": "Dominio Ahora",
    "tercero_rut": "76543817-1",
    "tercero_razsocial": "Dominio Ahora SPA",
    "tercero_direccion": "Av Las Perdices 3611",
    "tercero_comuna": "Peñalolén",
    "tercero_ciudad": "Santiago",
    "tercero_pais": "Chile",
    "contacto_id": 0,
    "contacto_nombre": null,
    "contacto_telefono": null,
    "contacto_email": null,
    "presu_id": 0,
    "presu_nombre": null,
    "tasa_iva": 19,
    "tasa_ret": 11.5,
    "valor_afecto": 12000,
    "valor_exento": 0,
    "valor_iva": 2280,
    "valor_ie": 0,
    "valor_ret": 0,
    "valor_costo": 12000,
    "valor_total": 14280,
    "rechazada": false,
    "per_cont_id": 51,
    "per_cont": "Mar-21",
    "cond_comercial": "30 días contra factura",
    "cond_comercial_detalle": "30 dias contra entrega de factura",
    "mext": true,
    "tasa_cambio": 674.5394,
    "curr_id": 1,
    "curr_nombre": "Dolar Americano",
    "valor_afecto_mext": 17.79,
    "valor_exento_mext": 0,
    "valor_iva_mext": 3.38,
    "valor_ret_mext": 0,
    "valor_total_mext": 21.17
  },
  "detalles": {
    "count": 1,
    "data": [
      {
        "id": 10898,
        "codigo": "",
        "detalle": "Dominio gael.es.pulento.cl",
        "cantidad": 1,
        "veces": 1,
        "precio_unit": 12000.0559,
        "precio_unit_mext": 17.79,
        "descuento_unit": 0,
        "precio_total": 12000.0559,
        "precio_total_mext": 17.79,
        "exento": false
      }
    ]
  },
  "pagos": {
    "count": 1,
    "data": [
      {
        "id": 12184,
        "estado_id": 7,
        "cuota": "1/1",
        "valor_comp": 21.17,
        "fecha_comp": "2021-04-09T13:03:25.000Z",
        "valor_pagado": 21.17,
        "fecha_pagado": "2021-03-15T11:56:01.000Z",
        "curr_nombre": "USD",
        "forma_pago": "Tarjeta de Crédito",
        "cta_origen": "TC BCI USD"
      }
    ]
  },
  "documentos": {
    "count": 1,
    "data": [
      {
        "id": 7763,
        "estado_id": 3,
        "numero": 765441,
        "documento_tipo": "Factura Electrónica",
        "dte_id": 5654,
        "recibido": true,
        "fecha_recibido": "2021-03-12T10:31:12.363Z"
      }
    ]
  }
}
```

### HTTPS Request

`GET https://api.gael.cloud/v2/comegr/detalle`

### Parámetros

Parámetro | Requerido | Tipo | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- 
<b>id</b> | Obligatorio | `int` | *Id de la transacción a consultar* | 