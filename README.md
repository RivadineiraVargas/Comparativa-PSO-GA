# Comparativa entre PSO y GA para Ajuste Parabólico

Este proyecto implementa y compara dos algoritmos de optimización metaheurística, la **Optimización por Enjambre de Partículas (PSO)** y el **Algoritmo Genético (GA)**, para ajustar una función parabólica a un conjunto de datos `(x, y)`. El objetivo es encontrar los coeficientes `a`, `b`, y `c` de la ecuación `y_pred = a + b*x + c*x**2` que minimicen el Error Cuadrático Medio (MSE) entre los valores predichos y los datos originales.

## Contenido

-   `comparativa_pso_ga.ipynb`: El notebook principal de Jupyter que contiene la implementación y el análisis.
-   `x_data.txt`: Archivo con los datos de entrada para 'x'.
-   `y_data.txt`: Archivo con los datos de salida para 'y'.
-   `requirements.txt`: Lista de las dependencias de Python necesarias.

## Cómo Ejecutar el Proyecto

1.  **Clonar el repositorio:**
    ```bash
    git clone <URL_DEL_REPOSITORIO>
    cd comparativa-pso-ga
    ```
2.  **Crear y activar un entorno virtual (recomendado):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # En Linux/macOS
    # o
    .\venv\Scripts\activate   # En Windows
    ```
3.  **Instalar las dependencias:**
    ```bash
    pip install -r requirements.txt
    ```
    (Asegúrate de que `scikit-opt` y otras librerías necesarias estén listadas en `requirements.txt`).
4.  **Ejecutar el notebook de Jupyter:**
    ```bash
    jupyter notebook
    ```
    Abre el archivo `comparativa_pso_ga.ipynb` en tu navegador y ejecuta todas las celdas.

## Análisis y Resultados

El notebook realiza 10 ejecuciones para cada algoritmo (PSO y GA) para evaluar su rendimiento y convergencia en la tarea de ajuste parabólico.

### Resumen de Resultados

Los resultados muestran que, para este problema específico, **PSO** logra una mayor precisión en el ajuste y una convergencia más rápida y consistente en comparación con el **GA**.

-   **PSO** alcanza valores de MSE significativamente más bajos (del orden de 1e-10) y valores de R2 muy cercanos a 1, indicando un ajuste casi perfecto a los datos. La convergencia del PSO es notablemente más rápida, estabilizándose en un error muy bajo en pocas iteraciones.
-   **GA** también logra ajustar la curva, pero con un MSE considerablemente más alto (del orden de 1e-05 a 1e-03) y una mayor variabilidad en los resultados entre las diferentes ejecuciones. Su convergencia es más lenta y tiende a estancarse en mínimos locales o soluciones subóptimas en comparación con PSO.

### Visualizaciones

El proyecto incluye gráficos para visualizar:

1.  **Ajuste parabólico:** Comparación visual del ajuste de la curva parabólica a los datos originales para la mejor ejecución de PSO y GA.
2.  **Convergencia:** Gráficos que muestran cómo el mejor MSE encontrado evoluciona a lo largo de las iteraciones/generaciones para ambos algoritmos, destacando la diferencia en velocidad y nivel de optimización alcanzado.
