Análisis de Riesgo Crediticio
Descripción del proyecto
Este proyecto tiene como objetivo desarrollar modelos de machine learning capaces de predecir el riesgo de incumplimiento (default) en préstamos, a partir de variables financieras y características de los clientes.
El análisis incluye etapas de limpieza de datos, preprocesamiento, modelado y evaluación de desempeño, con foco en la aplicación al negocio crediticio.
________________________________________
Objetivo
Construir un sistema de scoring que permita identificar clientes con alta probabilidad de incumplimiento, priorizando la detección de casos riesgosos para reducir pérdidas económicas.
________________________________________
Dataset
El dataset utilizado no se incluye en el repositorio debido a su tamaño.
Puede descargarse desde: https://www.kaggle.com/datasets/joebeachcapital/loan-default
El conjunto de datos contiene información sobre préstamos otorgados, incluyendo variables como ingresos, tasa de interés, historial crediticio y propósito del préstamo.
________________________________________
Metodología
El análisis se desarrolló en las siguientes etapas:
●	Limpieza y selección de variables (eliminación de data leakage)
●	Transformación de variables (incluyendo codificación de variables categóricas)
●	Manejo de valores faltantes
●	Escalado de variables numéricas
●	División del dataset en entrenamiento (80%) y prueba (20%) de forma estratificada
________________________________________
Modelado
Se evaluaron distintos modelos de clasificación supervisada:
●	Dummy Classifier (baseline)
●	Regresión Logística (con balanceo de clases)
●	XGBoost (ajustado para desbalance)
Las métricas utilizadas fueron:
●	Accuracy
●	Precision
●	Recall
●	F1-score
●	ROC AUC
Dado el desbalance de clases, se priorizó el análisis de recall y F1-score.
________________________________________
Segmentación del modelo
Como parte del diseño de la solución, se evaluó una arquitectura segmentada del modelo, dividiendo los préstamos en:
●	Préstamos de bajo monto
●	Préstamos de alto monto
Esta segmentación se basó en diferencias observadas en la tasa de incumplimiento entre ambos grupos.
Se entrenaron modelos independientes para cada segmento, comparando su desempeño con el modelo general.
________________________________________
Resultados
Los resultados muestran que:
●	Los modelos sin balanceo presentan alta accuracy pero baja capacidad para detectar incumplimientos.
●	La regresión logística balanceada logra un mejor recall, siendo más efectiva para identificar clientes en riesgo.
●	XGBoost presenta un desempeño competitivo en términos de ROC AUC.
●	La segmentación por monto del préstamo genera mejoras leves en el desempeño, especialmente en recall.
________________________________________
Conclusiones
●	El recall es una métrica clave en este problema, ya que permite identificar casos de incumplimiento.
●	Existe un trade-off entre precisión y detección de riesgo.
●	La regresión logística balanceada se presenta como una opción robusta e interpretable.
●	La segmentación del modelo aporta valor, aunque su impacto es moderado.
●	Algunas variables, como la ubicación geográfica, muestran alta importancia y requieren análisis adicional.
________________________________________
Estructura del repositorio
analisis-riesgo-crediticio/
│
├── notebooks/
│   └── modelo_creditos.ipynb
│
├── data/
│   └── info dataset.md
│
└── README.md

________________________________________
Tecnologías utilizadas
●	Python
●	Pandas
●	NumPy
●	Scikit-learn
●	XGBoost
●	Matplotlib
●	Seaborn
●	Google Colab
________________________________________
Cómo ejecutar
1.	Clonar el repositorio:
git clone <https://colab.research.google.com/drive/1wDB5ocKwbu4ljLhFL9g-RbntJy_j4bVI#scrollTo=O10E9i5kXFv2>

2.	Descargar el dataset desde el enlace indicado

3.	Abrir el notebook en Google Colab o Jupyter Notebook

4.	Ejecutar las celdas en orden

________________________________________
Autores
Badaro, Galo
Basualdo, Andrea Carolina
Belotti, Ignacio José 
Mena, Iván Gonzalo

Diplomatura en Ciencia de Datos y Análisis Avanzado – UTN BA


