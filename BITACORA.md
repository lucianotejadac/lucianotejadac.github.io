# Bitácora de decisiones

## 2026-10-03 · Creación de la página principal

**Contexto.** Había 19 repositorios con GitHub Pages activo, cada uno con su simulador, pero
ningún punto de entrada común. Los estudiantes recibían enlaces sueltos por U-Cursos.

**Decisión.** Crear el repositorio de usuario `lucianotejadac.github.io` con un solo
`index.html` estático que enlaza los simuladores agrupados en cinco áreas: física y
radiofarmacia, adquisición y consolas, procesamiento SPECT, PET/CT y visores DICOM. Incluye
un buscador en el cliente que ignora tildes y mayúsculas, y modo oscuro automático.

**Alternativas descartadas.**
- Generar la lista desde la API de GitHub en tiempo de carga: dependería de la red y del
  límite de peticiones, y mostraría repos que no son para estudiantes.
- Jekyll con colección de simuladores: agrega una capa de construcción para una página que
  cambia pocas veces al semestre.

**Consecuencias.**
- `cardiaco-movil-dev` queda fuera a propósito: es la versión de revisión del docente.
- `consola-pet` y `simulador-cintigrafia-osea` aparecen en dos secciones cada uno; el
  contador de la cabecera cuenta direcciones únicas, no tarjetas.
- Cuando se publique un simulador nuevo hay que agregar su tarjeta a mano (ver README).

## 2026-10-03 · Estética Windows 95 / PowerPoint de los 90

**Contexto.** La primera versión usaba un diseño neutro de tarjetas. El usuario pidió que
la página principal tuviera la misma estética retro que SPECT Lab 95 y los simuladores
renales y tiroideo.

**Decisión.** La página se presenta como una ventana de "Microsoft PowerPoint" sobre el
escritorio verde azulado, en vista Clasificador de diapositivas: cada simulador es una
diapositiva 4:3 con plantilla azul degradado, título amarillo y viñetas, numerada en
orden. Barra de menú, barra de herramientas con el buscador, barra de estado, barra de
tareas con reloj y diálogo "Acerca de" en el menú "?". Paleta y tipografía tomadas de
`spect-lab-95/simulador95.css` (Tahoma / MS Sans Serif, #c0c0c0, #000080, #1084d0).

**Alternativas descartadas.**
- Modo oscuro automático: Windows 95 no lo tenía y rompería la estética; se quitó.
- Escritorio con iconos en vez de clasificador: menos legible con 20 entradas.

**Consecuencias.**
- En pantallas angostas las diapositivas pierden la proporción 4:3 y crecen en altura
  para no cortar el texto; en escritorio se mantiene la proporción.
- La captura con `chrome --headless --screenshot --window-size=390` no reproduce un
  viewport móvil real; para revisar el móvil se usa Playwright con el Chrome instalado.

## 2026-10-03 · Solo estética de PC de los 90, sin simular programas

**Contexto.** La versión anterior imitaba una ventana de PowerPoint con barra de título,
menús, barra de tareas y diapositivas. El usuario pidió quitar toda simulación de
programas o ventanas y conservar solo la estética de PC noventera.

**Decisión.** Fondo gris #c0c0c0, cabecera con degradado azul marino, tipografía Tahoma,
botones y tarjetas con bisel en relieve, descripciones en paneles hundidos blancos y
secciones como cuadros de grupo con leyenda. Cada simulador lleva un icono cuadrado con
dos o tres letras en un color de la paleta de 16 colores según el área.

**Alternativas descartadas.**
- Ventana, menús, barra de tareas, diálogo «Acerca de» y vista de diapositivas: eran
  simulación de programas, justo lo que se pidió evitar.

**Consecuencias.**
- La página ya no tiene ningún elemento que parezca interactivo sin serlo.
