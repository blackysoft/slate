# Unidad de Control

## Lista Unidades de Control

Lista de todas las unidades de control

> Obtener todas las unidades de control para la empresa con id = 1:

```python
#TO-DO
```

```shell
curl "https://api.gael.cloud/v2/ucontrol/lista?empresa_id=1" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET
```

```javascript
//TO-DO
```

> El ejemplo anterior retorna el siguiente JSON:

```json
{
  "count": 24,
  "data": [
    {
      "id": 39,
      "estado_id": 5,
      "nombre": "Proyecto X",
      "tipo": true,
      "unegocio_id": 9,
      "unegocio_nombre": "Negocio XYZ",
      "creado_por_id": 7,
      "creado_por": "Juán Perez",
      "empresa_nombre": "Empresa Pulenta",
      "empresa_id": 1
    },
    ......
  ]
}
```

### HTTPS Request

<aside class="api-endpoint">
    <div class="endpoint-data">
        <i class="label label-get">GET</i>
        <h6>https://api.gael.cloud/v2/ucontrol/lista</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- 
<b>empresa_id</b> | Opcional | `int` | *Id de la empresa a consultar* | `null`


## Detalle Unidad de Control

Entrega detalle más completo de la unidad de control a consultar

> Obtener detalle de la unidad de control con el id = 2046:

```python
#TO-DO
```

```shell
curl "https://api.gael.cloud/v2/ucontrol/detalle?ucontrol_id=2046" \
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
      "id": 2046,
      "estado_id": 1,
      "nombre": "Proyecto X",
      "creado_fecha": "2020-01-25T16:47:53.023Z",
      "descripcion": "Transformación Digital Proyecto X",
      "tipo": true,
      "unegocio_id": 12,
      "unegocio_nombre": "Desarrollos a Medida",
      "usuario_id": 2,
      "empresa_id": 1,
      "empresa_nombre": "Empresa Pulenta",
      "tipo_cliente": 2,
      "mext": true,
      "tercero_id": 2138,
      "activo_por_id": 2,
      "activo_por_nombre": "Juán Perez",
      "activo_fecha": "2020-01-25T16:55:22.000Z"
    }
  ]
}
```

### HTTPS Request

<aside class="api-endpoint">
    <div class="endpoint-data">
        <i class="label label-get">GET</i>
        <h6>https://api.gael.cloud/v2/ucontrol/detalle</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- 
<b>ucontrol_id</b> | Obligatorio | `int` | *Id de la unidad de control a consultar* | 