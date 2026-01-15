# 01. Fine-tuned Prophet Forecasting for Strategic Revenue Growth

## Objetivo del proyecto
El objetivo principal fue implementar un motor de proyección de ingresos para una entidad de e-commerce, utilizando algoritmos de **Prophet** y una metodología de estabilización logarítmica. [cite_start]Se buscó transformar la complejidad multiplicativa de los datos en un modelo aditivo de alta precisión para asegurar previsiones financieras fiables para el ciclo fiscal 2025[cite: 259, 270].

## Problema identificado
Al escalar el negocio, se detectó un incremento en la volatilidad absoluta (confirmado por un diagnóstico de correlación media-varianza de **0.86**). [cite_start]Las fluctuaciones estacionales se expandían en proporción a la tendencia de crecimiento, lo que invalidaba los modelos de promedio móvil tradicionales[cite: 259, 314, 315].

## Metodología aplicada
1. [cite_start]**Transformación logarítmica:** Se aplicó para estabilizar la varianza y neutralizar los riesgos de escala que distorsionaban las proyecciones a largo plazo[cite: 260, 283].
2. [cite_start]**Optimización de hiperparámetros:** Calibración de puntos de cambio de tendencia (*changepoint prior scale*) a **0.05** para capturar cambios estructurales genuinos sin sobreajustar a fluctuaciones diarias[cite: 263, 275].
3. [cite_start]**Validación (Backtesting):** Se utilizó validación cruzada de ventana móvil, logrando un **MAPE del 3.58%**, cifra dentro del umbral de tolerancia financiera del 5%[cite: 261, 390].

## Resultados y proyecciones para 2025
El modelo proyecta para el ciclo fiscal 2025:
* [cite_start]**Ingresos Centrales:** \$2,148,183.25 USD[cite: 430, 510].
* [cite_start]**Escenario Pesimista:** \$1,954,988.95 USD[cite: 510].
* [cite_start]**Escenario Optimista:** \$2,382,609.36 USD[cite: 510].

[cite_start]Estos escenarios permiten una asignación de capital estratégica y una gestión de riesgos basada en datos[cite: 262, 279].

## Stack técnico
* **Prophet:** Motor de series temporales.
* **Pandas & NumPy:** Manipulación y limpieza de datos.
* **Seaborn & Matplotlib:** Visualización de tendencias y diagnósticos de varianza.