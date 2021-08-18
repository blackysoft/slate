# Remuneraciones

## Reporte Liquidación de Sueldo

Obtener la liquidación de sueldo de un trabajador en formato PDF o HTML

> Obtener el reporte de liquidación de sueldo de la remuneración con id = 13018:

```python
#TO-DO
```

```shell
#El siguiente ejemplo retorna el reporte de liquidación de sueldo en formato PDF
curl "https://api.gael.cloud/v2/remuneraciones/reporte?remun_id=13018&formato=pdf" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET \
  --output reporte_remuneracion.pdf

#El siguiente ejemplo retorna el reporte de liquidación de sueldo en HTML
curl "https://api.gael.cloud/v2/remuneraciones/reporte?remun_id=13018&formato=html" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET
```

```javascript
//TO-DO
```

### HTTPS Request

<aside class="api-endpoint">
    <div class="endpoint-data">
        <i class="label label-get">GET</i>
        <h6>https://api.gael.cloud/v2/remuneraciones/reporte</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- 
<b>remun_id</b> | Obligatorio | `int` | *Id de la liquidación de sueldo* | `null`
<b>formato</b> | Obligatorio | `string` | `pdf` `html` | *Formato del reporte* | `null`


## Reporte Liquidación de Sueldo Masivo

Obtener todas las liquidaciones de sueldo para una empresa y período determinado.

<aside class="notice">
  Este endpoint retorna un archivo comprimido en formato <b>.zip</b> con todas las liquidaciones de sueldo en formato <b>.pdf</b> generadas para el período y empresa solicitadas.
  <br>
  <br>
  Las remuneraciones se encontrarán agrupadas por unidad de control en diferentes carpetas.
</aside>

> Obtener las liquidaciones de sueldo de Enero 2021 para la empresa con el id = 1:

```python
#TO-DO
```

```shell
curl "https://api.gael.cloud/v2/remuneraciones/reporte_masivo?periodo=2101&empresa_id=1" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET \
  --output Remuneraciones_Enero21.zip
```

```javascript
//TO-DO
```

> El ejemplo anterior retorna un archivo .zip con el siguiente contenido:

```plaintext

|-Proyecto A1
 | |- Johnny Gioeli.pdf
 | |- Jarzombek Bobby.pdf
 | |- Pesch Doro.pdf
 | |- Lynch George.pdf
 | |- Van Halen Alex.pdf
 |-Proyecto A2
 | |- Gossow Angela.pdf
 | |- Becker Jason.pdf
 |-Proyecto A3
 | |- Allen Russell.pdf
 | |- Rullo Jason.pdf
```

### HTTPS Request

<aside class="api-endpoint">
    <div class="endpoint-data">
        <i class="label label-get">GET</i>
        <h6>https://api.gael.cloud/v2/remuneraciones/reporte_masivo</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Formato | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- | ----------- 
<b>periodo</b> | Obligatorio | `string` | `YYMM` | *Período a consultar* | `null`
<b>empresa_id</b> | Obligatorio | `int` |  | *Id de la empresa a consultar* | `null`