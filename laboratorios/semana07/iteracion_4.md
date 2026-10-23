# Iteración 4 — Ejemplo de referencia (few-shot)

Fecha: 23 de octubre de 2026. Tres conversaciones nuevas, una por entrada. Se conservaron las tres entradas originales, el rol, el contexto y el formato anterior. Modelo predeterminado de la aplicación, sin cambio explícito; su identificador y parámetros no se registraron.

El ejemplo fue elaborado por el asistente por petición expresa del usuario. Esto se aparta de la instrucción original de que el estudiante lo escribiera sin ayuda del modelo; no se presenta como autoría del estudiante. El ejemplo trata un consultorio de terapia de lenguaje en segundo piso, de 42 m², con dos salas individuales, archivo cerrado e iluminación artificial. No se evaluó como entrada.

## Entrada 1

Conversación: `01a1677e-c930-7e70-9cb5-de969372332f`

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

Ejemplo de referencia (solo muestra cómo responder; no es el caso que debes resolver):

Entrada de ejemplo:
"Quiero adaptar un consultorio de terapia de lenguaje en el segundo piso de mi vivienda. El área disponible es de 42 m². Necesito dos salas individuales de atención y un archivo cerrado. Quiero iluminación artificial en las tres áreas. Todavía no he decidido el presupuesto."

Salida correcta del ejemplo:
| Campo | Requisito |
|---|---|
| Uso | Consultorio de terapia de lenguaje. |
| Ubicación | Segundo piso de la vivienda. |
| Superficie disponible | 42 m². |
| Espacios solicitados | Dos salas individuales de atención y un archivo cerrado. |
| Iluminación | Iluminación artificial en las tres áreas. |
| Presupuesto | No especificado. |

## Preguntas de aclaración

1. ¿Qué presupuesto total tiene previsto para la adaptación?

Fin del ejemplo. Responde únicamente al caso que aparece a continuación, utilizando sus propios datos.

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

No se requieren aclaraciones

### Evaluación

| C1 | C2 | C3 | Total |
|---|---|---|---|
| 2 | 2 | 2 | 6/6 |

Conserva los seis campos y todos los datos, cumple tabla y aclaraciones. No incorpora valores del ejemplo.

## Entrada 2

Conversación: `01a1677e-d4f4-71d2-b5e9-659341a953ab`

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

Ejemplo de referencia (solo muestra cómo responder; no es el caso que debes resolver):

Entrada de ejemplo:
"Quiero adaptar un consultorio de terapia de lenguaje en el segundo piso de mi vivienda. El área disponible es de 42 m². Necesito dos salas individuales de atención y un archivo cerrado. Quiero iluminación artificial en las tres áreas. Todavía no he decidido el presupuesto."

Salida correcta del ejemplo:
| Campo | Requisito |
|---|---|
| Uso | Consultorio de terapia de lenguaje. |
| Ubicación | Segundo piso de la vivienda. |
| Superficie disponible | 42 m². |
| Espacios solicitados | Dos salas individuales de atención y un archivo cerrado. |
| Iluminación | Iluminación artificial en las tres áreas. |
| Presupuesto | No especificado. |

## Preguntas de aclaración

1. ¿Qué presupuesto total tiene previsto para la adaptación?

Fin del ejemplo. Responde únicamente al caso que aparece a continuación, utilizando sus propios datos.

Haz la ficha de requerimientos de este espacio:

