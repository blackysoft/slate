# Unidad de Control

## Lista Unidades de Control

Lista de todas las unidades de control

> Obtener todas las unidades de control para la empresa con id = 1 y la unidad de negocio con id = 2:

```python
#TO-DO
```

```shell
curl "https://api.gael.cloud/v2/ucontrol/lista" \
  -H "Content-Type: application/json" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET  \
  --data '{"empresaid": 1, "unegocioid": 2}'
```

```javascript
//TO-DO
```

> El ejemplo anterior retorna el siguiente JSON:

```json
{
  "count": 59,
  "data": [
    {
      "id": 3,
      "TProy": false,
      "UNegocioID": 2,
      "GastIng": false,
      "UsuarioID": 1,
      "FechaCreac": "2017-05-19T17:45:30.870Z",
      "Notas": null,
      "EmpresaID": 1,
      "HasFecEjec": false,
      "FecIni": null,
      "FecEjec": null,
      "PerContID": null,
      "Borrado": true,
      "Cop": false,
      "CopID": null,
      "StatusID": 1,
      "Lock": true,
      "TercId": null,
      "HasAna": false,
      "PPresu": false,
      .......
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
<b>empresaid</b> | Opcional | `int` | *Id de la empresa a consultar* | `null`
<b>unegocioid</b> | Opcional | `int` | *Id de la unidad de negocio* | `null`
<b>borrado</b> | Opcional | `bool` | *Incluye registros borrados* | `false`

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
curl "https://api.gael.cloud/v2/ucontrol/detalle" \
  -H "Content-Type: application/json" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET  \
  --data '{"id": 2046}'
```

```javascript
//TO-DO
```

> El ejemplo anterior retorna el siguiente JSON:

```json
{
  "count": 1,
  "data": {
    "id": 2046,
    "Codigo": "XYZ",
    "TProy": true,
    "UNegocioID": 12,
    "GastIng": false,
    "UsuarioID": 2,
    "FechaCreac": "2020-01-25T16:47:53.023Z",
    "Notas": "Desarrollo de plataformas adicionales",
    "EmpresaID": 1,
    "HasFecEjec": true,
    "FecIni": "2020-01-13T00:00:00.000Z",
    "FecEjec": "2020-11-13T00:00:00.000Z",
    "PerContID": null,
    "Borrado": false,
    "Cop": false,
    "CopID": 0,
    "StatusID": 1,
    "Lock": true,
    "TercId": 2138,
    "HasAna": false,
    "PPresu": true,
    "PCotiz": true,
    "PEval": false,
    "OC": true,
    "EG": true,
    "FR": true,
    "NV": true,
    "NI": false,
    "LIQ": false,
    "REM": false,
    "TI": false,
    "Mext": true,
    "Descripc": "Proyecto de Transformación Digital XYZ",
    "TClie": 2,
    "Verif": false,
    "VerifFec": null,
    "Mgr2ID": 0,
    "Forced": false,
    "CantForced": 0,
    "Task": true,
    "Mgr1ID": 0,
    "Mgr3ID": 0,
    "Mgr4ID": 0,
    "tVtaID": 1,
    "tProyAdmID": 1,
    "tProyProdID": 1,
    "ActFij": false,
    "Nombre": "Unidad de control XYZ",
    "Notif": false,
    "ActivFech": "2020-01-25T16:55:22.000Z",
    "ActivUsuarioID": 2,
    "EtapaID": 0,
    "ProyPreStatusID": 0,
    "BloqFech": null,
    "BloqUsuarioID": 0,
    "FinalFech": null,
    "FinalUsuarioID": 0,
    "ArchFech": null,
    "ArchUsuarioID": 0,
    "TNegocioID": 0,
    "NegocioEst": 0,
    "VentaEst": 0,
    "ConcilNotes": null,
    "Prioridad": 0
  }
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
<b>id</b> | Obligatorio | `int` | *Id de la unidad de control a consultar* | 