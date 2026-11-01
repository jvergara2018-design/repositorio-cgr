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

## Hechas
(ninguna todavía)
