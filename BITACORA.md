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

## 2026-10-03 · Licencia MIT en todos los repositorios

**Contexto.** Solo `simulador-atenuacion-rx` tenía licencia abierta (MIT). Otros 17 repos
no tenían licencia, lo que por defecto equivale a todos los derechos reservados.
`simulador-gantry-3d` tenía una reserva de derechos explícita. El simulador cardíaco
SPECT/CT, el de marcaje, el de Compton, el de control de calidad del eluido y el del
generador también la declaraban en su HTML y en el README. El usuario pidió pasar todo a MIT.

**Decisión.** Se agregó un LICENSE con el texto MIT estándar, a nombre de Luciano Tejada
Castro, 2026, en los 19 repos que no lo tenían. Los avisos de «Todos los derechos
reservados» y de la Ley 17.336 se cambiaron por «Licencia MIT»: comentarios de cabecera,
metadatos, diálogo «Derechos de autor», pies de página, README y AVISO-LEGAL. Los READMEs
sin sección de licencia recibieron una al final.

**Se conservó.** Los avisos de terceros: Three.js, Planck.js, dicom-parser y Chart.js
(MIT), el modelo de Quaternius (CC0) y las imágenes de TCIA (CC BY 4.0). Esos componentes
siguen bajo sus propias licencias. También se conservaron la advertencia de uso educativo
y la exclusión de responsabilidad clínica.

**Consecuencias.** Cualquiera puede reutilizar, modificar y redistribuir los simuladores,
incluso con fines comerciales, siempre que conserve el aviso de copyright. El pie de esta
página, «Código abierto», ahora es exacto. Los simuladores nuevos deben nacer con LICENSE MIT.
