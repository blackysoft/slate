# Contabilidad

## Reporte Auxiliar

Muestra un informe de los comprobantes en formato `PDF` o `HTML`

> Obtener comprobantes entre las fechas 21-06-2021 al 21-07-2021

```python
#TO-DO
```

```shell
#El siguiente ejemplo retorna el reporte en formato PDF
curl "https://api.gael.cloud/v2/contabilidad/auxiliar_reporte?empresa_id=2&cuenta_contable=5&tipo_auxiliar=1&agrupado_documento=false&solo_saldo=false&fecha_desde=21-06-2021&fecha_hasta=21-07-2021&formato=pdf" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET \
  --output reporte_auxiliar.pdf

#El siguiente ejemplo retorna el reporte en formato HTML
curl "https://api.gael.cloud/v2/contabilidad/auxiliar_reporte?empresa_id=2&cuenta_contable=5&tipo_auxiliar=1&agrupado_documento=false&solo_saldo=true&fecha_desde=21-06-2021&fecha_hasta=21-07-2021&id_tercero=32&formato=html" \
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
        <h6>https://api.gael.cloud/v2/contabilidad/auxiliar_reporte</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Formato | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- | ----------- 
<b>empresa_id</b> | Obligatorio | `int` |  | *Id de la empresa* | `null`
<b>formato</b> | Obligatorio | `string` | `pdf` `html` | *Formato del reporte* | `null`
<b>cuenta_contable</b> | Obligatorio | `int` | | *Cuenta Contable a consultar* | `0`
<b>tipo_auxiliar</b> | Obligatorio | `int` | | *Tipo auxiliar en relación a la cuenta contable a consultar* | `0`
<b>solo_saldo</b> | Obligatorio | `bool` |  | *Indica si se muestra sólo el saldo* | `false`
<b>agrupado_documento</b> | Obligatorio | `bool` |  | *Indica si se muestran los registros agrupado por documento* | `false`
<b>id_tercero</b> | Opcional | `int` |  | *Id del tercero* | `0`
<b>fecha_desde</b> | Opcional | `date` | `DD-MM-YYYY` | *Fecha desde* | `null`
<b>fecha_hasta</b> | Opcional | `date` | `DD-MM-YYYY` | *Fecha hasta* | `null`



## Reporte Libro de Compras / Ventas

Muestra un informe de los registros, ya sea documentos de Compra o Venta, en formato `PDF` o `HTML`

> Obtener registros de libro de Compras con período May-21.

```python
#TO-DO
```

```shell
#El siguiente ejemplo retorna el reporte en formato PDF
curl "https://api.gael.cloud/v2/contabilidad/libcompravta?empresa_id=15&periodo=2105&tipo_libro=1&formato=pdf" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET \
  --output libro_compra.pdf

#El siguiente ejemplo retorna el reporte en formato HTML
curl "https://api.gael.cloud/v2/contabilidad/libcompravta?empresa_id=15&periodo=2105&tipo_libro=0&formato=html" \
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
        <h6>https://api.gael.cloud/v2/contabilidad/libcompravta</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Formato | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- | ----------- 
<b>empresa_id</b> | Obligatorio | `int` |  | *Id de la empresa* | `null`
<b>periodo</b> | Obligatorio | `string` | `YYMM` | *Período a consultar* | `null`
<b>formato</b> | Obligatorio | `string` | `pdf` `html` | *Formato del reporte* | `null`
<b>tipo_libro</b> | Obligatorio | `int` | `0` `1` | *Tipo de libro contable a consultar* | `0`

El parámetro **tipo_libro** admite los valores `0` `1`. Estos configuran el reporte de la siguiente manera:

* `tipo_libro=0` Reporte **Libro de Ventas**
* `tipo_libro=1` Reporte **Libro de Compras**


## Reporte Libro de Remuneraciones

Muestra un informe de renumeraciones de sueldo de los trabajdores de la empresa según período en formato `PDF` o `HTML`

> Obtener registros de libro de Remuneraciones con período Ene-21.

```python
#TO-DO
```

