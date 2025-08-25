# Sweet_Lift_Taxi
## Predicción de pedidos de taxi 

Este proyecto tiene como objetivo construir un modelo de predicción para estimar la **cantidad de pedidos de taxi en aeropuertos durante la próxima hora**.  

La empresa **Sweet Lift Taxi** busca usar estos pronósticos para **atraer más conductores en horas pico**, optimizando la disponibilidad del servicio.  

La métrica de evaluación principal es el **RECM (Raíz del Error Cuadrático Medio)**, la cual debe ser **≤ 48** en el conjunto de prueba.  

---

## Objetivos del proyecto  

- Preparar y remuestrear los datos para intervalos de **una hora**.  
- Analizar los datos históricos para identificar tendencias y patrones.  
- Entrenar y comparar distintos modelos de series temporales.  
- Evaluar el rendimiento en un conjunto de prueba (10% de los datos).  
- Alcanzar un **RECM ≤ 48** en el test set.  

---

## Descripción de los datos  

Archivo: `[/datasets/taxi.csv](https://practicum-content.s3.us-west-1.amazonaws.com/datasets/taxi.csv?etag=11687de0e23962e5a11c9d8ae13eb630)`  

- `num_orders`: número de pedidos de taxi en un intervalo de tiempo.  

Los datos corresponden a registros históricos de pedidos en aeropuertos, en una resolución temporal menor a 1 hora, que deben ser **remuestreados a intervalos horarios**.  

---

## Instrucciones seguidas en el proyecto  

1. **Carga y preparación de datos**  
   - Lectura del dataset.  
   - Conversión de la columna de tiempo a formato datetime.  
   - Remuestreo de los datos a intervalos de 1 hora.  

2. **Análisis exploratorio (EDA)**  
   - Identificación de tendencias, estacionalidad y ruido.  
   - Visualización de la serie temporal.  

3. **Modelado**  
   - División en train/test (90% / 10%).  
   - Entrenamiento de múltiples modelos, como:  
     - Regresión lineal.  
     - Modelos de árboles de decisión y bosques aleatorios.  
     - Modelos de potenciación del gradiente (XGBoost, LightGBM, CatBoost).  
     - Métodos de series temporales clásicos (ARIMA, Prophet) si aplica.  
   - Ajuste de hiperparámetros.  

4. **Evaluación**  
   - Cálculo del RECM en el conjunto de prueba.  
   - Comparación de modelos y selección del mejor.  

5. **Conclusiones**  
   - Discusión sobre qué modelo funciona mejor y por qué.  
   - Posibles mejoras futuras en el pipeline.  

---

## Tecnologías utilizadas  

- [Python 3](https://www.python.org/)  
- [Pandas](https://pandas.pydata.org/)  
- [Scikit-learn](https://scikit-learn.org/stable/)  
- [Statsmodels](https://www.statsmodels.org/) o [Prophet](https://facebook.github.io/prophet/) para series temporales (opcional).  
- [Matplotlib](https://matplotlib.org/) / [Seaborn](https://seaborn.pydata.org/) para visualización.  
- [LightGBM](https://lightgbm.readthedocs.io/) / [XGBoost](https://xgboost.readthedocs.io/) / [CatBoost](https://catboost.ai/) (modelos de gradient boosting).  

---
   git clone https://github.com/tuusuario/TaxiDemandPrediction.git
   cd TaxiDemandPrediction
