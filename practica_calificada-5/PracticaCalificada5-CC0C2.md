### Práctica Calificada 5 - CC0C2 Procesamiento del Lenguaje Natural

**Tema general:** modelos multimodales, modelos de difusión, Stable Diffusion, despliegue de sistemas de lenguaje y fundamentos de MLOps.

**Modalidad:** individual.

**Entrega:** repositorio con notebook, README, video técnico y evidencia de ejecución.

**Duración del video:** estrictamente mayor a 12 minutos.

**Condición central:** no habrá exposición presencial por razones de tiempo. Por ello, el video será tratado como evidencia principal de autoría, comprensión técnica y defensa del trabajo.

#### Propósito de la evaluación

La Práctica Calificada 5 evalúa si el estudiante comprende y puede defender técnicamente los conceptos trabajados en los temas de modelos multimodales, modelos de difusión, generación de imágenes y despliegue de sistemas de lenguaje del curso CC0C2.

El objetivo no es premiar la simple ejecución de código ni la generación automática de notebooks mediante IA. El objetivo es verificar si el estudiante puede construir un sistema funcional, modificarlo de forma significativa, explicar el flujo interno del modelo multimodal o de difusión, justificar decisiones de arquitectura, interpretar métricas de evaluación, analizar restricciones de despliegue y defender técnicamente su propio trabajo.

El uso de IA no está prohibido como apoyo. Sin embargo, una entrega producida con IA y no comprendida por el estudiante será considerada inválida.

Código correcto sin explicación correcta no aprueba la práctica.

#### Líneas de proyecto permitidas

Cada estudiante debe construir su trabajo a partir de una de las siguientes líneas de proyecto.

- Vision Transformers, CLIP y representaciones texto-imagen.
- Modelos de visión y lenguaje, VQA y aplicaciones multimodales.
- Autoencoders, VAE y GANs como contexto histórico de generación.
- Modelos de difusión, DDPM, DDIM, Stable Diffusion y condicionamiento.
- RLHF, serving, monitorización, latencia, privacidad, seguridad y edge vs cloud.
- Sistemas multimodales integrados que combinen comprensión visual, lenguaje y generación.

El estudiante puede reutilizar materiales públicos, ejemplos propios o plantillas iniciales, pero debe identificar claramente qué parte fue tomada como base, qué parte fue modificada, qué parte fue agregada por el estudiante y qué parte recibió apoyo de IA.

#### Entregables obligatorios

Cada estudiante debe entregar la dirección de URL de su repositorio con los siguientes elementos.

- Un notebook `.ipynb` reproducible.
- Un archivo `README.md`.
- Un video técnico con voz propia.
- Evidencia de ejecución interna.
- Comparación entre línea base y variante.
- Registro de ejecución con semilla, entorno, librerías, modelo usado y datos usados.
- Una sección llamada `Declaración de autoría y uso de IA`.

#### Modalidad definitiva de evaluación

La práctica se evaluará únicamente mediante la entrega del repositorio y el video técnico.

No habrá exposición presencial.

El video debe cumplir el rol de defensa asíncrona. Por esta razón, no debe ser una presentación superficial ni una lectura de texto. Debe mostrar al estudiante trabajando con su notebook, programando cambios, ejecutando celdas, prediciendo efectos, interpretando resultados y explicando técnicamente el código.

La duración debe ser estrictamente mayor a 12 minutos. Se recomienda una duración entre 14 y 18 minutos.

Un video de 12 minutos exactos o menos no será válido.

#### Regla habilitante de validez académica

La práctica solo será calificada si el video contiene todos los elementos siguientes.