Quiero un consultorio en la planta baja de mi casa. Necesito un espacio privado para atender a una persona a la vez y una pequeña sala de espera. Quiero luz natural en ambos espacios. No sé cuántos metros tengo disponibles y todavía no he definido mi presupuesto.
```

### Respuesta completa sin corregir

| Campo | Requisito |
|---|---|
| Uso | Consultorio; especialidad no especificada. |
| Ubicación | Planta baja de la casa. |
| Superficie disponible | No especificado. |
| Espacios solicitados | Un espacio privado para atender a una persona a la vez y una sala de espera (Ambiguo: “pequeña”). |
| Iluminación | Luz natural en ambos espacios. |
| Presupuesto | No especificado. |

## Preguntas de aclaración

1. ¿Qué especialidad tendrá el consultorio?
2. ¿Cuántos metros cuadrados están disponibles?
3. ¿Qué tamaño o capacidad espera para la sala de espera?
4. ¿Qué presupuesto total tiene previsto para la adaptación?

### Evaluación

| C1 | C2 | C3 | Total |
|---|---|---|---|
| 2 | 2 | 1 | 5/6 |

Reconoce especialidad, superficie y presupuesto faltantes y pregunta por ellos. Persiste ‘especialidad no especificada’ en vez de la etiqueta exacta ‘No especificado’. No inventa datos ni copia valores del ejemplo.

## Entrada 3

Conversación: `01a1677e-e090-7322-905d-7f204a58f87d`

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

Ejemplo de referencia (solo muestra cómo responder; no es el caso que debes resolver):

Entrada de ejemplo:
"Quiero adaptar un consultorio de terapia de lenguaje en el segundo piso de mi vivienda. El área disponible es de 42 m². Necesito dos salas individuales de atención y un archivo cerrado. Quiero iluminación artificial en las tres áreas. Todavía no he decidido el presupuesto."

Salida correcta del ejemplo:
| Campo | Requisito |
|---|---|
| Uso | Consultorio de terapia de lenguaje. |
| Ubicación | Segundo piso de la vivienda. |
| Superficie disponible | 42 m². |
| Espacios solicitados | Dos salas individuales de atención y un archivo cerrado. |
| Iluminación | Iluminación artificial en las tres áreas. |
| Presupuesto | No especificado. |

## Preguntas de aclaración

1. ¿Qué presupuesto total tiene previsto para la adaptación?

Fin del ejemplo. Responde únicamente al caso que aparece a continuación, utilizando sus propios datos.

Haz la ficha de requerimientos de este espacio:

Quiero un consultorio de psicología en la planta baja de mi casa, con sala de espera, espacio privado de consulta y baño. El área disponible mide 20 m²; en esa misma área hay un rectángulo libre de 5 por 6 metros, sin obstáculos. Quiero luz natural en la sala de espera, pero también digo que no debe entrar luz natural en ningún espacio del consultorio. Mi presupuesto máximo total es de $180,000 MXN, aunque puedo gastar hasta $230,000 MXN en total sin cambiar el alcance. Que quede amplio.
```

### Respuesta completa sin corregir

| Campo | Requisito |
|---|---|
| Uso | Consultorio de psicología. |
| Ubicación | Planta baja de la casa. |
| Superficie disponible | **Contradicción:** el área disponible mide 20 m²; también se indica que en esa misma área hay un rectángulo libre de 5 × 6 m (30 m²), sin obstáculos. |
| Espacios solicitados | Sala de espera, espacio privado de consulta y baño. **Ambiguo:** “Que quede amplio”. |
| Iluminación | **Contradicción:** se solicita luz natural en la sala de espera y también se indica que no debe entrar luz natural en ningún espacio del consultorio. |
| Presupuesto | **Contradicción:** presupuesto máximo total de $180,000 MXN; también se indica que puede gastar hasta $230,000 MXN en total sin cambiar el alcance. |

## Preguntas de aclaración

1. ¿Qué superficie disponible debe considerarse: 20 m² o el rectángulo libre de 5 × 6 m (30 m²)?
2. ¿Qué significa para usted que el espacio quede “amplio”?
3. ¿Debe entrar luz natural en la sala de espera o no debe entrar en ningún espacio?
4. ¿Cuál es el presupuesto máximo total: $180,000 MXN o $230,000 MXN?

### Evaluación

| C1 | C2 | C3 | Total |
|---|---|---|---|
| 2 | 2 | 2 | 6/6 |

Conserva las versiones contradictorias, aplica las etiquetas y pregunta por los tres conflictos y por ‘amplio’. No copia datos del ejemplo.

## Total

**17/18 puntos.**
