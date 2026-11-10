# Pruebas antes de publicar WAREHOUSE LMS

1. Abrir `index.html` localmente y revisar que carguen las tres unidades.
2. Completar las lecciones requeridas para habilitar los quizzes.
3. Presentar cada quiz y comprobar que muestra 15 preguntas, cuatro alternativas y retroalimentación final.
4. Confirmar que el orden de preguntas y alternativas cambia entre intentos.
5. Verificar penalización: 0,50 por incidencia en quizzes y 0,75 en examen final; nunca debe bajar de 0,0.
6. Cambiar de pregunta con los botones internos: no debe aumentar incidencias.
7. Cambiar realmente a otra pestaña durante un intento de prueba: debe registrar una incidencia.
8. Completar las tres unidades y sus quizzes para habilitar el examen final de 30 preguntas.
9. En el examen final, ingresar el nombre del estudiante y finalizar.
10. Verificar que se agrega exactamente una fila en la pestaña de Google Sheets `resultados`, con `Unidad = WAREHOUSE LMS`, nota final, intento e incidencias. No deben aparecer filas de quizzes.
11. Confirmar que la fila mantiene los nueve encabezados existentes y que no se crean columnas nuevas.

Nota: el envío se configura en el LMS, pero la petición `no-cors` no permite leer una confirmación del servidor desde el navegador. La verificación del registro debe hacerse en Google Sheets.
