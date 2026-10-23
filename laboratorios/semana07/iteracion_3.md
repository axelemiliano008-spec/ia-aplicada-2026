# Iteración 3 — Formato de salida y manejo explícito de incertidumbre

Fecha: 23 de octubre de 2026. Cada entrada se ejecutó en una conversación nueva. Se conservaron las entradas y la rúbrica de la Parte 1. Se utilizó el modelo predeterminado de la aplicación, sin cambiarlo explícitamente; su identificador y parámetros no se registraron.

Cambio respecto a la iteración anterior: se conservaron rol y contexto y se añadió el bloque de salida con tabla, aclaraciones y reglas para incertidumbre, como pide el paso 3.3.

## Entrada 1

Conversación: `01a16778-e56e-74f2-8e94-f29cb69285a7`

### Prompt completo enviado

```text
Eres arquitecto encargado de recopilar requerimientos para adaptar consultorios en viviendas. Tu lector es el arquitecto que preparará una propuesta preliminar y necesita información precisa.

Contexto: este texto proviene de un formulario que llenan propietarios sin conocimientos técnicos. El sistema organiza solicitudes de adaptación de consultorios en viviendas; pueden llegar datos completos, incompletos, contradictorios o ambiguos. La ficha comprende seis campos: uso (incluida la especialidad del consultorio), ubicación, superficie disponible, espacios solicitados, iluminación y presupuesto. El alcance es registrar los requisitos del propietario para una revisión preliminar; no desarrollar un diseño, repartir superficies, estimar costos ni evaluar cumplimiento normativo.

Responde únicamente con esta tabla en Markdown y la sección de aclaraciones indicada, sin texto adicional:

| Campo | Requisito |
|---|---|
| Uso | |
| Ubicación | |
| Superficie disponible | |
| Espacios solicitados | |
| Iluminación | |
| Presupuesto | |

## Preguntas de aclaración

Conserva todos los datos explícitos de la entrada, sin convertir propuestas o suposiciones en requisitos confirmados. Si un dato no puede determinarse a partir del texto, escribe "No especificado" en el campo correspondiente y pregunta por él. Si un campo contiene datos incompatibles, escribe "Contradicción", conserva ambas versiones y pregunta cuál debe utilizarse. Si una expresión no es medible o tiene varias interpretaciones, escribe "Ambiguo" en el campo relacionado y pregunta qué significa para el propietario. Puedes acompañar estas marcas con los datos que sí se conocen. Formula una lista numerada con una pregunta por cada punto pendiente de los seis campos. Si no hay puntos pendientes para completar la ficha, escribe "No se requieren aclaraciones". No solicites información ajena al alcance de la ficha.

Haz la ficha de requerimientos de este espacio:

Quiero adaptar un consultorio de nutrición en la planta baja de mi casa. Dispongo de un área rectangular de 30 m². Necesito una sala de espera para dos personas, un espacio privado de consulta y un baño. Quiero luz natural en la sala de espera y en el espacio de consulta. Mi presupuesto total para la adaptación es de $250,000 MXN.
```

### Respuesta completa sin corregir

| Campo | Requisito |
|---|---|
| Uso | Consultorio de nutrición. |
| Ubicación | Planta baja de la casa. |
| Superficie disponible | Área rectangular de 30 m². |
| Espacios solicitados | Sala de espera para dos personas, espacio privado de consulta y baño. |
| Iluminación | Luz natural en la sala de espera y en el espacio de consulta. |
| Presupuesto | $250,000 MXN en total para la adaptación. |

## Preguntas de aclaración

No se requieren aclaraciones.

### Evaluación

| C1 | C2 | C3 | Total |
|---|---|---|---|
| 2 | 2 | 2 | 6/6 |

Seis campos completos, formato exacto y ‘No se requieren aclaraciones’. Conserva los datos de la entrada.

## Entrada 2

Conversación: `01a16778-fb2f-7390-8cdd-13417a534215`

### Prompt completo enviado

```text
Eres arquitecto encargado de recopilar requerimientos para adaptar consultorios en viviendas. Tu lector es el arquitecto que preparará una propuesta preliminar y necesita información precisa.

Contexto: este texto proviene de un formulario que llenan propietarios sin conocimientos técnicos. El sistema organiza solicitudes de adaptación de consultorios en viviendas; pueden llegar datos completos, incompletos, contradictorios o ambiguos. La ficha comprende seis campos: uso (incluida la especialidad del consultorio), ubicación, superficie disponible, espacios solicitados, iluminación y presupuesto. El alcance es registrar los requisitos del propietario para una revisión preliminar; no desarrollar un diseño, repartir superficies, estimar costos ni evaluar cumplimiento normativo.

Responde únicamente con esta tabla en Markdown y la sección de aclaraciones indicada, sin texto adicional:

| Campo | Requisito |
|---|---|
| Uso | |
| Ubicación | |
| Superficie disponible | |
| Espacios solicitados | |
| Iluminación | |
| Presupuesto | |

## Preguntas de aclaración

Conserva todos los datos explícitos de la entrada, sin convertir propuestas o suposiciones en requisitos confirmados. Si un dato no puede determinarse a partir del texto, escribe "No especificado" en el campo correspondiente y pregunta por él. Si un campo contiene datos incompatibles, escribe "Contradicción", conserva ambas versiones y pregunta cuál debe utilizarse. Si una expresión no es medible o tiene varias interpretaciones, escribe "Ambiguo" en el campo relacionado y pregunta qué significa para el propietario. Puedes acompañar estas marcas con los datos que sí se conocen. Formula una lista numerada con una pregunta por cada punto pendiente de los seis campos. Si no hay puntos pendientes para completar la ficha, escribe "No se requieren aclaraciones". No solicites información ajena al alcance de la ficha.

Haz la ficha de requerimientos de este espacio:

Quiero un consultorio en la planta baja de mi casa. Necesito un espacio privado para atender a una persona a la vez y una pequeña sala de espera. Quiero luz natural en ambos espacios. No sé cuántos metros tengo disponibles y todavía no he definido mi presupuesto.
```

