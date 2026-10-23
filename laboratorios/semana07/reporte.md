# Parte 1 — Definición de una buena respuesta

## Tarea y resultado esperado

La tarea elegida es transformar solicitudes de adaptación de un consultorio en una ficha de requisitos arquitectónicos preliminares. Una buena respuesta organiza lo que el cliente dijo, conserva los datos y hace visibles los puntos que requieren aclaración.

El formato requerido es una tabla Markdown de dos columnas, `Campo` y `Requisito`, con exactamente seis filas de datos, en este orden: Uso, Ubicación, Superficie disponible, Espacios solicitados, Iluminación y Presupuesto. Después debe aparecer el encabezado `Preguntas de aclaración` y una lista numerada de preguntas o la frase `No se requieren aclaraciones`.

Un campo sin datos debe contener `No especificado`. Un campo con datos incompatibles debe contener `Contradicción`, conservar ambas versiones y tener una pregunta para resolverla. Una expresión no medible como “amplio” debe identificarse como `Ambiguo` y generar una pregunta, sin asignarle medidas inventadas. Estas marcas pueden acompañar los datos que sí se conocen del campo.

## Criterios de calidad

| Criterio | 0 puntos | 1 punto | 2 puntos |
| --- | --- | --- | --- |
| C1. Completitud de la ficha | Faltan dos o más de los seis campos requeridos. | Falta exactamente uno de los seis campos requeridos. | Aparecen los seis campos: uso, ubicación, superficie disponible, espacios solicitados, iluminación y presupuesto. Un campo marcado como desconocido cuenta como presente. |
| C2. Formato verificable | No cumple ninguna de las dos condiciones A y B descritas abajo. | Cumple exactamente una de las condiciones A y B. | Cumple ambas condiciones A y B. |
| C3. Fidelidad y manejo de incertidumbre | Añade al menos un dato no proporcionado como si fuera un requisito confirmado, altera un dato explícito o elige una versión de una contradicción sin señalarla. | No incurre en los errores de 0 puntos, pero deja sin marcar al menos un dato faltante, contradicción o ambigüedad; omite una de las versiones contradictorias; o falta al menos una pregunta de aclaración necesaria. | Conserva los datos explícitos sin inventar, marca todos los datos faltantes, contradicciones y ambigüedades con las etiquetas definidas, conserva ambas versiones de cada contradicción y formula preguntas para resolver cada punto pendiente. Si no hay puntos pendientes, indica que no se requieren aclaraciones. |

**Condición A de C2:** presenta una tabla Markdown con las dos columnas indicadas, exactamente seis filas de datos y el orden de campos especificado.

**Condición B de C2:** después de la tabla incluye el encabezado `Preguntas de aclaración` con una lista numerada o la frase `No se requieren aclaraciones`.

**Regla de evaluación de C3:** primero se comprueba si existe un error de 0 puntos. Si existe, la calificación es 0 aunque la respuesta también tenga aciertos. Si no existe, se asignan 2 puntos únicamente cuando cumple todas las condiciones de esa columna; en otro caso se asigna 1.

## Referencia para evaluar las tres entradas

- **Entrada 1:** los seis campos tienen información. Debe conservar nutrición, planta baja, 30 m², sala de espera para dos personas, consulta privada, baño, luz natural en espera y consulta y $250,000 MXN. No requiere aclaraciones para llenar esta ficha.
- **Entrada 2:** faltan la especialidad o tipo de consulta, la superficie disponible y el presupuesto. Debe señalar estos tres puntos y preguntar por ellos. Debe conservar la planta baja, la atención de una persona a la vez, la sala de espera y la luz natural en ambos espacios. No debe añadir un baño como requisito confirmado.
- **Entrada 3:** debe señalar la contradicción entre 20 m² y las dimensiones de 5 × 6 m (equivalentes a 30 m²), la contradicción sobre la entrada de luz natural, los dos máximos de presupuesto ($180,000 y $230,000 MXN) y la ambigüedad de “amplio”. Debe preguntar por cada uno de estos cuatro puntos. El cálculo de 30 m² es válido si se identifica como derivado de las dimensiones dadas.

La evaluación se limita a los seis campos y a los puntos pendientes definidos aquí. No se penaliza la ausencia de estudios técnicos, normativa o información ajena al alcance de la ficha.

## Puntaje

Cada entrada puede obtener de 0 a 6 puntos: C1 + C2 + C3. Cada iteración usa las tres entradas y puede obtener de 0 a 18 puntos. Una calificación alta en completitud o formato no compensa una invención: como condición de aceptación, las tres entradas deben obtener 2 en C3.

## ¿Por qué C3 es el más importante?

C3 es el más importante porque una persona puede confiar en una respuesta bien presentada aunque contenga datos inventados. En este proyecto, inventar una superficie o elegir un presupuesto sin aclararlo podría llevar a planear espacios que no caben o a preparar una propuesta que supera lo que el cliente puede pagar. Marcar lo que falta y preguntar permite que el cliente confirme los requisitos antes de avanzar.

Este criterio cubre el riesgo de convertir información incompleta o contradictoria en requisitos aparentemente confirmados. La ficha es una base preliminar de comunicación; no demuestra por sí sola que el proyecto sea viable.

## Evidencia visual

La imagen `tabla_criterios.png` reproduce la rúbrica y las condiciones de formato para adjuntarla como evidencia visual. Es una imagen generada de la tabla, no una captura de una aplicación.
