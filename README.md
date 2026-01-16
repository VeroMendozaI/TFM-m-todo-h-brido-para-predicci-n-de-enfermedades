# Método Híbrido de Aprendizaje Automático para la Predicción de Enfermedades Crónicas a partir de Datos Clínicos

## Descripción
Este proyecto corresponde al Trabajo de Fin de Máster (TFM) y tiene como objetivo
construir un pipeline reproducible de preparación de datos clínicos y modelado
predictivo de diabetes utilizando datos clínicos del estudio NHANES.

El propósito de este sistema es mejorar la precisión diagnóstica y ofrecer interpretaciones comprensibles que respalden la toma de decisiones médicas, contribuyendo así a superar la falta de transparencia que caracteriza a muchos modelos actuales de inteligencia artificial aplicados en salud.

---

## Datos
Los datos provienen de NHANES, un estudio transversal representativo de la población
estadounidense, que incluye información demográfica, antropométrica, bioquímica y
clínica.

---

## Metodología (resumen)
El pipeline implementado incluye los siguientes pasos:

1. Normalización y limpieza de nombres de variables
2. Eliminación de variables con más del 60 % de valores faltantes
3. Limpieza de códigos especiales de NHANES (7, 9, 77, 99 → NaN)
4. Análisis del mecanismo de ausencia (MCAR / MAR)
5. Creación de indicadores de valores faltantes
6. Definición de bloques clínicos de imputación
7. Imputación múltiple (M = 3) mediante Random Forest
8. Evaluación de la calidad de la imputación (medias, medianas, KS test, boxplots)
9. Construcción de variables clínicas derivadas (IMC categórico, proxy de CKD)
10. Preparación del dataset para modelado predictivo
11. Entrenamiento y evaluación de modelos de clasificación

---

## Estructura del repositorio

```text
├── data/
│   ├── raw/              # Datos NHANES originales (no incluidos)
│   ├── processed/        # Datasets tras limpieza e imputación
│
├── notebooks/
│   ├── cleaning.ipynb
│
├── requirements.txt
└── README.md
```

---

## Reproducibilidad
Instalar dependencias:

```bash
pip install -r requirements.txt
```

---

## Resultados principales
El modelo base entrenado sobre el conjunto de datos imputado alcanzó un rendimiento
elevado (ROC-AUC ≈ 1), atribuible a la inclusión de variables clínicas estrechamente
relacionadas con los criterios diagnósticos de diabetes.

Este resultado valida la coherencia interna del pipeline, aunque también evidencia
la presencia de información diagnóstica explícita en los predictores. Por ello, se
exploran escenarios alternativos excluyendo dichas variables para evaluar la
capacidad predictiva en ausencia de fuga de información.

---

## Limitaciones


## Autor
Verónica Mendoza Iguarán  
Máster Universitario en Inteligencia Artificial  
Universidad Internacional de La Rioja - UNIR  
Escuela Superior de Ingeniería y Tecnología  
Director: Ignacio Ramos Garcia  
Año: 2026  
