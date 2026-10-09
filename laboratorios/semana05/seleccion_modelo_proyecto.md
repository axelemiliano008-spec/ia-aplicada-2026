# Selección de modelo generativo para el proyecto Estacionamiento inteligente

## Modelos evaluados

- **Gemma 4 26B A4B IT (`gemma-4-26b-a4b-it`) en Google AI Studio:** modelo utilizado en las nueve ejecuciones de temperatura y en las pruebas de contexto y posición de la aguja.
- **Gemini 3 Flash Preview:** se inspeccionó su control de temperatura (0 a 2, valor inicial 1), pero no se ejecutaron pruebas porque la cuenta mostraba una restricción de acceso.
- **Gemini 3.5 Flash Lite y Gemini 3.1 Flash Lite:** se inspeccionaron sus ajustes, pero la interfaz no ofrecía control de temperatura. No se usaron para las mediciones.
- **Semana 1: ChatGPT, Gemini y DeepSeek.** La [comparativa publicada](../semana01/comparativa_modelos.md) documenta recomendaciones de arquitecturas híbridas para análisis de correos sospechosos, datos necesarios y riesgos. Los tres respetaron la estructura y el límite de palabras según ese registro. No se documentan versiones exactas ni mediciones de temperatura o contexto. Las mejoras porcentuales se identificaron como afirmaciones por verificar, no resultados garantizados.

La opción «GPT-5.x & O1/3» del tokenizador de OpenAI se utilizó para contar tokens; esto no constituye una evaluación de generación de esos modelos.

## Evidencia de tokens

Tokens de mi documento de referencia: **1,844**, medidos sobre el texto completo del documento ficticio de cuatro páginas, antes de insertar la aguja. El documento tiene **10,175 caracteres**.

Caracteres por token en español: **6.24** en el párrafo de 100 palabras (736 / 118), **6.89** en la frase corta (62 / 9) y **5.52** en el documento completo (10,175 / 1,844).

Implicación para mi proyecto: los documentos de tamaño similar al de referencia caben completos en la configuración probada. El presupuesto debe calcularse con el tokenizador del modelo elegido y reservar espacio para instrucciones y respuestas. No debo trasladar directamente el conteo de OpenAI a Gemma ni asumir una proporción fija entre español e inglés.

## Evidencia de temperatura

Temperatura que usaré para tareas de precisión: **0**, porque produjo **17 palabras distintas** entre tres respuestas, frente a 22 con 0.7 y 21 con 1.5. Las ejecuciones 2 y 3 fueron idénticas; la primera cambió una preposición. La temperatura 0 no garantizó igualdad absoluta ni garantiza exactitud factual.

Temperatura que usaré inicialmente para tareas creativas: **1.5**, porque produjo tres respuestas diferentes y 21 palabras distintas, frente a dos respuestas diferentes y 17 palabras distintas con temperatura 0. Esta es una configuración provisional: 0.7 obtuvo 22 palabras distintas y no se hizo una prueba específica de nombres creativos. Los datos no demuestran que 1.5 sea la mejor temperatura para creatividad.

Se inició un chat nuevo por ejecución y se conservó el prompt. Los ajustes fueron razonamiento High, Top P 0.95 y máximo de salida de 32,768 tokens. La búsqueda de Google permaneció activada y bloqueada en esta interfaz de Gemma, lo cual limita el aislamiento experimental.

## Evidencia de contexto

La entrada fue rechazada con aproximadamente **475,695 tokens mostrados por AI Studio**, en el **intento 9**, con **256 copias**. El mensaje indicaba que se superó el máximo de tokens de entrada permitido para el modelo. No fue una respuesta incorrecta: no hubo generación de respuesta.

El último intento aceptado fue el **8**, con **128 copias** y **237,880 tokens visibles**. En todos los intentos aceptados se recuperó AZUL-7342. No se observó olvido ni invención del código, y no se determinó el umbral exacto entre 128 y 256 copias. Las lecturas para 32 y 64 copias fueron anómalamente parecidas (119,312 y 119,262) y se conservan como registros de interfaz, sin tratarlas como medidas exactas de entrada.

Mi documento de referencia mide aproximadamente **1,844 tokens con el tokenizador de OpenAI**. Una copia con la aguja y la pregunta produjo un chat de **2,157 tokens visibles en AI Studio después de responder**. Son mediciones de diferente alcance y tokenizador.

Por lo tanto: **el documento de referencia cabe completo** en la configuración ensayada. No necesito dividirlo ni resumirlo para esta prueba. Para documentos mayores mediré la entrada real y la dividiré si excede el límite disponible, sin asumir que toda la ventana puede dedicarse al documento.

La aguja se recuperó en el inicio, la mitad y el final de una sola copia. Se hizo una prueba por posición. En la saturación, la aguja solo estaba en la primera copia, por lo que quedó relativamente más cerca del inicio al aumentar el texto. Esto no demuestra precisión universal en contextos largos.

## Decisión

Modelo elegido: **Gemma 4 26B A4B IT en Google AI Studio**, para tareas de redacción y consulta de documentación ficticia o no personal autorizada del proyecto Estacionamiento inteligente. Es el modelo con mediciones controladas disponibles en este laboratorio; esta elección no establece superioridad frente a los modelos de la semana 1. Faro Azul es únicamente el escenario ficticio del documento de prueba. Las pruebas no evalúan detección visual de ocupación ni autorizan usar AI Studio para procesar cámaras reales.

Configuración: temperatura **0** para extraer datos de documentos y preparar borradores que requieran consistencia; temperatura **1.5**, provisional, para proponer alternativas creativas. Se verificará cada dato extraído contra el texto original antes de incorporarlo a un reporte de seguridad.

Restricciones de datos según la [política de la semana 4](../semana04/politica_datos_proyecto.md):

- Las herramientas externas solo recibirán datos ficticios o información no personal previamente revisada y autorizada por el encargado de datos. Se preferirán ejemplos sintéticos y conteos agregados.
- No se enviarán imágenes reales del estacionamiento (D3), ni siquiera con rostros o placas difuminados. El diseño exige procesamiento local; estos ensayos de texto no validan ese componente visual.
- No se enviarán datos sensibles, rostros, placas, contactos, contraseñas, registros identificables, recorridos individuales, ubicaciones vinculadas a personas ni información reservada.
- La revisión incluye metadatos, contexto, posibilidades de reidentificación, prompts, adjuntos, capturas, registros y conexiones de agentes.
- Se verificarán destinos y permisos. Cualquier excepción exige revisar política, matriz, diagrama y proveedor y obtener la aprobación del líder antes del envío, conforme a la política del proyecto.

El documento utilizado en este laboratorio es ficticio. El borrador de un aviso de privacidad requiere revisión antes de publicarse.

La evidencia está en `tablas_experimentos.xlsx`. El archivo `documento_prueba_contexto.txt` contiene una sola copia y una sola aparición de la aguja.
