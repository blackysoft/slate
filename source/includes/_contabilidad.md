# Contabilidad

## Libro Mayor

Obtener reporte de libro mayor en formato PDF o HTML

```python
#TO-DO
```

```shell
curl -X GET --header 'Accept: application/json' \
' -H "ApiKey: xxxxxxxxxxxxxxxx"' \
'https://api.gael.cl/v2/general/endpoints/libMayor/reporte'
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

`GET https://api.gael.cl/v2/general/endpoints/libMayor/reporte`

### Parámetros

Parámetro | Requerido | Tipo | Formato | Descripción
--------- | ------- | ----------- | ----------- | -----------
UsuarioID | ✔ | int | | Id del usuario
EmpresaID | ✔ | int | | Id de la empresa a consultar
Anio | ❌ | string(4) | `YYYY` | Año del período contable a consultar
Periodo | ❌ | string(4) | `YYMM` | Período contable a consultar
Filtro | ❌ | string(100) | | Filtro opcional
Format | ✔ | string(4)| `pdf` o `html` | Formato de la respuesta (html o pdf)