- Explicación del objetivo del proyecto.
- Identificación del línea de proyecto elegida.
- Explicación de la línea base.
- Explicación de la modificación principal.
- Codificación en vivo de al menos dos cambios.
- Ejecución de esos cambios.
- Predicción del efecto esperado antes de ejecutar.
- Interpretación del resultado obtenido después de ejecutar.
- Explicación de tensores de imagen, latentes, embeddings multimodales, parámetros de difusión, métricas de calidad, latencia o throughput, según corresponda.
- Respuesta a preguntas técnicas avanzadas.
- Cierre técnico sobre qué hizo, por qué lo hizo y qué significan sus resultados.

Si el video solo muestra celdas ya ejecutadas, solo lee texto, solo describe resultados o no incluye codificación en vivo, la práctica será inválida.

#### Regla frente a entregas generadas por IA

Se considerará entrega superficial o inválida aquella en la que el estudiante haga una o más de las siguientes acciones.

- Lee texto genérico sin conectarlo con su notebook.
- No puede explicar sus propias funciones.
- No puede explicar dimensiones de tensores de imagen, espacios latentes, embeddings multimodales, parámetros de difusión o métricas de despliegue.
- No puede justificar por qué eligio una variante.
- No puede interpretar los resultados.
- No modifica una celda simple durante el video.
- No explica una línea de código relevante.
- Presenta resultados sin reproducibilidad mínima.
- Presenta un notebook aparentemente correcto, pero sin defensa técnica real.

La IA puede usarse como apoyo. La evaluación se centra en apropiación conceptual, defensa técnica y trazabilidad del trabajo.

#### Estructura obligatoria del video

El video debe seguir esta estructura.

- Presentacion breve del proyecto.
- Línea de proyecto elegida.
- Problema técnico.
- Línea base.
- modificación principal.
- Primera codificación en vivo.
- Predicción antes de ejecutar.
- Ejecución.
- Interpretación del resultado.
- Segunda codificación en vivo.
- Predicción antes de ejecutar.
- Ejecución.
- Interpretación del resultado.
- Explicación de tensores de imagen, latentes, embeddings multimodales, parámetros de difusión, métricas o restricciones de despliegue.
- Comparación línea base contra variante.
- Respuesta a preguntas avanzadas.
- Limitaciones.
- Cierre sobre qué hizo, por qué lo hizo y qué significan sus resultados.
- Puente al curso.

El video debe mostrar pantalla completa o notebook completo. No se aceptan videos compuestos solo por diapositivas. Debe escucharse la voz del estudiante.

#### Codificación en vivo obligatoria

Cada estudiante debe realizar dos ejercicios de codificación en vivo durante el video.

El primer ejercicio será una modificación común obligatoria.

El segúndo ejercicio será una modificación específica según el proyecto elegido.

No basta con cambiar un valor. El estudiante debe explicar qué valor tenía antes, qué valor coloca ahora, qué espera que ocurra, qué ocurrió realmente y si el resultado confirma o contradice su hipótesis.

#### Ejercicio A: modificación común obligatoria

El estudiante debe modificar en pantalla una parte del experimento y explicar el efecto esperado antes de ejecutar.

Puede elegir una de las siguientes opciones.

- Cambiar la resolución de imagen de entrada y explicar su impacto en memoria y calidad de representación.
- Cambiar el número de pasos de difusión y explicar su efecto en calidad y tiempo de generación.
- Cambiar la escala de guidance (guidance scale) y explicar cómo afecta la adherencia al prompt.
- Cambiar el tamaño de batch y explicar su impacto en memoria GPU y throughput.
- Cambiar la semilla y explicar por qué cambia la imagen generada o la salida del modelo.
- Cambiar el prompt de condicionamiento y explicar cómo cambia la distribución de la salida generada.
- Cambiar la temperatura o top_p de un modelo multimodal y explicar su efecto en diversidad de respuesta.
- Cambiar el número de tokens de entrada y explicar su impacto en latencia y memoria.
- Cambiar la precisión de cuantización (fp16, int8) y explicar su efecto en calidad y velocidad.
- Cambiar el tamaño del modelo cargado y explicar su impacto en latencia de inferencia.

