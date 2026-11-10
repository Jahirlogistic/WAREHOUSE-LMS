WAREHOUSE LMS — paquete de trabajo académico

Se incorpora CONTENIDO_ACADEMICO_UNIDAD_1.md como desarrollo técnico ampliado de la Unidad 1.
El index.html original se conserva sin cambios en esta etapa, conforme a la decisión de consolidar primero el contenido académico y después intervenir la aplicación.

Reglas acordadas para integración futura:
- Google Sheets recibe exclusivamente registros al finalizar el examen final integrador.
- No se envían calificaciones de quizzes ni resultados parciales.
- Una fila por cada presentación final completada.
- Unidad = "WAREHOUSE LMS".
- Se conserva la estructura de nueve columnas ya existente.
- Se registran intento e incidencias; Detalle puede quedar vacío.
- Escala de nota 0,0 a 5,0.
- Penalización acumulativa: 0,50 por incidencia en quizzes; 0,75 por incidencia en examen final.
- Debe evitarse contabilizar navegación interna o recargas como salida real.
- La integración debe validarse antes de enviar calificaciones reales.

Pendiente:
- Unidades 1, 2 y 3 desarrolladas en manuales técnicos separados.
- Revisar el banco de preguntas para convertirlo en casos extensos de decisión con cuatro alternativas plausibles.
- Completar la simulación táctica de asignación de equipos, personal y ubicaciones.
- Implementar identificación y persistencia multiusuario segura.
- Endurecer el receptor Apps Script (validación, autenticación y selección explícita de pestaña) antes de producción.


## Fase de evaluaciones — banco preparado
- Quiz Unidad 1: 15 casos.
- Quiz Unidad 2: 15 casos.
- Quiz Unidad 3: 15 casos.
- Examen final integrador: 30 casos.
- Cuatro alternativas plausibles, una mejor respuesta y retroalimentación técnica por ítem.
- Banco disponible en JSON para integración y Markdown para revisión docente.
- Antes de producción: aleatorizar orden de preguntas/opciones, definir duración, guardar intento y evitar penalizar cambios internos de pantalla.


## Integración del motor de evaluación
- `index.html` ahora consume el banco JSON incorporado en el script: 15 preguntas por quiz y 30 para final.
- Orden de preguntas y alternativas aleatorio por intento; clave correcta preservada.
- Retroalimentación técnica al finalizar cada evaluación.
- Detección de salida limitada al evento `visibilitychange` con estado oculto; navegación interna de preguntas no cuenta como salida.
- Al finalizar únicamente el examen final se envía una fila con los nueve campos acordados a Apps Script.
- No se hizo un POST de prueba para evitar insertar datos ficticios.
- La petición del navegador usa `no-cors`; por seguridad del navegador no se puede leer el resultado del receptor. La confirmación definitiva requiere revisar la pestaña `resultados` después de un examen real.
