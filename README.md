# Clasificación de Radiografías de Tórax con Redes Neuronales Convolucionales (CNN)

Este proyecto desarrolla y compara dos modelos de aprendizaje profundo para la **clasificación automática de radiografías de tórax** en cuatro categorías:  
**COVID-19, Neumonía, Normal y No COVID**.  
Se emplea un modelo de **CNN construida desde cero** y otro basado en **Transfer Learning** para evaluar diferencias de rendimiento, precisión y capacidad de generalización.

---

## 1. Descripción del Proyecto

El objetivo principal es **detectar patrones característicos** en radiografías de tórax que permitan diferenciar entre casos de COVID-19, neumonía bacteriana o viral, pacientes sanos y otros casos no relacionados con COVID.

Este trabajo busca contribuir al desarrollo de herramientas automáticas de apoyo diagnóstico que puedan reducir el tiempo de análisis médico y mejorar la detección temprana de enfermedades respiratorias.

---

## 2. Dataset Utilizado

Se utilizó el conjunto de datos **COVID-19 Radiography Database**, disponible públicamente en Kaggle.  
El dataset incluye imágenes de rayos X de tórax clasificadas en cuatro carpetas:

- `COVID`
- `Pneumonia`
- `Normal`
- `No COVID`

Cada clase fue balanceada para el entrenamiento mediante técnicas de muestreo y preprocesamiento de imágenes.

---

## 3. Preprocesamiento de Datos

El proceso de limpieza y preparación de imágenes se fundamentó en la revisión de **tres artículos científicos** enfocados en el tratamiento de imágenes médicas y detección de COVID-19 mediante aprendizaje profundo.  
Entre los pasos principales se incluyeron:

- Redimensionamiento y normalización de las imágenes.  
- Aumento de datos (*Data Augmentation*) para reducir sobreajuste.  
- Divisiones estratificadas en conjuntos de entrenamiento, validación y prueba.  
- Estandarización de formatos de entrada para compatibilidad con redes convolucionales.

---

## 4. Arquitectura de los Modelos

Se implementaron dos enfoques complementarios:

### 4.1 Modelo CNN desde cero
Diseñado manualmente con capas convolucionales, *max pooling* y *dropout* para evitar sobreajuste.  
Permite entender el flujo interno de una CNN aplicada a imágenes médicas.

### 4.2 Modelo con Transfer Learning
Se utilizó una arquitectura preentrenada (**EfficientNetB0**) sobre *ImageNet*, ajustada con *fine-tuning* a las radiografías del dataset.  
Este modelo acelera el entrenamiento y mejora la generalización al aprovechar características visuales ya aprendidas.

---

## 5. Comparación y Resultados

Ambos modelos fueron evaluados mediante métricas de desempeño estándar:

- Accuracy  
- Precision, Recall y F1-score por clase  
- Matriz de confusión  
- Curvas ROC y AUC  

Se observó que el modelo basado en **Transfer Learning** alcanzó una **mayor precisión global** y un mejor equilibrio entre sensibilidad y especificidad, especialmente en la detección de COVID-19.

---

## 6. Requisitos del Entorno

El proyecto fue desarrollado en **Python 3.x** empleando las siguientes librerías principales:

- TensorFlow / Keras  
- NumPy  
- Pandas  
- Matplotlib  
- scikit-learn  

El notebook puede ejecutarse en **Google Colab** o en entornos locales con GPU.

---

## 7. Estructura del Notebook

El archivo principal es:
Se organiza en las siguientes secciones:

1. Importación de librerías y carga de datos  
2. Preprocesamiento y visualización  
3. Definición y entrenamiento de la CNN base  
4. Implementación de Transfer Learning  
5. Evaluación comparativa  
6. Conclusiones

---

## 8. Conclusiones

El experimento demuestra que el **Transfer Learning** ofrece una ventaja significativa en tareas de clasificación médica con datasets limitados, al reducir el tiempo de entrenamiento y mejorar la precisión sin necesidad de diseñar arquitecturas complejas desde cero.

Sin embargo, la **CNN personalizada** mantiene un valor educativo importante al permitir comprender cómo se extraen y combinan las características visuales en imágenes médicas.

---

## 9. Referencias

El diseño del preprocesamiento y los criterios de evaluación se apoyaron en tres artículos científicos especializados en visión por computador y diagnóstico de COVID-19 mediante CNNs.  
(Se recomienda citar los artículos utilizados aquí según formato APA o IEEE).

---

## Autor

**Juan Camilo Sanmiguel Pinto**  
Proyecto académico y demostrativo de portafolio en aprendizaje profundo aplicado a imágenes médicas.