#### Ejercicio B: modificación específica según proyecto

Además del cambio común, el estudiante debe hacer una modificación técnica relacionada directamente con su proyecto.

La modificación debe ser visible en el video, debe ejecutarse y debe interpretarse.

### Proyecto 1: Vision Transformer para clasificación de imágenes

**Tema central:** arquitectura ViT, patch embedding, positional encoding y clasificación visual.

El estudiante debe cargar un modelo ViT preentrenado, procesar imágenes en patches, mostrar la atención entre patches y comparar la clasificación contra un modelo CNN tradicional o contra diferentes resoluciones de patch.

La modificación obligatoria puede ser cambiar el tamaño de patch, el número de heads de atención, la resolución de entrada o agregar una capa de clasificación personalizada.

La evidencia interna mínima debe incluir la forma del tensor de imagen de entrada, la forma después de patch embedding, la forma de los tokens de atención y los logits de salida.

Código mínimo sugerido para mostrar en el video.

```python
print("Imagen de entrada:", image.shape)
print("Patches:", patches.shape)
print("Tokens después de embedding:", tokens.shape)
print("Attention map shape:", attention_map.shape)
print("Logits:", logits.shape)
print("Clase predicha:", predicted_class)
```

Preguntas avanzadas obligatorias.

- ¿Por qué un Vision Transformer divide la imagen en patches en lugar de procesar píxeles individuales?
- ¿Qué diferencia hay entre positional encoding en ViT y en transformers de lenguaje?
- ¿Cómo afecta el tamaño del patch al trade-off entre resolución espacial y costo computacional?
- ¿Por qué la atención global en ViT puede ser menos eficiente que convoluciones locales para imágenes pequeñas?
- ¿Qué relación hay entre el token CLS y la representación global de la imagen?.

### Proyecto 2: CLIP y representaciones texto-imagen

**Tema central:** aprendizaje contrastivo, espacio compartido texto-imagen y zero-shot classification.

El estudiante debe cargar un modelo CLIP, generar embeddings de texto e imagen, calcular similitudes y realizar clasificación zero-shot sobre un conjunto de imágenes propias. Debe comparar al menos dos estrategias de prompting para la clasificación.

La modificación obligatoria consiste en comparar dos conjuntos de prompts distintos y analizar cómo cambian las probabilidades de clasificación.

Código mínimo sugerido para mostrar en el video.

```python
print("Embedding imagen:", image_embedding.shape)
print("Embedding texto:", text_embedding.shape)
print("Matriz de similitud:", similarity_matrix.shape)
print("Clase predicha:", predicted_label)
print("Probabilidades top-3:", top_probs)
```

Preguntas avanzadas obligatorias.

- ¿Por qué CLIP usa una función de pérdida contrastiva en lugar de clasificación supervisada tradicional?
- ¿Qué limitación tiene la clasificación zero-shot cuando las clases son muy específicas o técnicas?
- ¿Cómo afecta la calidad del prompt a la representación del texto en CLIP?
- ¿Por qué el espacio compartido de CLIP permite búsqueda cruzada pero no garantiza alíneación semántica perfecta?
- ¿Qué riesgo de sesgo introduce entrenar CLIP con datos web no curados?.

### Proyecto 3: VLM y respuesta visual a preguntas (VQA)

**Tema central:** modelos de visión y lenguaje, generación condicionada a imagen y texto.

El estudiante debe usar un VLM para responder preguntas sobre imágenes, comparar respuestas con diferentes niveles de detalle en la pregunta y analizar casos donde el modelo falla. Debe mostrar el flujo de tokens de imagen y texto hacia el modelo.

La modificación obligatoria consiste en cambiar la formulacion de la pregunta y analizar cómo afecta la calidad y exactitud de la respuesta.

Código mínimo sugerido para mostrar en el video.

