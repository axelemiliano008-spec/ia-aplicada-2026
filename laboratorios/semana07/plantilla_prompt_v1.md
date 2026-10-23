# Plantilla: ficha de requerimientos arquitectónicos v1

Variables: {ROL_LECTOR}, {ENTRADA}

Versión: 1.0. Fecha: 2026-10-23. Basada en el prompt adoptado de la iteración 5.

## Plantilla

Copiar únicamente el bloque siguiente, después de sustituir las variables:

```text
Eres arquitecto encargado de recopilar requerimientos para adaptar consultorios en viviendas. Tu lector es {ROL_LECTOR}.

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

{ENTRADA}
```

## Instrucciones de uso

### Qué poner en cada variable

| Variable | Contenido | Valor utilizado durante las pruebas |
|---|---|---|
| {ROL_LECTOR} | Descripción de la persona que utilizará la ficha y de su necesidad de información. No añadir un punto final dentro del valor. | el arquitecto que preparará una propuesta preliminar y necesita información precisa |
| {ENTRADA} | Solicitud completa del propietario, conservando cifras, unidades, negaciones, datos faltantes y contradicciones. | Cada una de las tres entradas de evaluación y, después, la entrada 4 de robustez. |

Los datos de uso, ubicación, superficie, espacios, iluminación y presupuesto cambian dentro de {ENTRADA}; no se modifican en otras partes del prompt. El rol de arquitecto, el dominio de consultorios en viviendas, las seis filas y el ejemplo permanecen fijos. No sustituir los datos del ejemplo por los del caso ni enviar el ejemplo como entrada de evaluación.

1. Abrir una conversación nueva para cada caso.
2. Copiar el bloque de la plantilla y sustituir las dos variables, quitando las llaves.
3. Verificar que no quede ninguna variable pendiente y enviar el prompt completo.
4. Revisar los seis campos, las etiquetas y las preguntas antes de utilizar la ficha. La sección Análisis se acepta porque el destinatario es una persona.
5. Si se cambia el lector, el dominio, los campos o las instrucciones, validar la nueva variante con casos independientes y registrar su versión.

### Modelo probado

Se utilizó el modelo predeterminado de Codex en conversaciones nuevas. No se registró un identificador verificable del modelo, su versión ni sus parámetros de generación. Por ello, no se atribuye la prueba a un modelo específico y la reproducibilidad exacta queda limitada. En futuras ejecuciones debe anotarse el nombre que muestre la aplicación y sus ajustes disponibles.

### Puntaje obtenido

| Evaluación del prompt de la iteración 5 | C1 | C2 | C3 | Total |
|---|---|---|---|---|
| Tres entradas originales, suma | 6/6 | 6/6 | 6/6 | 18/18 |
| Entrada nueva de robustez | 2/2 | 2/2 | 2/2 | 6/6 |

Promedio original: 6/6 por entrada. Caída en la prueba de robustez: 0 puntos. Los resultados corresponden al lector indicado y al dominio probado. Sustituir ese valor por otro lector no conserva automáticamente la validación.

### Limitaciones conocidas

- Se hizo una sola ejecución por entrada y versión. Cuatro casos no garantizan el desempeño general ni descartan sobreajuste.
- La cuarta entrada fue completa: no amplía por sí sola la validación de todos los tipos de datos faltantes o contradicciones.
- La rúbrica exige etiquetas exactas. En las iteraciones 3 y 4 se perdió un punto por “especialidad no especificada”, aunque el dato faltante fue reconocido correctamente.
- La sección Análisis puede repetir información explícita; no garantiza mayor precisión. Es un resumen de evidencia, no un razonamiento detallado.
- La ficha registra requisitos. No demuestra viabilidad arquitectónica, cumplimiento normativo ni costos reales.
- La instrucción inicial de salida se amplía explícitamente al final para admitir Análisis. Se conserva esta redacción porque fue la versión probada.
- El ejemplo few-shot fue elaborado por el asistente por petición expresa del usuario. No se presenta como autoría independiente del estudiante. No produjo un aumento de puntaje en la iteración 4.

### Referencias de la entrega

- [Entradas originales](entradas.md).
- [Prueba y respuestas de la iteración 5](iteracion_5.md).
- [Tabla de resultados exportada](evaluacion.csv).
- [Puntajes por entrada y robustez](evaluacion_detalle.csv).
