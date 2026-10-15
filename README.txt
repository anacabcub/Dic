# Mi Diccionario Inglés–Español

## Contenido
- `index.html`: aplicación web adaptable a iPhone.
- `manifest.webmanifest`: configuración para instalarla como app web.
- `sw.js`: caché básica de la aplicación (PWA).
- `README.txt`: instrucciones y limitaciones.

## Funciones
- Añadir palabras y expresiones manualmente.
- Traducción automática opcional mediante MyMemory (requiere Internet).
- Reconocimiento OCR en fotos con Tesseract.js (la librería se carga desde CDN y requiere Internet la primera vez).
- Buscar, ordenar, editar y borrar entradas.
- Significados alternativos.
- Exámenes por número de preguntas o tiempo, corrección y lista de errores.
- Exportar e importar un JSON para copias de seguridad.
- Datos persistentes en el almacenamiento local del navegador.

## Cómo usarlo en iPhone
La forma recomendada es alojar estos archivos en un sitio HTTPS estático (por ejemplo, GitHub Pages o un proveedor de alojamiento estático) y abrir la URL en Safari. Después:
1. Pulsa Compartir en Safari.
2. Elige “Añadir a pantalla de inicio”.
3. Abre la app desde el nuevo icono.
4. En la sección Inicio, usa “Exportar copia JSON” regularmente.

También puedes abrir `index.html` en un navegador de ordenador para probarlo, pero abrir el archivo directamente desde Archivos en iOS puede limitar el almacenamiento, la instalación PWA y las llamadas externas.

## Persistencia y privacidad
Las entradas se guardan en `localStorage` del navegador y no se sincronizan automáticamente con iCloud ni entre dispositivos. Si borras los datos de Safari o cambias de navegador/dispositivo, podrías perderlas. Exporta e importa `Diccionario.json` para hacer copias o migrar.

La traducción se solicita a `api.mymemory.translated.net` y el OCR carga Tesseract.js desde jsDelivr. Esas funciones requieren conexión y dependen de servicios externos; no hay garantía de disponibilidad ni de exactitud. Revisa las traducciones antes de guardarlas.

## Limitaciones de esta versión
- El cronómetro se comprueba entre preguntas; no puede cerrar automáticamente un cuadro de respuesta que permanezca abierto.
- La validación acepta respuestas alternativas registradas y normaliza acentos, mayúsculas, espacios y puntuación, pero no determina equivalencia semántica compleja.
- El OCR detecta líneas de texto, no decide con fiabilidad qué términos son vocabulario útil; revisa el texto detectado.
- Para instalar como PWA y usar el service worker, debe servirse desde HTTPS o localhost.
- No se incluyen claves API ni suscripciones de pago.
