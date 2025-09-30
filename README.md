# regresion-clasificacion-estudiantes
Proyecto de Machine Learning para predicción de rendimiento académico de estudiantes mediante modelos de regresión y clasificación.
# Proyecto ML — Regresión & Clasificación: Rendimiento académico de estudiantes

Predicción de **nota final** (regresión) y de **aprobado** (clasificación binaria) a partir de variables académicas y de hábitos de estudio.

> Módulo ThePower: *Regresión y clasificación (opcional)*

---

## 1) Objetivos

- **Regresión:** predecir `nota_final` (0–100).
- **Clasificación:** predecir `aprobado` (`1` si `nota_final ≥ 60`, `0` en caso contrario).
- Cumplir los requisitos del proyecto: **EDA**, **preprocesado**, **entrenamiento/validación** para ambos enfoques, y **entrega en GitHub**.

---

## 2) Dataset

Archivo: `datos/dataset_estudiantes.csv`  
Columnas de entrada:

- `horas_estudio_semanal` (num)
- `nota_anterior` (num)
- `tasa_asistencia` (num, %)
- `horas_sueno` (num)
- `edad` (num)
- `nivel_dificultad` (cat)
- `tiene_tutor` (cat)
- `horario_estudio_preferido` (cat)
- `estilo_aprendizaje` (cat)

Variables objetivo:
- **Regresión:** `nota_final` (0–100)
- **Clasificación:** `aprobado` (1 si `nota_final ≥ 60`, 0 si no). Si no existe, se genera en el código.

## 3) Estructura del repositorio
  .
├─ datos/
│ └─ dataset_estudiantes.csv
├─ cuadernos/
│ ├─ 01_EDA.ipynb
│ ├─ 02_Preprocesado.ipynb
│ ├─ 03_Modelo_Regression.ipynb
│ └─ 04_Modelo_Clasificacion.ipynb
├─ modelos/
│ ├─ preprocesador.pkl
│ ├─ nombres_features.csv
│ ├─ X_train_proc.npy
│ ├─ X_test_proc.npy
│ ├─ y_reg_train.csv
│ ├─ y_reg_test.csv
│ ├─ y_clf_train.csv
│ └─ y_clf_test.csv
├─ .gitignore
├─ LICENCIA
└─ LEÁME.md / README.md


> **Nota:** El directorio `modelos/` se genera al ejecutar `02_Preprocesado.ipynb`.

---

## 4) Requisitos y entorno

- Python 3.10+ (recomendado 3.11/3.12)
- Dependencias (archivo `requirements.txt`):

pandas
numpy
scikit-learn
matplotlib
seaborn
joblib


---

## 5) Cómo reproducir (paso a paso)

1. Ejecutar `cuadernos/01_EDA.ipynb` (exploración, correlaciones y observaciones).
2. Ejecutar `cuadernos/02_Preprocesado.ipynb` (imputación, escalado, one-hot, splits).
3. Ejecutar `cuadernos/03_Modelo_Regresion.ipynb` (LinearRegression y RandomForest).
4. Ejecutar `cuadernos/04_Modelo_Clasificacion.ipynb` (LogisticRegression y RandomForestClassifier).

Todos los notebooks están diseñados para funcionar con las rutas relativas establecidas.

---

## 6) Resultados

### Regresión (test)
| Modelo                 | MAE  | RMSE | R²   |
|------------------------|------|------|------|
| LinearRegression       | …    | …    | …    |
| RandomForestRegressor | …    | …    | …    |

### Clasificación (test)
| Modelo                 | Accuracy | Precision | Recall | F1   | ROC-AUC |
|------------------------|----------|-----------|--------|------|---------|
| LogisticRegression     | …        | …         | …      | …    | …       |
| RandomForestClassifier | …        | …         | …      | …    | …       |

---

## 7) Decisiones técnicas

- Estratificación por `aprobado` para preservar proporciones.
- `ColumnTransformer` para evitar fugas (fit solo en train).
- `class_weight='balanced'` en clasificación por desbalance.
- Semilla fija para reproducibilidad (`random_state=42`).

---

## 8) Autor

Proyecto académico de Machine Learning – ThePower  
Desarrollado por **@atnecan**

