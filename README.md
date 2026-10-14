# 🔎 Inventario y configuración de un dataset de segmentación

Este repositorio contiene una práctica introductoria de **inventario y configuración de datasets de segmentación de imágenes**, desarrollada como parte del taller **«Del dataset a U-Net: segmentación de imágenes con Deep Learning»**.

Para esta actividad utilizaremos una **versión reducida y reorganizada del Oxford-IIIT Pet Dataset**, que contiene fotografías de perros y gatos, sus correspondientes máscaras de segmentación y archivos de anotaciones.

El propósito es familiarizarse con la organización de un dataset, identificar sus componentes y comprender cómo se relacionan las imágenes con sus anotaciones y obtener un inventario y un archivo de configuración antes de comenzar las siguientes etapas del proyecto.

---

## 🎯 Objetivo

Explorar la estructura y los componentes de un dataset de segmentación mediante herramientas de Python, identificando archivos, rutas, metadatos y anotaciones espaciales para comprender cómo se organiza la información que posteriormente utilizará un modelo de Deep Learning.

---

## 📁 Organización del proyecto

El notebook utiliza las siguientes ubicaciones dentro del repositorio:

```text
del-dataset-a-unet_inventario_y_configuracion_minidataset/
├── data/
│   └── raw/
│       ├── images/
│       │   ├── chihuahua/
│       │   │   ├── chihuahua_12.jpg
│       │   │   ├── chihuahua_12.png
│       │   │   ├── chihuahua_12.xml
│       │   │   └── ...
│       │   ├── Maine_Coon/
│       │   │   ├── Maine_Coon_13.jpg
│       │   │   ├── Maine_Coon_13.png
│       │   │   ├── Maine_Coon_13.xml
│       │   │   └── ...
│       │   ├── Siamese/
│       │   │   ├── Siamese_101.jpg
│       │   │   ├── Siamese_101.png
│       │   │   ├── Siamese_101.xml
│       │   │   └── ...
│       │   └── Sphynx/
│       │       ├── Sphynx_19.jpg
│       │       ├── Sphynx_19.png
│       │       ├── Sphynx_19.xml
│       │       └── ...
│       └── list.txt
└── notebooks/
    └── explorar_data.ipynb
```

Los archivos del minidataset se encuentran en `data/raw/`.

Cada categoría cuenta con su propio directorio dentro de `images/`, donde se almacenan conjuntamente las fotografías, máscaras y anotaciones individuales.

Los archivos correspondientes a una misma muestra comparten el **mismo nombre base**, pero tienen extensiones diferentes.

Por ejemplo:

```text
Sphynx_19.jpg
Sphynx_19.png
Sphynx_19.xml
```

Además, el archivo `list.txt`, ubicado en `data/raw/`, contiene información de clasificación asociada con las imágenes.

> [!NOTE]
> El minidataset contiene únicamente una pequeña selección de imágenes del Oxford-IIIT Pet Dataset original, reorganizada con fines didácticos.
>
> No representa el conjunto completo de datos ni está diseñado para entrenar o evaluar modelos de segmentación de manera representativa.

---

## 🧩 Componentes del minidataset

| Componente | Formato | Descripción |
|---|---|---|
| **Fotografía** | `.jpg` | Imagen original del animal. |
| **Máscara** | `.png` | Anotación espacial que identifica regiones de la imagen a nivel de píxel. |
| **Anotación individual** | `.xml` | Contiene información de la imagen, como sus dimensiones, clase y *bounding box* de la cabeza del animal. |
| **Etiquetas de clasificación** | `.txt` | Archivo `list.txt` con los identificadores de clase, especie y raza asociados con las imágenes. |

### 🏷️ Identificadores de clasificación

El archivo `list.txt` conserva la convención de identificadores utilizada en el Oxford-IIIT Pet Dataset original.

| Campo | Descripción | Valores |
|---|---|---|
| `class_id` | Identificador de la categoría o raza. | `1–37` |
| `species_id` | Identificador de la especie. | `1`: gato, `2`: perro |
| `breed_id` | Identificador de la raza dentro de cada especie. | Gatos: `1–25`; perros: `1–12` |

> [!NOTE]
> Aunque se conserva la convención de identificadores del dataset original, este minidataset contiene únicamente cuatro categorías: `chihuahua`, `Maine_Coon`, `Siamese` y `Sphynx`.

---

## 💻 Requisitos

Para ejecutar la práctica se utilizan las siguientes bibliotecas:

| Biblioteca | Uso |
|---|---|
| `pathlib` | Construcción y exploración de rutas. |
| `xml.etree.ElementTree` | Lectura de anotaciones XML. |
| `numpy` | Inspección de valores numéricos. |
| `pillow` (`PIL`) | Lectura y procesamiento de imágenes. |
| `pandas` | Lectura y procesamiento de CSV. |
| `json` | Lectura y procesamiento de JSON. |

También necesitarás un entorno compatible con Jupyter Notebooks.

Las bibliotecas `pathlib`, `json` y `xml.etree.ElementTree` forman parte de la biblioteca estándar de Python.

---

## 📚 Dataset de referencia

**Oxford-IIIT Pet Dataset**

Parkhi, O. M., Vedaldi, A., Zisserman, A., & Jawahar, C. V. (2012).

*Cats and Dogs.*

IEEE Conference on Computer Vision and Pattern Recognition (CVPR).

[Consultar el dataset original →](https://www.robots.ox.ac.uk/~vgg/data/pets/)

El conjunto de imágenes utilizado en esta práctica es una selección reducida y reorganizada con fines didácticos. Su utilización debe respetar las condiciones de uso de las imágenes del dataset original.

---

## 🔗 Taller

Esta práctica forma parte del **Módulo 2 · Ingeniería del dataset** del taller:

[**Del dataset a U-Net: segmentación de imágenes con Deep Learning →**](https://github.com/bettypau-open-knowledge/del-dataset-a-unet)

**Bettypau Open Knowledge**

*Aprende · Experimenta · Construye · Comparte*