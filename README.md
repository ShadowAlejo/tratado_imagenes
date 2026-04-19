# 🖼️ Tratado de Imágenes — SIMDv2

Pipeline de procesamiento, mejora y análisis de imágenes con detección de rostros mediante técnicas de visión por computadora.

---

## 📋 Descripción General

Este proyecto implementa un flujo completo de **tratamiento digital de imágenes** utilizando Python en un entorno Jupyter Notebook (`SIMDv2.ipynb`). El pipeline abarca desde la carga de imágenes originales hasta su conversión a escala de grises, normalización, mejora visual y detección de rostros, generando carpetas de salida organizadas para cada etapa del proceso.

---

## 🗂️ Estructura del Proyecto

```
tratado_imagenes/
│
├── SIMDv2.ipynb               # Notebook principal con todo el pipeline
│
├── imagenes/                  # Imágenes originales de entrada
├── imagenes_gris/             # Imágenes convertidas a escala de grises
├── imagenes_mejoradas/        # Imágenes con mejora de contraste y brillo
└── imagenes_normalizadas/     # Imágenes normalizadas para procesamiento
```

---

## ⚙️ Tecnologías y Librerías

| Tecnología       | Uso                                          |
|------------------|----------------------------------------------|
| Python 3.x       | Lenguaje principal                           |
| Jupyter Notebook | Entorno de desarrollo interactivo            |
| OpenCV (`cv2`)   | Procesamiento de imágenes y detección facial |
| NumPy            | Operaciones matriciales sobre píxeles        |
| MediaPipe        | Detección y análisis de rostros              |
| Matplotlib       | Visualización de resultados                  |

---

## 🔄 Pipeline de Procesamiento

El flujo del proyecto sigue las siguientes etapas en orden:

1. **Carga de imágenes** — Se leen todas las imágenes desde la carpeta `imagenes/`
2. **Conversión a escala de grises** — Se genera una versión en grises y se almacena en `imagenes_gris/`
3. **Normalización** — Se normalizan los valores de píxeles para homogeneizar el dataset, guardando resultados en `imagenes_normalizadas/`
4. **Mejora visual** — Se aplican técnicas de mejora de contraste (ecualización de histograma, ajuste de brillo) y se guardan en `imagenes_mejoradas/`
5. **Detección de rostros** — Se aplica un algoritmo de detección facial sobre las imágenes procesadas utilizando OpenCV y/o MediaPipe

---

## 📊 Resultados

- **Total de imágenes procesadas:** 58
- **Detecciones exitosas:** ~48–50
- **Tasa de éxito aproximada:** ~85–86%

---

## ⚠️ Limitaciones Conocidas

### 🔴 Falla en la Detección de Rostros

El algoritmo de detección de rostros presenta una **tasa de error conocida**:

- Se han identificado entre **8 y 10 detecciones incorrectas** sobre un total de **58 imágenes** procesadas.
- Estos errores pueden deberse a condiciones de iluminación desfavorables, ángulos extremos del rostro, oclusiones parciales o baja resolución de algunas imágenes de entrada.
- Se recomienda revisar manualmente los resultados y considerar el ajuste de los parámetros de sensibilidad del detector para mejorar la precisión.

---

## 🖥️ Requisitos de Hardware

> ### ⚠️ ADVERTENCIA — Equipo de Alto Rendimiento Requerido
>
> Este proyecto realiza operaciones intensivas de procesamiento de imágenes en lote. Se **recomienda encarecidamente** ejecutarlo en un equipo con especificaciones técnicas adecuadas.
>
> El proyecto fue desarrollado y probado en el siguiente hardware:
>
> | Componente | Especificación                        |
> |------------|---------------------------------------|
> | CPU        | Intel Core i7-12700H                  |
> | GPU        | NVIDIA RTX 3060 Mobile — 6 GB VRAM    |
> | RAM        | 32 GB DDR5 @ 4800 MT/s                |
>
> Ejecutar el notebook en equipos con especificaciones significativamente inferiores puede resultar en:
> - Tiempos de procesamiento muy elevados
> - Bloqueo o cierre del kernel de Jupyter
> - Errores de memoria (`MemoryError`) al manejar grandes volúmenes de imágenes

---

## 🚀 Instalación y Uso

### 1. Clonar el repositorio

```bash
git clone https://github.com/ShadowAlejo/tratado_imagenes.git
cd tratado_imagenes
```

### 2. Crear entorno virtual (recomendado)

```bash
python -m venv venv
source venv/bin/activate        # Linux / macOS
venv\Scripts\activate           # Windows
```

### 3. Instalar dependencias

```bash
pip install opencv-python numpy matplotlib mediapipe jupyter
```

### 4. Agregar imágenes de entrada

Coloca las imágenes que deseas procesar dentro de la carpeta `imagenes/`.

### 5. Ejecutar el notebook

```bash
jupyter notebook SIMDv2.ipynb
```

Ejecuta las celdas en orden de arriba hacia abajo para seguir el pipeline completo.

---

## 📁 Carpetas de Salida

Las carpetas de resultados se generan automáticamente durante la ejecución:

| Carpeta                  | Contenido                                   |
|--------------------------|---------------------------------------------|
| `imagenes_gris/`         | Imágenes en escala de grises                |
| `imagenes_normalizadas/` | Imágenes con píxeles normalizados           |
| `imagenes_mejoradas/`    | Imágenes con mejora de contraste/brillo     |

---

## 👤 Autor

**Alejandro Torres**
- GitHub: [@ShadowAlejo](https://github.com/ShadowAlejo)

---

## 📄 Licencia

Este proyecto es de uso académico. Para otros usos, contactar al autor.
