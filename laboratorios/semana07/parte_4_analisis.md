# Parte 4 — Tabla de resultados, análisis y robustez

## Paso 4.1 — Resultados acumulados

Cada criterio suma las tres entradas: máximo 6 por criterio y 18 por iteración.

| Iteración | Técnica aplicada | Criterio 1 | Criterio 2 | Criterio 3 | Total | Observación |
|---|---|---|---|---|---|---|
| 0 | Línea base (zero-shot) | 6 | 0 | 2 | 8 | Campos presentes; formatos distintos y un requisito de acceso al baño añadido sin confirmación. |
| 1 | Rol | 6 | 0 | 3 | 9 | Vocabulario arquitectónico y datos pendientes; faltan formato y etiquetas exactas. |
| 2 | Rol + contexto | 6 | 0 | 3 | 9 | Respuestas centradas en los seis campos; persisten diferencias de formato y aclaración. |
| 3 | Rol + contexto + formato | 6 | 6 | 5 | 17 | Cumple el formato; falta la etiqueta exacta de especialidad en una respuesta. |
| 4 | Anterior + ejemplos (few-shot) | 6 | 6 | 5 | 17 | Sin copia de datos del ejemplo; persiste la misma diferencia de etiqueta. |
| 5 | Anterior + cadena de razonamiento | 6 | 6 | 6 | 18 | Análisis previo breve, tabla y etiquetas completas; se acepta el análisis para revisión humana. |

## Paso 4.2 — Análisis de la curva

### ¿Qué iteración produjo el mayor salto y en qué criterio?

La iteración 3 produjo el mayor salto: pasó de 9 a 17 puntos, una mejora de 8. El cambio principal ocurrió en C2, que pasó de 0 a 6, porque las tres respuestas utilizaron la tabla y la sección de aclaraciones exigidas. C3 pasó de 3 a 5, mientras que C1 permaneció en 6.

Este paso añadió un bloque que incluía tanto el formato como las reglas para datos desconocidos, contradictorios o ambiguos. Por eso, el aumento corresponde al bloque completo: la prueba no permite atribuir cada punto exclusivamente al formato.

### ¿Alguna iteración bajó el puntaje?

No. La secuencia fue 8, 9, 9, 17, 17 y 18. Las iteraciones 2 y 4 no mejoraron el total, pero tampoco lo redujeron. El contexto hizo las respuestas más concisas sin sumar puntos, porque C1 ya estaba en su máximo. El ejemplo no corrigió la diferencia entre “especialidad no especificada” y la etiqueta exacta “No especificado”.

Los criterios sí discriminaron: C2 y C3 cambiaron entre versiones. Que C1 se mantuviera en 6 indica que la completitud básica ya estaba lograda; no significa que todas las respuestas tuvieran la misma calidad. No se cambió la rúbrica después de ver los resultados.

### ¿Qué prompt se adoptará para el proyecto?

Adoptaré el prompt de la iteración 5, que obtuvo 18/18, como plantilla compartida para el equipo. Las instrucciones, el ejemplo y el formato quedarán fijos; cada persona sustituirá únicamente el texto de entrada. Aunque es más largo, su uso cotidiano consiste en pegar el caso en el lugar indicado.

El análisis previo es aceptable porque un arquitecto revisará la ficha. Permite comprobar qué datos están explícitos, qué cálculos son verificables y qué no puede determinarse antes de usar la tabla. La mejora frente a la iteración 4 fue de un solo punto por una etiqueta, así que no se interpreta como garantía de mayor precisión en cualquier caso. El ejemplo no mostró una mejora medible, pero se conserva porque forma parte de la versión que se probó; eliminarlo exigiría validar esa nueva variante.

La plantilla reutilizable está en `prompt_adoptado.md`. El análisis es un resumen de evidencias, no un desarrollo de razonamiento paso a paso.

## Paso 4.3 — Prueba de robustez

Se seleccionó el prompt de la iteración 5 antes de redactar y ejecutar la cuarta entrada. Se hizo una sola prueba en una conversación nueva, sin modificar el prompt ni repetir la ejecución para mejorar el puntaje.

La nueva solicitud corresponde a un consultorio de fisioterapia en un anexo de 4 × 7 m. Incluye sala de espera para tres personas, atención privada, almacén, uso de un baño existente, iluminación distinta según el espacio y dos partidas complementarias de presupuesto: $180,000 MXN de obra y $30,000 MXN de mobiliario.

| Criterio | Puntaje | Evidencia |
|---|---|---|
| C1. Completitud | 2/2 | Presenta los seis campos y conserva el uso del baño existente sin proponer uno nuevo. |
| C2. Formato | 2/2 | Incluye Análisis con tres viñetas, tabla de seis filas en el orden requerido y Preguntas de aclaración. |
| C3. Fidelidad e incertidumbre | 2/2 | Deriva 28 m² de 4 × 7 m y $210,000 MXN de las dos partidas, conservando los datos originales. No confunde las partidas con topes contradictorios ni inventa dimensiones por espacio. |
| **Total** | **6/6** | **Cumple los tres criterios.** |

Promedio de las tres entradas originales de la iteración 5: (6 + 6 + 6) / 3 = **6 puntos**.

Puntaje de la entrada nueva: **6 puntos**. Caída: 6 − 6 = **0 puntos**.

La caída no supera 2 puntos, por lo que **no se activa la señal de sobreajuste establecida por el laboratorio**. Con este promedio, una nueva calificación de 3/6 o menos sí superaría el umbral; 4/6 sería una caída de exactamente 2, no mayor.

### ¿Qué aporta validar con una entrada nueva?

Las tres primeras entradas se usaron repetidamente para evaluar y elegir las versiones del prompt. Un buen resultado en ellas podía deberse a que las instrucciones se ajustaron a sus características. La cuarta entrada no se utilizó durante esos ajustes y presenta combinaciones nuevas: superficie mediante dimensiones, presupuesto dividido en partidas y una exclusión explícita de obra.

Resolverla correctamente aporta evidencia de que el prompt puede aplicar sus reglas a un caso que no se utilizó para elegirlo. Las tres primeras no podían aportar esa independencia. Sin embargo, una sola entrada no demuestra que el prompt esté libre de sobreajuste ni que funcione con todos los usuarios; este caso tampoco añade un nuevo conflicto de datos faltantes. Harían falta más casos independientes y variados para sostener una conclusión general.

La entrada, el prompt enviado, la respuesta completa y su evaluación se conservan en `prueba_robustez.md`. El modelo se dejó en la configuración predeterminada de la aplicación; no se registró un identificador verificable ni parámetros de generación.
