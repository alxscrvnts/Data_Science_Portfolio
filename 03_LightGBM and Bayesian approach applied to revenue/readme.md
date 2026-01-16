# 03. Strategic Revenue Forecasting under a Bayesian Uncertainty Framework

## Objetivo del proyecto

El objetivo principal fue transicionar de pronósticos deterministas (puntos estáticos) a un Marco de Incertidumbre Bayesiana para la dirección financiera. Se buscó cuantificar no solo el ingreso esperado, sino el riesgo asociado, estableciendo un "Corredor de Seguridad Anual" que permita una toma de decisiones basada en probabilidades reales y no en metas lineales.

## Problema identificado

En el entorno corporativo, las proyecciones suelen entregarse como cifras únicas que ignoran la volatilidad del mercado. Este enfoque tradicional genera "ceguera de riesgo", donde el departamento de Finanzas carece de un piso (floor) y un techo (ceiling) validados matemáticamente, lo que resulta en presupuestos vulnerables a fluctuaciones estacionales y cambios en el comportamiento del usuario.

## Metodología aplicada

Se implementó un enfoque híbrido que combina el poder predictivo del Machine Learning con la robustez estadística de la Inferencia Bayesiana:

1. Ingeniería de características y memoria histórica: Identificación de drivers clave (conversion rate, ad spend) y creación de lags de 7 y 30 días para capturar la dependencia temporal y los ciclos del negocio.
2. Validación robusta (Backtesting): Uso de TimeSeriesSplit para asegurar que el modelo fuera probado exclusivamente en datos cronológicos no vistos, logrando un R^2 global del 97.99%.
3. Cuantificación de incertidumbre (MCMC): Implementación de simulaciones de Monte Carlo mediante cadenas de Markov (algoritmo NUTS en PyMC). Se utilizó el error de validación cruzada (MAE) como prior para generar una distribución posterior que refleja la incertidumbre inherente del mercado.

## Resultados y proyecciones

El marco permitió transformar una cifra incierta en un rango de gestión estratégica para los próximos 365 días:

1. Pronóstico anual garantizado: Se estableció un ingreso total proyectado de $1,235,814.96, con un piso de seguridad validado de $1,230,427.06.
2. Probabilidad de éxito: El modelo cuantificó una probabilidad del 54.95% de superar el rendimiento del año anterior, proporcionando una métrica intuitiva de crecimiento para los stakeholders.
3. Drivers de crecimiento: Se decodificó el modelo de Gradient Boosting, identificando que el Conversion Rate mantiene una correlación de 0.96 con el ingreso, mientras que los gastos de publicidad operan como el principal modulador de volatilidad.

## Stack técnico

**LightGBM:** Motor de regresión de alto rendimiento para capturar relaciones no lineales y dependencias temporales.
**PyMC & ArviZ:** Marco de inferencia bayesiana y visualización de distribuciones posteriores (HDI).
**Scikit-learn:** Implementación de TimeSeriesSplit para validación cruzada sin fuga de datos (leakage).
**Pandas & NumPy:** Ingeniería de variables de retardo (lags) y manipulación de series de tiempo.