# Semana 3 — Limpieza y transformación de registros de acceso

Dataset ficticio de laboratorio. Exportación de valores desde Google Sheets: 40 registros crudos y 37 registros en la versión seudonimizada y generalizada.

## Tabla de transformaciones

| Columna original | Qué le hice | Técnica | Por qué |
|---|---|---|---|
| id | Conservar | Mantener el identificador del registro. | Distingue accesos y permite rastrear incidencias. Puede vincularse con el original; conserva riesgo residual. |
| nombre | Seudonimizar | Sustituir por id_persona, con códigos estables P001–P036, UNIQUE y BUSCARV. | Permite relacionar visitas sin mostrar nombres. La llave permanece privada y no se exporta. |
| correo | Enmascarar y después eliminar | Extraer la primera letra, concatenar tres asteriscos y conservar el dominio; retirar la columna tras verificarla. | No aporta al análisis y una dirección enmascarada no permite contactar a la persona. |
| telefono | Eliminar | Retirar completamente la columna. | Es un identificador directo innecesario para analizar patrones de acceso. |
| fecha_acceso | Generalizar | Sustituir por semana con WEEKNUM(fecha,2), comenzando en lunes. | Permite analizar tendencias semanales sin revelar el día exacto. Los faltantes siguen vacíos. |
| hora_entrada | Generalizar | Sustituir por franja: Madrugada (00:00–05:59), Mañana (06:00–11:59), Tarde (12:00–17:59) o Noche (18:00–23:59). | Reduce precisión temporal y permite reconocer franjas inusuales. |
| area | Conservar | Mantener el texto normalizado durante la limpieza. | Es necesaria para analizar dónde ocurren los accesos; combinada con otros datos puede facilitar la identificación. |
| empresa | Generalizar | Sustituir por tipo_empresa: Constructora, Diseño o Soporte TI. | Conserva el giro sin mostrar el nombre de la empresa. Los faltantes siguen vacíos. |
| motivo | Conservar | Mantener el texto normalizado durante la limpieza. | Ayuda a interpretar el acceso; la normalización de capitalización no restituyó la tilde faltante. |

Se conservan fecha_valida y hora_laboral como indicadores calculados antes de la generalización. El CSV contiene valores, no fórmulas ni enlaces a la llave privada.

## Comparación contra la clave de errores

Este recuento corresponde al cierre de la Parte 2. Incluye los errores de las diez filas iniciales y los añadidos. Se considera detectado lo corregido o identificado en el reporte o en incidencias; detectar no siempre significa corregir.

| Tipo de error | Introducidos | Detectados por la limpieza | Faltaron | Por qué faltaron / observación |
|---|---:|---:|---:|---|
| Fila duplicada exacta, incluido id | 2 | 2 | 0 | Se eliminaron dos copias exactas. |
| Duplicado que solo difiere en id | 1 | 1 | 0 | Se compararon todas las columnas excepto id. |
| Fecha en formato dd/mm/aaaa | 4 | 4 | 0 | Se reconocieron y convirtieron a fecha. |
| Fecha inválida | 2 | 2 | 0 | Se dejaron vacías y se documentaron. |
| Correo incompleto o con mayúsculas | 5 | 5 | 0 | Se normalizaron mayúsculas; los no corregibles se dejaron vacíos. |
| Teléfono con espacios o corto | 4 | 4 | 0 | Se quitaron espacios; el número corto se dejó vacío. |
| Área con distinta capitalización | 4 | 4 | 0 | Se normalizó con fórmula. |
| Celda vacía en empresa o teléfono | 5 | 5 | 0 | Se documentaron; no se inventaron valores. |
| Hora fuera de horario laboral | 5 | 5 | 0 | Se conservaron como accesos inusuales, no como errores de captura. |
| Capitalización y acento en motivo | 1 | 1 | 0 | Se detectó y documentó; la tilde sigue pendiente. |
| Nombre en minúsculas | 1 | 0 | 1 | En la Parte 2 no se normalizó ni validó nombre (id 8). |
| Hora sin cero inicial | 1 | 0 | 1 | Se validó el horario, no el formato de dos dígitos (id 2). |
| **Total** | **35** | **33** | **2** | |

Los vacíos de empresa se documentaron en incidencias aunque las cuatro validaciones no los muestran en el filtro. Posteriormente, en la seudonimización, se normalizaron los nombres para asignar códigos estables; esto no modifica retrospectivamente el resultado de la Parte 2.

Si el procedimiento dejó pasar errores conocidos, no basta con confiar en que una hoja sin alertas está limpia. Es necesario revisar qué comprueba cada regla y qué errores quedan fuera de ella.

## Verificación y riesgo residual

- La versión transformada tiene 37 accesos y 36 códigos de persona.
- Se encontraron 21 combinaciones de tipo_empresa, area y franja; 10 aparecen una sola vez.
- Una combinación de dos accesos pertenece a una sola persona (P003). El número de filas no equivale al número de personas.
- Los códigos estables, el id original y los datos indirectos mantienen posibilidades de vinculación. El nombre accesos_anonimizado no implica anonimato completo.
- La generalización temporal hace que visitas legítimas distintas puedan parecer iguales. La eliminación de duplicados se realizó antes de generalizar.

## Archivos y alcance

- accesos_crudo.csv: datos ficticios con errores intencionales; conserva identificadores directos.
- accesos_anonimizado.csv: valores seudonimizados y generalizados, sin columnas de nombre, correo ni teléfono.
- transformaciones.md: documentación de transformaciones, errores y limitaciones.

No se incluyen tabla_seudonimos, accesos_limpio, clave_errores ni el libro completo. El usuario autorizó expresamente publicar accesos_crudo.csv como excepción a la prohibición de archivos con nombres, por tratarse del dataset ficticio solicitado en el laboratorio. El CSV crudo no es un archivo anonimizado.

Al publicar ambas versiones en el mismo repositorio, el id conservado permite vincularlas. Esa publicación conjunta solo sirve como demostración con datos ficticios; no preserva la confidencialidad de las identidades del conjunto.
