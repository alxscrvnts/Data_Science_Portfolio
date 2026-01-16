# 02. Optimizing Deep Learning for SaaS Churn Prediction

## Objetivo del proyecto
El objetivo principal fue identificar los precursores sutiles de la fuga de clientes (churn) en cuentas corporativas de alto valor mediante la implementación de una red neuronal optimizada. Se priorizó el Recall sobre el Accuracy para asegurar que ninguna asociación estratégica se pierda por "ceguera predictiva".

## Problema identificado
La plataforma "SaaS-Stream" detectó que, aunque el 93% del portafolio es estable, el 7% de deserción se concentra en el nivel "High-Ticket". Este problema presentaba un severo desbalance de clases (93% vs 7%), donde las señales de los clientes más críticos quedaban enterradas bajo los datos de la mayoría estable.

## Metodología aplicada
Arquitectura de Red Neuronal: Se diseñó una red secuencial de tres capas con un esquema de "embudo" (16-8-1 neuronas) y una capa de Dropout del 20% para forzar la extracción de predictores relevantes y evitar el sobreajuste.

1. Tratamiento de desbalance (Cost-Weighting vs SMOTE): Se compararon técnicas de sobremuestreo sintético y ponderación de costos, aplicando una penalización de error de 25x para la clase minoritaria.

2. Optimización y validación: Uso de RandomizedSearchCV y validación cruzada estratificada (StratifiedKFold) para ajustar hiperparámetros, enfocándose en maximizar el F1-Score y la recuperación de cuentas en riesgo.

## Resultados y proyecciones
Este sistema permite una transición de un modelo observacional a una gobernanza proactiva, protegiendo el Ingreso Anual Recurrente (ARR). La evaluación de 100 nuevas cuentas corporativas demostró el impacto del marco preventivo:

1. Tasa de churn detectada: 22%, comparada con el promedio histórico de 6.75%.

2. Sensibilidad del modelo: Se confirmó que cada ticket de soporte adicional incrementa la probabilidad de fuga en un 25%.

3. Umbral crítico: El uso de API por debajo de 40 unidades se estableció como el indicador principal de vulnerabilidad de la cuenta.


## Stack técnico

**TensorFlow & Keras:** Arquitectura de aprendizaje profundo.

**Imbalanced-learn (SMOTE):** Manejo de desbalance de datos.

**Scikit-learn:** Preprocesamiento, escalado estándar y métricas de validación.

**Seaborn & Matplotlib:** Visualización de correlaciones y distribuciones Gamma/Poisson.