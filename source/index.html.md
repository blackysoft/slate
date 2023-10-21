---
title: API Gael Cloud

language_tabs: # must be one of https://github.com/rouge-ruby/rouge/wiki/List-of-supported-languages-and-lexers
  - shell
  - python
  - javascript

toc_footers:
  - <a target="_blank" href='https://status.gael.cloud'>🚩 Status Gael Cloud</a>
  - <a target="_blank" href='https://gael.cloud'>🌎 Sitio Web Gael Cloud</a>
  - <a target="_blank" href='https://blog.gael.cloud'>🗒️ Blog Gael Cloud</a>
  - <a target="_blank" href='https://www.linkedin.com/company/gael'>🏛️ LinkedIn Gael Cloud</a>
  - <a href="mailto:soporte@gael.cloud">📧 Contacto</a>

search: true

code_clipboard: true

includes:
  - _errors
  - _empresas
  - _usuarios
  - _ucontrol
  - _categorias
  - _comegr
  - _venting
  - _fondrend
  - _presupuestos
  - _documentos
  - _sii
  - _remuneraciones
  - _contabilidad
  - _rrhh
  - _fes
---

# Introducción

Bienvenido a la **API de Gael Cloud** 👋 

Tenemos ejemplos en distintos lenguajes *(Shell, Python y JavaScript)*. Puedes revisar los códigos de ejemplo en el área oscura de la derecha y puedes cambiar el lenguaje de programación haciendo click en los tabs de la barra superior derecha.

Esta api está compuesta de dos secciones:

