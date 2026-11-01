# Notas de diseño del sitio

Registro de decisiones para las revisiones semanales del diseño. Cada revisión debe leer este archivo antes de proponer cambios y actualizarlo al terminar.

## Línea aprobada (01-11-2026)
- Estilo institucional y sobrio: encabezado azul marino #132A4F, acciones #1F5AA6, fondo #F4F6F9, tarjetas blancas con borde #DCE1E8.
- Una sola tipografía sans (Source Sans 3 con respaldo del sistema).
- Tarjetas con franja izquierda de color según prioridad (rojo #B42318, ámbar, verde #1E6B45).
- La ficha se abre en un panel lateral con los datos en tabla.
- El usuario lo usa sobre todo en iPhone (Safari).

## Rechazado por el usuario
- Diseño "tipo expediente" (serifas, sellos de prioridad inclinados, fondo papel, tono violeta). No volver a esa línea.
- Tarjetas construidas como `<button>` con contenido complejo: Safari las dibuja mal.

## Funciones que deben mantenerse
- Un solo `index.html` para dos versiones: pública (GitHub Pages, lee Supabase por REST) y privada (claude.ai, lee por el conector `mcp` y usa `sample` para el abogado beta).
- Pestañas: Repositorio, Boletines, Plazos y Abogado (beta, solo en claude.ai).
- "Mi seguimiento" solo en claude.ai.
- Panel "Etapas del sumario" (filtro por etapa procesal, columna `etapas` en Supabase), agregado el 01-11-2026 a pedido del usuario.

## Historial de propuestas semanales
(La revisión semanal agrega aquí una línea por semana: fecha, cambios propuestos y si se publicaron o se descartaron.)
