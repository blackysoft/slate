# Unidad de Control

## Lista Unidades de Control

Lista de todas las unidades de control

> Obtener todas las unidades de control para la empresa con id = 1 y la unidad de negocio con id = 2:

```python
#TO-DO
```

```shell
curl "https://api.gael.cloud/v2/ucontrol/lista?empresa_id=1" \
  -H "Content-Type: application/json" \
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
      "id": 3,
      "estado_id": 1,
      "ucontrol_nombre": "Proyecto X",
      "ucontrol_tipo": false,
      "unegocio_id": 2,
      "unegocio_nombre": "Negocio bueno",
      "usuario_id": 2,
      "empresa_id": 1
      ...
    }
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
<b>empresa_id</b> | Obligatorio | `int` | *Id de la empresa a consultar* | `null`

<aside class="notice">
    Los parámetros se pueden combinar para filtrar la información según consideres necesario.
</aside>

## Detalle Unidad de Control

Entrega detalle más completo de la unidad de control a consultar

> Obtener detalle de la unidad de control con el id = 2046:

```python
#TO-DO
```

```shell
curl "https://api.gael.cloud/v2/ucontrol/detalle?ucontrol_id=1" \
  -H "Content-Type: application/json" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET
```

```javascript
//TO-DO
```

> El ejemplo anterior retorna el siguiente JSON:

```json
{
  "id": 1,
  "estado_id": 1,
  "ucontrol_nombre": "Proyecto X",
  "creado_fecha": "2021-01-15T17:38:49.940Z",
  "ucontrol_descripion": "Un proyecto interesante",
  "ucontrol_tipo": false,
  "unegocio_id": 1,
  "unegocio_nombre": "Varios",
  "usuario_id": 1,
  "empresa_id": 1,
  "empresa_nombre": "Empresa Uno",
  "tipo_cliente": 1,
  "mext": false,
  "tercero_id": 15,
  "activo_por_id": 0,
  "activo_por_nombre": "Andrés Colombino",
  "activo_fecha": "2021-01-15T18:05:23.820Z"
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