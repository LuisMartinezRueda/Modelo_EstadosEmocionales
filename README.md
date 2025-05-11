## Modelo de Clasificación Emocional

Este sistema emplea algoritmos de aprendizaje automático para clasificar señales fisiológicas periféricas (`EDA`, `BVP`, `Temperatura`) en tres estados emocionales: **neutro**, **estrés** y **diversión**.

### Algoritmos evaluados
- Random Forest
- Support Vector Machine (SVM)
- K-Nearest Neighbors (KNN)
- XGBoost

### Dataset utilizado
- [WESAD Dataset](https://ubi29.informatik.uni-siegen.de/usi/data_wesad.html)
- Señales empleadas: EDA (actividad electrodérmica), BVP (volumen del pulso sanguíneo), TEMP (temperatura de la piel)

### Preprocesamiento
- Sincronización de señales por timestamp
- Segmentación en ventanas de 10 segundos
- Extracción de características estadísticas y espectrales
- Normalización (`Z-score`)
- Balanceo de clases con:
  - SMOTE
  - SMOTE-Tomek
  - ADASYN

### Métricas de evaluación
- Accuracy
- Precision
- Recall
- F1-score
- AUC (Area Under Curve)

### Mejor modelo
El modelo XGBoost, entrenado con la técnica de balanceo SMOTE-Tomek, logrando un rendimiento destacado:

| Estado emocional | Precisión | Recall | F1-score |
|------------------|-----------|--------|----------|
| Amusement        | 0.87      | 0.92   | 0.89     |
| Baseline         | 0.96      | 0.92   | 0.94     |
| Stress           | 0.86      | 0.90   | 0.88     |

- **Accuracy global:** `0.91`
- **Macro avg:** Precision: `0.90`, Recall: `0.91`, F1-score: `0.90`
- **Weighted avg:** Precision: `0.92`, Recall: `0.91`, F1-score: `0.92`
