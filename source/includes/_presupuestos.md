# Presupuestos

## Lista de presupuestos

Lista todos los presupuestos de Gastos o Ventas presentes en el módulo de presupuestos de Gael Gestión.

Se podrán consultar:

* Presupuestos de Gastos (`tipo: 0`)
* Presupuestos de Ventas (`tipo: 1`)

> Obtener todos los presupuestos de Gastos para la empresa con el id = 5

```python
#TO-DO
```

```shell
curl "https://api.gael.cloud/v2/presupuestos/lista?empresa_id=5&tipo=0" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET
```

```javascript
//TO-DO
```

> El ejemplo anterior retorna el siguiente JSON:

```json
{
    "count": 9,
    "data": [
        {
            "id": 1804,
            "numero_documento": null,
            "fecha_emision": null,
            "fecha_vencimiento": null,
            "total_afecto": 150000,
            "total_exento": 0,
            "total_iva": 28500,
            "total_final": 178500,
            "tasa_iva": 19,
            "es_documento_parcial": false,
            "id_tipo_doc": 2,
            "recibido_ok": false,
            "id_recibido_por": null,
            "fecha_recepcion": null,
            "es_moneda_extranjera": false,
            "nombre_documento": "Factura Electrónica",
            "descripcion_moneda": "Peso Chileno",
            "nombre_emitido_por": null,
            "id_periodo_contable": null,
            "periodo_contable": null,
            "id_tercero": 1538,
            "rut_tercero": "77777777-7",
            "razon_social": "Testing Spa",
            "observacion": null,
            "id_operacion": 1,
            "id_moneda": 0,
            "nombre_moneda": "CLP",
            "id_categoria": 561,
            "nombre_categoria": "Transporte",
            "id_tipo_transaccion": 1,
            "id_unidad_control": 151,
            "unidad_control": "Unidad de Control X",
            "tipo_unidad_control": true,
            "id_unidad_negocio": 9,
            "id_area": 0,
            "id_status": 1,
            "id_rcv": 0,
            "id_oc": 4964,
            "correlativo_oc": "C-0352-25",
            "id_status_oc": 4,
            "id_empresa": 1,
            "empresa_nombre": "Empresa X",
            "tipo_venta": "Mixta",
            "id_tipo_compra": 5,
            "anticipo": false,
            "es_factura_cedida": false,
            "id_tercero_cesion": 0
        },
        ......
    ]
}
```

### HTTPS Request

<aside class="api-endpoint">
    <div class="endpoint-data">
        <i class="label label-get">GET</i>
        <h6>https://api.gael.cloud/v2/presupuestos/lista</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Formato | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- | ----------- 
<b>empresa_id</b> | Opcional | `int` |  | *Id de la empresa a consultar* | `null`
<b>tipo</b> | Opcional | `int` |  | *Tipo de presupuesto a consultar* | `null`
<b>estado_id_desde</b> | Opcional | `int` | | *Estado desde a consultar* | `null`
<b>estado_id_hasta</b> | Opcional | `int` | | *Estado hasta a consultar* | `null`
<b>fech_creado_desde</b> | Opcional | `date` | `DD-MM-YYYY` | *Fecha creación desde a consultar* | `null`
<b>fech_creado_hasta</b> | Opcional | `date` | `DD-MM-YYYY` | *Fecha creación hasta a consultar* | `hoy`
<b>fech_emit_desde</b> | Opcional | `date` | `DD-MM-YYYY` | *Fecha emisión desde a consultar* | `null`
<b>fech_emit_hasta</b> | Opcional | `date` | `DD-MM-YYYY` | *Fecha emisión hasta a consultar* | `hoy`
<b>fech_aprob_desde</b> | Opcional | `date` | `DD-MM-YYYY` | *Fecha aprobación desde a consultar* | `null`
<b>fech_aprob_hasta</b> | Opcional | `date` | `DD-MM-YYYY` | *Fecha aprobación hasta a consultar* | `hoy`
<b>fech_cerrado_desde</b> | Opcional | `date` | `DD-MM-YYYY` | *Fecha cierre desde a consultar* | `null`
<b>fech_cerrado_hasta</b> | Opcional | `date` | `DD-MM-YYYY` | *Fecha cierre hasta a consultar* | `hoy`
<b>area_id</b> | Opcional | `int` | | *Id de la unidad de negocio* | `null`
<b>unegocio_id</b> | Opcional | `int` |  | *Id de la unidad de negocio* | `null`
<b>ucontrol_id</b> | Opcional | `int` |  | *Id de la unidad de control* | `null`
<b>tercero_id</b> | Opcional | `int` |  | *Id del proveedor* | `null`
<b>con_detalle</b> | Opcional | `bool` |  | *Incluir detalles de la transacción* | `false`

