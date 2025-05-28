# 🛢️ Predicción de ganancias en pozos petroleros

Este proyecto consiste en el desarrollo de un modelo de aprendizaje automático para predecir las ganancias esperadas de pozos petroleros, con base en datos geológicos reales.

La idea es ayudar a una empresa petrolera a decidir en qué regiones invertir, maximizando beneficios y minimizando riesgos financieros.

---

## 🔍 Objetivo

- Predecir la cantidad de recursos extraídos en nuevos pozos con regresión lineal.
- Estimar ganancias potenciales en cada región.
- Evaluar riesgos con simulaciones de bootstrap.

---

## 🛠️ Herramientas y tecnologías

- `pandas`
- `numpy`
- `scikit-learn`
- `Jupyter Notebook`

---

## 🧠 Técnicas utilizadas

- Regresión lineal
- Simulación estadística con bootstrapping (1000 iteraciones)
- Evaluación del ingreso promedio esperado
- Cálculo de intervalos de confianza (95%)
- Estimación del riesgo de pérdida

---

## 📊 Dataset

Se utilizaron tres archivos `.csv` (`geo_data_0.csv`, `geo_data_1.csv`, `geo_data_2.csv`) que contienen:
- `feature`: Característica geológica predictora
- `target`: Producción esperada (en miles de barriles)
- `id`: Identificador del pozo

---

## 📌 Conclusiones destacadas

- La **Región 1** fue identificada como la opción más viable:
  - Mayor ingreso promedio esperado: **$104,848,209.26**
  - Intervalo de confianza del 95% está por encima del punto de equilibrio
  - Riesgo de pérdida más bajo: **0.9%**

---

## 🚀 Cómo ejecutarlo

1. Clona este repositorio:
   ```bash
   git clone https://github.com/cesardud/oil-well-profit-prediction.git
   cd oil-well-profit-prediction
   pip install -r requirements.txt
   jupyter notebook notebook.ipynb


