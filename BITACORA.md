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