```python
print("Imagen:", image.shape)
print("Pregunta:", question)
print("Tokens de imagen:", image_tokens.shape)
print("Tokens de texto:", text_tokens.shape)
print("Respuesta generada:", answer)
print("Probabilidad del token de respuesta:", answer_prob)
```

Preguntas avanzadas obligatorias.

- ¿Por qué un VLM necesita proyectar los patches de imagen al espacio de embeddings de texto?
- ¿Qué diferencia hay entre VQA con generación libre y VQA con clasificación sobre respuestas predefinidas?
- ¿Cómo puede una pregunta ambigua hacer que el VLM alucine detalles no presentes en la imagen?
- ¿Por qué el orden de los tokens de imagen y texto en el input afecta la atención del modelo?
- ¿Qué limitación tiene evaluar un VLM solo con accuracy cuando las respuestas pueden ser parcialmente correctas?.

### Proyecto 4: Autoencoder y VAE para representaciones latentes

**Tema central:** compresión en espacio latente, regularización y reconstrucción.

El estudiante debe implementar o adaptar un autoencoder y un VAE, comparar la calidad de reconstrucción, mostrar el espacio latente y analizar la interpolacion entre puntos latentes. Debe explicar la diferencia entre reconstrucción determinista y generación probabilística.

La modificación obligatoria consiste en comparar dos tamaños de espacio latente y analizar el efecto en calidad de reconstrucción y capacidad de interpolacion.

Código mínimo sugerido para mostrar en el video.

```python
print("Imagen original:", original_image.shape)
print("Espacio latente:", latent_vector.shape)
print("Imagen reconstruida:", reconstructed_image.shape)
print("Pérdida de reconstrucción:", recon_loss)
print("Pérdida KL:", kl_loss)
print("Interpolacion punto A a B:", interpolated_latents.shape)
```

Preguntas avanzadas obligatorias.

- ¿Por qué un VAE regulariza el espacio latente con una pérdida KL mientras que un autoencoder simple no lo hace?
- ¿Qué problema ocurre si el espacio latente es demasiado pequeño para la complejidad de los datos?
- ¿Qué diferencia hay entre reconstrucción y generación en el contexto de un VAE?
- ¿Por qué la interpolacion en el espacio latente de un VAE bien entrenado produce transiciones coherentes?
- ¿Cómo se relaciona el espacio latente de un VAE con el espacio latente usado en modelos de difusión?.

### Proyecto 5: Modelo de difusión básico

**Tema central:** proceso de difusión hacia adelante, ruido gaussiano y denoising paso a paso.

El estudiante debe implementar o adaptar un pipeline de difusión simple sobre datos de baja dimensionalidad o imágenes pequeñas, mostrar el proceso de agregación de ruido, el entrenamiento del modelo de denoising y la generación inversa. Debe visualizar al menos tres etapas del proceso de difusión.

La modificación obligatoria consiste en cambiar el número de pasos de difusión y analizar el efecto en calidad visual y tiempo de generación.

Código mínimo sugerido para mostrar en el video.

```python
print("Imagen original:", x0.shape)
print("Imagen en paso t:", xt.shape)
print("Ruido agregado:", noise.shape)
print("Predicción de ruido:", predicted_noise.shape)
print("Imagen denoised:", x_t_minus_1.shape)
print("Número de pasos:", num_timesteps)
```

Preguntas avanzadas obligatorias.

- ¿Por qué el proceso de difusión hacia adelante es markoviano y cómo se relaciona con la reversibilidad?
- ¿Qué representa exactamente el modelo de denoising: la imagen limpia, el ruido agregado o el score?
- ¿Por qué aumentar el número de pasos de difusión mejora la calidad pero también el costo computacional?
- ¿Qué diferencia hay entre muestreo con DDPM y muestreo con DDIM?
- ¿Cómo se relaciona la varianza del ruido en cada paso con la programación de ruido (noise schedule)?.

### Proyecto 6: Stable Diffusion y generación condicionada

**Tema central:** generación de imágenes a partir de texto, espacio latente condicionado y guidance.

