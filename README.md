# Predicción de Churn con Modelos de Ensamble  
**Desafío 1 — Ciencia de Datos (SDM)**

Este proyecto forma parte de mi portafolio profesional en ciencia de datos.  
Su objetivo es aplicar técnicas de **ensamble de modelos** (Random Forest, Bagging, Árboles de Decisión y variantes optimizadas) para resolver un problema realista de **clasificación binaria orientada a la predicción de churn** en telecomunicaciones.

El enfoque combina:
- Exploración sistemática del dataset (EDA),
- Entrenamiento de modelos individuales y de ensamble,
- Evaluación comparativa con métricas robustas,
- Análisis de interpretabilidad y segmentación de clientes de alto riesgo.

---

## 1. Contexto del problema

Una empresa ficticia de telecomunicaciones busca identificar clientes con alta probabilidad de abandono.  
El dataset contiene variables de uso, facturación, antigüedad y atributos del servicio contratado.

El objetivo es:
1. **Predecir churn** (sí/no),
2. **Identificar modelos que mejor capturan el patrón de abandono**,  
3. **Determinar drivers clave** del comportamiento de baja.

Este tipo de análisis es central en industrias basadas en ingresos recurrentes: telecomunicaciones, banca, SaaS, utilities y otros servicios.

---

## 2. Estructura del repositorio

```text
ml-ensambles-desafio-1/
├── notebooks/               # Exploración, modelado y reportes ejecutables
│   ├── 00_ensambles_desafio_sdm_original.ipynb
│   └── 02_modelos_ensamble_churn_sdm.ipynb
│
├── src/ml_ensambles_desafio_1/   # Utilidades (pipelines, modelos, evaluación)
│
├── data/
│   ├── raw/                 # Dataset original (versionado)
│   └── processed/           # Derivados (no versionados)
│
├── reports/                 # Gráficos, métricas y salidas exportadas
│   └── figures/
│
├── requirements.txt         # Dependencias del proyecto
└── README.md
```

---

## 3. Cómo ejecutar el proyecto (Windows / PowerShell)

### 1) Crear y activar entorno virtual

~~~bash
python -m venv .venv
. .venv/Scripts/activate
~~~

### 2) Instalar dependencias

~~~bash
pip install -r requirements.txt
~~~

### 3) Ejecutar notebooks

~~~bash
jupyter notebook notebooks/02_modelos_ensamble_churn_sdm.ipynb
~~~

> Verifica que aparece `(.venv)` en tu terminal para asegurar el entorno correcto.

---

## 4. Ejecutar en Google Colab

Si prefieres ejecutar el análisis directamente en la nube, sin instalar dependencias locales, puedes abrir el notebook principal en Google Colab usando el siguiente acceso directo:

[![Abrir en Google Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/sergiodelgado/ml-ensambles-desafio-1/blob/main/notebooks/02_modelos_ensamble_churn_sdm.ipynb)

Este entorno permite:
- Ejecutar el notebook sin configuración adicional,
- Modificar código y probar variantes,
- Usar recursos gratuitos de GPU/TPU (si fuese necesario),
- Mantener el flujo de análisis reproducible desde GitHub.

---


## 5. Resultados y análisis

Los notebooks incluyen:

### Evaluación de modelos
- Árbol de Decisión (baseline y optimizado)
- Bagging
- Random Forest (+ búsqueda de hiperparámetros)
- Comparación de métricas:
  - Accuracy  
  - Precision / Recall  
  - F1-score  
  - ROC–AUC  

### Visualizaciones
- Matrices de confusión  
- Curvas ROC  
- Feature Importance  
- Distribuciones de churn

### Segmentación
- Ranking de clientes con mayor probabilidad de abandono  
- Exportación automática a `reports/`  

---

## 6. Próximas mejoras sugeridas
- Validación cruzada estratificada y búsqueda más exhaustiva de hiperparámetros.  
- Calibración de probabilidades (Platt/Isotonic).  
- Explainability: SHAP, Permutation Importance.  
- Pipeline reproducible con `src/` + `notebooks/` + `reports/`.  
- Publicación del informe como HTML o en GitHub Pages.  
- Versión ejecutable en Google Colab con badge directo desde README.

---

## 7. Licencia
MIT — uso libre con atribución.
