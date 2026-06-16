# Tarea 2 – Módulo 2: Regresión Lineal Simple en Machine Learning

## Introducción

La regresión es una de las técnicas más utilizadas en Machine Learning para predecir valores numéricos a partir de datos históricos. En esta actividad se investigan los conceptos fundamentales de la Regresión Lineal Simple, sus métricas de evaluación y las buenas prácticas para construir modelos capaces de generalizar correctamente a nuevos datos.

## 1️⃣ ¿Qué es la regresión y cuál es su propósito en Machine Learning?

La regresión es una técnica de aprendizaje supervisado cuyo objetivo es predecir una variable numérica continua a partir de una o varias variables independientes.

Se utiliza para estimar valores como:

- 🏠 Precio de una vivienda
- 💰 Salario de un empleado
- 📈 Ventas futuras
- ⚡ Consumo energético

La principal diferencia con la clasificación es que la regresión predice valores numéricos, mientras que la clasificación predice categorías o etiquetas.

**Ejemplo:**

- Regresión → Predecir un salario de 45.000 €
- Clasificación → Determinar si un correo es spam o no

## 2️⃣ ¿Qué es la Regresión Lineal Simple y qué representa la ecuación ŷ = β₀ + β₁·X?

La Regresión Lineal Simple es un modelo matemático que representa la relación entre una variable independiente (X) y una variable dependiente (y) mediante una línea recta.

**Ecuación del modelo:**

ŷ = β₀ + β₁·X

Donde:

- **ŷ** → Valor predicho por el modelo.
- **β₀** → Intercepto o punto donde la recta corta el eje Y.
- **β₁** → Pendiente de la recta.
- **X** → Variable independiente.

### Ejemplo práctico

Si utilizamos los años de experiencia para predecir el salario:

- β₀ representa el salario estimado con 0 años de experiencia.
- β₁ indica cuánto aumenta el salario por cada año adicional de experiencia.

## 3️⃣ ¿Cuáles son los supuestos de la Regresión Lineal?

Para que el modelo sea válido deben cumplirse varios supuestos:

### 📍 Linealidad

La relación entre X e y debe aproximarse a una línea recta.

### 📍 Homocedasticidad

La variabilidad de los errores debe mantenerse constante.

### 📍 Independencia de errores

Los errores de una observación no deben depender de otra.

### 📍 Normalidad de los residuos

Los residuos deberían seguir una distribución aproximadamente normal.

Verificar estos supuestos permite obtener modelos más fiables y conclusiones más precisas.

## 4️⃣ ¿Qué es la función de coste? Diferencia entre MSE y MAE

La función de coste mide el error cometido por el modelo comparando los valores reales con las predicciones.

### 📊 MSE (Mean Squared Error)

Calcula el promedio de los errores elevados al cuadrado.

**Fórmula:**

MSE = (1/n) Σ(y − ŷ)²

**Ventajas:**

- Penaliza fuertemente los errores grandes.
- Muy utilizada durante el entrenamiento.

**Desventaja:**

- Sensible a valores atípicos (outliers).

### 📊 MAE (Mean Absolute Error)

Calcula el promedio de los errores absolutos.

**Fórmula:**

MAE = (1/n) Σ|y − ŷ|

**Ventajas:**

- Fácil de interpretar.
- Menos sensible a outliers.

Se suele preferir MAE cuando se busca una métrica más robusta y sencilla de explicar.

## 5️⃣ ¿Qué significa dividir los datos en train y test?

La división train/test consiste en separar los datos en dos conjuntos:

### 🧠 Train (Entrenamiento)

Se utiliza para construir y entrenar el modelo.

### 🧪 Test (Prueba)

Se utiliza para evaluar el rendimiento con datos no vistos previamente.

Esta división permite comprobar si el modelo es capaz de generalizar correctamente a nuevas observaciones.

Si se evaluara con los mismos datos de entrenamiento, el resultado sería demasiado optimista y poco realista.

## 6️⃣ ¿Qué métricas se usan para evaluar un modelo de regresión?

### 📈 R² (Coeficiente de Determinación)

Mide la proporción de variabilidad explicada por el modelo.

**Fórmula:**

R² = 1 − (SSres / SStot)

**Interpretación:**

- R² = 1 → Ajuste perfecto.
- R² = 0 → No explica la variabilidad.
- Cuanto más cercano a 1, mejor.

### 📈 MSE (Mean Squared Error)

MSE = (1/n) Σ(y − ŷ)²

Mide el error promedio al cuadrado.

### 📈 RMSE (Root Mean Squared Error)

RMSE = √MSE

Representa el error medio en las mismas unidades de la variable objetivo.

### 📈 MAE (Mean Absolute Error)

MAE = (1/n) Σ|y − ŷ|

Representa el error absoluto promedio cometido por el modelo.

## 7️⃣ ¿Qué son los residuos y para qué sirve analizarlos?

Los residuos representan la diferencia entre el valor real y el valor predicho.

**Fórmula:**

Residuo = y − ŷ

Un residuo cercano a cero indica que la predicción ha sido precisa.

Analizar los residuos permite:

- 🔍 Detectar errores sistemáticos.
- 🔍 Comprobar si el modelo es adecuado.
- 🔍 Identificar posibles incumplimientos de los supuestos de regresión.

Si los residuos muestran patrones claros, puede indicar que la relación no es lineal o que existe algún problema en el modelo.

## 8️⃣ ¿Qué es el overfitting y cómo se detecta comparando R² en train y test?

El overfitting o sobreajuste ocurre cuando el modelo aprende demasiado bien los datos de entrenamiento, incluyendo ruido y particularidades específicas de la muestra.

Se detecta comparando el rendimiento entre entrenamiento y prueba:

### ✅ Buen ajuste

- R² Train = 0.90
- R² Test = 0.88

El modelo generaliza correctamente.

### ⚠️ Overfitting

- R² Train = 0.98
- R² Test = 0.55

El modelo funciona muy bien en entrenamiento pero falla con datos nuevos.

## 9️⃣ ¿Qué es la validación cruzada (Cross-Validation)?

La validación cruzada es una técnica que divide los datos en varios grupos o *folds*.

El proceso consiste en:

1. Entrenar el modelo con varios folds.
2. Evaluarlo con el fold restante.
3. Repetir el proceso varias veces.
4. Calcular el promedio de las métricas obtenidas.

### 🎯 Ventajas

- Reduce la dependencia de una única partición train/test.
- Proporciona una evaluación más robusta.
- Aprovecha mejor los datos disponibles.

## 📝 Conclusión

La Regresión Lineal Simple constituye una de las bases fundamentales del Machine Learning supervisado. A través de este modelo es posible comprender conceptos clave como entrenamiento, predicción, evaluación y análisis de errores.

Además, métricas como **R²**, **MAE**, **MSE** y **RMSE** permiten medir objetivamente el rendimiento del modelo, mientras que técnicas como la **validación cruzada** ayudan a garantizar que los resultados sean fiables y generalizables a nuevos datos.

## 👩‍💻 Autor

**Gabriela Granja**  
**Marketing, Automation & AI**

🔗 GitHub: https://github.com/gabrielagranja

*Proyecto desarrollado dentro del Bootcamp de Inteligencia Artificial y Data Science de Factoría F5.*
