# lucianotejadac.github.io

Página principal de los simuladores docentes de medicina nuclear, publicada en
https://lucianotejadac.github.io/

Es un único `index.html` autocontenido, sin dependencias externas. Cada simulador vive en su
propio repositorio con GitHub Pages; esta página solo los enlaza y los agrupa por área.

## Agregar un simulador

1. Publicar el repositorio del simulador en Pages (rama `main`, raíz).
2. Copiar una línea `<li class="item …">` dentro de la sección que corresponda en `index.html`.
3. Ajustar `data-href`, el enlace, el icono, título, etiqueta, descripción y `data-tags` (palabras para el buscador).
4. Para destacarlo, agregar `<span class="new">¡NUEVO!</span>` después del enlace y cambiar el banner superior.
5. Hacer commit y push a `main`; Pages se reconstruye solo. El contador LED se calcula solo.

El collage de `img/collage.jpg` sale del caso demo público de cintigrafía ósea (CMB-PCA, CC BY 4.0); su cita está en el pie de página.

Las versiones de revisión (por ejemplo `cardiaco-movil-dev`) no se listan aquí.

## Licencia

© 2026 Luciano Tejada Castro. Distribuido bajo licencia [MIT](LICENSE).
Los componentes y datos de terceros conservan sus propias licencias, indicadas en este documento o junto a ellos.
