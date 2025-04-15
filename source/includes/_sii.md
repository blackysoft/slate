# SII

## Lista BHE

Entrega lista de boletas de honorarios electrónicas recibidas en el SII

<aside class="notice">
    Para poder utilizar este endpoint, es necesario ingresar la clave del SII de la empresa en Gael Cloud
</aside>

> Obtener la lista de BHE recibidas, para la empresa con id = 1 durante marzo del 2020

```python
#TO-DO
```

```shell
#El siguiente ejemplo retorna la lista de BHE recibidas
curl "https://api.gael.cloud/v2/integrations/sii/bhe_resumen?empresa_id=1&periodo=0320" \
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
  "data": [
    {
      "numero": "44",
      "estado": "Vigente",
      "estado_cod": "N",
      "estado_id": 1,
      "fecha": "2020-03-30T03:00:00.000Z",
      "rut_emisor": "11111111-1",
      "nombre_emisor": "RICHIE SAMBORA",
      "es_soc_profesional": false,
      "cod_barras": "1111111100044F6C75GA",
      "honorarios_brutos": 111111,
      "honorarios_retenidos": 11944,
      "honorarios_liquidos": 99167
    },
    {
      "numero": "6",
      "estado": "Vigente",
      "estado_cod": "N",
      "estado_id": 1,
      "fecha": "2020-03-31T03:00:00.000Z",
      "rut_emisor": "55555555-5",
      "nombre_emisor": "NUNO BETTENCOURT",
      "es_soc_profesional": false,
      "cod_barras": "5555555500006M821E3B",
      "honorarios_brutos": 616246,
      "honorarios_retenidos": 66246,
      "honorarios_liquidos": 550000
    }
  ],
  "totales": {
    "honorarios": 727357,
    "retencion_emisor": 0,
    "retencion_receptor": 78190,
    "liquido": 649167
  }
}
```

### HTTPS Request

<aside class="api-endpoint">
    <div class="endpoint-data">
        <i class="label label-get">GET</i>
        <h6>https://api.gael.cloud/v2/integrations/sii/bhe_resumen</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Formato | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- | ----------- 
<b>empresa_id</b> | Opcional | `int` |  | *Id de la empresa* | `null`
<b>periodo</b> | Obligatorio | `string` | `MMYY` | *Período a consultar* | `null`

## Reporte BHE

Entrega el reporte en PDF *(base64)* de la boleta de honorarios electrónica recibida en el SII

<aside class="notice">
    Para poder utilizar este endpoint, es necesario ingresar la clave del SII de la empresa en Gael Cloud
</aside>

> Obtener el reporte de la BHE con el código de barras 1111111100044F6C75GA

```python
#TO-DO
```

```shell
#El siguiente ejemplo retorna la BHE en formato PDF (base64)
curl "https://api.gael.cloud/v2/integrations/sii/bhe_reporte?empresa_id=1&codigo=1111111100044F6C75GA" \
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
      "pdf": "JVBERi0xLjMKxOGE4MGJkMzc2YmE..."
    }
  ]
}
```

### HTTPS Request

<aside class="api-endpoint">
    <div class="endpoint-data">
        <i class="label label-get">GET</i>
        <h6>https://api.gael.cloud/v2/integrations/sii/bhe_reporte</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Formato | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- | ----------- 
<b>empresa_id</b> | Opcional | `int` |  | *Id de la empresa* | `null`
<b>codigo</b> | Opcional | `string` | | *Código de barras* | `null`
<b>docid</b> | Opcional | `int` | | *ID Documento de Compra* | `null`