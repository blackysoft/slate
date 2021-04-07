---
title: API Gael

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - python
  - javascript

toc_footers:
  - <a target="_blank" href='https://gael.cloud'>🌎 Sitio Web Gael</a>
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

---

# ⚠ ¡Aviso Importante! ⚠

Cambiamos el dominio **.cl** por **.cloud**.

<aside class="notice">
  El dominio <b>.cl</b> funcionará hasta el día <b>14/04/2021</b> (extendimos el plazo)
</aside>

# Introducción

Bienvenido a la **API de GAEL** 👋 

Tenemos ejemplos en distintos lenguajes *(Shell, Python y JavaScript)*. Puedes revisar los códigos de ejemplo en el área oscura de la derecha y puedes cambiar el lenguaje de programación haciendo click en los tabs de la barra superior derecha.

Esta api está compuesta de dos secciones:

* **[Pública](#publica)**
* **Privada**

Todos los endpoints de carácter público presentados en la sección [Pública](#publica), pueden ser utilizados libremente en cualquier entorno, **sin propósitos comerciales.**

<aside class="warning">
En caso de detectar uso indebido de cualquiera de los endpoints públicos, procederemos a banear ips <b>sin previo aviso</b>👀
</aside>

Para interactuar con cualquiera de los endpoints que no estén presentes en la sección [Pública](#publica), es necesario ser cliente activo de [GAEL](https://gael.cl) y contar con una **ApiKey**. Para más información revisar la sección [Autenticación](#autenticacion)

La documentación de esta API fué creada utilizando [Slate](https://github.com/slatedocs/slate).

## A considerar
* Esta API opera bajo arquitectura **REST** y entrega información formateada en **JSON**
* Solamente están permitidas las solicitudes utilizando el protocolo **HTTPS**
* Todas las fechas son entregadas según la norma **[ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html)**

# Pública

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

`GET https://api.gael.cloud/general/public/monedas`



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

`GET https://api.gael.cloud/general/public/monedas/{codigo}`



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

`GET https://api.gael.cloud/general/public/clima`



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

`GET https://api.gael.cloud/general/public/clima/{codigo}`


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
    "Fecha": "2020/10/01 16:30:55",
    "Latitud": "-21.386",
    "Longitud": "-69.830",
    "Profundidad": "44.0",
    "Magnitud": "3.1 Ml",
    "Agencia": "GUC",
    "RefGeografica": "43 km al NO de Quillagua",
    "FechaUpdate": "01/10/2020 17:30:00"
  },
  .......
]
```

### HTTPS Request

`GET https://api.gael.cloud/general/public/sismos`


## 👷‍♀️Indicadores Previred

Información previsional.

La información previsional se actualiza una vez al mes **(día 20)**, según la web de PREVIRED.

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
'https://api.gael.cloud/general/public/previred/062020'
```

```javascript
//TO-DO
```

> El ejemplo anterior retorna el siguiente JSON:

```json
{
  "PreviredID": 89,
  "Fecha": "2020-06-20T19:00:02.000Z",
  "PeriodoMY": "062020",
  "PeriodoYM": "2006",
  "UFDescPeriodo": "al 30 de Junio 2020",
  "UFValPeriodo": "28696,42",
  "UFDescPeridoAnt": "al 31 de Mayo 2020",
  "UFValPeriodoAnt": "28716,52",
  "UTMDesc": "Junio 2020",
  "UTMVal": "50372",
  "UTAVal": "604464",
  "RTIAfpUF": "80,2",
  "RTIIpsUF": "60",
  "RTISegCesUF": "120,4",
  "RTIAfpPesos": "2301453",
  .......
}
```

### HTTPS Request

`GET https://api.gael.cloud/general/public/previred/{periodo}`


## 🏢Indicadores Impuesto Único

Información sobre impuesto único de 2da categoría.

La información sobre impuesto único se actualiza una vez al mes **(día 20)**, según la web del SII.

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

`GET https://api.gael.cloud/general/public/impunico/{periodo}`


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