```shell
#El siguiente ejemplo retorna el reporte en formato PDF
curl "https://api.gael.cloud/v2/contabilidad/libremun?empresa_id=3&periodo=2101&formato=pdf" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET \
  --output libro_remuneraciones.pdf

#El siguiente ejemplo retorna el reporte en formato HTML
curl "https://api.gael.cloud/v2/contabilidad/libremun?empresa_id=3&periodo=2101&formato=html" \
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
        <h6>https://api.gael.cloud/v2/contabilidad/libremun</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Formato | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- | ----------- 
<b>empresa_id</b> | Obligatorio | `int` |  | *Id de la empresa* | `null`
<b>periodo</b> | Obligatorio | `string` | `YYMM` | *Período a consultar* | `null`
<b>formato</b> | Obligatorio | `string` | `pdf` `html` | *Formato del reporte* | `null`


## Reporte Libro de Honorarios

Obtiene un informe de todos los honorarios según período en formato `PDF` o `HTML`

> Obtener registros de libro de Honorarios con período Jul-21.

```python
#TO-DO
```

```shell
#El siguiente ejemplo retorna el reporte en formato PDF
curl "https://api.gael.cloud/v2/contabilidad/libreten?empresa_id=7&periodo=2107&formato=pdf" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET \
  --output libro_honorarios.pdf

#El siguiente ejemplo retorna el reporte en formato HTML
curl "https://api.gael.cloud/v2/contabilidad/libreten?empresa_id=7&periodo=2107&formato=html" \
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
        <h6>https://api.gael.cloud/v2/contabilidad/libreten</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Formato | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- | ----------- 
<b>empresa_id</b> | Obligatorio | `int` |  | *Id de la empresa* | `null`
<b>periodo</b> | Obligatorio | `string` | `YYMM` | *Período a consultar* | `null`
<b>formato</b> | Obligatorio | `string` | `pdf` `html` | *Formato del reporte* | `null`


## Certificados

Muestra los registros, ya sea certificado de sueldo u honorarios, por año de un trabajador en formato `PDF` o `HTML`

> Obtener certficado de sueldo del trabajador Jason Becker en el año 2021.

```python
#TO-DO
```

```shell
#El siguiente ejemplo retorna el reporte en formato PDF
curl "https://api.gael.cloud/v2/contabilidad/certificados?empresa_id=2&tercero_id=21&certificado=0&año=2021&formato=pdf" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET \
  --output certificado.pdf

#El siguiente ejemplo retorna el reporte en formato HTML
curl "https://api.gael.cloud/v2/contabilidad/certificados?empresa_id=2&tercero_id=21&certificado=1&año=2021&formato=html" \
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
        <h6>https://api.gael.cloud/v2/contabilidad/certificados</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Formato | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- | ----------- 
<b>empresa_id</b> | Obligatorio | `int` |  | *Id de la empresa* | `null`
<b>tercero_id</b> | Obligatorio | `int` |  | *Id del trabajador* | `null`
<b>certificado</b> | Obligatorio | `int` |  | *Certificado a consultar* | `null`
<b>año</b> | Obligatorio | `string` | `YYMM` | *Año a consultar* | `null`
<b>formato</b> | Obligatorio | `string` | `pdf` `html` | *Formato del reporte* | `null`

El parámetro **certificado** admite los valores `0` `1`. Estos configuran el reporte de la siguiente manera:

* `certificado=0` **Certificado de Sueldos**
* `certificado=1` **Certificado de Honorarios**



## Declaraciones Juradas

Obtiene los registros, ya sea para declaración jurada sobre sueldos u honorarios, por año en formato `PDF` o `HTML`

> Obtener DJ 1887 sobre Sueldos en el año 2021.

```python
#TO-DO
```

```shell
#El siguiente ejemplo retorna el reporte en formato PDF
curl "https://api.gael.cloud/v2/contabilidad/decjuradas?empresa_id=3&formulario=1887&año=2021&formato=pdf" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET \
  --output declaracion_jurada.pdf

#El siguiente ejemplo retorna el reporte en formato HTML
curl "https://api.gael.cloud/v2/contabilidad/decjuradas?empresa_id=3&formulario=1887&año=2021&formato=html" \
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
        <h6>https://api.gael.cloud/v2/contabilidad/decjuradas</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Formato | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- | ----------- 
<b>empresa_id</b> | Obligatorio | `int` |  | *Id de la empresa* | `null`
<b>formulario</b> | Obligatorio | `int` |  | *DecTipo formulario DJ a consultar* | `null`
<b>año</b> | Obligatorio | `string` | `YYMM` | *Año a consultar* | `null`
<b>formato</b> | Obligatorio | `string` | `pdf` `html` | *Formato del reporte* | `null`

El parámetro **formulario** admite los siguientes valores:

* `formulario=1887` **Formulario DJ 1887 sobre Sueldos**
* `formulario=1879` **Formulario DJ 1879 sobre Honorarios**