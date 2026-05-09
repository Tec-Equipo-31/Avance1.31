# Stanford Dogs Dataset - Análisis Exploratorio de Datos (EDA)

## Descripción del Proyecto

Este notebook presenta un análisis exploratorio de datos (EDA) completo del **Stanford Dogs Dataset**, un conjunto de datos de visión computacional orientado a la clasificación de imágenes de perros por raza. A diferencia de datasets tabulares tradicionales, este análisis se enfoca en características visuales como dimensiones de imágenes, distribución de clases, calidad de los datos y posibles problemas en las imágenes.

## Equipo 31 - TC5035 Proyecto Integrador

**Instructores:**
- Dra. Grettel Barceló Alonso  
- Dr. Luis Eduardo Falcón Morales

**Estudiantes:**
- A00194173 Adriana González Ugalde
- A01123424 José Alberto Herrera Bernal  
- A00534649 Carlos Alberto Parra Arredondo

## Objetivos del Análisis

1. Describir la estructura general del Stanford Dogs Dataset
2. Identificar el número total de imágenes y razas disponibles
3. Analizar la distribución de imágenes por clase
4. Revisar la existencia de imágenes faltantes, corruptas o sin etiqueta
5. Explorar las dimensiones de las imágenes (ancho, alto, proporción)
6. Detectar valores atípicos en tamaño o formato de imagen
7. Evaluar el balance entre clases
8. Justificar operaciones de preprocesamiento necesarias

## Principales Hallazgos

### Estadísticas Generales
- **Total de imágenes:** 20,580
- **Total de razas:** 120
- **Balance de clases:** Relativamente balanceado (raza con más imágenes: 252, con menos: 148)
- **Calidad de datos:** Sin imágenes corruptas o faltantes

### Características de las Imágenes
- **Dimensiones promedio:** 442.53 × 385.86 píxeles
- **Formato de color:** 99.995% RGB, 0.005% RGBA (1 imagen)
- **Tamaño de archivo promedio:** 36.90 KB
- **Aspect ratio promedio:** 1.19 (ligeramente más anchas que altas)

### Valores Atípicos
- **Ancho:** 2.29% de outliers (rango: 97-3264 píxeles)
- **Alto:** 2.59% de outliers (rango: 100-2562 píxeles)  
- **Aspect ratio:** 0.19% de outliers (rango: 0.39-3.63)
- **Tamaño de archivo:** 3.68% de outliers (rango: 2.94-1097.59 KB)

## Preprocesamiento Recomendado

1. **Conversión a RGB:** Estandarizar todas las imágenes a formato RGB
2. **Redimensionamiento:** Transformar a tamaño uniforme (ej. 224×224 píxeles)
3. **Manejo de proporciones:** Evitar deformación excesiva usando padding o recorte controlado
4. **Normalización:** Escalar valores de píxeles de [0,255] a [0,1]
5. **Data Augmentation:** Aplicar solo en entrenamiento (rotaciones, volteos, cambios de brillo)
6. **Validación de datos:** Mantener verificación automática de integridad de imágenes

## Tecnologías Utilizadas

- **Python 3.x**
- **Pandas** - Análisis y manipulación de datos
- **NumPy** - Computación numérica
- **Matplotlib** - Visualización de datos
- **PIL/Pillow** - Procesamiento de imágenes
- **Pathlib** - Manejo de rutas de archivos

## Estructura del Dataset

```
Stanford Dogs Dataset/
├── n02085620-Chihuahua/
├── n02085782-Japanese_spaniel/
├── n02085936-Maltese_dog/
└── ... (120 carpetas de razas)
```

Cada carpeta contiene imágenes de una raza específica, identificadas por un código de ImageNet seguido del nombre de la raza.

## Conclusiones

El Stanford Dogs Dataset es adecuado para tareas de clasificación multiclase de visión computacional. Presenta alta diversidad visual con fondos, posturas e iluminaciones variadas, lo que representa un desafío realista para los modelos. La ausencia de imágenes corruptas y el balance relativamente bueno entre clases permiten proceder directamente al preprocesamiento y modelado.

Se recomienda el uso de modelos de redes neuronales convolucionales o modelos preentrenados debido a la complejidad del problema de clasificar 120 razas con características visuales finas.

## Archivos del Proyecto

- `Avance1_31.ipynb` - Notebook principal con el análisis exploratorio completo
- `README.md` - Documentación del proyecto
- `.gitignore` - Configuración para ignorar archivos no deseados

## Próximos Pasos

1. Implementación del preprocesamiento de imágenes
2. Separación en conjuntos de entrenamiento, validación y prueba
3. Entrenamiento de modelos de clasificación
4. Evaluación con métricas apropiadas para clasificación multiclase
5. Optimización de hiperparámetros y arquitecturas