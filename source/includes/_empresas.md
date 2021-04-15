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
    "empresa_nombre": "Empresa Uno",
    "empresa_rut": "55555555-5",
    "empresa_razonsocial": "Empresa Uno SPA",
    "empresa_estado": true
    },
    ...
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
curl "https://api.gael.cloud/v2/empresa/detalle?empresa_id=1" \
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
  "empresa_nombre": "Empresa Uno",
  "empresa_activa": true,
  "empresa_rut": "55555555-5",
  "empresa_razonsocial": "Empresa Uno SpA",
  "empresa_giro": "Buena Actividad",
  "empresa_url": "www.empresauno.com",
  "empresa_direccion": "Av. Siempreviva #1234",
  "empresa_ciudad": "Ciudad",
  "empresa_comuna": "Comuna",
  "empresa_telefono": "123 456 78"
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
<b>empresa_id</b> | Obligatorio | `int` | *Id de la empresa a consultar* | `null`