* **[Pública](#publica)**
* **Privada**

Todos los endpoints de carácter público presentados en la sección [Pública](#publica), pueden ser utilizados libremente en cualquier entorno, **sin propósitos comerciales.**

<aside class="warning">
En caso de detectar uso indebido de cualquiera de los endpoints públicos, procederemos a banear ips <b>sin previo aviso</b>👀
</aside>

Para interactuar con cualquiera de los endpoints que no estén presentes en la sección [Pública](#publica), es necesario ser cliente activo de [Gael Cloud](https://gael.cloud) y contar con una **ApiKey**. Para más información revisar la sección [Autenticación](#autenticacion)

Si vas a utilizar nuestra API, es importante que **tengas en consideración los siguientes puntos:**

* Esta API opera bajo arquitectura [REST](https://www.redhat.com/es/topics/api/what-is-a-rest-api) y entrega información formateada en [JSON](https://www.json.org/json-es.html)
* Solamente están permitidas las solicitudes utilizando el protocolo [HTTPS](https://developers.google.com/search/docs/advanced/security/https?hl=es)
* Todas las fechas son entregadas según la norma [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html)

La documentación de esta API fué creada utilizando [Slate](https://github.com/slatedocs/slate).

# Pública

## ⚠️ Rate Limiting

<aside class="warning">
¡Ojo, con la cantidad de requests!
</aside>

Los endpoints referentes a la a sección [Pública](#publica) están protegidos con *rate limiting*. 

Esto significa que tu ip quedará **baneada por una hora** si es que realizas más de **9 requests en un intervalo de 10 segundos.**

Si tu IP queda baneada... a esperar no más. La API retornará el código **429** y el JSON mostrado en el ejemplo

<aside class="info">
Revisa tu código para limintar la cantidad de requests por segundo.
</aside>

> Si tu IP queda baneada por realizar demasiados requests seguidos, la api retornará el siguiente JSON:

```json
{
  "error": {
    "type": "rate_limiting_error",
    "code": 0,
    "message": "Cantidad de requests excedido"
  }
}
```

## 💲 Todas las monedas

Obtener valores actuales de cambio nominal (CLP) respecto a diversas monedas extranjeras.

Los valores de tipo de cambio se actualizan cada **30 minutos** desde la web del BANCO CENTRAL DE CHILE.

```python
import requests
response = requests.get("https://api.gael.cloud/general/public/monedas")
print(response.text)
```

```shell
curl -X GET --header 'Accept: application/json' \
'https://api.gael.cloud/general/public/monedas'
```

```javascript
//TO-DO
```

> El ejemplo anterior retorna el siguiente JSON:

```json
[
  {
    "Codigo": "UF",
    "Nombre": "Unidad de Fomento",
    "Valor": "28708,80"
  },
  {
    "Codigo": "USD",
    "Nombre": "Dolar Americano",
    "Valor": "788,15"
  },
  {
    "Codigo": "UTM",
    "Nombre": "Unidad Tributaria Mensual",
    "Valor": "50372,00"
  },
  {
    "Codigo": "THB",
    "Nombre": "Baht tailandes",
    "Valor": "24,95"
  },
  .......
]
```

### HTTPS Request

<aside class="api-endpoint">
    <div class="endpoint-data">
        <i class="label label-get">GET</i>
        <h6>https://api.gael.cloud/general/public/monedas</h6>
    </div>
</aside>

## 💲 Moneda por código

Obtener valor actual de cambio nominal (CLP) de la moneda específica.
<aside class="notice">
Puedes revisar los códigos de las monedas utilizando el request general.
</aside>

```python
import requests
response = requests.get("https://api.gael.cloud/general/public/monedas/USD")
print(response.text)
```

```shell
curl -X GET --header 'Accept: application/json' \
'https://api.gael.cloud/general/public/monedas/USD'
```

```javascript
//TO-DO
```

> El ejemplo anterior retorna el siguiente JSON:

```json
{
  "Codigo": "USD",
  "Nombre": "Dolar Americano",
  "Valor": "788,15",
  "Fecha": "2020-10-01T19:30:01.000Z"
}
```

### HTTPS Request

<aside class="api-endpoint">
    <div class="endpoint-data">
        <i class="label label-get">GET</i>
        <h6>https://api.gael.cloud/general/public/monedas/{codigo}</h6>
    </div>
</aside>


## 🌤 Todos los climas

Datos climáticos procedentes de estaciones meteorológicas a lo largo del país.

Los datos climáticos se actualizan acorde a lo entregado por la web de la DIRECCIÓN METEOROLÓGICA DE CHILE.

```python
import requests
response = requests.get("https://api.gael.cloud/general/public/clima")
print(response.text)
```

```shell
curl -X GET --header 'Accept: application/json' \
'https://api.gael.cloud/general/public/clima'
```

```javascript
//TO-DO
```

> El ejemplo anterior retorna el siguiente JSON:

```json
[
  {
    "Codigo": "SCFA",
    "Estacion": "Antofagasta",
    "HoraUpdate": "17:00",
    "Temp": "15",
    "Humedad": "77",
    "Estado": "Nublado",
    "Icono": "parcial.png"
  },
  {
    "Codigo": "SCAR",
    "Estacion": "Arica",
    "HoraUpdate": "17:00",
    "Temp": "18",
    "Humedad": "73",
    "Estado": "Nubosidad parcial",
    "Icono": "parcialalta.png"
  },
  .......
]
```

### HTTPS Request

<aside class="api-endpoint">
    <div class="endpoint-data">
        <i class="label label-get">GET</i>
        <h6>https://api.gael.cloud/general/public/clima</h6>
    </div>
</aside>

## 🌤 Clima por código

Obtener valor actual del clima registrado por la estación meteorológica específica.
<aside class="notice">
Puedes revisar los códigos de las estaciones meteorológicas utilizando el request general.
</aside>

```python
import requests
response = requests.get("https://api.gael.cloud/general/public/clima/SCQN")
print(response.text)
```

```shell
curl -X GET --header 'Accept: application/json' \
'https://api.gael.cloud/general/public/clima/SCQN'
```

```javascript
//TO-DO
```

> El ejemplo anterior retorna el siguiente JSON:

```json
{
  "Codigo": "SCQN",
  "Estacion": "Santiago Centro",
  "HoraUpdate": "17:20",
  "Temp": "18.0",
  "Humedad": "42",
  "Estado": "Despejado",
  "Icono": "despejado.png"
}
```

### HTTPS Request

<aside class="api-endpoint">
    <div class="endpoint-data">
        <i class="label label-get">GET</i>
        <h6>https://api.gael.cloud/general/public/clima/{codigo}</h6>
    </div>
</aside>


## 🚨 Sismos

Datos acerca de últimos sismos ocurridos en Chile.

Los datos sismológicos se actualizan cada 5 minutos según la web del CENTRO SISMOLÓGICO NACIONAL.

```python
import requests
response = requests.get("https://api.gael.cloud/general/public/sismos")
print(response.text)
```

```shell
curl -X GET --header 'Accept: application/json' \
'https://api.gael.cloud/general/public/sismos'
```

```javascript
//TO-DO
```

> El ejemplo anterior retorna el siguiente JSON:

```json
[
  {
    "Fecha": "2022-07-18 18:35:54",
    "Profundidad": "121",
    "Magnitud": "2.6",
    "RefGeografica": "43 km al O de Ollagüe",
    "FechaUpdate": "2022-07-18T23:10:00.830Z"
  },
  .......
]
```

### HTTPS Request

<aside class="api-endpoint">
    <div class="endpoint-data">
        <i class="label label-get">GET</i>
        <h6>https://api.gael.cloud/general/public/sismos</h6>
    </div>
</aside>

## 👷‍♀️Indicadores Previred

Información previsional.

La información previsional se actualiza una vez al día, según la web de PREVIRED.

<aside class="notice">
El parámetro <i>periodo</i> tiene el formato MES/AÑO 
</aside>

```python
import requests
response = requests.get("https://api.gael.cloud/general/public/previred/062020")
print(response.text)
```

```shell
curl -X GET --header 'Accept: application/json' \
'https://api.gael.cloud/general/public/previred/072022'
```

```javascript
//TO-DO
```

> El ejemplo anterior retorna el siguiente JSON:

```json
{
  "PreviredID": 1074,
  "Fecha": "2022-07-24T21:46:02.947Z",
  "PeriodoMY": "072022",
  "PeriodoYM": "2207",
  "UFDescPeriodo": "al 31 de Julio 2022",
  "UFValPeriodo": "33417,26",
  "UFDescPeridoAnt": "al 30 de Junio 2022",
  "UFValPeriodoAnt": "33086,83",
  "UTMDesc": "Julio 2022",
  "UTMVal": "58248",
  "UTAVal": "698976",
  "RTIAfpUF": "81,6",
  "RTIIpsUF": "60",
  "RTISegCesUF": "122,6",
  "RTIAfpPesos": "2726848",
  "RTIIpsPesos": "1985210",
  "RTISegCesPesos": "4096956",
  "RMITrabDepeInd": "380000",
  "RMIMen18May65": "283471",
  "RMITrabCasaPart": "380000",
  "RMINoRemu": "244944",
  "APVTopeMensUF": "50",
  "APVTopeAnuUF": "600",
  "APVTopeMensPesos": "1670863",
  "APVTopeAnuPesos": "20050356",
  "DepConvenidoUF": "900",
  "DepConvenidoPesos": "30075534",
  "AFCCpiEmpleador": "2,4",
  "AFCCpiTrabajador": "0,6",
  "AFCCpfEmpleador": "3,0",
  "AFCCpfTrabajador": "0",
  "AFCCpi11Empleador": "0,8",
  "AFCCpi11Trabajador": "0",
  "AFCTcpEmpleador": "3,0",
  "AFCTcpTrabajador": "0",
  "AFPCapitalTasaDep": "11,44",
  "AFPCapitalTasaSIS": "1,84",
  "AFPCapitalTasaInd": "13,28",
  "AFPCuprumTasaDep": "11,44",
  "AFPCuprumTasaSIS": "1,84",
  "AFPCuprumTasaInd": "13,28",
  "AFPHabitatTasaDep": "11,27",
  "AFPHabitatTasaSIS": "1,84",
  "AFPHabitatTasaInd": "13,11",
  "AFPPlanVitalTasaDep": "11,16",
  "AFPPlanVitalTasaSIS": "1,84",
  "AFPPlanVitalTasaInd": "13,00",
  "AFPProVidaTasaDep": "11,45",
  "AFPProVidaTasaSIS": "1,84",
  "AFPProVidaTasaInd": "13,29",
  "AFPModeloTasaDep": "10,58",
  "AFPModeloTasaSIS": "1,84",
  "AFPModeloTasaInd": "12,42",
  "AFPUnoTasaDep": "10,69",
  "AFPUnoTasaSIS": "1,84",
  "AFPUnoTasaInd": "12,53",
  "AFamTramoAMonto": "15597",
  "AFamTramoADesde": "0",
  "AFamTramoAHasta": "398443",
  "AFamTramoBMonto": "9571",
  "AFamTramoBDesde": "398443",
  "AFamTramoBHasta": "581968",
  "AFamTramoCMonto": "3025",
  "AFamTramoCDesde": "581968",
  "AFamTramoCHasta": "907672",
  "AFamTramoDMonto": "0",
  "AFamTramoDDesde": "907672",
  "AFamTramoDHasta": "9999999999",
  "TrabPesadoCalif": "4",
  "TrabPesadoEmpl": "2",
  "TrabPesadoTrabaj": "2",
  "TrabMenosPesadoCalif": "2",
  "TrabMenosPesadoEmpl": "1",
  "TrabMenosPesadoTrabaj": "1"
}
```

### HTTPS Request

<aside class="api-endpoint">
    <div class="endpoint-data">
        <i class="label label-get">GET</i>
        <h6>https://api.gael.cloud/general/public/previred/{periodo}</h6>
    </div>
</aside>


## 🏢Indicadores Impuesto Único

Información sobre impuesto único de 2da categoría.

La información sobre impuesto único se actualiza una vez al mes **(día 14)**, según la web del SII.

<aside class="notice">
El parámetro <i>periodo</i> tiene el formato MES/AÑO 
</aside>

```python
import requests
response = requests.get("https://api.gael.cloud/general/public/impunico/062020")
print(response.text)
```

```shell
curl -X GET --header 'Accept: application/json' \
'https://api.gael.cloud/general/public/impunico/062020'
```

```javascript
//TO-DO
```

> El ejemplo anterior retorna el siguiente JSON:

```json
{
  "ImpUnicoID": 14,
  "FechaUpdate": "2020-06-20T20:00:03.000Z",
  "PeriodoMY": "062020",
  "PeriodoYM": "2006",
  "PeriodoNombre": "Junio 2020",
  "FechaDesde": "2020-06-01T04:00:00.000Z",
  "FechaHasta": "2020-06-30T04:00:00.000Z",
  "TR1Desde": "0",
  "TR1Hasta": "680022,00",
  "TR1Factor": "0",
  "TR1CReb": "0",
  "TR1TIEfectiva": "0",
  "TR2Desde": "680022,01",
  .......
}
```

### HTTPS Request

<aside class="api-endpoint">
    <div class="endpoint-data">
        <i class="label label-get">GET</i>
        <h6>https://api.gael.cloud/general/public/impunico/{periodo}</h6>
    </div>
</aside>


# Autenticación 

> Para autenticar un request, usa el siguiente código:

```python
#TO-DO
```

```shell
# Mediante shell, puedes pasar el header correcto en cada request
curl "https://api.gael.cloud/v2/todos_los_endpoints" \
  -H "ApiKey: xxxxxxxxxxxxxxxx"
```

```javascript
//TO-DO
```

> Asegurate de reemplazar `xxxxxxxxxxxxxxxx` por tu ApiKey.

La API de GAEL utiliza **ApiKeys** para conceder acceso a los diferentes endpoints ofrecidos por la API. Para obtener una **ApiKey** asociada a tu cuenta de cliente, debes enviar un correo electrónico a <a href="mailto:soporte@gael.cloud">soporte@gael.cloud</a> o contactar directamente con tu agente.

La API espera que la **ApiKey** esté incluida en todos los requests hacia el servidor en un header que se compone de la siguiente manera: 

`ApiKey: xxxxxxxxxxxxxxxx`

<aside class="notice">
Debes reemplazar <code>xxxxxxxxxxxxxxxx</code> por la <b>ApiKey</b> asociada a tu cuenta. Esta <b>ApiKey</b> sirve para todas las empresas asociadas a esta cuenta.
</aside>