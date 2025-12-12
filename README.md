# Predicción de Churn con Modelos de Ensamble  
**Desafío 1 — Ciencia de Datos (SDM)**

Proyecto de **machine learning aplicado** orientado a la **detección temprana de churn** en telecomunicaciones, utilizando modelos de ensamble y métricas enfocadas en la clase minoritaria.

Este trabajo forma parte de mi **portafolio profesional en Data Science / Machine Learning** y cubre el ciclo completo:
- exploración y comprensión del problema,
- modelado con múltiples enfoques,
- evaluación crítica de métricas,
- interpretación de resultados,
- traducción a decisiones de negocio accionables.

---

## 1. Contexto del problema

Una empresa ficticia de telecomunicaciones busca identificar clientes con **alta probabilidad de abandono (churn)** antes de que este ocurra, con el fin de priorizar acciones de retención.

El dataset contiene variables de:
- uso del servicio,
- facturación y sobrecargos,
- antigüedad del cliente,
- interacción con soporte.

### Objetivos del proyecto
1. **Predecir churn** (clasificación binaria).
2. **Comparar modelos base y de ensamble** bajo un escenario de clases desbalanceadas.
3. **Identificar los drivers principales del abandono** desde una perspectiva técnica y de negocio.
4. **Generar rankings accionables de clientes en riesgo**.

Este tipo de análisis es central en industrias de ingresos recurrentes como telecomunicaciones, banca, seguros, SaaS y utilities.

---

## 2. Enfoque metodológico

El proyecto se desarrolla de forma incremental y comparativa:

- **Exploración de datos (EDA)** con foco en desbalance, patrones de uso y costos.
- **Modelos base**: Árbol de Decisión.
- **Modelos de ensamble**:
  - Bagging homogéneo con SMOTE.
  - Bagging heterogéneo (con calibración de importancia).
  - Random Forest (baseline y optimizado).
- **Optimización** mediante GridSearchCV.
- **Evaluación** con métricas adecuadas para churn:
  - Precision, Recall y F1-score (clase positiva).
  - Balanced Accuracy.
  - ROC–AUC.
- **Interpretabilidad** vía importancia de variables.
- **Segmentación final** de clientes con mayor riesgo.

---

## 3. Estructura del repositorio

~~~text
ml-ensambles-desafio-1/
├── notebooks/                    # Exploración, modelado y reportes ejecutables
│   ├── 00_ensambles_desafio_sdm_original.ipynb
│   └── 02_modelos_ensamble_churn_sdm.ipynb
│
├── src/ml_ensambles_desafio_1/    # Utilidades (bagging, evaluación)
│
├── data/
│   ├── raw/                      # Dataset original
│   └── processed/                # Derivados intermedios
│
├── reports/
│   └── figures/                  # Gráficos y salidas
│
├── requirements.txt
└── README.md
~~~

---

## 4. Ejecución local (Windows / PowerShell)

### 1) Crear y activar entorno virtual

~~~bash
python -m venv .venv
. .venv/Scripts/activate
~~~

### 2) Instalar dependencias

~~~bash
pip install -r requirements.txt
~~~

### 3) Ejecutar el notebook principal

~~~bash
jupyter notebook notebooks/02_modelos_ensamble_churn_sdm.ipynb
~~~

---

## 5. Ejecución en Google Colab

El notebook principal puede ejecutarse directamente en Google Colab:

[![Abrir en Google Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/sergiodelgado/ml-ensambles-desafio-1/blob/main/notebooks/02_modelos_ensamble_churn_sdm.ipynb)

Esto permite:
- reproducir el análisis sin configuración local,
- experimentar con variantes del modelo,
- mantener trazabilidad desde GitHub.

---

## 6. Resultados principales

### Comparación de modelos

Se evaluaron múltiples enfoques, destacando:

- Árbol de Decisión (baseline y optimizado).
- Bagging homogéneo + SMOTE (alto recall, más falsos positivos).
- Bagging heterogéneo calibrado (buen equilibrio, mayor complejidad).
- **Random Forest optimizado (modelo final)**.

### Modelo final recomendado

**Random Forest optimizado (GridSearchCV)**:
- ROC–AUC: **0.86**
- Recall (Churn): **0.63**
- F1-score (Churn): **0.71**
- OOB Accuracy: **0.94**

### Variables más influyentes

- `DayMins`
- `MonthlyCharge`
- `CustServCalls`
- `OverageFee`

Estas variables confirman que el churn está asociado a **uso intensivo, costos elevados y fricción operativa**, en línea con el análisis exploratorio.

---

## 7. Segmentación de clientes de alto riesgo

El modelo final permite generar un **ranking de clientes por probabilidad estimada de churn**, identificando patrones comunes en los casos de mayor riesgo y habilitando:

- campañas de retención focalizadas,
- ofertas personalizadas,
- alertas tempranas basadas en datos.

---

## 8. Próximas extensiones posibles

- Calibración de probabilidades (Platt / Isotonic).
- Explainability avanzada (SHAP, Permutation Importance).
- Umbrales de decisión dependientes de costo.
- Pipeline productivo (scikit-learn + serialización).
- Publicación del reporte como HTML o GitHub Pages.

---

## 9. Licencia

MIT — uso libre con atribución.
