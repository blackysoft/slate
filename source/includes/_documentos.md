# Documentos

## Lista de DTE

Entrega una lista de documentos detallados, con o sin listado de movimientos, según parámetros de entrada

> Obtener la lista de documentos, con listado de movimientos, para la empresa con id = 1 y fechas desde 01-04-2021, hasta 05-04-2021

```python
#TO-DO
```

```shell
#El siguiente ejemplo retorna la lista de DTE según los filtros indicados
curl "http://localhost:3001/v2/documentos/lista?id_empresa=1&fech_emit_desde=01-04-2021&fech_emit_hasta=05-04-2021&con_detalle=true" \
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
      "id": 123,
      "id_oc": 1234596,
      "numero_documento": 99875,
      "fecha_emision": "2021-04-01T00:00:00.000Z",
      "fecha_vencimiento": null,
      "total_afecto": 100000,
      "total_excento": 0,
      "total_iva": 19000,
      "total_final": 119000,
      "es_documento_parcial": true,
      "id_tipo_doc": 2,
      "recepcion_ok": true,
      "id_recibido_por": 6,
      "fecha_recepcion": "2021-04-13T17:16:43.523Z",
      "es_moneda_extranjera": false,
      "id_moneda": 0,
      "nombre_documento": "Factura Electrónica",
      "nombre": "Steve Rogers",
      "descripcion_moneda": "Peso Chileno",
      "id_periodo_contable": 20,
      "rut_tercero": "12345678-9",
      "razon_social": "Stars & Stripres CO.",
      "periodo_contable": "Abr-21",
      "id_tercero": 123,
      "tasa_iva": 19,
      "observacion": null,
      "id_operacion": 1,
      "moneda": "CLP",
      "id_categoria": 5,
      "nombre_categoria": "Elementos de Protección Personal",
      "id_tipo_transaccion": 1,
      "unidad_control": "AVG",
      "tipo_unidad_control": true,
      "id_unidad_negocio": 1,
      "id_area": 0,
      "id_unidad_control": 30,
      "id_status": 2,
      "id_dte": 21231,
      "correlativo_oc": "C-12345-15",
      "id_status_oc": 4,
      "id_empresa": 1,
      "empresa_nombre": "Stark Industries",
      "tipo_venta": "Afecta",
      "id_tipo_compra": 1,
      "anticipo": false,
      "es_factura_cedida": false,
      "id_tercero_cesion": 0,
      "detalles":{
        "count": 1,
        "data":[
          {
            "NroLinDet": "1",
            "CdgItem":{
              "TpoCodigo": "INT1",
              "VlrCodigo": "123456789"
            },
            "NmbItem": "Escudo vibranium diseño estrella",
            "QtyItem": "2.00",
            "UnmdItem": "Unidad",
            "PrcItem": "1390",
            "MontoItem": "50000"
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
        <h6>https://api.gael.cloud/v2/documentos/lista</h6>
    </div>
</aside>

### Parámetros

Parámetro | Requerido | Tipo | Formato | Descripción | Default
--------- | ------- | ----------- | ----------- | ----------- | ----------- 
<b>con_detalle</b> | Opcional | `bool` |  | *Parámetro que indica si se requiere el detalle de los movimientos del documento* | `false`
<b>id_empresa</b> | Opcional | `int` |  | *Id de la empresa* | `null`
<b>id_tipo_transaccion</b> | Opcional | `int` |  | *Id tipo transacción* | `null`
<b>estado_id_desde</b> | Opcional | `int` | `0` a `9` | *Id de estado desde* | `0`
<b>estado_id_hasta</b> | Opcional | `int` | `0` a `9` | *Id de estado hasta* | `0`
<b>fech_emit_desde</b> | Opcional | `date` | `DD-MM-YYYY` | *Fecha emisión de documento, desde* | `null`
<b>fech_emit_hasta</b> | Opcional | `date` | `DD-MM-YYYY` | *Fecha emisión de documento, hasta* | `null`
<b>id_area</b> | Opcional | `int` |  | *Id del área* | `0`
<b>id_unidad_negocio</b> | Opcional | `int` |  | *Id de la unidad de negocio* | `0`
<b>id_unidad_control</b> | Opcional | `int` |  | *Id de la unidad de control* | `0`
<b>id_categoria</b> | Opcional | `int` |  | *Id de la categoría* | `0`
<b>id_operacion</b> | Opcional | `int` |  | *Id de la operación* | `0`
<b>id_tercero</b> | Opcional | `int` |  | *Id del tercero* | `0`

<aside class="notice">
    El parámetro <b>con_detalle</b> puede venir como parámetro indicando <i>true</i> o <i>false</i>, pero si no se recibe como parámetro, se tomará como <i>false</i>
</aside>


## Reporte DTE

Entrega el DTE asociado al documento en formato `PDF`, `XML`, `JSON` o `HTML`

> Obtener el DTE asociado al documento de compra con id = 6484

```python
#TO-DO
```

```shell
#El siguiente ejemplo retorna el DTE con su copia cedible en formato PDF
curl "https://api.gael.cloud/v2/documentos/reporte?doc_id=6484&is_doc_venta=false&formato=pdf&cedible=2" \
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

<aside class="notice">
    El parámetro <b>cedible</b> sólo tiene efecto cuando el parámetro <b>formato</b> tiene valor <i>pdf</i> o <i>html</i>
</aside>

El parámetro **cedible** admite los valores `0` `1` `2`. Estos configuran el reporte de la siguiente manera:

* `cedible=0` Reporte de DTE **sin** copia cedible
* `cedible=1` Reporte de DTE **solo** copia cedible
* `cedible=2` Reporte de DTE **con** copia cedible