El estudiante debe usar Stable Diffusion o un modelo similar para generar imágenes a partir de prompts, comparar resultados con diferentes valores de guidance scale, diferentes prompts y diferentes semillas. Debe mostrar el flujo completo: tokenización del prompt, encoding textual, diffusion en espacio latente y decodificación a imagen.

La modificación obligatoria consiste en comparar dos valores de guidance scale y analizar el trade-off entre fidelidad al prompt y diversidad visual.

Código mínimo sugerido para mostrar en el video.

```python
print("Prompt:", prompt)
print("Embedding textual:", text_embedding.shape)
print("Latente inicial:", latent.shape)
print("Latente final:", final_latent.shape)
print("Imagen generada:", generated_image.shape)
print("Guidance scale:", guidance_scale)
print("Pasos de difusión:", num_inference_steps)
```

Preguntas avanzadas obligatorias.

- ¿Por qué Stable Diffusion opera en espacio latente en lugar de espacio de píxeles?
- ¿Qué función cumple el text encoder en el pipeline de Stable Diffusion?
- ¿Por qué un guidance scale muy alto puede producir artefactos o imágenes sobre-saturadas?
- ¿Qué diferencia hay entre negative prompting y guidance scale bajo?
- ¿Cómo se relaciona la arquitectura UNet del modelo de difusión con la preservación de estructura espacial?.

### Proyecto 7: Evaluación de calidad de generación de imágenes

**Tema central:** métricas de calidad para imágenes generadas, comparación cuantitativa y análisis visual.

El estudiante debe generar un conjunto de imágenes con al menos dos configuraciones distintas de un modelo de difusión, calcular métricas como FID, IS o métricas perceptuales simples, y comparar visual y cuantitativamente los resultados.

La modificación obligatoria consiste en cambiar el número de pasos de inferencia o el scheduler y analizar como evolucionan las métricas de calidad.

Código mínimo sugerido para mostrar en el video.

```python
print("Configuración A:", config_a)
print("Configuración B:", config_b)
print("FID A:", fid_a)
print("FID B:", fid_b)
print("IS A:", is_a)
print("IS B:", is_b)
print("Comparación visual: imagen A vs imagen B")
```

Preguntas avanzadas obligatorias.

- ¿Por qué FID mide la distancia entre distribuciones de caracteristicas y no entre imágenes individuales?
- ¿Qué limitación tiene Inception Score cuando el modelo genera pocas clases o modos?
- ¿Por qué una métrica de calidad baja no garantiza que las imágenes sean semánticamente correctas?
- ¿Cómo se relaciona la calidad métrica con la fidelidad al prompt en generación condicionada?
- ¿Qué sesgo introduce usar una red preentrenada en ImageNet para evaluar imágenes de dominio diferente?.

### Proyecto 8: Despliegue y optimización de inferencia

**Tema central:** latencia, throughput, cuantización, batching y monitorización de sistemas de lenguaje.

El estudiante debe cargar un modelo de lenguaje o multimodal, medir latencia de inferencia con diferentes tamaños de entrada, aplicar cuantización o pruning, comparar throughput antes y después de la optimización, y discutir el trade-off entre calidad y velocidad.

La modificación obligatoria consiste en comparar dos estrategias de optimización (por ejemplo, cuantización int8 vs fp16, o batching dinámico vs estático) y analizar el efecto en latencia, memoria y calidad de salida.

Código mínimo sugerido para mostrar en el video.

```python
print("Modelo original:", model_name)
print("Parámetros totales:", total_params)
print("Latencia promedio (ms):", avg_latency)
print("Throughput (tokens/s):", throughput)
print("Memoria usada (MB):", memory_mb)
print("Modelo optimizado:", optimized_model_name)
print("Latencia optimizada (ms):", optimized_latency)
print("Throughput optimizado (tokens/s):", optimized_throughput)
print("Memoria optimizada (MB):", optimized_memory)
```

