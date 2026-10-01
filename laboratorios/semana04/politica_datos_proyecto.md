# Política de datos del proyecto Estacionamiento inteligente

## 1. Alcance

- D1, espacios libres u ocupados: **no personal**; D2, ubicación de los cajones: **no personal**, sin vincularlos con personas.
- D3, imágenes del estacionamiento: **personal** cuando aparecen rostros, placas u otros elementos identificables; es el dato de mayor riesgo.
- D4, cantidades de entradas y salidas por hora: **no personal**, únicamente conteos agregados.
- D5, historial de ocupación: **no personal**, sin identificar ni seguir a personas o vehículos.
- D6, tipo de espacio: **no personal**; indica general, accesible o moto, sin atribuir discapacidad a una persona.
- D7, reportes de fallas de sensores: **no personal**, sin identificadores de usuarios ni credenciales en los registros.
- La política cubre captura, uso, copias y eliminación; no autoriza datos sensibles. Si cambia el contenido o permite reidentificación, se revisará su categoría antes de usarlo.

## 2. Ciclo de vida

- **Captura:** el encargado de datos limita las cámaras a cajones, presenta avisos y documenta consentimiento válido o excepción antes del piloto.
- **Almacenamiento:** el administrador del sistema conserva D3 temporalmente en un equipo local cifrado, con cuentas individuales y acceso por rol; excluye imágenes de respaldos.
- **Uso:** el encargado de procesamiento verifica el ocultamiento de rostros y placas antes del modelo local, registra accesos y habilita revisión humana y pruebas de errores.
- **Compartición:** el encargado de programación bloquea la salida de D3 a terceros; la app muestra únicamente ID y disponibilidad del cajón.
- **Retención:** el administrador del sistema justifica un máximo propuesto de 24 horas para D3 y revisa su vencimiento; documenta bloqueo legal y plazo cuando corresponda.
- **Eliminación:** el administrador borra originales, versiones, copias y temporales al vencer el plazo aplicable y registra la comprobación. Véase el [diagrama actualizado](ciclo_vida_dato_proyecto.png) y su [archivo editable](ciclo_vida_dato_proyecto.drawio).

## 3. Normativa aplicable

- La [LFPDPPP publicada en 2025](https://www.diputados.gob.mx/LeyesBiblio/pdf/LFPDPPP.pdf) aplica al tratamiento de D3 identificable por particulares: principios del art. 5, consentimiento, aviso, proporcionalidad, seguridad y derechos ARCO; la autoridad es la Secretaría Anticorrupción y Buen Gobierno.
- El art. 26, fracción II, regula la oposición a determinados tratamientos automatizados sin intervención humana. El prototipo actual solo estima ocupación; antes de añadir decisiones sobre personas se revisará ese supuesto y se habilitarán los mecanismos correspondientes.
- No se identifica un vínculo territorial que haga aplicable la [Ley de IA de la UE](https://eur-lex.europa.eu/legal-content/ES/TXT/?uri=CELEX:32024R1689), art. 2.1; detectar ocupación no convierte por sí solo al sistema en alto riesgo conforme al art. 6. Se revisará si cambia su uso o mercado.
- Se adopta voluntariamente el [NIST AI RMF 1.0](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf): Gobernar, Mapear, Medir y Gestionar. La [matriz de cumplimiento](matriz_cumplimiento_proyecto.xlsx) distingue obligaciones, recomendaciones, supuestos no aplicables y requisitos no encontrados; NIST no sustituye la ley.

## 4. Controles comprometidos

- **A1/C01 y A2/C02 — Encargado de datos, con apoyo de programación:** colocar letrero y aviso en app sobre IA, errores y contacto humano; documentar consentimiento válido o excepción del art. 9 antes del piloto, informar a participantes y evitar captar transeúntes.
- **A3/C03 y A4/C04 — Encargado de datos y encargado de procesamiento:** presentar aviso previo con enlace al completo, finalidad, responsable y medios ARCO; encuadrar cajones, ocultar rostros y placas antes del modelo y no pedir nombres, teléfonos ni correos.
- **A5/C05 y A6/C06 — Encargado de procesamiento:** registrar antes del piloto riesgo, daño, probabilidad, responsable, medida y prueba, y revisar tras cambios; permitir al operador corregir estados y detener la detección, registrando correcciones sin identificar conductores.
- **A7/C07 y A8/C08 — Administrador del sistema y encargado de procesamiento, respectivamente:** justificar el máximo de 24 h, eliminar originales, copias y temporales y documentar bloqueo cuando corresponda; comparar falsos libres/ocupados por cajón e iluminación y corregir diferencias sin registrar discapacidad ni identidad.
- **A9/C09 y A10/C10 — Encargado de procesamiento y administrador del sistema, respectivamente:** mantener contacto para reclamos y habilitar oposición ARCO y revisión antes de añadir decisiones sobre personas; cifrar el equipo, usar cuentas individuales, limitar D3 al operador autorizado por rol y registrar accesos.
- **A11/C11 — Encargado de programación:** bloquear envíos de D3 a nube, IA generativa o terceros, compartir solo ID y estado del cajón, y revisar proveedor, contrato y reglas antes de cambiar el diseño; comprobar el tráfico de salida. Son compromisos a implementar y probar antes del piloto.

## 5. Manejo de datos con herramientas de IA

- Durante las semanas **5 a 13**, ChatGPT, Gemini, DeepSeek, Dify y otras herramientas o agentes externos solo recibirán datos ficticios o información no personal previamente revisada y autorizada por el encargado de datos.
- D1, D2, D4, D5, D6 y D7 solo podrán usarse si no incluyen ni permiten inferir identidades, recorridos individuales, ubicaciones asociadas a personas, credenciales o información reservada; se preferirán ejemplos sintéticos y conteos agregados.
- **D3 real no se subirá a servicios externos, aun con rostros o placas difuminados**, conforme al diseño local. Para ejercicios generativos se usarán imágenes totalmente ficticias; queda prohibido enviar datos sensibles, rostros, placas, contactos, contraseñas o registros identificables.
- En el modelo local, D3 se procesará después de ocultar identificadores y verificar que no queden elementos reconocibles. Quitar nombres o difuminar no garantiza anonimización: deben revisarse también metadatos, contexto y posibles cruces con otros datos.
- La regla incluye prompts, adjuntos, capturas, bases de conocimiento, registros de ejecución y conexiones de agentes. Dify u otra herramienta autoalojada no se considerará local si transmite información a un modelo, complemento o servicio externo.
- El encargado de programación comprobará destinos y permisos; el encargado de datos revisará cada conjunto antes de autorizarlo. Cualquier excepción requerirá revisar matriz, diagrama, base legal y proveedor, y obtener aprobación del líder del proyecto antes del envío; un incidente exige detener el flujo y avisar al responsable de datos.

## 6. Revisión

- El líder del proyecto aprobará esta política antes del piloto; los responsables de cada etapa deberán conocer sus tareas y aportar evidencias de los controles.
- El encargado de datos coordinará una revisión mensual durante las semanas 5 a 13 y una revisión inmediata ante incidentes o cambios de finalidad, datos, modelos, proveedores o normativa.
- Toda modificación se aprobará por el líder del proyecto, se versionará en GitHub y actualizará conjuntamente política, matriz y diagrama; no se habilitarán nuevos tratamientos antes de esa aprobación. Versión inicial: **1 de octubre de 2026**.
