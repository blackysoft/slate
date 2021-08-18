# Documentos

## Lista de documentos de compra

Entrega una lista de documentos de compra, con o sin listado de movimientos, según parámetros de entrada

<aside class="notice">
    Este endpoint entrega información relacionada a <b>documentos de compra</b>, con o sin detalle de movimientos por documento.
</aside>

> Obtener la lista de documentos, <b>con</b> listado de movimientos, para la empresa con id = 1 y fechas desde 01-05-2021, hasta 02-05-2021

```python
#TO-DO
```

```shell
#El siguiente ejemplo retorna la lista de documentos según los filtros indicados
curl "https://api.gael.cloud/v2/documentos/compra/lista?id_empresa=1&fech_emit_desde=01-05-2021&fech_emit_hasta=02-05-2021&con_detalle=true" \
  -H "ApiKey: XXXXXXXXXXXXXXXXXXXXXXXXXXXXX" \
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
      "id": 12351,
      "numero_documento": 223144,
      "fecha_emision": "2021-05-02T00:00:00.000Z",
      "fecha_vencimiento": null,
      "total_afecto": 0,
      "total_exento": 6400,
      "total_iva": 0,
      "total_final": 6400,
      "tasa_iva": 19,
      "es_documento_parcial": true,
      "id_tipo_doc": 4,
      "recibido_ok": true,
      "id_recibido_por": 6,
      "fecha_recepcion": "2021-06-07T12:53:36.120Z",
      "es_moneda_extranjera": false,
      "nombre_documento": "Factura Exenta Electrónica",
      "descripcion_moneda": "Peso Chileno",
      "nombre_emitido_por": "Clark Kent",
      "id_periodo_contable": 21,
      "periodo_contable": "May-21",
      "id_tercero": 581,
      "rut_tercero": "76574879-8",
      "razon_social": "Supermen of America suc. Chile",
      "observacion": null,
      "id_operacion": 2,
      "id_moneda": 0,
      "nombre_moneda": "CLP",
      "id_categoria": 15,
      "nombre_categoria": "Trajes",
      "id_tipo_transaccion": 1,
      "id_unidad_control": 30,
      "unidad_control": "Vestimenta",
      "tipo_unidad_control": true,
      "id_unidad_negocio": 1,
      "id_area": 0,
      "id_status": 3,
      "id_dte": 123144,
      "id_oc": 65477,
      "correlativo_oc": "C-4535-21",
      "id_status_oc": 7,
      "id_empresa": 1,
      "empresa_nombre": "Sastres DC",
      "tipo_venta": "Afecta",
      "id_tipo_compra": 1,
      "anticipo": false,
      "es_factura_cedida": false,
      "id_tercero_cesion": 0,
      "cod_custom": null,
      "detalles": {
        "count": 1,
        "data": [
          {
            "NroLinDet": "1",
            "IndExe": "1",
            "NmbItem": "TRJ",
            "DscItem": "Traje anti kriptonita",
            "QtyItem": "1.0",
            "PrcItem": "6400.0",
            "MontoItem": "6400"
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
        <h6>https://api.gael.cloud/v2/documentos/compra/lista</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Formato | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- | ----------- 
<b>id_empresa</b> | Opcional | `int` |  | *Id de la empresa* | `null`
<b>id_tipo_transaccion</b> | Opcional | `int` |  | *Id tipo transacción* | `null`
<b>estado_id_desde</b> | Opcional | `int` | `0` a `6` | *Id de estado desde* | `0`
<b>estado_id_hasta</b> | Opcional | `int` | `0` a `6` | *Id de estado hasta* | `0`
<b>fech_emit_desde</b> | Opcional | `date` | `DD-MM-YYYY` | *Fecha emisión de documento, desde* | `null`
<b>fech_emit_hasta</b> | Opcional | `date` | `DD-MM-YYYY` | *Fecha emisión de documento, hasta* | `hoy`
<b>id_area</b> | Opcional | `int` |  | *Id del área* | `0`
<b>id_unidad_negocio</b> | Opcional | `int` |  | *Id de la unidad de negocio* | `0`
<b>id_unidad_control</b> | Opcional | `int` |  | *Id de la unidad de control* | `0`
<b>id_categoria</b> | Opcional | `int` |  | *Id de la categoría* | `0`
<b>id_operacion</b> | Opcional | `int` |  | *Id de la operación* | `0`
<b>id_tercero</b> | Opcional | `int` |  | *Id del tercero* | `0`
<b>con_detalle</b> | Opcional | `bool` |  | *Indica si se muestran los detalles del documento* | `false`

## Lista de documentos de venta

Entrega una lista de documentos de venta, con o sin listado de movimientos, según parámetros de entrada

<aside class="notice">
    Este endpoint entrega información relacionada a <b>documentos de venta</b>, con o sin detalle de movimientos por documento.
</aside>

> Obtener la lista de documentos, <b>con</b> listado de movimientos, para la empresa con id = 1 y fechas desde 01-02-2021, hasta 02-02-2021

```python
#TO-DO
```

```shell
#El siguiente ejemplo retorna la lista de documentos según los filtros indicados
curl "https://api.gael.cloud/v2/documentos/venta/lista?id_empresa=1&fech_emit_desde=01-02-2021&fech_emit_hasta=02-02-2021&con_detalle=true" \
  -H "ApiKey: XXXXXXXXXXXXXXXXXXXXXXXXXXXXX" \
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
      "id": 646,
      "numero_documento": 34532,
      "fecha_documento": "2021-02-02T00:00:00.000Z",
      "fecha_vencimiento": null,
      "total_afecto": 3302344,
      "total_exento": 0,
      "total_iva": 627445,
      "total_final": 3929789,
      "tasa_iva": 19,
      "anticipo": false,
      "descuento_documento": 0,
      "descuento_documento_porcent": 0,
      "es_documento_parcial": false,
      "id_tipo_doc": 653,
      "emitido_ok": true,
      "id_emitido_por": 5,
      "nombre_emitido_por": "Elmer Figueroa",
      "fecha_emision": "2021-02-02T11:09:08.837Z",
      "es_moneda_extranjera": false,
      "nombre_documento": "Factura Electrónica",
      "id_periodo_contable": 34,
      "periodo_contable": "Feb-21",
      "id_tercero": 233,
      "rut_tercero": "76100200-K",
      "razon_social": "Torero S A",
      "tercero": false,
      "observacion": null,
      "id_operacion": 12314,
      "id_moneda": 1,
      "nombre_moneda": "CLP",
      "descripcion_moneda": "Peso Chileno",
      "id_nv": 6436,
      "id_status_nv": 7,
      "id_categoria": 76,
      "nombre_categoria": "Venta Cliente",
      "id_tipo_transaccion": 34,
      "id_unidad_control": 768,
      "tipo_unidad_control": true,
      "id_unidad_negocio": 81,
      "id_area": 0,
      "id_status": 3,
      "correlativo_nv": "V-0098-13",
      "recibido_ok": false,
      "id_recibido_por": 2,
      "fecha_recepcion": "2021-02-02T11:09:08.837Z",
      "id_empresa": 1,
      "empresa_nombre": "ONU",
      "id_comprobante_contable": 1231,
      "id_dte": 887,
      "codigo_referencia": null,
      "id_dte_referencia1": 24266,
      "dte_referencia1": "87345379977",
      "fecha_dte_referencia1": "2021-02-02T00:00:00.000Z",
      "razon_dte_referencia1": "ORDEN DE COMPRA CLIENTE",
      "id_dte_referencia2": null,
      "dte_referencia2": null,
      "fecha_dte_referencia2": "2021-02-02T00:00:00.000Z",
      "razon_dte_referencia2": null,
      "id_dte_referencia3": null,
      "dte_referencia3": null,
      "fecha_dte_referencia3": "2021-02-02T00:00:00.000Z",
      "razon_dte_referencia3": null,
      "acteco": 429000,
      "tipo_despacho": null,
      "cedido": false,
      "cedido_a_nombre": null,
      "cedido_a_rut": null,
      "id_tipo_prod_vta": 0,
      "detalles": {
        "count": 1,
        "data": [
          {
            "NroLinDet": "1",
            "NmbItem": "Rosas y motos",
            "DscItem": "Rosas frescas y motos choperas para grabar vídeo clip musical",
            "QtyItem": "1.00",
            "PrcItem": "3302344.00",
            "MontoItem": "3302344"
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
        <h6>https://api.gael.cloud/v2/documentos/venta/lista</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Formato | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- | ----------- 
<b>id_empresa</b> | Opcional | `int` |  | *Id de la empresa* | `null`
<b>id_tipo_transaccion</b> | Opcional | `int` |  | *Id tipo transacción* | `null`
<b>estado_id_desde</b> | Opcional | `int` | `0` a `6` | *Id de estado desde* | `0`
<b>estado_id_hasta</b> | Opcional | `int` | `0` a `6` | *Id de estado hasta* | `0`
<b>fech_emit_desde</b> | Opcional | `date` | `DD-MM-YYYY` | *Fecha emisión de documento, desde* | `null`
<b>fech_emit_hasta</b> | Opcional | `date` | `DD-MM-YYYY` | *Fecha emisión de documento, hasta* | `hoy`
<b>id_area</b> | Opcional | `int` |  | *Id del área* | `0`
<b>id_unidad_negocio</b> | Opcional | `int` |  | *Id de la unidad de negocio* | `0`
<b>id_unidad_control</b> | Opcional | `int` |  | *Id de la unidad de control* | `0`
<b>id_categoria</b> | Opcional | `int` |  | *Id de la categoría* | `0`
<b>id_operacion</b> | Opcional | `int` |  | *Id de la operación* | `0`
<b>id_tercero</b> | Opcional | `int` |  | *Id del tercero* | `0`
<b>con_detalle</b> | Opcional | `bool` |  | *Indica si se muestran los detalles del documento* | `false`

## Reporte DTE

Entrega el DTE asociado al documento en formato `PDF`, `XML`, `JSON` o `HTML`

> Obtener el DTE asociado al documento de compra con id = 6484

```python
#TO-DO
```

```shell
#El siguiente ejemplo retorna el DTE con su copia cedible en formato PDF
curl "https://api.gael.cloud/v2/documentos/reporte?doc_id=6484&is_doc_venta=false&formato=pdf&cedible=2&tipo_papel=0" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET \
  --output dte_cedible.pdf

#El siguiente ejemplo retorna el DTE en formato JSON
curl "https://api.gael.cloud/v2/documentos/reporte?doc_id=6484&is_doc_venta=false&formato=json" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET
```

```javascript
//TO-DO
```

> El ejemplo anterior retorna el siguiente JSON:

```json
{
  "DTE": {
    "version": "1.0",
    "Documento": {
      "ID": "MiPE76385871-16758",
      "Encabezado": {
        "IdDoc": {
          "TipoDTE": "33",
          "Folio": "666",
          "FchEmis": "2021-04-01",
          "TpoTranCompra": "1",
          "TpoTranVenta": "1",
          "FmaPago": "1"
        },
        "Emisor": {
          "RUTEmisor": "76658541-0",
          "RznSoc": "GRUPO PULENTO SPA",
          "GiroEmis": "SERVICIOS INTEGRALES DE INFORMATICA",
          "Telefono": "2 23466527",
          "CorreoEmisor": "ADMINISTRACION@PULENTO.CL",
          "Acteco": "611090",
          "CdgSIISucur": "078817192",
          "DirOrigen": "AVENIDA NUEVA PROVIDENCIA 3652",
          "CmnaOrigen": "PROVIDENCIA",
          "CiudadOrigen": "SANTIAGO"
        },
        "Receptor": {
          "RUTRecep": "76698536-7",
          "RznSocRecep": "EMPRESA XYZ",
          "GiroRecep": "ACTIVIDADES DE CONSULTORIA",
          "DirRecep": "AV LAS CONDES 16751",
          "CmnaRecep": "LAS CONDES",
          "CiudadRecep": "SANTIAGO"
        },
        "Totales": {
          "MntNeto": "60000",
          "TasaIVA": "19.00",
          "IVA": "11400",
          "MntTotal": "71400"
        }
      },
      "Detalle": {
        "NroLinDet": "1",
        "NmbItem": "23096",
        "DscItem": "Ionizador termonuclear marca ACME",
        "QtyItem": "1.00",
        "PrcItem": "60000.00",
        "MontoItem": "60000"
      },
      "TED": {
        "version": "1.0",
        "DD": {
          "RE": "76658541-0",
          "TD": "33",
          "F": "666",
          "FE": "2021-04-01",
          "RR": "76698536-7",
          "RSR": "EMPRESA XYZ",
          "MNT": "71400",
          "IT1": "23096",
          "CAF": {
            "version": "1.0",
            "DA": {
              "RE": "76658541-0",
              "RS": "GRUPO PULENTO SPA",
              "TD": "33",
              "RNG": {
                "D": "666",
                "H": "666"
              },
              "FA": "2021-04-01",
              "RSAPK": {
                "M": "...",
                "E": "Aw=="
              },
              "IDK": "300"
            },
            "FRMA": {
              "_": "...",
              "algoritmo": "SHA1withRSA"
            }
          },
          "TSTED": "2021-04-01T09:32:56"
        },
        "FRMT": {
          "_": "...",
          "algoritmo": "SHA1withRSA"
        }
      },
      "TmstFirma": "2021-04-01T09:32:56"
    },
    "Signature": {
      "xmlns": "http://www.w3.org/2000/09/xmldsig#",
      "SignedInfo": {
        "CanonicalizationMethod": {
          "Algorithm": "http://www.w3.org/TR/2001/REC-xml-c14n-20010315"
        },
        "SignatureMethod": {
          "Algorithm": "http://www.w3.org/2000/09/xmldsig#rsa-sha1"
        },
        "Reference": {
          "URI": "#MiPE76385871-16758",
          "Transforms": {
            "Transform": {
              "Algorithm": "http://www.w3.org/TR/2001/REC-xml-c14n-20010315"
            }
          },
          "DigestMethod": {
            "Algorithm": "http://www.w3.org/2000/09/xmldsig#sha1"
          },
          "DigestValue": "..."
        }
      },
      "SignatureValue": "...",
      "KeyInfo": {
        "KeyValue": {
          "RSAKeyValue": {
            "Modulus": "...",
            "Exponent": "AQAB"
          }
        },
        "X509Data": {
          "X509Certificate":"..."
        }
      }
    }
  }
}
```

### HTTPS Request

<aside class="api-endpoint">
    <div class="endpoint-data">
        <i class="label label-get">GET</i>
        <h6>https://api.gael.cloud/v2/documentos/reporte</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Formato | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- | ----------- 
<b>doc_id</b> | Obligatorio | `int` |  | *Id del documento a consultar* | `null`
<b>is_doc_venta</b> | Obligatorio | `bool` |  | *Documento es de compra o de venta* | `null`
<b>formato</b> | Obligatorio | `string` | `pdf` `html` `json` `xml` | *Formato del reporte* | `null`
<b>cedible</b> | Opcional | `int` | `0` `1` `2` | *Copia cedible o no* | `0`
<b>tipo_papel</b> | Opcional | `int` | `0` `1` | *Formato Papel para el reporte* | `0`

<aside class="notice">
    El parámetro <b>cedible</b> sólo tiene efecto cuando el parámetro <b>formato</b> tiene valor <i>pdf</i> o <i>html</i>
</aside>

El parámetro **cedible** admite los valores `0` `1` `2`. Estos configuran el reporte de la siguiente manera:

* `cedible=0` Reporte de DTE **sin** copia cedible
* `cedible=1` Reporte de DTE **solo** copia cedible
* `cedible=2` Reporte de DTE **con** copia cedible

<aside class="notice">
    Al igual que el parámetro anterior, el parámetro <b>tipo_papel</b> sólo tiene efecto cuando el parámetro <b>formato</b> tiene valor <i>pdf</i> o <i>html</i>
</aside>

El parámetro **tipo_papel** admite los valores `0` `1`. Estos configuran el reporte de la siguiente manera:

* `tipo_papel=0` Reporte de DTE en formato **papel oficio/carta**
* `tipo_papel=1` Reporte de DTE en formato **papel continuo**

## Lista BHE

Entrega lista de boletas de honorarios electrónicas recibidas en el SII

<aside class="notice">
    Para poder utilizar este endpoint, es necesario ingresar la clave del SII de la empresa en GAEL
</aside>

> Obtener la lista de BHE recibidas, para la empresa con id = 1 durante marzo del 2020

```python
#TO-DO
```

```shell
#El siguiente ejemplo retorna la lista de BHE recibidas
curl "https://api.gael.cloud/v2/documentos/bhe/lista?empresa_id=1&periodo=2003" \
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
        <h6>https://api.gael.cloud/v2/documentos/bhe/lista</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Formato | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- | ----------- 
<b>empresa_id</b> | Opcional | `int` |  | *Id de la empresa* | `null`
<b>periodo</b> | Obligatorio | `string` | `YYMM` | *Período a consultar* | `null`



## Reporte BHE

Entrega el reporte en PDF de la boleta de honorarios electrónica recibida en el SII

<aside class="notice">
    Para poder utilizar este endpoint, es necesario ingresar la clave del SII de la empresa en GAEL
</aside>

> Obtener el reporte de la BHE con el código de barras 1111111100044F6C75GA

```python
#TO-DO
```

```shell
#El siguiente ejemplo retorna la BHE en formato PDF
curl "https://api.gael.cloud/v2/documentos/bhe/reporte?empresa_id=1&codigo=1111111100044F6C75GA" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET \
  --output bhe.pdf
```  

```javascript
//TO-DO
```

### HTTPS Request

<aside class="api-endpoint">
    <div class="endpoint-data">
        <i class="label label-get">GET</i>
        <h6>https://api.gael.cloud/v2/documentos/bhe/reporte</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Formato | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- | ----------- 
<b>empresa_id</b> | Opcional | `int` |  | *Id de la empresa* | `null`
<b>codigo</b> | Obligatorio | `string` | | *Código de barras* | `null`

## Reporte Recibo

Muestra un reporte del Recibo asociado en formato `PDF` o `HTML`

> Obtener el recibo asociado con su posvta_id = 2490

```python
#TO-DO
```

```shell
#El siguiente ejemplo retorna el reporte en formato PDF
curl "https://api.gael.cloud/v2/documentos/recibo/reporte?posvta_id=2490&formato=pdf&tipo_papel=1" \
  -H "ApiKey: xxxxxxxxxxxxxxxx" \
  -X GET \
  --output reporte_recibo.pdf

#El siguiente ejemplo retorna el reporte en formato HTML
curl "https://api.gael.cloud/v2/documentos/recibo/reporte?posvta_id=2490&formato=html&tipo_papel=0" \
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
        <h6>https://api.gael.cloud/v2/documentos/recibo/reporte</h6>
    </div>
</aside>


### Parámetros

Parámetro | Requerido | Tipo | Formato | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- | ----------- 
<b>posvta_id</b> | Obligatorio | `int` |  | *Id del recibo a consultar* | `null`
<b>formato</b> | Obligatorio | `string` | `pdf` `html` | *Formato del reporte* | `null`
<b>tipo_papel</b> | Obligatorio | `int` | `0` `1` | *Formato Papel para el reporte* | `0`

<aside class="notice">
    El parámetro <b>tipo_papel</b> sólo tiene efecto cuando el parámetro <b>formato</b> tiene valor <i>pdf</i> o <i>html</i>
</aside>

El parámetro **tipo_papel** admite los valores `0` `1`. Estos configuran el reporte de la siguiente manera:

* `tipo_papel=0` Reporte Recibo en formato **papel oficio/carta**
* `tipo_papel=1` Reporte Recibo en formato **papel continuo**