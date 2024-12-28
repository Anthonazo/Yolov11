# Proyecto: Clasificación de Objetos con YOLOv11

  - **Moya Ochoa Anthony Joel** con enlace a `@anthonazo`
  - **Yanza Caceres Daniel Brian** con enlace a `@danielyanza`

Este proyecto tiene como objetivo realizar la clasificación de objetos utilizando técnicas de Deep Learning, específicamente con el modelo YOLOv11 para la detección de objetos

## Estructura del Proyecto

El proyecto está organizado en tres carpetas principales:

1. **augmentation**: Contiene el código y los notebooks para la creación y aumento del conjunto de datos utilizando la librería [Albumentations](https://albumentations.ai/).
    - Archivos:
        - `augmentation.ipynb`: Código en formato Jupyter Notebook para la aplicación de transformaciones sobre el conjunto de datos.
        - `augmentation.html`: Versión en HTML del Jupyter Notebook.
        
2. **data**: Aquí se encuentran los datos necesarios para el entrenamiento del modelo YOLOv11. Esta carpeta contiene imágenes y sus correspondientes archivos de etiquetas en formato YOLO, así como el archivo `data.yaml` que define la configuración del conjunto de datos.
    - Archivos:
        - `train/`: Carpeta con las imágenes y labels que se utilizaron para el entrenamiento.
        - `test/`: Carpeta con las imagenes y labels que se usaron para la validacion del modelo.
        - `data.yaml`: Archivo que contiene la configuración del conjunto de datos en formato YAML.
        
3. **training**: Esta carpeta contiene todo el código y los resultados relacionados con el entrenamiento de YOLOv11. Incluye el proceso de entrenamiento, la evaluación y los resultados visuales, como las métricas de precisión y recall. También se incluye el video de las pruebas de rendimiento comparando el uso de CPU y GPU.
    - Archivos:
        - `yolo_train.ipynb`: Código para entrenar el modelo YOLOv11 con el conjunto de datos cargado.
        - `yolo_train.html`: Versión en HTML del notebook de entrenamiento.

## Detalles de YOLOv11

### Entrenamiento

El modelo YOLOv11 fue entrenado con un conjunto de datos personalizado de objetos, con imágenes etiquetadas en formato YOLO. El entrenamiento se realizó utilizando una GPU de Google Colab para acelerar el proceso. Durante el entrenamiento, se utilizaron los siguientes parámetros:

- **Modelo Base**: YOLOv11 (peso preentrenado `yolo11s.pt`).
- **Épocas**: 15
- **Tamaño de Imagen**: 640x640

Los resultados del entrenamiento incluyen métricas clave como la precisión, recall y mAP (mean Average Precision), que pueden ser consultadas en los archivos de resultados generados.

### Resultados de Entrenamiento

Los resultados obtenidos durante el entrenamiento fueron los siguientes:

- **Precisión en conjunto completo (mAP@50)**: 0.964
- **mAP a 50-95**: 0.805

Se pueden encontrar gráficos visuales, como la matriz de confusión y las predicciones realizadas sobre el conjunto de validación, en la carpeta `training`.

## Requisitos

Para ejecutar este proyecto, necesitarás tener instaladas las siguientes librerías y herramientas:

- Python 3.7 o superior
- PyTorch
- Albumentations
- Ultralytics (para trabajar con YOLO)
- Google Colab (opcional, pero recomendado para el uso de GPU)

Instala las librerías necesarias utilizando:

```bash
pip install torch albumentations ultralytics
