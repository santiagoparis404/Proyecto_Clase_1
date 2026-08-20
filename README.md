# Plan de entrenamiento · 30 días

Aplicación web de una sola página para seguir un plan de fuerza de 3 sesiones
semanales durante 4 semanas, generada a partir de `plan-30-dias.pdf`.

**Ver:** https://santiagoparis404.github.io/Proyecto_Clase_1/

## Qué hace

- **Filtro por sesión** — todas, o A (lunes, empuje), B (miércoles, tirón), C (viernes, piernas y hombros).
- **Registro de cargas** — los kilos son el único campo editable; reps y series vienen fijas del plan.
  Cada valor se compara con la semana anterior y muestra la variación en porcentaje.
- **Tutorial por ejercicio** — puntos de técnica, errores frecuentes y enlace a video.
- **Análisis de progreso** — sesiones completadas, tonelaje semanal, progresión de cargas
  por ejercicio y curva de carga normalizada.

La semana 4 aplica la descarga del plan: una serie menos en cada ejercicio.

## Detalles técnicos

Un solo archivo `index.html`, sin dependencias ni conexión a internet.
Los datos se guardan en `localStorage` del navegador y pueden exportarse
e importarse como JSON.
