🎮 Análisis Exploratorio de Datos (EDA) – Elden Ring
Este proyecto es un Análisis Exploratorio de Datos (EDA) que investiga el comportamiento y la retención de los jugadores de Elden Ring a través de reseñas reales extraídas de la API pública de Steam.

🚀 Hallazgo Principal: La Paradoja de la Retención
![Gráfico comparativo de la retención de jugadores](grafico_resultado.png)
A nivel analítico, los datos revelaron el fenómeno del "Veterano Frustrado":
🔴 Detractores (No recomiendan): Presentan una retención mediana de 471.95 horas.
🟢 Promotores (Sí recomiendan): Presentan una retención mediana de 171.10 horas.

Insight: El 70% de las reseñas provienen de jugadores "Hardcore" (más de 100 horas acumuladas). Esto indica que las reseñas negativas no reflejan un rechazo inicial al producto, sino frustración en el contenido end-game o tras recientes parches de balanceo.

🛠️ Herramientas y Tecnologías
Entorno: Visual Studio Code (VS Code), Jupyter Notebooks (.ipynb).
Extracción de Datos: requests (Steam Web API).
Limpieza y Análisis: pandas.
Visualización: matplotlib, seaborn.

📋 Fases del Proyecto
1. Extracción (API de Steam)
Conexión a la API para descargar un paquete de datos en formato JSON del juego (ID: 1245620).
Estructuración inicial en un DataFrame de Pandas, identificando variables clave como el texto de la reseña (review), la satisfacción (voted_up) y el diccionario de datos del usuario (author).

2. Limpieza Extrema (Data Cleaning)
Extracción de métricas anidadas dentro de la columna author utilizando .apply() y funciones lambda para obtener las horas de juego reales (playtime_forever).
Reducción de dimensionalidad eliminando columnas redundantes o sin valor analítico directo con drop(), optimizando el uso de memoria.

3. Análisis de Retención
Uso de la mediana como métrica de tendencia central al agrupar los datos (groupby), garantizando que los valores atípicos (outliers) de usuarios con miles de horas no sesguen los resultados.
Segmentación de usuarios extremos (Hardcore Gamers) para entender la distribución de la muestra.

4. Visualización de Datos
Representación visual de los insights a través de gráficos de barras comparativos.
Se aplicó un estilo visual limpio (whitegrid) y una paleta semántica (verde/rojo) para facilitar la lectura por parte de perfiles de negocio, incorporando etiquetas de datos directas sobre las barras.
