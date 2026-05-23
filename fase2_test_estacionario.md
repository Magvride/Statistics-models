# Fase 2 - Test de Estacionariedad (ADF)

## Objetivo

Se realizó un análisis de estacionariedad sobre las variables del dataset oceanográfico utilizando el test ADF (Augmented Dickey-Fuller).

Las variables analizadas fueron:

* Wind_speed
* sst
* Hs

---

# ¿Qué es el test ADF?

El test ADF es una prueba estadística utilizada en series temporales para determinar si una serie es estacionaria o no.

Una serie estacionaria es aquella que mantiene un comportamiento relativamente estable en el tiempo.

En cambio, una serie no estacionaria presenta tendencias o cambios continuos.

---

# ¿Para qué sirve?

El test ADF sirve para verificar si los datos son adecuados para ciertos análisis estadísticos y modelos de predicción.

Muchos modelos de series temporales funcionan mejor cuando los datos son estacionarios.

---

# p-value

El resultado más importante del test es el p-value.

Se utilizó un umbral de:

```text
0.05
```

Interpretación:

* Si el p-value es menor que 0.05, la serie se considera estacionaria.
* Si el p-value es mayor que 0.05, la serie se considera no estacionaria.

---

# Procedimiento 

Antes de ejecutar el test ADF fue necesario instalar la librería de herramientas estadísticas desde la terminal:

```bash
pip install statsmodels
```

Después se aplicó el test ADF a cada variable:

```python
from statsmodels.tsa.stattools import adfuller

variables = ['Wind_speed', 'sst', 'Hs']

for var in variables:

    serie = df[var].dropna()

    resultado = adfuller(serie)

    print(f'ADF Test para {var}')
    print(f'ADF Statistic: {resultado[0]}')
    print(f'p-value: {resultado[1]}')
```




