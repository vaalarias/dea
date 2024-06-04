# Análisis de Expresión Diferencial

### Valentina Janet Arias Ojeda

### *Clase Transcriptómica*
En este análisis de expresión diferencial (DEA, por sus siglas en inglés) del transcriptoma de ratones con Alzheimer (modelo 5xFAD) y ratones sanos (WT), centrado en el desarrollo del hipotálamo se realiza con el propósito de identificar cambios en los niveles de expresión de genes entre diferentes condiciones experimentales.

Para este propósito, se emplearon dos tipos de datos transcriptómicos: secuenciación de RNA (RNAseq) y microRNAs. Las lecturas obtenidas de RNAseq fueron alineadas utilizando HISAT2 y Bowtie1, con HISAT2 mostrando una mayor eficiencia de alineamiento. En cuanto a los microRNAs, después de una necesaria limpieza de las lecturas debido a su baja calidad inicial, se utilizó Bowtie1. Posteriormente, se realizó la asignación de las lecturas a características genómicas (genes) mediante feature counts.

Para llevar a cabo el DEA, se utilizarán las tablas de feature counts generadas en el alineamiento previo. En este estudio, aplicaremos tres metodologías estadísticas robustas: DESeq2, edgeR y pyDESeq2. Estos paquetes permiten ajustar la expresión por factores de confusión y controlar la tasa de falsos positivos, asegurando así la identificación precisa de genes diferencialmente expresados. DESeq2 y edgeR son herramientas consolidadas en el campo del análisis de expresión diferencial, conocidas por su capacidad de manejar datos con dispersiones variadas y por su riguroso control de calidad. pyDESeq2, por otro lado, es una implementación de DESeq2 en Python que facilita la integración con pipelines bioinformáticos y ofrece una interfaz amigable para el análisis y la visualización de datos.

Para el análisis exploratorio y visualización de los resultados del análisis de expresión diferencial consideramos estas siguientes representaciones:

- **PCA (Análisis de Componentes Principales):** Proporciona una representación visual de la variabilidad entre las muestras, permitiendo la detección de patrones o agrupaciones naturales en los datos. Es útil para identificar muestras atípicas y efectos de lote que podrían influir en los resultados del análisis.
- **Barplot de PC:** Muestra la contribución de cada componente principal a la variabilidad total en los datos. Esto ayuda a determinar cuántos componentes son necesarios para capturar una cantidad significativa de variabilidad y sugiere la presencia de patrones claros que podrían ser relevantes biológicamente.
- **Volcano Plot:** Representa el cambio en la expresión génica (fold change) frente a la significación estadística (valor p o FDR). Destaca los genes con cambios significativos en la expresión entre las condiciones experimentales, lo que facilita la identificación de genes candidatos para un análisis más detallado.
- **HeatMap:** Visualiza los patrones de expresión relativa entre genes y muestras, lo que permite identificar grupos de genes con perfiles de expresión similares y diferencias en la expresión entre las condiciones experimentales. Es una herramienta poderosa para explorar la estructura de los datos y detectar relaciones entre las muestras y los genes.
