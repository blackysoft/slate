# Categorías

## Lista Categorías

Lista de todas las categorías

> Obtener todas las categorías para la unidad de control con el id = 4:

```python
#TO-DO
```

```shell
curl "https://api.gael.cloud/v2/categoria/lista?empresa_id=1&unegocio_id=2" \
  -H "Content-Type: application/json" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET
```

```javascript
//TO-DO
```

> El ejemplo anterior retorna el siguiente JSON:

```json
"count": 4,
  "data": [
    {
      "id": 1,
      "categoria_nombre": "Materiales",
      "categoria_tipo": true,
      "ucontrol_id": 1,
      "unegocio_id": 2,
      "empresa_id": 1
    },
    ...
  ]
}
```

### HTTPS Request

<aside class="api-endpoint">
    <div class="endpoint-data">
        <i class="label label-get">GET</i>
        <h6>https://api.gael.cloud/v2/categoria/lista</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- 
<b>empresa_id</b> | Obligatorio | `int` | *Id de la empresa a consultar* | `null`
<b>unegocio_id</b> | Opcional | `int` | *Id de la unidad de negocio* | `null`
<b>ucontrol_id</b> | Opcional | `int` | *Id de la unidad de control* | `null`

<aside class="notice">
    Los parámetros se pueden combinar para filtrar la información según consideres necesario.
</aside>

## Detalle Categoría

Entrega detalle más completo de la categoría a consultar

> Obtener detalle de la categoría con el id = 27:

```python
#TO-DO
```

```shell
curl "https://api.gael.cloud/v2/categoria/detalle?categoria_id=1" \
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
  "categoria_nombre": "Materiales",
  "categoria_tipo": true,
  "categoria_activo": true,
  "ucontrol_id": 1,
  "unegocio_id": 1,
  "empresa_id": 1,
  "asignada": true,
  "creado_por_id": 1,
  "creado_fecha": "2021-02-12T20:20:55.353Z"
}
```

### HTTPS Request

<aside class="api-endpoint">
    <div class="endpoint-data">
        <i class="label label-get">GET</i>
        <h6>https://api.gael.cloud/v2/categoria/detalle</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- 
<b>categoria_id</b> | Obligatorio | `int` | *Id de la categoría a consultar* | 