Preguntas avanzadas obligatorias.

- ¿Por qué la cuantización reduce memoria pero puede introducir error de redondeo en activaciones?
- ¿Qué diferencia hay entre latencia de primer token (time to first token) y latencia por token?
- ¿Por qué el batching dinámico mejora throughput pero puede aumentar latencia de cola?
- ¿Cómo se relaciona el tamaño del modelo con el costo de despliegue en producción?
- ¿Qué métricas de monitorización son críticas para detectar degradación de un modelo en producción?.

### Proyecto 9: Sistema multimodal completo

**Tema central:** integración de comprensión visual, lenguaje y generación en un pipeline unificado.

El estudiante debe construir un pipeline que combine un VLM para comprensión de imagen con un modelo de difusión para generación de imagen. Por ejemplo: analizar una imagen con VLM, extraer una descripción, y usar esa descripción para generar una nueva imagen con Stable Diffusion. Debe comparar la calidad de la imagen generada cuando la descripción proviene del VLM vs cuando la descripción es escrita manualmente.

La modificación obligatoria consiste en comparar dos estrategias de descripción: descripción detallada del VLM vs prompt manual, y analizar la fidelidad de la imagen generada a cada tipo de entrada.

Código mínimo sugerido para mostrar en el video.

```python
print("Imagen de entrada:", input_image.shape)
print("Descripción del VLM:", vlm_description)
print("Prompt manual:", manual_prompt)
print("Imagen generada desde VLM:", image_from_vlm.shape)
print("Imagen generada desde manual:", image_from_manual.shape)
print("Comparación de similitud:", similarity_score)
```

Preguntas avanzadas obligatorias.

- ¿Por qué la calidad de la descripción del VLM limita la calidad de la imagen generada?
- ¿Qué informacion se pierde al pasar de imagen a texto y luego de texto a imagen?
- ¿Cómo se relaciona el espacio latente del VLM con el espacio latente del modelo de difusión?
- ¿Qué riesgo introduce la acumulacion de errores en un pipeline de multiples modelos?
- ¿Como evaluarías la calidad de un sistema multimodal cuando no existe una respuesta única correcta?.

#### Preguntas transversales obligatorias

Además de las preguntas específicas del proyecto, todo estudiante debe responder al menos cinco de las siguientes preguntas en el video.

- ¿Qué parte de tu trabajo corresponde a percepción, qué parte a generación y qué parte a despliegue?
- ¿Qué componente de tu notebook sería más difícil de detectar si estuviera mal implementado?
- ¿Qué resultado podría parecer bueno, pero ser técnicamente engañoso?
- ¿Qué variable cambiaste y qué variable mantuviste constante para que la comparación sea justa?
- ¿Qué parte de tu resultado depende del dataset de imágenes y no del modelo?
- ¿Qué parte de tu resultado depende del prompt y no del aprendizaje del modelo?
- ¿Qué evidencia muestra que tu cambio no fue cosmético?
- ¿Qué error esperas si aumentas demasiado la resolución de las imágenes de entrada?
- ¿Qué error esperas si reduces demasiado el número de pasos de difusión?
- ¿Qué significa que un modelo de difusión sea markoviano desde el punto de vista de la probabilidad?
- ¿Dónde aparece la distribución de probabilidad en tu notebook?
- ¿Dónde aparece la función de pérdida o métrica de evaluación?
- ¿Qué parte de tu código controla la calidad visual?
- ¿Qué parte de tu código controla la diversidad de generación?
- ¿Qué parte de tu código controla la latencia de inferencia?
- ¿Qué parte de tu código permite reproducibilidad?
- ¿Como distinguirías un error de implementación de una mala elección de hiperparámetros?
- ¿Qué resultado inválidaría tu conclusión?
- ¿Qué simplificación hiciste por limitaciones de cómputo?
- ¿Qué harías distinto si tuvieras una GPU con más memoria y tiempo ilimitado?.

