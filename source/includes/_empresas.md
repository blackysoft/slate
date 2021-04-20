# Empresas

## Lista de empresas

Lista de todas las empresas **activas**

```python
#TO-DO
```

```shell
curl "https://api.gael.cloud/v2/empresa/lista" \
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
      "id": 1,
      "nombre": "Empresa Pulenta",
      "rut": "76658632-5",
      "razon_social": "Empresa Pulenta SpA",
      "giro": "OTRAS ACTIVIDADES DE SERVICIOS INFORMÁTICOS"
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
curl "https://api.gael.cloud/v2/empresa/detalle?empresa_id=1" \
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
      "id": 1,
      "nombre": "Empresa Pulenta",
      "rut": "76658632-5",
      "razon_social": "Empresa Pulenta SpA",
      "giro": "OTRAS ACTIVIDADES DE SERVICIOS INFORMÁTICOS",
      "activa": true,
      "url": "www.empresapulenta.cl",
      "direccion": "Av Las Condes #6541",
      "ciudad": "Santiago",
      "comuna": "Las Condes",
      "telefono": "21892-1258"
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
<b>empresa_id</b> | Obligatorio | `int` | *Id de la empresa a consultar* | `null`