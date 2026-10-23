# Portafolio de prompts — Registro de la semana 6

Este archivo se crea el 23 de octubre de 2026 para registrar la entrega de la semana 7. Las entradas previas P01–P03 permanecen en el [portafolio existente del proyecto](../../proyecto/portafolio_prompts/README.md).

## P04 — Ficha de requerimientos arquitectónicos v1

**Fecha:** 2026-10-23. **Versión:** v1.0. **Estado:** probada con tres entradas y una entrada nueva de robustez.

### Objetivo y alcance

Convertir solicitudes de adaptación de consultorios en viviendas en una ficha de seis campos, señalando información faltante, contradictoria o ambigua. Este es el caso didáctico de Arquitectura utilizado en el laboratorio 7. No es una validación del proyecto Estacionamiento inteligente ni del dominio de Ciberseguridad.

### Plantilla

[Abrir plantilla_prompt_v1.md](../semana07/plantilla_prompt_v1.md).

Variables: `{ROL_LECTOR}` y `{ENTRADA}`. El equipo conserva las instrucciones y el ejemplo y sustituye únicamente esas variables. El lector probado fue “el arquitecto que preparará una propuesta preliminar y necesita información precisa”. La plantilla incluye instrucciones de uso, modelo probado, puntajes y limitaciones.

### Modelo y configuración

- Aplicación: Codex, modelo predeterminado; identificador y versión no registrados.
- Parámetros: configuración predeterminada; valores no registrados.
- Conversaciones independientes para cada entrada y versión.
- El ejemplo few-shot fue elaborado por el asistente por petición expresa del usuario.

### Tabla de iteraciones resumida

Cada criterio suma las tres entradas: máximo 6 puntos por criterio y 18 en total.

| Iteración | Técnica aplicada | C1 | C2 | C3 | Total |
|---|---|---|---|---|---|
| 0 | Línea base (zero-shot) | 6 | 0 | 2 | 8/18 |
| 1 | Rol | 6 | 0 | 3 | 9/18 |
| 2 | Rol + contexto | 6 | 0 | 3 | 9/18 |
| 3 | Rol + contexto + formato | 6 | 6 | 5 | 17/18 |
| 4 | Anterior + ejemplos (few-shot) | 6 | 6 | 5 | 17/18 |
| 5 | Anterior + análisis previo | 6 | 6 | 6 | 18/18 |

Se adopta la iteración 5. La entrada nueva de robustez obtuvo C1 = 2, C2 = 2 y C3 = 2, total 6/6. El promedio original fue 6/6 y la caída fue 0, por lo que no se activa la señal de sobreajuste del laboratorio. No se calculó una tasa de error factual: esta prueba usa una rúbrica de completitud, formato y fidelidad.

### Resultados y evidencia

- [Entradas originales](../semana07/entradas.md).
- [Iteración 0](../semana07/iteracion_0.md), [1](../semana07/iteracion_1.md), [2](../semana07/iteracion_2.md), [3](../semana07/iteracion_3.md), [4](../semana07/iteracion_4.md) y [5](../semana07/iteracion_5.md): prompts y respuestas completos.
- [Resultados resumidos en CSV](../semana07/evaluacion.csv) y [detalle por entrada en CSV](../semana07/evaluacion_detalle.csv).
- [Prueba de robustez completa](../semana07/prueba_robustez.md).
- [Rúbrica original](../semana07/reporte.md) y [análisis de resultados](../semana07/parte_4_analisis.md).

### Evaluación y limitaciones

El mayor salto ocurrió en la iteración 3: +8 puntos, de los cuales 6 corresponden a formato. Ese paso también añadió reglas de incertidumbre, por lo que no se puede aislar el efecto del formato. El ejemplo no aumentó el puntaje. La mejora final de un punto correspondió al uso de una etiqueta exacta.

Los resultados proceden de una ejecución por caso y versión. Cuatro casos no prueban desempeño general. Cambiar el lector o trasladar la plantilla al estacionamiento exige nuevas pruebas. La salida es una ficha preliminar para revisión humana, no una evaluación de viabilidad arquitectónica.

### Historial

| Versión | Fecha | Cambio | Resultado |
|---|---|---|---|
| v1.0 | 2026-10-23 | Conversión del prompt adoptado de la iteración 5 en plantilla con variables. | 18/18 en las tres entradas; 6/6 en robustez para la configuración original. |

### Datos utilizados

Solicitudes sintéticas de consultorios. No se incluyeron fotografías del estacionamiento ni datos de personas reales. Esta entrada conserva el carácter didáctico de los ejemplos y no altera los registros previos del proyecto.