#### Requisitos mínimos del notebook

El notebook debe contener las siguientes secciones.

- Título del proyecto.
- Nombre del estudiante.
- Línea de proyecto elegida.
- Objetivo.
- Línea base.
- modificación significativa.
- Configuración experimental.
- Dataset, imágenes o prompts utilizados.
- Tabla de dimensiones o estructuras de datos.
- Evidencia de cálculo interno.
- Comparación línea base contra variante.
- Análisis de errores.
- Conclusión técnica.
- Declaración de autoría y uso de IA.
- Sección final llamada `Puente al curso`.

#### Celda de verificacion personal

Cada notebook debe incluir una celda llamada `CELDA DE VERIFICACION PERSONAL`.

La celda debe contener lo siguiente.

- Nombre completo del estudiante.
- Fecha de ejecución.
- Modelo usado.
- Semilla.
- Tamaño del dataset o lista de prompts.
- Frase técnica propia que explique el objetivo.
- Variante elegida según el proyecto.

Ejemplo sugerido.

```python
STUDENT_NAME = "Nombre completo"
EXECUTION_DATE = "AAAA-MM-DD"
PROJECT_TRACK = "Proyecto X: línea de proyecto elegida"
MODEL_NAME = "modelo usado"
SEED = 42
VARIANT = "descripción breve de la variante"

print("Estudiante:", STUDENT_NAME)
print("Fecha:", EXECUTION_DATE)
print("Línea de proyecto:", PROJECT_TRACK)
print("Modelo:", MODEL_NAME)
print("Semilla:", SEED)
print("Variante:", VARIANT)
```

#### Requisitos mínimos del README

El archivo `README.md` debe contener las siguientes secciones.

- Título.
- Objetivo.
- Línea de proyecto elegida.
- Resumen de la línea base.
- modificación realizada.
- Como ejecutar el notebook.
- Principales resultados.
- Limitaciones.
- Qué se muestra en el video.
- Declaración de autoría y uso de IA.

#### Declaración de autoría y uso de IA

El estudiante debe incluir en el notebook y en el README una declaración breve con el siguiente contenido.

```
Declaro que comprendo el código, los resultados y las explicaciones entregadas en esta práctica.
Si utilicé herramientas de IA, las use como apoyo para redacción, depuración o consulta, pero la implementación final, la interpretación técnica y la defensa del trabajo son responsabilidad mia.
```

Si el estudiante uso IA, debe indicar para qué la usó.

Ejemplos válidos.

- Usé IA para revisar redacción del README.
- Usé IA para depurar un error de dimension de tensores de imagen.
- Usé IA para entender una advertencia de la librería de difusión.
- Usé IA para generar una primera versión de una función de evaluación que luego modifiqué y explique.

Ejemplos no válidos.

- Usé IA para hacer todo el notebook.
- No se qué partes hizo la IA.
- Solo ejecuté el código generado.
- No puedo explicar la función generada.

#### Rúbrica sobre 20 puntos

#### A. Video técnico y defensa asíncrona: 6 puntos

- 1 punto: explica el problema y el línea de proyecto.
- 1 punto: explica la línea base.
- 1 punto: explica la modificación principal.
- 1 punto: interpreta resultados.
- 1 punto: responde preguntas avanzadas.
- 1 punto: conecta el trabajo con el curso.

#### B. Codificación en vivo: 5 puntos

- 1 punto: realiza una modificación común obligatoria.
- 1 punto: realiza una modificación específica del proyecto.
- 1 punto: predice el efecto antes de ejecutar.
- 1 punto: interpreta el resultado después de ejecutar.
- 1 punto: explica errores, cambios de forma, latencia, métricas o salida generada.

#### C. Evidencia interna y comprensión técnica: 4 puntos

