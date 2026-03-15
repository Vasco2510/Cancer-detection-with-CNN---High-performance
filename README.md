Clasificación de Cáncer de Mama en Imágenes Histopatológicas (BreakHis)

Este proyecto realiza un análisis comparativo entre dos arquitecturas de Redes Neuronales Convolucionales (CNN) para la detección de tumores benignos y malignos utilizando el dataset BreakHis. El objetivo principal es evaluar el desempeño de una CNN personalizada entrenada desde cero frente a una ResNet18 pre-entrenada mediante Transfer Learning.

📌 Descripción del Proyecto

El diagnóstico temprano del cáncer de mama es vital. Este proyecto utiliza visión artificial para procesar biopsias digitales y automatizar la clasificación. Se exploran métricas no solo a nivel de imagen individual, sino también a nivel de paciente (vía votación mayoritaria), lo cual refleja con mayor precisión la realidad clínica.

Características Principales:

Dataset: BreakHis (9,109 imágenes de 82 pacientes).

Modelos: 1. CNN Personalizada (TensorFlow/Keras).
2. ResNet18 (PyTorch) con pesos de ImageNet.

Niveles de Magnificación: 40X, 100X, 200X y 400X.

📂 Estructura del Repositorio

El proyecto está organizado en dos formatos para facilitar tanto la lectura rápida como el mantenimiento:

1. Versiones de Cuadernos Principales

CNN ResNet18.ipynb: Implementación completa del modelo ResNet18 usando PyTorch.

Compacted version - Customized CNN.ipynb: Versión "todo en uno" de la CNN personalizada para una ejecución rápida.

2. Versión Modularizada (Carpeta: Modularized version - Customized CNN)

Ideal para producción o entendimiento paso a paso:

DataSimplification.ipynb: Preprocesamiento, limpieza y organización de los datos de BreakHis.

EDA.ipynb: Análisis Exploratorio de Datos (distribución de clases, pacientes y visualización).

modelTraining.ipynb: Definición de la arquitectura, entrenamiento y guardado de pesos.

model_testing.ipynb: Evaluación exhaustiva, matrices de confusión y métricas por paciente.

3. Documentación y Resultados

Slides Presentation + Project insights.pdf: Presentación ejecutiva con los hallazgos clave.

paperwork - Breast detection insights.pdf: Documentación detallada de la metodología e investigación.

🚀 Cómo Continuar y Mejorar el Proyecto

Si deseas llevar este proyecto al siguiente nivel, aquí tienes algunas rutas recomendadas:

1. Preprocesamiento Avanzado

Normalización de Tinciones: Las imágenes histopatológicas varían mucho según el laboratorio. Implementar métodos como Macenko o Vahadane para estandarizar los colores reduciría el ruido del modelo.

Data Augmentation: Aplicar rotaciones, flips y variaciones de brillo para mejorar la generalización en la CNN personalizada.

2. Arquitecturas y Validación

Probar otros Modelos: Evaluar arquitecturas más profundas como ResNet50, EfficientNet o Vision Transformers (ViTs).

Validación Cruzada Externa: Probar los pesos entrenados en otros datasets como BACH o Camelyon para verificar la robustez fuera del entorno BreakHis.

3. Implementación de Votación por Magnificación

Actualmente se usa votación por paciente. Una mejora sería entrenar modelos específicos por magnificación (ej. solo 400X) y combinar sus predicciones en un ensamble.

📈 Recomendaciones Generales

Priorizar el Recall: En diagnósticos médicos, es preferible tener un falso positivo que un falso negativo (un cáncer no detectado). Ajustar los umbrales de clasificación para maximizar el Recall de la clase 'Malignant'.

Análisis de Errores: Revisar manualmente las imágenes que el modelo clasifica erróneamente para identificar si hay patrones (como exceso de grasa o falta de enfoque) que confundan a la red.

Entorno de Ejecución: Se recomienda el uso de GPUs (como las disponibles en Kaggle o Google Colab) debido al volumen de datos y la profundidad de ResNet18.

Este proyecto fue desarrollado por: Eduardo Tello, Abel Escobar, Luis Romero y Adrián Sandoval.
