# Documentos

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
