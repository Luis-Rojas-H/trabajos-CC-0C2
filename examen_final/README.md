# Proyecto 4: Predicción de Elegibilidad de Postulantes mediante NLP

## Descripción del Problema

Este proyecto resuelve el problema de la clasificación manual y sesgada de postulantes frente a ofertas laborales (o perfiles de ingreso a cursos técnicos). El objetivo es comparar un enfoque de extracción de características léxicas (Línea Base con TF-IDF) frente a un enfoque de comprensión semántica profunda (Variante con Embeddings Densos) para automatizar la predicción de elegibilidad.

---

## Arquitectura y Fases del Proyecto

### Fase 1: Ingesta y Saneamiento de Datos

- **El Reto:** Los datos del mundo real contienen valores nulos (`NaN`) que, al concatenarse en Pandas, destruyen cadenas de texto válidas (ej. `"Experiencia en Python" + NaN = NaN`).
- **La Solución:** Se aplicó un saneamiento previo aislando cada columna y utilizando `.fillna('')`. Esto garantizó la protección de la información del candidato antes de construir el corpus consolidado (documento de texto unificado en minúsculas).

### Fase 2: Vectorización Léxica (Línea Base)

- **Teoría:** Se implementó **TF-IDF** (Term Frequency - Inverse Document Frequency). Este modelo penaliza las palabras comunes (como "el", "del") y premia las palabras raras y específicas de cada documento.
- **Parámetros Clave:** \* `stop_words_es`: Se eliminó la sintaxis irrelevante en español usando la librería NLTK.
  - `Similitud del Coseno`: Se calculó el ángulo entre el vector de la oferta y el del candidato. Un valor de 1.0 indica coincidencia exacta de palabras; 0.0 indica ninguna coincidencia léxica.

### Fase 3: Entrenamiento y Clasificación (Regresión Logística)

- **Teoría:** Para convertir el puntaje de similitud en una predicción binaria (1 = Elegible, 0 = No Elegible), se utilizó un modelo de **Regresión Logística**. Este algoritmo aplica la función sigmoide para mapear la similitud en una curva probabilística estricta entre 0 y 1.
- **Decisiones de Parámetros:**
  - `test_size=0.2`: Se reservó el 20% de los datos para la prueba final, garantizando que el modelo se evalúe con perfiles que nunca ha visto.
  - `random_state=42`: Semilla aleatoria que garantiza la **reproducibilidad** del experimento.
  - `stratify=y`: Crucial en bases de datos reales. Asegura que la proporción original de contratados y rechazados se mantenga idéntica en los bloques de entrenamiento y prueba.
  - `class_weight='balanced'`: Evita que el modelo se vuelva "perezoso" ante clases desbalanceadas (ej. muchos más rechazados que aceptados), forzándolo a penalizar severamente los Falsos Negativos (dejar escapar a un buen talento).

### Fase 4: Variante con Embeddings Semánticos

- **Limitación de la Línea Base:** El Análisis de Casos demostró que TF-IDF genera altos índices de Falsos Negativos porque busca coincidencia exacta de caracteres. Si la oferta pide "Gestión" y el CV dice "Administración", TF-IDF otorga 0% de similitud.
- **La Solución Semántica:** Se implementó el modelo de lenguaje pre-entrenado `SentenceTransformers` (`paraphrase-multilingual-MiniLM-L12-v2`). Este transformer mapea frases completas en un espacio vectorial denso, capturando el **contexto y los sinónimos** en idioma español.

### Fase 5: Comparación de Rendimiento

- **Métricas Evaluadas:** Al graficar el rendimiento, se observó un salto significativo en la métrica _Recall_ (Exhaustividad) y en el _F1-Score_ al pasar a la Variante.
- **Conclusión:** El modelo semántico demostró ser drásticamente superior para procesos de Recursos Humanos o asignación de matrículas, ya que logra identificar talentos con habilidades transferibles independientemente del vocabulario específico que hayan utilizado al redactar su perfil.

### Fase 6: Despliegue en Consola

Se construyó la función `evaluar_candidato()` que simula un entorno de producción, recibiendo cadenas de texto inéditas y automatizando todo el pipeline (Vectorización -> Predicción -> Explicación).

---

## Limitaciones, Sesgos y Uso Responsable

De acuerdo con las mejores prácticas en Ciencia de Datos, se declaran las siguientes advertencias de uso:

1. **Sesgo Histórico:** La Regresión Logística aprende de las decisiones pasadas de los reclutadores. Si históricamente hubo sesgos de género o edad, el modelo los replicará matemáticamente.
2. **Privacidad:** El modelo opera estrictamente sobre habilidades y experiencia. Se requiere una limpieza previa (anonimización) para evitar procesar datos sensibles (nombres, direcciones o identificadores gubernamentales).
3. **Herramienta de Soporte:** La Inteligencia Artificial no es infalible. Las exclusiones léxicas o alucinaciones semánticas pueden ocurrir. El puntaje de compatibilidad debe usarse como un filtro inicial de eficiencia, delegando la decisión final de elegibilidad al criterio humano profesional.

---

## Instrucciones de Reproducción

1. Revisar el archivo `../Docker.md`
2. Asegurar que los datos originales residan en la carpeta `/datos`.
3. Ejecutar el cuaderno principal `/notebooks/revisar_datos.ipynb` y luego `/notebooks/examen_final.ipynb`de forma secuencial.