- 1 punto: muestra tensores de imagen, latentes, embeddings multimodales, parámetros de difusión, métricas o flujo de despliegue.
- 1 punto: explica dimensiones o estructuras correctamente.
- 1 punto: conecta el cálculo interno con el código.
- 1 punto: justifica por qué su variante es técnicamente relevante.

#### D. Análisis experimental: 3 puntos

- 1 punto: compara línea base contra variante.
- 1 punto: incluye evidencia cuantitativa, visual o tabular.
- 1 punto: analiza limitaciones y errores.

#### E. Repositorio, notebook y README: 2 puntos

- 1 punto: notebook ordenado, ejecutable y reproducible.
- 1 punto: README claro con declaración de autoría y uso de IA.

#### Penalizaciones críticas

Estas penalizaciones tienen prioridad sobre la rúbrica.

- Video inexistente: 0/20.
- Video sin voz propia: 0/20.
- Video de 12 minutos exactos o menos: 0/20.
- Video sin codificación en vivo: 0/20.
- Video que solo lee texto o muestra celdas ya ejecutadas: 0/20.
- No responder preguntas avanzadas: máximo 10/20.
- No explicar dimensiones o estructuras centrales del proyecto: máximo 10/20.
- No comparar línea base contra variante: descuento de 3 puntos.
- No incluir README: descuento de 2 puntos.
- No declarar uso de IA: descuento de 2 puntos.
- Notebook generado automáticamente sin defensa técnica: 0/20.
- Código correcto sin explicación correcta: 0/20.
- Explicación genérica desconectada del notebook: 0/20.

#### Criterio de autenticidad

El objetivo no es impedir el uso de IA. El objetivo es impedir que el estudiante entregue un producto que no comprende.

La autenticidad se evaluará mediante la modificación en vivo, la explicación de errores, la predicción antes de ejecutar, la interpretación después de ejecutar, la explicación de dimensiones y estructuras, la respuesta a preguntas avanzadas y la conexion entre notebook, código, resultado y teoría.

Un estudiante puede usar IA como apoyo, pero debe demostrar control técnico sobre el trabajo entregado.

#### Qué se considera una buena entrega

Una buena entrega parte de una línea de proyecto permitida, reconstruye una línea base, introduce una modificación real, compara resultados, muestra evidencia interna, explica dimensiones, analiza errores, reconoce limitaciones, usa vocabulario técnico correctamente y conecta código, matemática y resultado.

#### Qué se considera una mala entrega

Una mala entrega solo ejecuta celdas, cambia nombres o colores sin modificar el experimento, presenta texto genérico generado por IA, no explica el código, no explica tensores de imagen ni latentes ni parámetros de difusión, no interpreta resultados, no compara línea base contra variante, no muestra cálculo interno y no demuestra aprendizaje real.

#### Cierre obligatorio

Todo video y todo README deben terminar con dos secciones obligatorias.

#### Qué hice, por qué lo hice y qué significan mis resultados

El estudiante debe explicar en lenguaje propio qué implementó, qué modificó, por qué esa modificación es técnicamente relevante, qué evidencia obtuvo y qué significan los resultados.

#### Puente al curso

El estudiante debe conectar su proyecto con al menos dos temas relacionados.

- Modelos multimodales.
- Vision Transformers.
- Representaciones texto-imagen.
- Modelos de difusión.
- Stable Diffusion.
- Generación condicionada.
- Espacios latentes.
- Cuantización y optimización.
- Latencia y throughput.
- Monitorización de sistemas de lenguaje.
- Edge vs cloud.
- Seguridad y privacidad en despliegue.
- Integración del curso y proyección hacia estudios avanzados.

#### Observación final para el estudiante

Esta práctica no evalúa solamente si el notebook funciona. Evalúa si el estudiante entiende el sistema multimodal o de difusión, el código, los datos, la modificación realizada, los resultados obtenidos y las limitaciones del experimento.

La nota depende de la evidencia técnica mostrada en el notebook y defendida en el video.
