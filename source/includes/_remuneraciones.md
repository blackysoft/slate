# Remuneraciones

## Reporte Liquidación de sueldo

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


## Reporte Liquidación de sueldo masivo

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

## Detalle Liquidación de sueldo

Entrega detalle completo de la liquidación de sueldo solicitada

Este endpoint posee tres posibles combinaciones de parámetros, todas devolviendo la información de <b>una sola liquidación</b>:

* <b>Solo ID de remuneración</b>, no es necesario enviar los demás parámetros
* <b>Período contable + RUT del trabajador + ID Empresa</b>, no es necesario enviar ID de remuneración
* <b>Período contable + ID del trabajador + ID Empresa</b>, no es necesario enviar ID de remuneración

> Obtener detalle de la liquidación para el usuario RUT = 13866125-5, ID empresa = 1 y período contable = febrero de 2021

```python
#TO-DO
```

```shell
curl "https://api.gael.cloud/v2/remuneraciones/detalle?periodo=0221&empresa_id=1&rut_empl=13866125-5" \
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
  "data":[
    {
      "correlativo": "S-0069-21",
      "per_cont": "Feb-21",
      "empresa_nombre": "Stark Industries",
      "empresa_rut": "76845691-0",
      "trabajador_nombre": "James Rhodes",
      "trabajador_cargo": "Falcon",
      "trabajador_rut": "13866125-5",
      "trabajador_trab_desde": "2001-07-13T00:00:00.000Z",
      "trabajador_contrato": "Indefinido",
      "trabajador_email": "jrhodes@starkindustries.com",
      "dias_base": 30,
      "ausencias": 0,
      "dias_trabajados": 30,
      "afp": "AFP Avengers",
      "afp_tasa_porc": 11.45,
      "salud": "Stark",
      "utm": 52005,
      "uf": 29709.83,
      "cargas": 2,
      "apv": null,
      "cotiz": 0,
      "mutual": "ISL (Sin Mutual)",
      "ccaf": null,
      "sueldo_base": 1500000,
      "sueldo_proporcional": 1500000,
      "atrasos": 0,
      "horas_extra": 0,
      "horas_extra_monto": 0,
      "gratifcacion_legal": 129240,
      "total_bonificaciones": 0,
      "sueldo_imponible": 1629240,
      "movilizacion": 50000,
      "colacion": 50000,
      "viatico": 0,
      "asignacion_familiar": 0,
      "total_no_imponible": 100000,
      "total_haberes": 1729240,
      "sueldo_tributable": 1263214,
      "prevision": 186548,
      "apv_monto": 0,
      "salud_monto": 114047,
      "adicional_salud": 60944,
      "impuesto_unico": 22446,
      "seguro_cesantia": 9775,
      "total_descs_prev": 393760,
      "sueldo_liquido": 1335480,
      "total_remuneracion": 1335480,
      "anticipos": 0,
      "prestamos": 0,
      "otros_descs": 0,
      "remuneracion_liquida": 1335480,
      "desc_fondo_rendir": 0,
      "total_descs_final": 0,
      "liquido_pago": 1335480,
      "costo_empresa": 1815101,
      "fecha_emision": "2021-02-28T16:22:54.000Z",
      "nombre_emisor": "Pepper Pots",
      "unegocio_nombre": "Gastos de administración y venta",
      "categoria_nombre": "Remuneraciones",
      "ucontrol_nombre": "Remuneraciones",
      "bonifs_descs":{
        "count": 0,
        "data":[
        ]
      },
      "pagos":{
        "count": 1,
        "data":[
          {
            "estado": "Cobrado",
            "monto": 1335480,
            "fecha_pago": "2021-02-28T15:43:49.000Z",
            "detalle": "Transf. Masiva cta. Banco  N°972981206"
          }
        ]
      }
    }
  ]
}
```

### HTTPS Request

<aside class="api-endpoint">
    <div class="endpoint-data">
        <i class="label label-get">GET</i>
        <h6>https://api.gael.cloud/v2/remuneraciones/detalle</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- 
<b>remun_id</b> | Obligatorio* | `int` | *Id de la remuneración a consultar* | 
<b>periodo</b> | Obligatorio* | `int` | *Período contable en el formato `MMYY`* | 
<b>empresa_id</b> | Obligatorio* | `int` | *Id de la empresa a consultar* | 
<b>rut_empl</b> | Obligatorio* | `string` | *RUT del empleado a consultar, sin puntos con guión* | 
