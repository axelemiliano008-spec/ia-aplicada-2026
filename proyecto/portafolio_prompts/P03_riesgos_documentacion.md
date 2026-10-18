# P03 — Riesgos al documentar el estacionamiento con IA

## Objetivo

Preparar un registro inicial de riesgos del uso de IA generativa para redactar documentación de Estacionamiento inteligente, distinguiendo hechos, ejemplos ficticios y medidas propuestas.

## Modelo y configuración

- Modelo: Gemma 4 26B A4B IT (`gemma-4-26b-a4b-it`), Google AI Studio.
- Temperatura: 0.
- Fecha de ejecución: 2026-10-18.
- Thinking level: High. Grounding with Google Search: activado y bloqueado por la interfaz. Otras opciones: valores por defecto; no se verificaron parámetros ocultos.
- Conversación de ejecución: https://aistudio.google.com/prompts/1MMu5AoA446H4lCg-v8DWGmTiMjKj-Aqa (puede requerir la cuenta del propietario).

## Prompt (versión v1)

```text
Actúa como asistente de documentación del proyecto Estacionamiento inteligente. El prototipo estima cajones libres u ocupados con procesamiento local y muestra ID y disponibilidad en una app. Su política prohíbe subir imágenes reales del estacionamiento a servicios externos, incluso difuminadas. Solo usamos descripciones públicas y ejemplos sintéticos. Redacta en español un registro inicial de tres riesgos del uso de IA generativa para preparar documentación del proyecto: información inventada, instrucciones maliciosas dentro de documentos y exposición de información sensible. Para cada riesgo incluye: una afirmación factual verificable, su fuente primaria con URL, un ejemplo totalmente ficticio del proyecto y una medida propuesta. Consulta NIST AI 600-1 y OWASP Top 10 for LLM Applications 2025; no inventes citas ni porcentajes. Distingue hechos documentados de recomendaciones. Máximo 350 palabras. No afirmes que los controles ya están implementados.
```

## Resultado obtenido

Respuesta completa, conservada como texto visible sin editar su contenido. Los encabezados y viñetas de la interfaz se presentan como texto plano en este bloque.

```text
Registro de Riesgos de IA Generativa: Proyecto Estacionamiento Inteligente

1. Alucinaciones (Información inventada)

Hecho: Los modelos de lenguaje pueden generar contenido que parece coherente pero es factualmente incorrecto o inexistente.

Fuente: NIST AI 600-1 (https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf).

Ejemplo: La IA redacta que el procesador local utiliza protocolo Zigbee para la comunicación, cuando el prototipo utiliza LoRaWAN.

Recomendación: Implementar un proceso de validación humana obligatoria para toda documentación técnica generada.

2. Inyección de instrucciones (Prompt Injection)

Hecho: Los modelos pueden ser manipulados mediante instrucciones maliciosas ocultas en los datos de entrada o documentos procesados.

Fuente: OWASP Top 10 for LLM Applications (https://owasp.org/www-project-top-10-for-large-language-model-applications/).

Ejemplo: Un archivo de descripción de cajones sintéticos contiene texto oculto que ordena a la IA ignorar la política de no subir imágenes reales.

Recomendación: Aplicar técnicas de sanitización de entradas y delimitación estricta de las instrucciones del sistema.

3. Exposición de información sensible

Hecho: Existe el riesgo de que el modelo revele datos confidenciales presentes en el contexto o en los datos de entrenamiento.

Fuente: OWASP Top 10 for LLM Applications (https://owasp.org/www-project-top-10-for-large-language-model-applications/).

Ejemplo: La IA incluye accidentalmente una dirección IP real de la red local en un manual de usuario generado a partir de notas de desarrollo.

Recomendación: Utilizar exclusivamente datos sintéticos y realizar un escaneo de información sensible (PII) antes de procesar cualquier texto con la IA.
```

## Verificación

Revisión realizada el 18 de octubre de 2026. Se contrastaron las tres afirmaciones etiquetadas como «Hecho»; los ejemplos son ficticios y las recomendaciones no prueban que existan controles implementados.

| **Afirmación verificable** | **Fuente primaria** | **Clasificación** |
| -------------------------- | ------------------- | ----------------- |
| Los modelos de lenguaje pueden generar contenido que parece coherente pero es factualmente incorrecto o inexistente. | [NIST AI 600-1](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf), sección 2.2 «Confabulation», p. 6 impresa (página 10 del PDF): describe contenido falso o erróneo presentado con confianza. | Correcta |
| Los modelos pueden ser manipulados mediante instrucciones maliciosas ocultas en los datos de entrada o documentos procesados. | [OWASP LLM01:2025](https://genai.owasp.org/llmrisk/llm01-prompt-injection/), «Indirect Prompt Injections»: archivos y otras fuentes externas pueden alterar el comportamiento del modelo. | Correcta |
| Existe el riesgo de que el modelo revele datos confidenciales presentes en el contexto o en los datos de entrenamiento. | [OWASP LLM02:2025](https://genai.owasp.org/llmrisk/llm022025-sensitive-information-disclosure/), descripción y escenario 3 «Data Leak via Training Data»: documenta exposición en salidas y por inclusión negligente de datos en entrenamiento. | Correcta |

Tasa de error de esta respuesta: **0 % en las tres afirmaciones factuales evaluadas**.

Cálculo: (0 parcialmente correctas + 0 alucinadas) / 3 × 100 = 0 %. Esto no mide la calidad de todas las recomendaciones ni demuestra ausencia de errores en futuras respuestas.

## Evaluación

- Qué funcionó: presentó los tres riesgos solicitados; separó hechos, fuentes, ejemplos y recomendaciones. Los tres hechos coincidieron con fuentes primarias. No inventó estadísticas ni afirmó que los controles estuvieran implementados.
- Qué falló: citó la página general de OWASP y omitió identificadores y secciones de la edición 2025; la verificación añadió enlaces directos. El ejemplo LoRaWAN/Zigbee es ficticio por el contexto del prompt, pero no lo rotuló explícitamente: no acredita la tecnología real del prototipo. La sanitización y delimitación propuestas no garantizan evitar inyecciones; OWASP indica que no está claro que exista una prevención infalible. Tampoco una IP implica automáticamente identificación de una persona: su tratamiento depende del contexto.
- Qué cambiaré en la siguiente versión: exigir enlaces directos a LLM01:2025 y LLM02:2025 y sección de NIST, rotular cada ejemplo «ficticio» y pedir responsable, prueba y limitación de cada medida. Es una mejora propuesta, todavía no ejecutada.

## Historial de versiones

| **Versión** | **Fecha** | **Cambio realizado** | **Resultado del cambio** |
| ----------- | --------- | -------------------- | ------------------------ |
| v1 | 2026-10-18 | Primera ejecución con el modelo elegido en la semana 5 y temperatura 0. | Tres riesgos; tres hechos verificados como correctos. Enlaces y ejemplos requieren mayor precisión. |

## Datos usados

Confirmo que este prompt cumple la sección 5 de la política de datos del proyecto: **sí respecto del contenido enviado**, porque usa la descripción pública del proyecto y pide ejemplos ficticios. No se enviaron fotografías, placas, rostros, contactos, direcciones IP reales, credenciales ni registros identificables.

Referencia: [política real de la semana 4, sección 5](../../laboratorios/semana04/politica_datos_proyecto.md#5-manejo-de-datos-con-herramientas-de-ia). Esta comprobación del contenido no acredita una autorización administrativa del encargado de datos que no esté documentada. No se incorporarán datos reales al servicio externo.
