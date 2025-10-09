# 🛢️ Predicción de Ganancias y Evaluación de Riesgos en Pozos Petroleros

Este proyecto consiste en el desarrollo de un modelo de Regresión Lineal para predecir las reservas de petróleo y ayudar a la compañía **OilyGiant** a seleccionar la mejor región para invertir en el desarrollo de 200 pozos nuevos, maximizando el beneficio y minimizando el riesgo.

---

## 🎯 Objetivo y Condiciones de Negocio

El proyecto debe asegurar la viabilidad de la inversión y la selección de la región óptima, cumpliendo con las siguientes condiciones estrictas:

* [cite_start]**Modelo Requisito:** Se debe utilizar exclusivamente la **Regresión Lineal** para el entrenamiento del modelo[cite: 73].
* [cite_start]**Volumen de Inversión:** El presupuesto para el desarrollo de **200 pozos** es de **$100 millones de USD**[cite: 66].
* [cite_start]**Punto de Equilibrio:** Para evitar pérdidas, la producción media requerida por pozo es de **$111.1$ mil barriles**[cite: 66, 68].
* [cite_start]**Proceso de Exploración:** La decisión de inversión se basa en un estudio de **$500$ puntos** de exploración, de los cuales se seleccionan los **$200$ mejores** para el cálculo del beneficio (Simulación *Bootstrapping*)[cite: 73].
* [cite_start]**Criterio de Riesgo:** Después de la evaluación de riesgo, solo se deben mantener las regiones con un **riesgo de pérdidas inferior al $2.5\%$**[cite: 73].
* [cite_start]**Decisión Final:** De las regiones que cumplan el criterio de riesgo, se seleccionará aquella con el **beneficio promedio más alto**[cite: 73].

---

## 🛠️ Herramientas y Tecnologías

### Lenguajes
* **Lenguajes:** Python.

### Librerías Core y Modelado
* **Core Data:** Pandas, NumPy (procesamiento de datos y álgebra lineal).
* **Machine Learning:** Scikit-learn (Regresión Lineal, Métricas de error).
* **Técnicas:** Simulación estadística con **Bootstrapping** (1000 iteraciones), División 75:25 (Train/Test).

---

## 🧠 Metodología y Análisis

1.  [cite_start]**Datos Sintéticos:** El análisis se realizó sobre datos sintéticos de tres regiones ($0, 1, 2$)[cite: 71]. [cite_start]Se confirmó que los datos estaban completos y listos para el modelado sin necesidad de preprocesamiento extensivo[cite: 8, 10].
2.  [cite_start]**Modelado Base (Regresión Lineal):** La Regresión Lineal fue entrenada para predecir el volumen de reservas en cada región[cite: 30, 32].
    * [cite_start]**RMSE y Medias:** El análisis inicial mostró que la producción promedio predicha de **ninguna de las regiones** ($92.39$k, $68.97$k, $94.94$k barriles) superaba el punto de equilibrio de $111.1$ mil barriles, lo que indicó la necesidad de una estrategia de selección de pozos más precisa[cite: 32, 18, 68].
3.  [cite_start]**Simulación *Bootstrapping* (Evaluación de Riesgo):** Para abordar la incertidumbre, se aplicó la técnica de *bootstrapping* con **$1000$ iteraciones** sobre muestras de $500$ puntos[cite: 22, 26, 73]. [cite_start]En cada iteración, se seleccionaron los $200$ pozos con el mayor valor predicho para calcular la ganancia real esperada[cite: 22].

---

## 📈 Resultados y Decisión Final (Bootstrapping)

La decisión final se basó en el análisis probabilístico de riesgo y beneficio del *bootstrapping*.

| Región | Ingreso Promedio Esperado | Intervalo de Confianza (95%) | Riesgo de Pérdida (Meta < 2.5%) |
| :--- | :--- | :--- | :--- |
| Región 0 | $104.21 millones | $98.89M — $109.63M | [cite_start]6.60% [cite: 26] |
| **Región 1** | **$104.85 millones** | **$101.04M — $108.88M** | [cite_start]**0.90%** [cite: 26] |
| Región 2 | $104.16 millones | $98.93M — $109.63M | [cite_start]5.70% [cite: 26] |

[cite_start]**Decisión Final:** Se propone la **Región 1** para el desarrollo de pozos[cite: 26].

**Justificación y Aplicación Práctica:**

* [cite_start]**Cumplimiento del Riesgo:** La Región 1 es la única que cumple con el criterio de riesgo estricto, con solo un **$0.90\%$ de probabilidad de pérdida** (muy inferior al $2.5\%$ máximo permitido)[cite: 26, 73].
* [cite_start]**Mayor Beneficio:** Ofrece el **ingreso promedio esperado más alto** entre las tres regiones[cite: 26].
* [cite_start]**Impacto Analítico:** La Región 1 se convierte en la opción más viable, ya que presenta una mayor probabilidad de contener pozos de alta producción, influida por diversos factores geológicos, lo que se traduce en mayores ganancias esperadas y el menor riesgo de pérdida[cite: 26]. [cite_start]El análisis de *bootstrapping* demostró que la decisión de inversión no debe basarse solo en la producción promedio, sino en la **gestión probabilística de riesgo**[cite: 26].

---


## 🚀 Cómo ejecutarlo

1. Clona este repositorio:
   ```bash
   git clone https://github.com/cesardud/oil-well-profit-prediction.git
2. Navega al proyecto:
   ```bash
   cd oil-well-profit-prediction
4. Instala las librerías requeridas:
    ```bash
   pip install -r requirements.txt
6. Abre el notebook:
    ```bash
   jupyter notebook notebook.ipynb

