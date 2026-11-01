# Mejoras futuras del sitio

Lista de mejoras acordadas para más adelante. Al implementar una, muévela a "Hechas" con la fecha.

## Pendientes
1. **Envío automático del boletín por correo con Supabase + Resend** (anotado el 01-11-2026)
   - Al guardarse un boletín nuevo en `public.boletines`, un trigger de base de datos o un webhook llama a una Edge Function de Supabase que envía el correo con Resend (gratis hasta 100 correos al día).
   - Ventajas: correo con formato propio, desde una dirección del usuario y con la posibilidad de enviarlo a varias personas (equipo).
   - Requiere: cuenta en Resend, dominio o remitente verificado y la API key guardada como secreto de la Edge Function.
   - Mientras tanto: la notificación por correo de la tarea programada (se activa en Tareas programadas → Boletín → Correo electrónico).
2. **Boletín por WhatsApp** (anotado el 01-11-2026)
   - Reutilizar la misma Edge Function. Opciones: CallMeBot (gratis, no oficial) o Bird (oficial, pagado y con aprobación de WhatsApp Business).

3. **Actualización en vivo** (anotado el 01-11-2026)
   - Con Supabase Realtime, el sitio abierto muestra un boletín o dictamen nuevo sin recargar.
   - Requiere activar Realtime en las tablas `dictamenes` y `boletines` y cargar la librería supabase-js en la página. No requiere nada del usuario.
4. **Búsqueda de texto completo** (anotado el 01-11-2026)
   - Búsqueda en la base de datos (Postgres full-text en español, con `unaccent`) en vez de filtrar en el navegador; tolera tildes y variaciones de palabras.
   - Conviene cuando el repositorio supere unos 100 documentos. No requiere nada del usuario.
5. **Inicio de sesión con correo** (anotado el 01-11-2026)
   - Supabase Auth con enlace mágico por correo, para que "Mi seguimiento" (estado y notas) funcione también en el sitio público y en cualquier navegador.
   - Requiere políticas RLS por usuario en `notas_seguimiento` (agregar la columna user_id). El usuario solo debe confirmar su correo.
6. **Suscripción al boletín** (anotado el 01-11-2026)
   - Formulario en el sitio para que el usuario o su equipo dejen su correo; tabla `suscriptores` con confirmación por correo (doble opt-in) y enlace para darse de baja.
   - Depende de la mejora 1 (envío con Resend).
7. **Abogado (beta) en el sitio público** (anotado el 01-11-2026)
   - Edge Function de Supabase que llama a la API de Claude con las reglas y el contexto del repositorio, para que la consulta funcione en cualquier navegador.
   - Requiere una API key de Anthropic (costo por consulta a cargo del usuario), límite de consultas por persona y, idealmente, la mejora 5 para restringir el acceso.

8. **Carga liviana del listado** (anotado el 01-11-2026; hacerla al llegar a unos 300 documentos)
   - Hoy cada visita descarga el repositorio completo. Pasar a descargar solo las columnas del listado (id, tipo, número, título, fecha, prioridad y un resumen corto) con paginación, y traer el detalle completo al abrir una ficha.
   - Motivo: el plan gratis de Supabase incluye 5 GB de transferencia al mes; con 1.000 fichas, cada visita bajaría unos 2 MB.
9. **Respaldo automático de la base de datos** (anotado el 01-11-2026)
   - El plan gratis de Supabase no incluye respaldos automáticos. Agregar a la tarea de lunes, miércoles y viernes (o a una semanal) la exportación de `dictamenes` y `boletines` a JSON en el repositorio de GitHub (carpeta `respaldo/`).
   - Excluir `notas_seguimiento` del repositorio público, o guardarla en un repositorio privado.

## Límites del plan gratis de Supabase (revisados el 01-11-2026)
- Base de datos: 500 MB por proyecto. Uso actual: 11 MB (casi todo es la estructura interna de Postgres); cada ficha ocupa unos 2 KB y cada boletín unos 2 KB. Alcanza para más de 100.000 fichas.
- Transferencia: 5 GB al mes. Es el límite que se alcanzaría primero si el sitio tiene muchas visitas con un repositorio grande (ver mejora 8).
- Pausa por inactividad: el proyecto se pausa tras una semana con muy poca actividad. Las tareas de lunes, miércoles y viernes lo mantienen activo; Supabase avisa por correo antes de pausar, y un proyecto pausado conserva sus datos.
- Sin respaldos automáticos (ver mejora 9).
- Si se supera algo: plan Pro, 25 USD al mes (8 GB de base, 250 GB de transferencia, respaldos diarios, sin pausas).

## Hechas
(ninguna todavía)
