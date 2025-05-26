# **Construccion de una Red Neuronal para Predecir Precios de Viviendas**
Un proyecto de instituto donde desarrollamos un modelo de ML, que pueda predecir precios de vivienda.


## **Objetivo**
El objetivo de este proyecto es investigar los fundamentos de redes neuronales y regresión lineal, y aplicar los conocimientos para crear, entrenar y evaluar un modelo de predicción de precios de viviendas utilizando Python y TensorFlow/Keras. Este trabajo integra estructuras de programación, visualización de datos.

1. **Regresión Lineal Simple**: Basada en una sola variable (ej. número promedio de habitaciones).  
2. **Red Neuronal Artificial**: Utilizando múltiples características del dataset para mejorar la precisión.  

Además, se buscó:  
 1. Analizar la relación entre las variables y el precio de las viviendas.  
 2. Evaluar el rendimiento de ambos modelos mediante métricas como **MSE (Error Cuadrático Medio)** y **R² (Coeficiente de Determinación)**.  
 3. Visualizar los resultados de manera clara para entender las diferencias entre los modelos.  

---
## **Metodología**  

### **1. Dataset y Preprocesamiento**  
  - Se utilizó el dataset **California Housing** de Scikit-learn, que contiene información como:  
  - Número de habitaciones (`AveRooms`).  
  - Ingreso medio de los residentes (`MedInc`).  
  - Ubicación geográfica (`Latitude`, `Longitude`).  
  - Precio de las viviendas (`PRICE`).  
  - Los datos se normalizaron para la red neuronal usando **StandardScaler**.  

### **2. Modelos Implementados**  

#### **Regresión Lineal Simple**  
- **Entrada:** Solo una variable (`AveRooms`).  
- **Salida:** Predicción del precio basada en una relación lineal.  
- **Métricas calculadas:**  
  - **MSE (Mean Squared Error)** → Mide el error promedio al cuadrado.  
  - **R² (R-squared)** → Indica qué porcentaje de la variabilidad del precio explica el modelo.  

#### **Red Neuronal (TensorFlow/Keras)**  
- **Arquitectura:**  
  - **Capas:** 2 capas ocultas con activación **ReLU** y una capa de salida lineal.  
  - **Optimizador:** Adam (tasa de aprendizaje = 0.001).  
  - **Función de pérdida:** MSE (Error Cuadrático Medio).  
- **Entrenamiento:**  
  - **80% datos para entrenamiento**, 20% para prueba.  
  - **Early Stopping** para evitar sobreajuste.  

### **3. Visualización de Resultados**  
Se generaron gráficos para:  
 **Relación entre variables y precio** (scatter plots).  
 **Comparación entre valores reales y predicciones**.  
 **Evolución del error durante el entrenamiento** (pérdida en entrenamiento vs validación).  
 **Comparación final entre modelos** (R² de Regresión Lineal vs Red Neuronal).  

---

## **Resultados Obtenidos**  

### **Regresión Lineal Simple**  
- **MSE:** ~1.2 (en escala normalizada).  
- **R²:** ~30-40% (explica solo una parte de la variabilidad).  
- **Conclusión:** Funciona bien para una sola variable, pero no captura relaciones complejas.  

### **Red Neuronal**  
- **MSE:** ~0.3 (mucho menor que la regresión lineal).  
- **R²:** ~70-80% (explica mejor la variabilidad del precio).  
- **Conclusión:** Aprende patrones no lineales y mejora significativamente las predicciones.  

### **Comparación Final**  
| Modelo               | MSE (↓ mejor) | R² (↑ mejor) |  
|----------------------|--------------|-------------|  
| **Regresión Lineal** | ~1.2         | ~30-40%     |  
| **Red Neuronal**     | **~0.3**     | **~70-80%** |  

**Conclusión:**  
- La **red neuronal supera a la regresión lineal** al considerar múltiples variables.  
- La **visualización de datos** fue clave para entender las relaciones entre características y precio.  
- **GitHub** permitió un control de versiones eficiente del proyecto.  

---  
### **Archivos Generados**  
- `feature_relationships.png` → Relación entre variables.  
- `linear_regression.png` → Resultados de regresión lineal.  
- `nn_training.png` → Evolución del entrenamiento de la red.  
- `nn_predictions.png` → Predicciones vs valores reales.  
- `model_comparison.png` → Comparación final de modelos.  

### **Posibles Mejoras**  
- Probar con **más capas y neuronas** en la red.  
- Usar **otras técnicas de regularización** (L2, Dropout).  
- Aplicar **GridSearchCV** para optimizar hiperparámetros.  

Este proyecto demostró que las **redes neuronales son poderosas para problemas de regresión**, pero requieren un buen preprocesamiento de datos y ajuste de hiperparámetros.