### Respuesta completa sin corregir

| Campo | Requisito |
|---|---|
| Uso | Consultorio; especialidad no especificada. |
| Ubicación | Planta baja de la casa. |
| Superficie disponible | No especificado. |
| Espacios solicitados | Espacio privado para atender a una persona a la vez y una sala de espera. El tamaño «pequeña» es Ambiguo. |
| Iluminación | Luz natural en ambos espacios. |
| Presupuesto | No especificado. |

## Preguntas de aclaración

1. ¿Qué especialidad tendrá el consultorio?
2. ¿Cuántos metros cuadrados tiene disponibles para la adaptación?
3. ¿Qué tamaño o capacidad considera adecuado para una sala de espera «pequeña»?
4. ¿Qué presupuesto tiene previsto?

### Evaluación

| C1 | C2 | C3 | Total |
|---|---|---|---|
| 2 | 2 | 1 | 5/6 |

Detecta y pregunta por los tres datos faltantes. El uso dice ‘especialidad no especificada’ en vez de la etiqueta exacta ‘No especificado’. C3 pierde un punto por cumplimiento literal, no por inventar datos.

## Entrada 3

Conversación: `01a16779-059c-7523-9333-0b0bf23bb75d`

### Prompt completo enviado

```text
Eres arquitecto encargado de recopilar requerimientos para adaptar consultorios en viviendas. Tu lector es el arquitecto que preparará una propuesta preliminar y necesita información precisa.

Contexto: este texto proviene de un formulario que llenan propietarios sin conocimientos técnicos. El sistema organiza solicitudes de adaptación de consultorios en viviendas; pueden llegar datos completos, incompletos, contradictorios o ambiguos. La ficha comprende seis campos: uso (incluida la especialidad del consultorio), ubicación, superficie disponible, espacios solicitados, iluminación y presupuesto. El alcance es registrar los requisitos del propietario para una revisión preliminar; no desarrollar un diseño, repartir superficies, estimar costos ni evaluar cumplimiento normativo.

Responde únicamente con esta tabla en Markdown y la sección de aclaraciones indicada, sin texto adicional:

| Campo | Requisito |
|---|---|
| Uso | |
| Ubicación | |
| Superficie disponible | |
| Espacios solicitados | |
| Iluminación | |
| Presupuesto | |

## Preguntas de aclaración

Conserva todos los datos explícitos de la entrada, sin convertir propuestas o suposiciones en requisitos confirmados. Si un dato no puede determinarse a partir del texto, escribe "No especificado" en el campo correspondiente y pregunta por él. Si un campo contiene datos incompatibles, escribe "Contradicción", conserva ambas versiones y pregunta cuál debe utilizarse. Si una expresión no es medible o tiene varias interpretaciones, escribe "Ambiguo" en el campo relacionado y pregunta qué significa para el propietario. Puedes acompañar estas marcas con los datos que sí se conocen. Formula una lista numerada con una pregunta por cada punto pendiente de los seis campos. Si no hay puntos pendientes para completar la ficha, escribe "No se requieren aclaraciones". No solicites información ajena al alcance de la ficha.

Haz la ficha de requerimientos de este espacio:

Quiero un consultorio de psicología en la planta baja de mi casa, con sala de espera, espacio privado de consulta y baño. El área disponible mide 20 m²; en esa misma área hay un rectángulo libre de 5 por 6 metros, sin obstáculos. Quiero luz natural en la sala de espera, pero también digo que no debe entrar luz natural en ningún espacio del consultorio. Mi presupuesto máximo total es de $180,000 MXN, aunque puedo gastar hasta $230,000 MXN en total sin cambiar el alcance. Que quede amplio.
```

### Respuesta completa sin corregir

| Campo | Requisito |
|---|---|
| Uso | Consultorio de psicología en la planta baja de la casa. |
| Ubicación | Planta baja de la casa. |
| Superficie disponible | Contradicción: se indican 20 m² disponibles y, en esa misma área, un rectángulo libre de 5 × 6 m (30 m²), sin obstáculos. Ambiguo: «Que quede amplio». |
| Espacios solicitados | Sala de espera, espacio privado de consulta y baño. |
| Iluminación | Contradicción: se solicita luz natural en la sala de espera y también que no entre luz natural en ningún espacio del consultorio. |
| Presupuesto | Contradicción: presupuesto máximo total de $180,000 MXN; también se indica que puede gastar hasta $230,000 MXN en total sin cambiar el alcance. |

## Preguntas de aclaración

1. ¿Cuál dato corresponde a la superficie disponible: 20 m² o un rectángulo libre de 5 × 6 m (30 m²)?
2. ¿Qué significa «amplio» para usted respecto al espacio disponible?
3. ¿Debe entrar luz natural en la sala de espera o no debe entrar en ningún espacio del consultorio?
4. ¿Cuál es el presupuesto máximo total que debemos registrar: $180,000 MXN o $230,000 MXN?

### Evaluación

| C1 | C2 | C3 | Total |
|---|---|---|---|
| 2 | 2 | 2 | 6/6 |

Conserva ambas versiones de los tres conflictos, marca Contradicción y Ambiguo y formula cuatro preguntas. Cumple el formato completo.

## Total de la iteración

**17/18 puntos.**
