# Ensambles | Desafío 1 (SDM)

Este proyecto forma parte de mi portafolio profesional en ciencia de datos.  
Su objetivo es aplicar técnicas de **ensambles de modelos** (Random Forest, Gradient Boosting, Stacking, etc.)  
para resolver un problema de clasificación y comparar su rendimiento usando métricas clave.

---

## 🧱 Estructura del proyecto
- `notebooks/` → análisis principal, exploración y experimentación.
- `src/` → utilidades reutilizables (carga de datos, métricas, pipelines).
- `data/` → crudos (no versionados) y procesados (muestras pequeñas).
- `reports/` → gráficos y métricas exportadas automáticamente.
- `requirements.txt` → dependencias para ejecutar el proyecto.

---

## ⚙️ Cómo ejecutar (Windows)
Abre **Git Bash o PowerShell** en la raíz del repo y corre en orden:

### 1) Crear y activar entorno virtual
~~~bash
python -m venv .venv && . .venv/Scripts/activate
~~~

### 2) Instalar dependencias
~~~bash
pip install -r requirements.txt
~~~

### 3) Abrir el notebook
~~~bash
jupyter notebook notebooks/01_ensambles_desafio_sdm.ipynb
~~~

> Si ves `(.venv)` al inicio de tu línea de comandos, el entorno está activo.

---

## 📊 Resultados esperados
- Comparación de modelos de ensamble.
- Tabla de métricas (F1, Precision, Recall, ROC-AUC).
- Visualizaciones (ROC, matriz de confusión, feature importance).
- Exportación de resultados en `reports/`.

---

## 🗺️ Futuras mejoras
- Búsqueda de hiperparámetros y validación cruzada estratificada.
- Calibración de probabilidades y ajuste de umbral.
- Explicabilidad (Permutation Importance / SHAP).
- Publicación del notebook como HTML (Pages).

---

## 📜 Licencia
MIT — uso abierto con atribución.
