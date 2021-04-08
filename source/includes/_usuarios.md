# Usuarios

## Detalle de un usuario

Listado de algunas características de un usuario

> Obtener aquellos detalles de un usuario con id = 1:

```python
#TO-DO
```

```shell
curl "https://api.gael.cloud/v2/usuario/detalle" \
  -H "Content-Type: application/json" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET  \
  --data '{"usuarioid": 1 }'
```

```javascript
//TO-DO
```

> El ejemplo anterior retorna el siguiente JSON:

```json
{
  "id": 1,
  "Nombre": "Esteban Rojas",
  "Email": "esteban@gael.cloud",
  .......
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
<b>usuarioid</b> | Obligatorio | `int` | *Id del usuario a consultar* | `null`