# Empresas

## Lista de empresas

Lista de todas las empresas

```python
#TO-DO
```

```shell
curl "https://api.gael.cloud/v2/empresa/lista" \
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
  "count": 2,
  "data":[
    {
    "id": 1,
    "Nombre": "Empresa 1",
    "RUT": "55555555-5",
    "RazonSocial": "Empresa 1",
    "Giro": "OTRAS ACTIVIDADES DE SERVICIOS INFORMÁTICOS",
    "URL": "www.url.com",
    "Activo": true
    },
    {
    "id": 1,
    "Nombre": "Empresa 2",
    "RUT": "66666666-6",
    "RazonSocial": "Empresa 2",
    "Giro": "OTRAS ACTIVIDADES DE SERVICIOS INFORMÁTICOS",
    "URL": "www.url2.com",
    "Activo": true
    }
  ]
}
```

### HTTPS Request

<aside class="api-endpoint">
    <div class="endpoint-data">
        <i class="label label-get">GET</i>
        <h6>https://api.gael.cloud/v2/empresa/lista</h6>
    </div>
</aside>

## Detalle de empresa

Entrega detalle más completo de la empresa a consultar


> Obtener detalle de la empresa con el id = 1

```python
#TO-DO
```

```shell
curl "https://api.gael.cloud/v2/empresa/detalle" \
  -H "Content-Type: application/json" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET  \
  --data '{"id": 1}'
```

```javascript
//TO-DO
```

> El ejemplo anterior retorna el siguiente JSON:

```json
{
  "count": 1,
  "data":[
    {
    "id": 1,
    "Nombre": "Empresa 1",
    "RUT": "55555555-5",
    "RazonSocial": "Empresa 1",
    "Giro": "OTRAS ACTIVIDADES DE SERVICIOS INFORMÁTICOS",
    "URL": "www.url.com",
    "Activo": true
    }
  ]
}
```

### HTTPS Request

<aside class="api-endpoint">
    <div class="endpoint-data">
        <i class="label label-get">GET</i>
        <h6>https://api.gael.cloud/v2/empresa/detalle</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- 
<b>id</b> | Obligatorio | `int` | *Id de la empresa a consultar* | `null`