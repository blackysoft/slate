# Categorías

## Lista Categorías

Lista de todas las categorías

> Obtener todas las categorías para la unidad de control con el id = 4:

```python
#TO-DO
```

```shell
curl "https://api.gael.cloud/v2/categoria/lista" \
  -H "Content-Type: application/json" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET  \
  --data '{"ucontrolid": 4}'
```

```javascript
//TO-DO
```

> El ejemplo anterior retorna el siguiente JSON:

```json
"count": 4,
  "data": [
    {
      "id": 31,
      "Categoria": "Intereses",
      "Tipo": true,
      "ProyectoID": 4,
      "UnegocioID": 2,
      "ContCtaID": 150,
      "EmpresaID": 1,
      "Activo": true
    },
    {
      "id": 32,
      "Categoria": "Comisiones Bancarias",
      "Tipo": true,
      "ProyectoID": 4,
      "UnegocioID": 2,
      "ContCtaID": 154,
      "EmpresaID": 1,
      "Activo": true
    },
    {
      "id": 33,
      "Categoria": "Otros Gastos Bancarios",
      "Tipo": true,
      "ProyectoID": 4,
      "UnegocioID": 2,
      "ContCtaID": 154,
      "EmpresaID": 1,
      "Activo": true
    },
    {
      "id": 96,
      "Categoria": "Comisiones TC",
      "Tipo": true,
      "ProyectoID": 4,
      "UnegocioID": 2,
      "ContCtaID": 154,
      "EmpresaID": 1,
      "Activo": true
    }
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
<b>empresaid</b> | Opcional | `int` | *Id de la empresa a consultar* | `null`
<b>unegocioid</b> | Opcional | `int` | *Id de la unidad de negocio* | `null`
<b>ucontrolid</b> | Opcional | `int` | *Id de la unidad de control* | `null`
<b>borrado</b> | Opcional | `bool` | *Incluye registros borrados* | `false`

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
curl "https://api.gael.cloud/v2/categoria/detalle" \
  -H "Content-Type: application/json" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET  \
  --data '{"id": 27}'
```

```javascript
//TO-DO
```

> El ejemplo anterior retorna el siguiente JSON:

```json
{
  "count": 1,
  "data": {
    "id": 27,
    "Categoria": "Software",
    "Tipo": true,
    "ProyectoID": 1,
    "UnegocioID": 1,
    "ContCtaID": 57,
    "EmpresaID": 1,
    "Activo": true,
    "Egr": true,
    "VisTrans": true,
    "VisRem": false,
    "VisPresu": true,
    "VisTi": false,
    "VisFR": false,
    "Asignada": true,
    "Borrado": false,
    "CreadoPorID": 0,
    "CreadoFecha": "2020-04-28T20:20:55.353Z"
  }
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
<b>id</b> | Obligatorio | `int` | *Id de la categoría a consultar* | 