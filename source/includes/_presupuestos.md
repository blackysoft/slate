# Presupuestos

## Lista de presupuestos

Lista todos los presupuestos de Gastos o Ventas presentes en el módulo de presupuestos de Gael Gestión.

Se podrán consultar:

* Presupuestos de Gastos (`tipo: 0`)
* Presupuestos de Ventas (`tipo: 1`)

> Obtener todos los presupuestos de Ventas para la empresa con el id = 5

```python
#TO-DO
```

```shell
curl "https://api.gael.cloud/v2/presupuestos/lista?empresa_id=5&tipo=1" \
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
	        "id": 12345,
	        "tipo_presupuesto": true,
	        "presu_nombre": "Evento Juego Entretenido",
	        "creado_por_id": 64,
	        "creado_por_nombre": "George Lynch",
	        "creado_fecha": "2021-08-03T17:54:35.027Z",
	        "estado_id": 4,
	        "estado": "Cerrado",
	        "empresa_id": 1,
	        "empresa_nombre": "Empresa XYZ",
	        "area_id": 0,
	        "area_nombre": null,
	        "unegocio_id": 3,
	        "unegocio_nombre": "Start Labs",
	        "ucontrol_id": 123,
	        "ucontrol_nombre": "Feria Start",
	        "valor_proyectado": 4769000,
	        "valor_ejecutado": 4769000,
	        "valor_provisionado": null,
	        "valor_neto_real": 4769000,
	        "valor_iva": 637750.2,
	        "valor_final": 11146502.2,
	        "variacion_neto": 0,
	        "variacion_bruto": 0,
	        "porcentaje_variacion": 0,
	        "emitido": true,
	        "emitido_fecha": "2021-08-03T17:57:59.000Z",
	        "emitido_por_id": 2,
	        "aprobado": true,
	        "aprobado_fecha": "2021-08-03T18:00:02.000Z",
	        "aprobado_por_id": 2,
	        "aprobado_por_nombre": "Andrés Colombino",
	        "cerrado": true,
	        "cerrado_fecha": "2021-08-05T18:13:56.000Z",
	        "cerrado_por_id": 2,
	        "cerrado_por_nombre": "Andrés Colombino",
	        "archivado": true,
	        "rechazado": false,
	        "rechazado_fecha": null,
	        "rechazado_por_id": 0,
	        "razon_rechazo": null,
	        "cantidad_cotiz_vinculada": 1,
	        "ultima_cotiz_id_vinculada": 123456,
	        "per_cont": "2108",
	        "moneda_extranjera": false,
	        "moneda_extr_nombre": null,
	        "valor_moneda_extr": null
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
<b>fech_rech_desde</b> | Opcional | `date` | `DD-MM-YYYY` | *Fecha rechazado desde a consultar* | `null`
<b>fech_rech_hasta</b> | Opcional | `date` | `DD-MM-YYYY` | *Fecha rechazado hasta a consultar* | `hoy`
<b>area_id</b> | Opcional | `int` | | *Id de la unidad de negocio* | `null`
<b>unegocio_id</b> | Opcional | `int` |  | *Id de la unidad de negocio* | `null`
<b>ucontrol_id</b> | Opcional | `int` |  | *Id de la unidad de control* | `null`
<b>tercero_id</b> | Opcional | `int` |  | *Id del proveedor* | `null`
<b>moneda_extranjera</b> | Opcional | `bool` |  | *Si presupuesto usa moneda extranjera* | `false`
<b>con_detalle</b> | Opcional | `bool` |  | *Incluir detalles de la transacción* | `false`

<aside class="notice">
    Los parámetros se pueden combinar para filtrar la información según consideres necesario.
</aside>



## Detalle Presupuesto

Entrega detalle más completo del presupuesto a consultar

Se entregará la siguiente información:

* Detalle del presupuesto
* Glosas que componen en el presupuesto

> Obtener detalle del presupuesto con el id = 12345

```python
#TO-DO
```

```shell
curl "https://api.gael.cloud/v2/presupuestos/detalle?id=12345" \
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
	        "id": 12345,
	        "tipo_presupuesto": true,
	        "presu_nombre": "Evento Juego Entretenido",
	        "creado_por_id": 64,
	        "creado_por_nombre": "George Lynch",
	        "creado_fecha": "2021-08-03T17:54:35.027Z",
	        "estado_id": 4,
	        "estado": "Cerrado",
	        "empresa_id": 1,
	        "empresa_nombre": "Empresa XYZ",
	        "area_id": 0,
	        "area_nombre": null,
	        "unegocio_id": 3,
	        "unegocio_nombre": "Start Labs",
	        "ucontrol_id": 123,
	        "ucontrol_nombre": "Feria Start",
	        "valor_proyectado": 4769000,
	        "valor_ejecutado": 4769000,
	        "valor_provisionado": null,
	        "valor_neto_real": 4769000,
	        "valor_iva": 637750.2,
	        "valor_final": 11146502.2,
	        "variacion_neto": 0,
	        "variacion_bruto": 0,
	        "porcentaje_variacion": 0,
	        "emitido": true,
	        "emitido_fecha": "2021-08-03T17:57:59.000Z",
	        "emitido_por_id": 2,
	        "aprobado": true,
	        "aprobado_fecha": "2021-08-03T18:00:02.000Z",
	        "aprobado_por_id": 2,
	        "aprobado_por_nombre": "Andrés Colombino",
	        "cerrado": true,
	        "cerrado_fecha": "2021-08-05T18:13:56.000Z",
	        "cerrado_por_id": 2,
	        "cerrado_por_nombre": "Andrés Colombino",
	        "archivado": true,
	        "rechazado": false,
	        "rechazado_fecha": null,
	        "rechazado_por_id": 0,
	        "razon_rechazo": null,
	        "cantidad_cotiz_vinculada": 1,
	        "ultima_cotiz_id_vinculada": 123456,
	        "per_cont": "2108",
	        "moneda_extranjera": false,
	        "moneda_extr_nombre": null,
	        "valor_moneda_extr": null,
	        "detalles":
	        {
	            "count": 14,
	            "data": [
		            {
		                "id": 123,
		                "detalle": "Consolas Videojuegos",
		                "prev_cantidad": 10,
		                "prev_veces": 1,
		                "prev_precio_unit": 5200000,
		                "prev_precio_total": 5298800,
		                "prev_valor_iva": 98800,
		                "ejec_cantidad": 10,
		                "ejec_veces": 1,
		                "ejec_precio_unit": 5200000,
		                "ejec_precio_total": 5298800,
		                "ejec_valor_iva": 98800,
		                "variacion": 0,
		                "ttrans_id": 1,
		                "nombre_transaccion": "Compra",
		                "codigo": null,
		                "categoria": "Equipos",
		                "categoria_id": 15,
		                "operacion": "Compra Afecta",
		                "operacion_id": 1,
		                "proveedor_nombre": null,
		                "proveedor_id": null,
		                "grupo_id": 122,
		                "grupo_nombre": "122 | Equipos",
		                "observaciones": null
		            },
	            	......
	        	]
	        }
	    }
    ]
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