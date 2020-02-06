
# Unidad 1. Epistemología, conceptos, bases geológicas e introducción a los procesos de la superficie terrestre

  - Movimiento estaciones GNSS de RD
  - Temperatura de derretimiento según presión por profundidad
  - Porcentaje de rocas por provincias

Dentro de las opciones de `knitr`, en el encabezado de este archivo, es
probable que encuentres el argumento `eval = F`. Antes de tejer debes
cambiarlo a `eval = T`, para que evalúe los bloques de código según tus
cambios.

## Asignaciones a cada estudiante

### Estación GNSS asignada

``` r
 # abreviatura      estación GNSS
 #       anala               SPED
 #       carol               LVEG
 #       danie               BARA
```

### Espesor de hielo asignado

``` r
 # abreviatura    espesor de hielo (km)
 #       anala                        3
 #       carol                        8
 #       danie                       14
```

### Provincia asignada

``` r
 # abreviatura     código de provincia
 #       anala                      03
 #       carol                      12
 #       danie                      24
```

## Movimiento debido a la tectónica de placas.

Calcula el movimiento E-O y N-S de tu estación GNSS para todo el periodo
del cual se disponga de datos, así como un promedio diario y un promedio
anual. Hay muchas formas de estimar una tasa. Te sugiero el siguiente
método “sencillo”, que es a la vez poco potente:

Localiza tu estación asignada en la carpeta `data/estaciones-gnss`.
Genera dos series temporales, una para E-O y otra para N-S, utilizando
la función `ts` (pertenece al paquete `stats`, que se carga por defecto
con R). De cada una, obtén una serie temporal suavizada, calculándola a
partir de la media móvil de la serie original para un orden de, por
ejemplo, 90 días (puedes probar otros órdenes). Para ello, utiliza la
función `ma` del paquete `forecast`. Opcionalmente, grafica la serie
suavizada con la función `plot`. Identifica el valor máximo de la serie
suavizada, el cual corresponde al **movimiento durante todo el
periodo**. Dicho valor, divídelo entre el número de días de la serie
(función `length` para obtener el número de días), con el cual obtendrás
el **movimiento diario promedio**. Multiplica por 365.25 el movimiento
diario para obtener el **movimiento anual promedio**.

## Temperatura de fusión del hielo a presión mayor que la atmosférica

Imagina que tienes un bloque de hielo con el espesor asignado.
Utilizando esta razón…

*dT/dP = -0.00074 °K/100 kPa*

…determina a qué temperatura se funde el hielo en la parte inferior de
tu bloque.

  - Datos útiles:
      - Densidad del hielo ~ 900 kg•m<sup>-3</sup>
      - Aceleración de la gravedad ~ 9.81 m•s<sup>-2</sup>
      - 1 kg•m•s<sup>-2</sup> = N
      - 1 N•m<sup>-2</sup> = 1 Pa
      - Presión atmosférica ~ 101 kPa
      - Temperatura de fusión del hielo a presión atmosférica ~ 273.15
        °K

## Porcentaje de rocas por provincias

En las carpetas `data/rocas` y `data/division-RD` encontrarás
GeoPackages con la división provincial y las rocas aflorantes del país,
respectivamente.

``` r
library(...)
source('estadistica-zonal-objetos-sf.R')
prov <- ...
miprov <- ...[ ... , ]
lito <- ...
zstatsf(..., ..., grpx = ..., grpy = ...)
```
