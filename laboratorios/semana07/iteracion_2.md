# Iteración 2 — Adición de contexto

Fecha: 23 de octubre de 2026. Cada entrada se ejecutó en una conversación nueva. Se conservaron las entradas y la rúbrica de la Parte 1. Se utilizó el modelo predeterminado de la aplicación, sin cambiarlo explícitamente; su identificador y parámetros no se registraron.

Cambio respecto a la iteración anterior: se conservó el rol y se añadió un bloque de contexto que define alcance y seis campos.

## Entrada 1

Conversación: `01a16778-ca10-7641-b23e-be1df2c42efe`

### Prompt completo enviado

```text
Eres arquitecto encargado de recopilar requerimientos para adaptar consultorios en viviendas. Tu lector es el arquitecto que preparará una propuesta preliminar y necesita información precisa.

Contexto: este texto proviene de un formulario que llenan propietarios sin conocimientos técnicos. El sistema organiza solicitudes de adaptación de consultorios en viviendas; pueden llegar datos completos, incompletos, contradictorios o ambiguos. La ficha comprende seis campos: uso (incluida la especialidad del consultorio), ubicación, superficie disponible, espacios solicitados, iluminación y presupuesto. El alcance es registrar los requisitos del propietario para una revisión preliminar; no desarrollar un diseño, repartir superficies, estimar costos ni evaluar cumplimiento normativo.

Haz la ficha de requerimientos de este espacio:

Quiero adaptar un consultorio de nutrición en la planta baja de mi casa. Dispongo de un área rectangular de 30 m². Necesito una sala de espera para dos personas, un espacio privado de consulta y un baño. Quiero luz natural en la sala de espera y en el espacio de consulta. Mi presupuesto total para la adaptación es de $250,000 MXN.
```

### Respuesta completa sin corregir

## Ficha de requerimientos

- **Uso:** Consultorio de nutrición.
- **Ubicación:** Planta baja de la vivienda.
- **Superficie disponible:** 30 m², área rectangular. No se indican sus dimensiones.
- **Espacios solicitados:** Sala de espera para dos personas, espacio privado de consulta y baño.
- **Iluminación:** Luz natural en la sala de espera y en el espacio de consulta.
- **Presupuesto:** $250,000 MXN para la adaptación.

### Evaluación

| C1 | C2 | C3 | Total |
|---|---|---|---|
| 2 | 0 | 1 | 3/6 |

Enumera los seis campos sin inventar datos. No presenta tabla ni sección de aclaraciones. Falta indicar ‘No se requieren aclaraciones’.

## Entrada 2

Conversación: `01a16778-d445-7dd1-9640-ae6bf9d32c58`

### Prompt completo enviado

```text
Eres arquitecto encargado de recopilar requerimientos para adaptar consultorios en viviendas. Tu lector es el arquitecto que preparará una propuesta preliminar y necesita información precisa.

Contexto: este texto proviene de un formulario que llenan propietarios sin conocimientos técnicos. El sistema organiza solicitudes de adaptación de consultorios en viviendas; pueden llegar datos completos, incompletos, contradictorios o ambiguos. La ficha comprende seis campos: uso (incluida la especialidad del consultorio), ubicación, superficie disponible, espacios solicitados, iluminación y presupuesto. El alcance es registrar los requisitos del propietario para una revisión preliminar; no desarrollar un diseño, repartir superficies, estimar costos ni evaluar cumplimiento normativo.

Haz la ficha de requerimientos de este espacio:

Quiero un consultorio en la planta baja de mi casa. Necesito un espacio privado para atender a una persona a la vez y una pequeña sala de espera. Quiero luz natural en ambos espacios. No sé cuántos metros tengo disponibles y todavía no he definido mi presupuesto.
```

### Respuesta completa sin corregir

## Ficha de requerimientos

| Campo | Requerimiento registrado |
|---|---|
| **Uso** | Consultorio; la especialidad no está especificada. Se atenderá a una persona a la vez. |
| **Ubicación** | En la planta baja de la vivienda. No se indica el área exacta dentro de esa planta. |
| **Superficie disponible** | No informada; la propietaria no sabe cuántos metros están disponibles. |
| **Espacios solicitados** | Un espacio privado para atender y una sala de espera pequeña. |
| **Iluminación** | Se solicita luz natural en el espacio de atención y en la sala de espera. |
| **Presupuesto** | Aún no definido. |

### Evaluación

| C1 | C2 | C3 | Total |
|---|---|---|---|
| 2 | 0 | 1 | 3/6 |

Incluye seis filas, pero la segunda columna se llama ‘Requerimiento registrado’. Identifica los tres datos faltantes sin usar las marcas exactas ni formular preguntas.

## Entrada 3

Conversación: `01a16778-dc82-78a2-8b45-003adcd5d734`

### Prompt completo enviado

```text
Eres arquitecto encargado de recopilar requerimientos para adaptar consultorios en viviendas. Tu lector es el arquitecto que preparará una propuesta preliminar y necesita información precisa.

Contexto: este texto proviene de un formulario que llenan propietarios sin conocimientos técnicos. El sistema organiza solicitudes de adaptación de consultorios en viviendas; pueden llegar datos completos, incompletos, contradictorios o ambiguos. La ficha comprende seis campos: uso (incluida la especialidad del consultorio), ubicación, superficie disponible, espacios solicitados, iluminación y presupuesto. El alcance es registrar los requisitos del propietario para una revisión preliminar; no desarrollar un diseño, repartir superficies, estimar costos ni evaluar cumplimiento normativo.

Haz la ficha de requerimientos de este espacio:

Quiero un consultorio de psicología en la planta baja de mi casa, con sala de espera, espacio privado de consulta y baño. El área disponible mide 20 m²; en esa misma área hay un rectángulo libre de 5 por 6 metros, sin obstáculos. Quiero luz natural en la sala de espera, pero también digo que no debe entrar luz natural en ningún espacio del consultorio. Mi presupuesto máximo total es de $180,000 MXN, aunque puedo gastar hasta $230,000 MXN en total sin cambiar el alcance. Que quede amplio.
```

### Respuesta completa sin corregir

## Ficha de requerimientos

| Campo | Información registrada |
|---|---|
| **Uso** | Consultorio de psicología. |
| **Ubicación** | Planta baja de la vivienda. |
| **Superficie disponible** | Se indican **20 m²** disponibles y, en esa misma área, un rectángulo libre de **5 × 6 m** sin obstáculos. Las medidas del rectángulo corresponden a 30 m², por lo que la superficie disponible requiere aclaración. |
| **Espacios solicitados** | Sala de espera, espacio privado de consulta y baño. El propietario solicita que el conjunto “quede amplio”; no especifica qué significa en términos concretos. |
| **Iluminación** | Se solicita luz natural en la sala de espera y también se indica que no debe entrar luz natural en ningún espacio del consultorio. Requisito contradictorio; requiere aclaración. |
| **Presupuesto** | Se señala un máximo total de **$180,000 MXN** y también que se podrían gastar hasta **$230,000 MXN** en total sin cambiar el alcance. El límite aplicable requiere aclaración. |

**Pendientes para la revisión preliminar:** confirmar la superficie disponible, el requisito de iluminación natural y el presupuesto máximo aplicable.

### Evaluación

| C1 | C2 | C3 | Total |
|---|---|---|---|
| 2 | 0 | 1 | 3/6 |

Registra las contradicciones y la ambigüedad. Usa la columna ‘Información registrada’. No aplica las etiquetas exactas ni pregunta por cada punto pendiente.

## Total de la iteración

**9/18 puntos.**
