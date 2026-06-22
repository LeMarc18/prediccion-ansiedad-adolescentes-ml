# Predicción de Niveles de Ansiedad en Adolescentes
Proyecto de Machine Learning: predicción de niveles de ansiedad en adolescentes usando Regresión Lineal y Random Forest

Proyecto de Machine Learning que explora si es posible predecir el nivel de ansiedad (anxiety_level) en adolescentes a partir de variables relacionadas con uso de redes sociales, hábitos de sueño, actividad física, rendimiento académico y nivel de estrés.
Dataset
Teen Mental Health Dataset — contiene ~1200 registros con variables demográficas, de comportamiento digital y de salud mental de adolescentes.

Variables principales:

anxiety_level: nivel de ansiedad (escala 1–10) — variable objetivo
stress_level, sleep_hours, physical_activity, academic_performance
daily_social_media_hours, screen_time_before_sleep, platform_usage
social_interaction_level, addiction_level, age, gender
depression_label: excluida del modelado por riesgo de data leakage
Metodología
Análisis exploratorio: revisión de distribución, correlaciones y balance de clases.
Justificación del target: se eligió anxiety_level (variable continua) sobre depression_label (clasificación binaria) debido al severo desbalance de clases en esta última (~97% / 3%).
Preprocesamiento:
Encoding de variables categóricas (gender, platform_usage, social_interaction_level)
Eliminación de depression_label como feature (data leakage)
Modelado:
Regresión Lineal (baseline)
Random Forest Regressor
Evaluación: MAE, RMSE y R² sobre conjunto de prueba, más análisis de feature_importances_.
Resultados
Métrica
Regresión Lineal
Random Forest
MAE
2.4742
2.4925
RMSE
2.8470
2.8493
R²
0.0016
0.0000396

Conclusión principal
Ambos modelos —uno lineal y otro basado en árboles, con capacidad de capturar relaciones no lineales e interacciones— obtienen un R² prácticamente igual a cero. El análisis de importancia de variables en Random Forest no muestra ningún predictor dominante (la importancia se distribuye de forma pareja entre las 13 features).

Esto indica que el nivel de ansiedad en este dataset no guarda una relación predecible con las variables disponibles, ya sea por:

Generación sintética/aleatoria de la variable anxiety_level en el dataset, o
Ausencia de los verdaderos determinantes de la ansiedad (factores genéticos, familiares, eventos de vida) entre las columnas disponibles.

Se considera trabajo futuro explorar modelos adicionales (Gradient Boosting, SVR) y, de ser posible, enriquecer el dataset con variables adicionales.

Estructura del repositorio

├── Proyecto_Machine_Learning.ipynb   # Notebook completo con análisis y modelos

├── Teen_Mental_Health_Dataset.csv    # Dataset utilizado

├── requirements.txt                  # Dependencias del proyecto

└── README.md
Requisitos
pandas

numpy

scikit-learn

matplotlib

