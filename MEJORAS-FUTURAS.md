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

## Hechas
(ninguna todavía)
