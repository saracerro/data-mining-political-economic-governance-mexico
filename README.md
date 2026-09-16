# Análisis del Impacto Político en la Economía Estatal (2000-2021)

## Objetivo del Proyecto
Este proyecto de Data Science analiza la relación entre el partido político gobernante y el desempeño económico (inflación y PIB) a nivel estatal. A través de pruebas estadísticas y modelos de Machine Learning, el objetivo es determinar si la permanencia en el poder y el cambio de gobierno influyen en la estabilidad económica.

## Metodología y Pipeline
El proyecto está estructurado en cuatro fases analíticas principales, utilizando datos públicos (2000-2021):

* **Data Wrangling:** Limpieza, estandarización y fusión (Outer Merge) de datos electorales y económicos mediante `pandas`.
* **Análisis Estadístico:** Aplicación de la prueba Chi-cuadrada para evaluar la independencia entre el partido político en el poder y los niveles de inflación (categorizados en terciles).
* **Machine Learning:** Entrenamiento de un Árbol de Decisión con validación cruzada y optimización de hiperparámetros (GridSearchCV) para predecir la categoría de inflación.
* **Reducción de Dimensionalidad:** Implementación de PCA (Análisis de Componentes Principales) con estandarización previa para visualizar las agrupaciones económicas y políticas en un espacio bidimensional.

## Resultados Clave
Los análisis arrojaron insights significativos sobre la dinámica política y económica:

| Método | Hallazgo Principal | Detalle |
| :--- | :--- | :--- |
| **Test Chi-cuadrada** | Asociación Significativa | Se rechazó H₀ (p < 0.05), confirmando que el nivel de inflación **no** es independiente del partido gobernante. |
| **Árbol de Decisión** | Importancia de Variables | La variable con mayor peso predictivo (~65%) fue `ANOS_EN_CARGA` (años consecutivos del partido en el poder). |
| **Análisis PCA** | Varianza Explicada | Los dos primeros componentes principales (PC1 y PC2) logran explicar aproximadamente el 63.5% de la varianza total de los datos. |

## Tecnologías y Ejecución
El proyecto está desarrollado íntegramente en Python.

* **Librerías principales:** `pandas`, `numpy`, `scikit-learn`, `scipy`, `matplotlib`, `seaborn`.
* **Cómo ejecutar:**
  1. Clona el repositorio e instala las dependencias (`pip install pandas scikit-learn scipy seaborn`).
  2. Asegúrate de colocar el archivo de datos original en el directorio raíz. *(Nota: Por privacidad/tamaño, el CSV original no está en el repositorio).*
  3. Ejecuta los scripts en orden para reproducir el preprocesamiento, el test estadístico, el modelo predictivo y los gráficos PCA.
