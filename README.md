# Registro interactivo de entrenamiento — 4 semanas

## Qué construí

Una aplicación web de un solo archivo (`plan-entrenamiento.html`) para seguir un plan de
entrenamiento de 3 sesiones semanales durante 4 semanas. Partí de un PDF con el plan y lo convertí
en algo usable durante el entrenamiento: filtrar por sesión, anotar el peso y las repeticiones de
cada ejercicio semana a semana, abrir un video de técnica, y ver el progreso acumulado (adherencia
por semana e incremento de carga por ejercicio). Es para mí, pero sirve para cualquiera que tenga
un plan en papel y hoy lo esté anotando en las notas del teléfono.

Se usa acá: **https://santiagoparis404.github.io/Proyecto_Clase_1/**

## Cómo se lo pedí

**1) El pedido inicial, con el PDF adjunto** (copiado tal cual, sin corregir la ortografía):

> el pdf que adjunto es un plan mensual de entrenamiento. Quiero crear un html interactivo que:
> filtre por sesion o ver los ejericcios de todas permita poner los pesos que voy usando cada
> semana en cada ejercicio cada ejercicio tenga un video tutorial mostrando como se hace contenga
> un analisis de datos progresivo de como va el progreso, marcando sesiones completadas por semana
> e incremento de pesos

**2) Sobre dónde vive la entrega:**

> ¿debo incluir el pdf en algún lado?

De ahí salieron dos decisiones: incluir el PDF original en `plan/` para que se pueda verificar de
dónde salieron los ejercicios, y publicar con GitHub Pages, porque un `.html` dentro de un repo se
ve como código fuente y no se ejecuta — sin Pages, la entrega no "funciona".

## Qué funciona

Probado en Chrome de escritorio, con datos cargados en 3 de las 4 semanas:

- **Filtro por sesión.** Botones Todas / A · Empuje / B · Tirón / C · Piernas, y un selector de
  semana 1–4 que cambia qué registro estás editando.
- **Carga de pesos.** Cada ejercicio tiene campo de peso, de repeticiones y un check "hecha".
  Se guarda solo, sin botón de guardar, y sobrevive a recargar la página.
- **Video de técnica.** Botón "▶ Técnica" en cada ejercicio: abre el buscador de YouTube con el
  nombre del ejercicio, y si pegás el link de uno que te guste queda embebido y reproducible ahí
  mismo para siempre.
- **Progreso.** Sesiones completas sobre 12, cargas registradas, incremento promedio de peso, y
  cuántos ejercicios subieron. Más una grilla de adherencia (3 sesiones × 4 semanas), un gráfico de
  progresión de carga por ejercicio y una tabla con la variación de la primera a la última semana.
- **Exportar / importar.** Botón que baja todos tus datos como JSON y otro que los vuelve a cargar.

**Cómo se usa:** abrís el link, elegís la semana, anotás el peso apenas terminás cada ejercicio y
tildás "hecha". Cuando quieras ver cómo venís, botón "Progreso".

## Qué falta o qué falló

- **Los videos no vienen precargados, y esa fue la parte que no salió como la pedí.** La idea
  original era un video embebido por ejercicio, ya elegido. El problema es que no hay forma de
  garantizar que un ID de YouTube siga existiendo: un video borrado o puesto en privado deja un
  reproductor roto dentro de la app, y son 19 ejercicios para verificar uno por uno. Lo di vuelta:
  la app abre la búsqueda del ejercicio y vos guardás el link que preferís, que queda embebido.
  Funciona y no se rompe, pero es un paso manual la primera vez.
- **Los datos viven en el navegador, no en una cuenta.** Uso `localStorage`, así que lo que cargo en
  la computadora no aparece en el teléfono. El exportar/importar JSON es un parche, no una solución.
  Arreglarlo de verdad pedía un backend, que excede la clase 1.
- **La app no lee el PDF: el plan está transcrito a mano dentro del código.** Si el plan cambia, hay
  que editar el HTML. Empecé pidiendo que "leyera el PDF" y me di cuenta de que eso obligaba a meter
  una librería de PDF entera para un plan que no va a cambiar en 4 semanas.
- **Sin probar en iOS Safari** ni con lector de pantalla.

## Qué aprendí

Aprendí que fácilmente podría crear una app universal para entrenar si cargara un número x de
ejercicios para que cualquier individuo pudiera armar su propio plan en base a los objetivos.
El universo y las opciones son infinitas, e incluso combinable con aplicaciones de salud del
teléfono.
