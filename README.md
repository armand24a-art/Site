# Página personal / Curriculum académico

Sitio de una sola página (`index.html`) con 14 secciones a las que se accede desde un
panel de navegación con iconos, estilo "panel de datos" (glassmorphism, acentos
luminosos, fondo con degradados en movimiento). La sección de inicio es **Biografía**.

## Comportamiento por dispositivo

El sitio se adapta automáticamente al ancho de la pantalla:

- **Laptop / escritorio (> 1024px):** rail de navegación vertical fijo a la izquierda,
  con un indicador luminoso que se desliza entre secciones.
- **Tablet (641px – 1024px):** el rail se convierte en una tira horizontal
  desplazable en la parte superior.
- **Celular (≤ 640px):** la navegación se convierte en un dock inferior fijo tipo
  app, solo con iconos, desplazable horizontalmente.

No necesitas configurar nada para esto: el CSS usa `@media queries` que detectan
el ancho de la ventana automáticamente.

## Estructura de secciones (14)

01. Biografía (inicio)
02. Trayectoria académica
03. Experiencia profesional
04. Líneas de investigación
05. Proyectos académicos
06. Publicaciones
07. Libros
08. Tesis
09. Cursos
10. Divulgación
11. Recursos
12. Colaboración
13. Reconocimientos
14. Contacto

> Nota: en tu mensaje original listaste 13 secciones pero pediste 14 ventanas,
> así que agregué **Contacto** como la 14ª. Puedes cambiar el nombre o quitarla
> editando el archivo `index.html` (ver más abajo).

## Cómo editar el contenido

Todo el sitio vive en un único archivo: `index.html`. No necesitas tocar CSS
ni JavaScript para actualizar tu información.

1. Abre `index.html` con cualquier editor de texto (VS Code, Bloc de notas, etc.)
2. Busca el bloque `<article id="NOMBRE_SECCION" ...>` de la sección que quieras editar.
   Por ejemplo, para la biografía busca `id="biografia"`.
3. Dentro de `<div class="content">...</div>` reemplaza el texto de ejemplo
   por tu información real. Puedes usar etiquetas simples:
   - `<p>...</p>` para párrafos
   - `<ul><li>...</li></ul>` para listas
   - `<strong>...</strong>` para negritas
   - `<a href="https://...">texto</a>` para enlaces
4. Guarda el archivo.

### Cambiar tu nombre y el título del encabezado

Al inicio del `<body>`, en la etiqueta `<header class="site-header">`,
edita:

```html
<h1>Nombre Apellido</h1>
<p class="role">Área de especialidad · Institución</p>
```

### Agregar tu foto

En la sección de biografía hay un recuadro con el texto "FOTO 150 × 190 px".
Para poner tu foto real:

1. Sube tu imagen a una carpeta `img/` dentro del proyecto (por ejemplo `img/foto.jpg`).
2. Reemplaza:

```html
<div class="bio-photo">FOTO<br>150 × 190 px</div>
```

por:

```html
<img class="bio-photo" src="img/foto.jpg" alt="Foto de Nombre Apellido" style="object-fit:cover;">
```

### Cambiar el orden o el nombre de una sección

Cada sección aparece dos veces en el archivo:
- Una vez en el menú (`<nav class="drawer">`), como `<button class="tab" data-target="...">`
- Otra vez en el contenido, como `<article id="...">`

El texto de `data-target` y de `id` debe coincidir exactamente en ambos lugares.

## Cómo publicarlo en GitHub Pages

1. Crea un repositorio nuevo en GitHub (por ejemplo `mi-curriculum`).
2. Sube el archivo `index.html` (y la carpeta `img/` si agregaste fotos) a la raíz del repositorio.
3. Ve a **Settings → Pages** dentro del repositorio.
4. En "Source", selecciona la rama `main` (o `master`) y la carpeta `/root`.
5. Guarda. GitHub te dará una URL como:
   `https://tu-usuario.github.io/mi-curriculum/`
6. Espera uno o dos minutos y abre esa URL — tu página ya estará publicada.

Cada vez que quieras actualizar tu información, edita `index.html`, sube
("commit") los cambios al repositorio y GitHub Pages se actualizará
automáticamente en unos minutos.

## Notas técnicas

- No requiere ningún framework ni proceso de compilación: es HTML, CSS y
  JavaScript puro en un solo archivo.
- Las tipografías (Fraunces, Libre Franklin, IBM Plex Mono) se cargan desde
  Google Fonts vía CDN, por lo que necesitas conexión a internet para verlas
  correctamente (si no hay conexión, el sitio usa una tipografía de
  respaldo del sistema).
- El sitio es responsivo: en pantallas angostas el menú lateral se convierte
  en una cuadrícula de botones arriba del contenido.
- Puedes compartir un enlace directo a una sección específica agregando el
  identificador al final de la URL, por ejemplo:
  `https://tu-usuario.github.io/mi-curriculum/#publicaciones`
