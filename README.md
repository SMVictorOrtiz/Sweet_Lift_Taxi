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

## Instalación y ejecución:

1) Clonar el repositorio y acceder a la carpeta del proyecto:
   git clone https://github.com/SMVictorOrtiz/Sweet_Lift_Taxi_Project.git
   cd Sweet_Lift_Taxi_Project

2) (Opcional, recomendado) Crear y activar un entorno virtual:
   # En macOS / Linux:
   python3 -m venv .venv
   source .venv/bin/activate

   # En Windows (PowerShell):
   python -m venv .venv
   .venv\Scripts\Activate.ps1

3) Instalar las dependencias necesarias:
   pip install -r requirements.txt

4) Ejecutar el notebook principal de análisis y modelado:
   jupyter notebook Project_15_Series_Temporales.ipynb

5) Ejecutar todas las celdas del notebook en orden para reproducir:
   - Carga y remuestreo de datos horarios
   - Análisis exploratorio de tendencias y patrones
   - División entre entrenamiento y prueba (90% / 10%)
   - Entrenamiento de modelos (regresión, árboles, boosting, etc.)
   - Cálculo del RECM (debe ser ≤ 48)
   - Comparación y conclusión sobre los modelos

NOTAS IMPORTANTES:
- El archivo de datos `taxi.csv` debe estar disponible en la ruta esperada (tal como está señalado en el notebook).
- Asegúrate de ejecutar los comandos desde la raíz del repositorio.
- Si usas modelos de series temporales adicionales como ARIMA o Prophet, revisa que tengas las dependencias correspondientes instaladas.
