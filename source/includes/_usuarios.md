# Usuarios

## Detalle de un usuario

Listado de algunas características de un usuario

> Obtener detalles de un usuario con id = 1:

```python
#TO-DO
```

```shell
curl "https://api.gael.cloud/v2/usuario/detalle?usuario_id=1" \
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
      "nombre": "Juán Perez",
      "nombre_corto": "Juanito",
      "email": "juanito@perez.cl",
      "creado_fecha": "2017-05-15T11:45:13.117Z"
    }
  ]
}
```

### HTTPS Request

<aside class="api-endpoint">
    <div class="endpoint-data">
        <i class="label label-get">GET</i>
        <h6>https://api.gael.cloud/v2/usuario/detalle</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- 
<b>usuario_id</b> | Obligatorio | `int` | *Id del usuario a consultar* | `null`