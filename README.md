# Métodos Estadísticos — Replicación de Paper

Preprocesamiento de datos oceanográficos y meteorológicos históricos de boyas del **NOAA NDBC** (National Data Buoy Center) para la replicación de un estudio estadístico publicado.

## Estado actual

El proyecto se encuentra en etapa inicial: solo se ha implementado la **carga y limpieza** de datos. Aún no se han desarrollado modelos estadísticos ni visualizaciones.

## Archivos

| Archivo | Descripción |
|---|---|
| `pre_procesamiento.ipynb` | Jupyter Notebook con el código de carga y limpieza de datos |
| `datos_historicos_2023` | Datos crudos en formato fixed-width de NOAA NDBC (~4.7 MB, ~52k líneas) |

## Datos

### Columnas

| Columna | Descripción | Unidades |
|---|---|---|
| `YY` | Año | — |
| `MM` | Mes | — |
| `DD` | Día | — |
| `hh` | Hora | UTC |
| `mm` | Minuto | — |
| `WDIR` | Dirección del viento (procedencia) | grados |
| `WSPD` | Velocidad del viento | m/s |
| `GST` | Ráfaga | m/s |
| `WVHT` | Altura significativa de ola | m |
| `DPD` | Periodo dominante de ola | seg |
| `APD` | Periodo promedio de ola | seg |
| `MWD` | Dirección media del ola | grados |
| `PRES` | Presión barométrica | hPa |
| `ATMP` | Temperatura del aire | °C |
| `WTMP` | Temperatura del agua | °C |
| `DEWP` | Punto de rocío | °C |
| `VIS` | Visibilidad | millas náuticas |
| `TIDE` | Nivel del agua | ft |

Los valores centinela (`99.0`, `99.00`, `999`, `999.0`) se reemplazan con `NaN`.

## Requisitos

- Python 3
- pandas
- numpy
- jupyter

```bash
pip install pandas numpy jupyter
```

## Uso

```bash
jupyter notebook pre_procesamiento.ipynb
```

Ejecutar todas las celdas. La segunda celda lee el archivo `datos_historicos_2023`, lo limpia y muestra las primeras 5 filas.

## Origen de los datos

[NOAA National Data Buoy Center](https://www.ndbc.noaa.gov/) — datos históricos de boyas meteorológicas y oceanográficas.

## Repositorio

`git@github.com:Magvride/Statistics-models.git`
