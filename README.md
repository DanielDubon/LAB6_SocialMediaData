# LAB6_SocialMediaData 📊🐦  

Análisis de datos de **redes sociales (Twitter/X)** sobre el tráfico en Guatemala, utilizando técnicas de limpieza, procesamiento de texto y visualización.  

El proyecto carga y procesa más de **5,600 tweets** recopilados de la cuenta [@traficogt](https://twitter.com/traficogt) y usuarios relacionados, con el objetivo de identificar patrones de **congestión vehicular**, horarios críticos y zonas más afectadas.  

## 🚀 Funcionalidades principales  

1. **Carga de datos**  
   - Lectura de archivo `data/traficogt.txt` en formato JSONL.  
   - Manejo automático de diferentes codificaciones de texto.  
   - Normalización de claves y conversión de fechas a UTC.  

2. **Limpieza y preprocesamiento**  
   - Conversión a minúsculas.  
   - Eliminación de URLs, menciones (@), hashtags (#) y emojis.  
   - Remoción de *stopwords* en español.  
   - Generación de columnas `text_clean` y `text_clean_nonums`.  

3. **Enriquecimiento de datos**  
   - Conversión de fechas a horario local de Guatemala.  
   - Variables derivadas: año, mes, día, hora, día de la semana, época lluviosa.  
   - Exportación de dataset limpio a **Parquet** o **CSV**.  

4. **Análisis exploratorio**  
   - Identificación de **horas pico de congestión**.  
   - Comparación entre época de lluvia y seca.  
   - Extracción de **topónimos y zonas** (ej. “Calzada Roosevelt”, “Zona 1”, “Mixco”).  
   - Ranking de lugares más mencionados en 2023 vs 2024.  
   - Medición del **efecto de la lluvia** sobre el tráfico en diferentes puntos de la ciudad.  

5. **Visualización**  
   - Gráficos de distribución horaria.  
   - Mapas de barras con los lugares más reportados.  
   - Comparaciones anuales y estacionales.  

## 📂 Estructura del proyecto  
## 📂 Estructura del proyecto  

| Carpeta / Archivo        | Descripción                          |
|--------------------------|--------------------------------------|
| `data/`                  | Carpeta que contiene los datos       |
| ├─ `traficogt.txt`       | Datos crudos (tweets)                |
| ├─ `tweets_clean.parquet`| Datos procesados (formato preferido) |
| └─ `tweets_clean.csv`    | Alternativa si no hay Parquet        |
| `notebook.ipynb`         | Análisis principal                   |
| `README.md`              | Este archivo                         |

## 🛠️ Tecnologías usadas  

- **Python 3.9+**  
- `pandas`, `numpy` → Manipulación de datos  
- `matplotlib` → Visualización  
- `re` (expresiones regulares) → Limpieza de texto  
- `pyarrow` o `fastparquet` → Manejo de archivos Parquet  

## 📊 Resultados destacados  

- **Horas con mayor congestión:** entre **13:00 y 19:00 hrs**, con picos en 14h y 18h.  
- **Lugares más reportados (2024):** Zona 1, Mixco, Zona 9, Villa Nueva.  
- **Cambio de patrones (2023 → 2024):** mayor peso en áreas céntricas (Z1, Z9, Z10).  
- La lluvia **agrava la congestión** en ejes como **Zona 10 y Los Próceres**.  

## ▶️ Uso  

1. Clonar el repositorio:  
   ```bash
   git clone https://github.com/DanielDubon/LAB6_SocialMediaData.git
   cd LAB6_SocialMediaData
    ```

2. Instalar dependencias:  
   ```bash
   pip install pandas numpy matplotlib pyarrow fastparquet
   ```
3. Ejecutar el notebook `notebook.ipynb` para cargar, procesar y analizar los datos.