## 🖥️ MÓDULO 1: R como herramienta para la Citometría de Flujo

- **OBJETIVO**: Familiarizarse con el entorno de R y las estructuras de datos específicas para citometría
- **CONTENIDO**:
  - 1.1. **R y RStudio para citometristas**: Un repaso rápido de la interfaz, scripts, y la gestión de proyectos en RStudio
  - 1.2. **Bioconductor, el aliado del citometrista**: ¿Qué es y por qué es el ecosistema esencial para el análisis de la citometría de flujo en R?
  - 1.3. **Paquetes clave: Instalación y carga de los paquetes fundamentales**: flowCore (para la interacción básica con archivos FCS), flowWorkspace (para manejar múltiples muestras y gating) y ggcyto (para la visualización avanzada)
  - 1.4. **Importación y exploración de datos**: Cómo leer archivos FCS en R y examinar los metadatos (parámetros, información del experimento, etc.):
    - 1.4.1. El Objeto **flowFrame**: La unidad fundamental. Cómo leer un único archivo .fcs en R
      - Accediendo a los metadatos: keywords() (voltajes, configuración del citómetro)
      - Explorando los canales/parámetros: colnames()
      - Visualización rápida y básica con plot()
    - 1.4.2. El Objeto **flowSet**: Manejando el experimento completo
      - Cómo importar múltiples archivos .fcs a la vez
      - Herramientas para gestionar el flowSet: sampleNames(), pData() para añadir metadatos del experimento (ej. Controles, Tratamientos, Pacientes)
