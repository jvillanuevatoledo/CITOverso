# 📊 CITOverso

De los datos crudos a los resultados publicables

- **AUDIENCIA**: Expertos en Citometría de Flujo, con conocimientos básicos en R
- **OBJETIVO FINAL**: Capacitar al estudiante para que pueda tomar un conjunto de datos de citometría (archivos .fcs) y realizar un análisis bidimensional completo, reproducible y de alta calidad, culminando en figuras y estadísticas listas para un reporte o publicación
- **DURACIÓN**: Consta de cinco sesiones de 2 horas cada una, más actividades extraclases
- **NOTA**: Este no es un curso introductorio a R, ni aborda los principios o aplicaciones de la citometría de flujo. Su objetivo es enseñar el análisis bidimensional de datos de citometría de flujo utilizando herramientas bioinformáticas como R

---

## 🖥️ MÓDULO 1: R como herramienta para la Citometría de Flujo

- **OBJETIVO**: Familiarizarse con el entorno de R y las estructuras de datos específicas para citometría
- **CONTENIDO**:
  - 1.1. **R y RStudio para citometristas**: Un repaso rápido de la interfaz, scripts, y la gestión de proyectos en RStudio
  - 1.2. **Bioconductor, el aliado del citometrista**: ¿Qué es y por qué es el ecosistema esencial para el análisis genómico y de citometría en R?
  - 1.3. **Paquetes clave: Instalación y carga de los paquetes fundamentales**: flowCore (para la interacción básica con archivos FCS), flowWorkspace (para manejar múltiples muestras y gating) y ggcyto (para la visualización avanzada)
  - 1.4. **Importación y exploración de datos**: Cómo leer archivos FCS en R y examinar los metadatos (parámetros, información del experimento, etc.):
    - 1.4.1. El Objeto **flowFrame**: La unidad fundamental. Cómo leer un único archivo .fcs en R
      - Accediendo a los metadatos: keywords() (voltajes, configuración del citómetro)
      - Explorando los canales/parámetros: colnames()
      - Visualización rápida y básica con plot()
    - 1.4.2. El Objeto **flowSet**: Manejando el experimento completo
      - Cómo importar múltiples archivos .fcs a la vez
      - Herramientas para gestionar el flowSet: sampleNames(), pData() para añadir metadatos del experimento (ej. Controles, Tratamientos, Pacientes)

---

## ⚙️ MÓDULO 2: Pre-procesamiento robusto y reproducible

- **OBJETIVO**: Aplicar el conocimiento experto en citometría para realizar un pre-procesamiento robusto y reproducible directamente en R
- **CONTENIDO**:
  - 2.1. **Compensación en R**: Cómo importar la matriz de compensación del archivo FCS o, más importante, cómo aplicar una nueva matriz de compensación directamente en el código. Discusión sobre las ventajas de hacerlo programáticamente
    - Extraer y examinar la matriz de compensación original del .fcs
    - Ejercicio Práctico: Aplicar una nueva matriz de compensación "on-the-fly" y comparar visualmente el antes y el después. Discutir por qué esto es superior a sobreescribir el archivo original.
  - 2.2. **Transformación de datos**: El "porqué" y el "cómo" de las transformaciones (logarítmica, biexponencial - logicle). Visualización del efecto de la transformación en la resolución de poblaciones?
    - Aplicar transformaciones log y biexponencial (logicle o hyperlog)
    - Ejercicio Práctico: Visualizar un mismo ploteo con diferentes ajustes de transformación para entender cómo impactan en la separación de poblaciones tenues vs. brillantes
  - 2.3. **Control de calidad (QC) automatizado**: Uso de R para filtrar eventos no deseados (detritos, dobletes, células muertas) de manera consistente en todo un experimento. Introducción a paquetes como flowAI para detectar anomalías en la adquisición de forma automática
    - Construir un script de R para realizar un QC secuencial
    - Paso 1: Gating de células únicas para eliminar dobletes (ej. FSC-A vs FSC-H)
    - Paso 2: Gating para eliminar detritos (ej. FSC-A vs SSC-A)
    - Paso 3: Gating de viabilidad para excluir células muertas (si se usó un marcador de viabilidad)
    - La importancia de guardar los resultados intermedios de este QC
  
---

## 🎯 MÓDULO 3: _Gating_ bidimensional y extracción de estadísticas

- **OBJETIVO**: Traducir la estrategia de gating manual (que ya dominan) a un flujo de trabajo programático en R, permitiendo la reproducibilidad y el análisis por lotes
- **CONTENIDO**:
  - 3.1. **Visualización con ggcyto**: Creación de gráficos de puntos (dot plots) y de contorno de alta calidad. ggcyto utiliza la misma gramática que ggplot2, el estándar de oro para la visualización en R
    - Construyendo gráficos ggplot2-style: capas, estéticas (aes), y geometrías (geom_hex, geom_point)
    - Personalización de ejes, títulos y límites para una claridad máxima
  - 3.2. **Definición de poblaciones (_Gating_)**:
    - Creación de gates bidimensionales (e.g., rectangleGate, polygonGate, ellipseGate) directamente en el código
    - Aplicación secuencial de gates para construir un árbol de gating jerárquico
    - El objeto GatingSet: Una estructura poderosa para aplicar un árbol de gating a todo un flowSet de una sola vez
  - 3.3. **Automatización del _Gating_**: Cómo aplicar un árbol de gating definido a un conjunto completo de muestras (flowSet) con unas pocas líneas de código
  - 3.4. **Extracción de estadísticas**: Obtención de frecuencias poblacionales y medianas de intensidad de fluorescencia (MFI) de manera automática para todas las muestras y poblaciones. Exportación de resultados a un archivo CSV para su posterior análisis

---

## 📊✍️ MÓDULO 4: Visualización para publicación y reportes Aautomatizados

- **OBJETIVO**: Transformar los resultados del análisis en productos finales profesionales y reproducibles
- **CONTENIDO**:
  - 4.1. **Gráficos con calidad de publicación**:
    - Afinando los gráficos de ggcyto: cambio de colores, temas, tamaños de fuente
    - Cómo superponer el gating sobre los gráficos para mostrar la estrategia de análisis
    - Exportar gráficos en alta resolución (PNG, TIFF, PDF)
  - 4.2. **Introducción a R _Markdown_**:
    - El concepto de "investigación reproducible"
    - Combinando texto (explicaciones, como en un “paper”), código R y sus salidas (gráficos, tablas) en un único documento
  - 4.3. **Creando tu primer reporte de análisis**:
    - **Proyecto final**: Construir un reporte en R Markdown que documente todo el análisis de un pequeño set de datos: desde la carga y QC, pasando por el gating, hasta la presentación de los gráficos y tablas de estadísticas finales con sus respectivas conclusiones.

---

## 📫 Contáctame
<p align="center">
  <a href="mailto:jvillanuevatoledo@gmail.com" target="_blank">
    <img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/>
  </a>
  <a href="https://www.linkedin.com/in/jairo-r-v-8a1192204" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/>
  </a>
   <a href="https://www.facebook.com/citometriadeflujo" target="_blank">
    <img src="https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&logo=facebook&logoColor=white" alt="Facebook"/>
</p>

---

<p align="center">
  <sub>Creado con ❤️ por <a href="https://github.com/jvillanuevatoledo">Jairo Villanueva</a></sub>
</p>