<aside class="notice">
    Los parámetros se pueden combinar para filtrar la información según consideres necesario.
</aside>



## Detalle Presupuesto

Entrega detalle más completo del presupuesto a consultar

Se entregará la siguiente información:

* Detalle del presupuesto
* Glosas que componen en el presupuesto

> Obtener detalle del presupuesto con el id = 52

```python
#TO-DO
```

```shell
curl "https://api.gael.cloud/v2/presupuestos/detalle?id=52" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET
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
            "id": 52,
            "tipo_presupuesto": false,
            "presu_nombre": "Presupuesto XYZ",
            "creado_por_id": 7,
            "creado_por_nombre": "Alberto Perez",
            "creado_fecha": "2025-02-25T16:28:17.363Z",
            "estado_id": 4,
            "estado": "Autorizado",
            "empresa_id": 1,
            "empresa_nombre": "Testing SpA",
            "area_id": null,
            "area_nombre": null,
            "unegocio_id": 9,
            "unegocio_nombre": "Producción",
            "ucontrol_id": 111,
            "ucontrol_nombre": "Unidad de Control X",
            "valor_proyectado": 97698024,
            "valor_ejecutado": 31922604.744,
            "valor_disponible": 65775419.256,
            "variacion_neto": -65775419.256,
            "porcentaje_variacion": -0.6732,
            "emitido": true,
            "emitido_fecha": "2025-03-21T16:33:06.000Z",
            "emitido_por_id": 7,
            "aprobado": true,
            "aprobado_fecha": "2025-03-22T16:33:23.000Z",
            "aprobado_por_id": 7,
            "aprobado_por_nombre": "Alberto Perez",
            "cerrado": false,
            "cerrado_fecha": null,
            "cerrado_por_id": 0,
            "cerrado_por_nombre": null,
            "archivado": false,
            "rechazado": false,
            "rechazado_fecha": null,
            "rechazado_por_id": 0,
            "razon_rechazo": null,
            "cantidad_cotiz_vinculada": null,
            "ultima_cotiz_id_vinculada": null,
            "per_cont": "2503",
            "moneda_extranjera": false,
            "moneda_extr_nombre": null,
            "valor_moneda_extr": 1
        }
    ],
    "detalles": {
        "count": 1,
        "data": [
            {
                "id": 1465,
                "detalle": "Item 1",
                "prev_cantidad": 1,
                "prev_veces": 1,
                "prev_precio_unit": 97698024,
                "prev_precio_total": 97698024,
                "prev_valor_iva": 0,
                "ejec_cantidad": 1,
                "ejec_veces": 1,
                "ejec_precio_unit": 10822070.654,
                "ejec_precio_total": 10822070.654,
                "ejec_valor_iva": 0,
                "variacion": -86875953.346,
                "ttrans_id": 0,
                "nombre_transaccion": null,
                "codigo": "C-0444-25",
                "categoria": "Categoria 1",
                "categoria_id": 247,
                "operacion": "Compra Internacional",
                "operacion_id": 29,
                "proveedor_nombre": "Proveedor XYZ",
                "proveedor_id": 761,
                "grupo_id": 371,
                "grupo_nombre": "371 | Nombre XYZ",
                "observaciones": null
            }
        ]
    }
}
```

### HTTPS Request

<aside class="api-endpoint">
    <div class="endpoint-data">
        <i class="label label-get">GET</i>
        <h6>https://api.gael.cloud/v2/presupuestos/detalle</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- 
<b>id</b> | Obligatorio | `int` | *Id del presupuesto a consultar* | 