# Paso 3.3 — Cruce entre matriz y diagrama

**Proyecto:** Estacionamiento inteligente. **Dato seguido:** D3, imágenes del estacionamiento. **Fecha:** 1 de octubre de 2026.

Comparé las once acciones de [matriz_cumplimiento_proyecto](https://docs.google.com/spreadsheets/d/1c448f4oF9WzD8CsUvxamRi3HW4To9D6KzLjwFd4E8oo/edit) con el diagrama anterior y actualicé el archivo en Draw.io. El resultado está en `ciclo_vida_dato_proyecto.drawio` y en su nueva exportación `ciclo_vida_dato_proyecto.png`, que incluye una copia editable.

**Agregué 5 controles nuevos y amplié 6 controles existentes. Las 11 acciones tienen correspondencia en el diagrama; no quedó ninguna sin cobertura documental.**

El conteo se hace por objetivo de control, no por cada frase o aparición en una etapa. Los controles C01, C04, C07 y C10 se mencionan en más de una etapa, pero cada uno se cuenta una sola vez. Las seis ampliaciones no se presentan como seis controles nuevos. A1–A11 son los números de las filas de la matriz y C01–C11 sus controles correspondientes.

| Acción de la matriz | Situación anterior | Control y etapa en el diagrama actualizado | Cambio |
| --- | --- | --- | --- |
| A1. Informar sobre IA, errores y contacto humano en letrero y app | Había aviso de privacidad, pero no aviso específico de IA. | C01: letrero previo en Captura y aviso en la app en Compartición. | Nuevo |
| A2. Documentar consentimiento válido o excepción; participantes informados y evitar transeúntes | Se mencionaban participantes que autorizan la captura. | C02, Captura: documentar la base antes del piloto, informar participantes y evitar captar transeúntes. | Ampliado |
| A3. Aviso visible previo y enlace al completo con finalidad, responsable y ARCO | Solo decía aviso visible. | C03, Captura: momento de presentación, enlace y contenido del aviso. | Ampliado |
| A4. Encuadrar cajones, ocultar rostros y placas; no pedir nombres, teléfonos ni correos | Había encuadre mínimo y ocultamiento antes del modelo. | C04, Captura y Uso: concretar datos excluidos y comprobar el ocultamiento antes del modelo. | Ampliado |
| A5. Registro previo de riesgos y revisión tras cambios | No aparecía un registro de riesgos. | C05, Uso: riesgo, daño, probabilidad, responsable, medida y prueba antes del piloto; revisión de cambios. Es transversal a las seis etapas. | Nuevo |
| A6. Corrección de estados y parada manual; registro sin identificar conductores | No se indicaba intervención del operador. | C06, Uso: permitir corrección y parada, y registrar correcciones sin identidad. | Nuevo |
| A7. Máximo propuesto de 24 h, justificar necesidad, borrar copias y temporales; bloqueo cuando corresponda | Había vencimiento automático, revisión diaria y borrado verificado. | C07, Retención y Eliminación: justificar el plazo, abarcar todas las copias y documentar motivo, plazo y restricciones del bloqueo aplicable. | Ampliado |
| A8. Comparar errores por tipo de cajón e iluminación y corregir diferencias sin datos de discapacidad o identidad | No se describía evaluación de diferencias. | C08, Uso: comparar falsos libres/ocupados y corregir diferencias sin esos datos personales. | Nuevo |
| A9. Contacto para reclamos y, si se amplía el sistema, oposición ARCO y revisión | No había canal ni condición para futuras decisiones sobre personas. | C09, Uso: contacto actual y requisito previo al despliegue de esa eventual ampliación. | Nuevo |
| A10. Cifrado, cuentas individuales, acceso por rol y registro de accesos | Había cifrado, roles y registro; faltaban cuentas individuales. | C10, Almacenamiento y Uso: cuentas individuales, operador autorizado, revisión de permisos y registro de accesos. | Ampliado |
| A11. Bloquear envío de D3, compartir solo estado e ID y revisar proveedor antes de cambiar | Existía bloqueo de salida e información no identificable. | C11, Compartición: incluir nube e IA generativa y revisar proveedor, contrato y reglas antes de un cambio. | Ampliado |

## Por qué son consistentes

La matriz dice qué me comprometo a hacer y el diagrama muestra dónde se realiza y qué rol lo tiene a cargo. Puedo seguir cada acción A1–A11 hasta un control C01–C11 y una o varias etapas. También revisé en sentido inverso: las medidas del diagrama, como excluir imágenes de respaldos, verificar el borrado o revisar el tráfico de salida, desarrollan las acciones de retención, acceso y compartición. No son obligaciones legales adicionales inventadas.

Ambos documentos mantienen los mismos supuestos: D3 se procesa localmente, solo se comparte el ID y estado del cajón, no hay terceros que reciban D3, y las 24 horas son un plazo propuesto que debe justificarse. La acción A9 conserva su condición: el prototipo actual no evalúa personas ni decide su acceso; si cambia esa finalidad, el diseño exige revisar y habilitar los mecanismos correspondientes antes del despliegue.

Esta validación demuestra **consistencia del diseño documentado**. No demuestra por sí sola que el programa ya tenga implementados los controles o que estos funcionen. Antes del piloto debo obtener evidencias: avisos y consentimientos o excepciones documentadas, pruebas de permisos, registro de riesgos, pruebas de parada y corrección, comparación de errores, prueba de ausencia de envíos externos y registros de eliminación.

## Qué pasaría si los documentos no coincidieran

Si entregara controles en el diagrama que la matriz no exige, no serían incorrectos automáticamente: podrían ser medidas voluntarias o una forma concreta de cumplir una acción más general. Tendría que relacionarlos con un riesgo y explicar su utilidad; si responden a un objetivo nuevo, añadiría una fila a la matriz. Sin esa explicación habría medidas sin justificación clara y sería difícil revisar su necesidad, costo y responsable.

Si la matriz tuviera acciones que el diagrama no contempla, estaría prometiendo medidas sin indicar en qué etapa ni bajo qué responsabilidad se aplican. Eso dejaría un vacío en el diseño, dificultaría comprobar el cumplimiento y podría dejar expuestas a las personas. Por eso añadí los cinco controles ausentes y precisé los otros seis antes de volver a exportar.

## Verificación realizada

- Se leyó la matriz vigente completa (once acciones).
- Se comparó con la versión anterior del diagrama y se conservaron las seis etapas y el recorrido rojo de D3.
- Se verificó la presencia de C01–C11 en el archivo actualizado y su correspondencia con A1–A11.
- Se aplicó la edición en Draw.io y se exportó de nuevo a PNG con la opción de incluir el diagrama editable activada.
- Se revisó visualmente la imagen para comprobar que los textos, etapas y flechas no se superponen ni quedan cortados.
