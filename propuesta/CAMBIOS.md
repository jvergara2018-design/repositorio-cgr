# Propuesta de diseño – 03-11-2026

Propuesta semanal pendiente de aprobación. No modifica el sitio publicado (`index.html` de la raíz). Para verla en el teléfono: https://jvergara2018-design.github.io/repositorio-cgr/propuesta/

## Cambios

1. **En el teléfono, la lista aparece antes.** Hoy, en un iPhone, hay que bajar casi una pantalla completa de filtros antes de ver el primer documento. Ahora el buscador queda siempre a la vista y los otros filtros (categoría, materia, tipo, prioridad, origen, orden y Mi seguimiento) se abren con un botón «Más filtros», que además indica cuántos están activos (por ejemplo, «Más filtros (2 activos)»). En el computador los filtros se ven igual que antes.
2. **Campos y botones cómodos para el dedo y sin zoom en Safari.** Los campos de búsqueda y las listas desplegables pasan a letra de 16 px: con letra más chica, el iPhone hace zoom automático al tocarlos y descuadra la página. Los botones (Actualizar, Copiar tabla, etapas del sumario, Cerrar ficha, documentos de un boletín, Quitar filtros, Mi seguimiento y Abogado) quedan con al menos 44 px de alto, el mínimo recomendado para tocar sin errores.
3. **Mensaje claro cuando no cargan los datos.** Si no hay conexión y no existe copia guardada, la lista ya no dice «Todavía no hay documentos cargados» (que da a entender que el repositorio está vacío), sino «No se pudieron cargar los documentos» con un botón «Reintentar». El aviso de error y el contador de resultados («4 de 72») ahora los anuncia el lector de pantalla.
4. **Etiquetas un poco más grandes en el teléfono.** Tipo, prioridad, etapa, categoría y efecto jurisprudencial de cada tarjeta suben de unos 12-13 px a 14 px, para leerlas sin acercar la pantalla.

No se tocaron colores, tipografía, estructura, la ficha lateral, los dos modos de datos (REST público y conector de claude.ai), Mi seguimiento ni la pestaña Abogado (beta). Se probó con los 72 documentos y 2 boletines reales, en 390×844 y 1280×900, modo claro y oscuro, el filtro plegable, la apertura de la ficha con teclado y el modo claude.ai simulado, sin errores de JavaScript.

## Capturas

Antes (teléfono): ![antes](antes-movil.png)

Después (teléfono): ![después](despues-movil.png)

Después (escritorio): ![después escritorio](despues-escritorio.png)

## Observación para más adelante
El sitio no tiene modo oscuro: en un teléfono con modo oscuro se ve igual que en modo claro (se lee bien). No se propone ahora porque implica definir nuevos colores; puede evaluarse si el usuario lo pide.
