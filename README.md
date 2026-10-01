# Predicción del abandono de clientes — Customer Churn

## Proyecto aplicado de Ciencia de Datos — UIDE

**Estudiante:** Karen Núñez Loor  
**Tipo de problema:** Clasificación binaria  
**Tema:** Predicción del abandono de clientes de telecomunicaciones

## Descripción

Este proyecto desarrolla un sistema de clasificación para identificar clientes con posible riesgo de abandono (*customer churn*) en una empresa de telecomunicaciones.

Se utiliza el dataset público **IBM Telco Customer Churn**, compuesto por 7.043 registros de clientes y 21 variables originales relacionadas con características del cliente, servicios contratados, permanencia, facturación y abandono.

El proyecto comprende las etapas de adquisición, auditoría y limpieza de datos, consultas SQL, análisis exploratorio, análisis estadístico, preprocesamiento, entrenamiento y comparación de modelos, evaluación, interpretación y revisión de aspectos relacionados con ética y uso responsable.

## Objetivo

Desarrollar y evaluar modelos de clasificación que permitan estimar el riesgo de abandono de clientes e identificar variables asociadas con este comportamiento.

## Metodología

El proyecto incluye:

- Auditoría y limpieza de datos.
- Análisis exploratorio y visualización.
- Consultas mediante SQLite.
- Análisis estadístico.
- Preparación de variables mediante pipelines.
- Regresión Logística.
- Random Forest.
- Modelo de línea base.
- Validación cruzada estratificada.
- Evaluación mediante accuracy, precision, recall, F1, ROC-AUC y PR-AUC.
- Interpretación de los coeficientes del modelo.
- Revisión básica del desempeño por grupos.
- Análisis de privacidad y uso responsable.

## Resultados principales

La variable objetivo presentó una tasa de abandono del **26,54 %**.

En el conjunto de prueba:

| Modelo | Accuracy | Precision | Recall | F1 | ROC-AUC | PR-AUC |
|---|---:|---:|---:|---:|---:|---:|
| Línea base | 0,735 | 0,000 | 0,000 | 0,000 | 0,500 | 0,265 |
| Regresión Logística | 0,738 | 0,504 | 0,783 | 0,614 | 0,842 | 0,633 |
| Random Forest | 0,774 | 0,560 | 0,682 | 0,615 | 0,839 | 0,645 |

Para el objetivo planteado se seleccionó la **Regresión Logística** como modelo principal, priorizando su mayor `recall` y su facilidad de interpretación.

El modelo identificó correctamente **293 de los 374 clientes que realmente abandonaron**, alcanzando un `recall` del **78,3 %**.

## Principales hallazgos

El análisis permitió identificar asociaciones entre el abandono y variables como:

- permanencia del cliente (`tenure`);
- tipo de contrato;
- servicio de internet;
- cargos mensuales y acumulados.

Los resultados representan asociaciones estadísticas y predictivas y no deben interpretarse como relaciones causales.

## Ética y uso responsable

Se realizó una revisión exploratoria del desempeño del modelo según género y condición de adulto mayor.

Los resultados muestran la importancia de monitorear posibles diferencias de desempeño entre grupos antes de utilizar un sistema predictivo en un contexto real.

Las predicciones deben utilizarse como herramienta de apoyo y no como mecanismo para tomar decisiones automáticas que puedan perjudicar a los clientes.

## Archivos del repositorio

- `proyecto_churn.ipynb`: notebook principal con el desarrollo completo del proyecto.
- `Telco-Customer-Churn.csv`: conjunto de datos utilizado para el análisis.
- `README.md`: descripción general del proyecto.

## Tecnologías utilizadas

- Python
- pandas
- NumPy
- Matplotlib
- Seaborn
- SQLite
- SciPy
- scikit-learn
- Joblib
- Google Colab

## Fuente de datos

IBM Telco Customer Churn.

Repositorio público de IBM utilizado como fuente del conjunto de datos.

## Reproducibilidad

El notebook contiene las etapas necesarias para cargar, preparar y analizar los datos, entrenar los modelos y reproducir los principales resultados del proyecto.

Se utiliza `RANDOM_STATE = 42` en los procesos aleatorios correspondientes para favorecer la reproducibilidad de los resultados.
