# Prueba de robustez — Entrada 4

Conversación: `01a16787-51d4-7750-be9d-75217a4e426a`

Una ejecución con el prompt de la iteración 5, sin modificarlo. Fecha de referencia del laboratorio: 23 de octubre de 2026.

## Prompt completo enviado

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

Como única ampliación del formato anterior, antes de la tabla escribe una sección titulada "Análisis" con exactamente tres viñetas: información explícita en el texto, qué se puede inferir con seguridad y qué no se puede determinar. Presenta un resumen breve basado en los datos, sin desarrollar un razonamiento paso a paso. Después escribe la tabla y la sección Preguntas de aclaración ya indicadas.

Haz la ficha de requerimientos de este espacio:

Quiero adaptar un consultorio de fisioterapia en un anexo al fondo de mi casa, al nivel del jardín. El área interior es un rectángulo de 4 por 7 metros. Necesito una sala de espera para tres personas, un espacio privado de atención y un almacén cerrado. No quiero construir un baño nuevo: los pacientes usarán el baño existente de la casa. Quiero luz natural en el espacio de atención e iluminación artificial en la sala de espera y el almacén. Dispongo de $180,000 MXN para la obra y otros $30,000 MXN para mobiliario; son dos partidas del mismo presupuesto de adaptación.
```

## Respuesta completa sin corregir

## Análisis

- Información explícita: consultorio de fisioterapia en un anexo al fondo de la casa, al nivel del jardín; área interior rectangular de 4 × 7 m; sala de espera para tres personas, espacio privado de atención y almacén cerrado; uso del baño existente; luz natural en atención e iluminación artificial en espera y almacén; $180,000 MXN para obra y $30,000 MXN para mobiliario.
- Se puede inferir con seguridad: la superficie interior es de 28 m² y el presupuesto total de adaptación es de $210,000 MXN, dividido entre obra y mobiliario.
- No se puede determinar: cómo se distribuirán los espacios ni las dimensiones individuales de cada uno.

| Campo | Requisito |
|---|---|
| Uso | Consultorio de fisioterapia. |
| Ubicación | Anexo al fondo de la casa, al nivel del jardín. |
| Superficie disponible | Área interior rectangular de 4 × 7 m (28 m²). |
| Espacios solicitados | Sala de espera para tres personas, espacio privado de atención y almacén cerrado. Los pacientes usarán el baño existente de la casa; no se solicita construir uno nuevo. |
| Iluminación | Luz natural en el espacio de atención e iluminación artificial en la sala de espera y el almacén. |
| Presupuesto | $210,000 MXN en total: $180,000 MXN para la obra y $30,000 MXN para mobiliario. |

## Preguntas de aclaración

No se requieren aclaraciones

## Evaluación

| C1 | C2 | C3 | Total |
|---|---|---|---|
| 2 | 2 | 2 | 6/6 |

C1: los seis campos están presentes. C2: cumple la tabla y las aclaraciones; se acepta el análisis previo como se decidió antes de la iteración 5. C3: conserva los requisitos, identifica la multiplicación 4 × 7 = 28 m² y la suma $180,000 + $30,000 = $210,000 como inferencias verificables; no inventa valores. No hay datos pendientes para los seis campos, por lo que corresponde indicar que no se requieren aclaraciones. Las dimensiones individuales de los espacios quedan fuera del alcance de la ficha.

Promedio original: (6 + 6 + 6) / 3 = 6. Puntaje nuevo: 6. Caída: 0. No supera el umbral de más de 2 puntos y no activa la señal de sobreajuste del laboratorio. Una sola entrada nueva no permite descartar sobreajuste en general.

