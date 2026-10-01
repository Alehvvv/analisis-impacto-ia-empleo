# Impacto de la IA en el sector laboral: análisis exploratorio de datos

Proyecto de análisis de datos en Python para practicar el flujo completo: cargar, limpiar, explorar, visualizar y concluir. Se analiza qué relación hay entre el nivel de adopción de inteligencia artificial, los salarios y el reemplazo de puestos de trabajo.

## Dataset

- **Fuente:** [AI Impact on Job Sector](https://www.kaggle.com/datasets/sumeakash/ai-impact-on-job-sector) (Kaggle, autor: sumeakash)
- **Tamaño:** 2.000 registros y 17 columnas, sin datos faltantes
- **Variables principales:** industria, rol, edad, años de experiencia, nivel de adopción de IA, riesgo de automatización, salario antes y después de la IA, estado laboral (`Unchanged`, `Modified`, `Replaced`), productividad y satisfacción

## Preguntas que busca responder

1. ¿Qué industrias tienen mayor proporción de empleos reemplazados?
2. ¿Una mayor adopción de IA se asocia con aumentos salariales?
3. ¿Qué variables están realmente relacionadas entre sí?
4. ¿Qué tan confiable es el dataset?

## Herramientas

Python, pandas, seaborn y matplotlib, trabajados en un Jupyter Notebook.

## Metodología

1. **Carga y revisión:** estructura, tipos de datos y valores faltantes.
2. **Columnas derivadas:** se calculó `Cambio_Salario_%` a partir del salario antes y después de la IA.
3. **Exploración:** conteos por categoría, medias por grupo y tablas dinámicas.
4. **Visualización:**
   - Boxplot del cambio salarial por industria y por nivel de adopción
   - Histograma de la productividad
   - Mapa de calor de correlaciones
   - Gráfico de dispersión del salario antes y después
   - Gráfico de barras de empleos reemplazados por industria

## Resultados principales

- **Salario y adopción de IA:** el cambio salarial promedio es de **2,53 %** con adopción baja, **4,71 %** con media y **10,41 %** con alta. La adopción alta también aumenta la dispersión, y una parte de los trabajadores presenta cambios negativos.
- **Reemplazo de puestos:** representa un **5,3 %** del total (106 de 2.000). Marketing (6,96 %), educación (6,14 %) y finanzas (6,00 %) son los sectores con mayor proporción, aunque las diferencias frente al resto son pequeñas.
- **Correlaciones:** las únicas relaciones fuertes son las obvias, edad con años de experiencia (0,99) y salario antes con salario después (0,94).

## Limitaciones: los datos parecen sintéticos

Varios indicios sugieren que el dataset fue generado con reglas y no recolectado de personas reales:

- El histograma de productividad es casi plano, en lugar de tener forma de campana.
- Los rangos de cambio salarial tienen límites exactos por nivel de adopción (por ejemplo, de -20 % a 40 % con adopción alta) y sin valores atípicos.
- `Job_Status` queda casi determinado por otras dos columnas: el estado "Replaced" solo aparece cuando la adopción de IA y el riesgo de automatización son ambos altos.

Por eso, **las conclusiones describen estos datos y no el mercado laboral real**.

## Qué aprendí

- Verificar qué significa cada columna y cómo se generaron los datos antes de sacar conclusiones.
- Preferir porcentajes sobre conteos al comparar grupos de distinto tamaño.
- Desconfiar de las correlaciones con columnas derivadas, que traen la relación incorporada.
- Distinguir entre una asociación y una causa.

## Cómo ejecutarlo

```bash
pip install pandas seaborn matplotlib jupyter
jupyter notebook
```

Descarga el archivo `ai_job_impact.csv` desde Kaggle, colócalo en la misma carpeta que el notebook y ejecuta las celdas en orden.

## Autor

Alexis Herrera
