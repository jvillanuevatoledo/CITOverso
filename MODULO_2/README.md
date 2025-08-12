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

<p align="center">
  <sub>Creado con ❤️ por <a href="https://github.com/jvillanuevatoledo">Jairo Villanueva</a></sub>
</p>
