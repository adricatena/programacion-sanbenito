# Taller Programacion Web - San Benito

## Módulo HTML Avanzado - Construyendo sobre los Fundamentos

### 0. Repaso de Contenidos Previos

**Resumen de conceptos fundamentales:**

- HTML es un lenguaje de marcado que define la estructura de páginas web
- Los elementos HTML se componen de etiquetas de apertura y cierre (`<etiqueta>contenido</etiqueta>`)
- Estructura básica: `<!DOCTYPE html>`, `<html>`, `<head>`, `<body>`
- Etiquetas fundamentales: encabezados (`<h1>` a `<h6>`), párrafos (`<p>`), listas (`<ul>`, `<ol>`, `<li>`), vínculos (`<a>`), imágenes (`<img>`)
- Elementos semánticos: `<section>`, `<article>`, `<header>`, `<footer>`

Este módulo avanzado construye sobre estos fundamentos para crear páginas web más completas, accesibles y funcionales.

### 1. Formularios HTML Avanzados

#### 1.1 Estructura y Atributos de Formularios

Los formularios son componentes clave para la interacción con el usuario. Permiten recopilar datos para procesarlos posteriormente.

**Estructura básica de un formulario:**

```html
<form
  action="procesar.php"
  method="post"
  id="formulario-contacto"
  name="contacto"
>
  <!-- Elementos del formulario -->
  <button type="submit">Enviar</button>
</form>
```

**Atributos importantes:**

- `action`: URL donde se envían los datos (servidor)
- `method`: Método HTTP para enviar datos (`get` o `post`)
  - `get`: Los datos se envían como parte de la URL (visible, limitado, para búsquedas)
  - `post`: Los datos se envían en el cuerpo de la solicitud HTTP (invisible, sin límite de tamaño, para datos sensibles)
- `id`: Identificador único para el formulario
- `name`: Nombre del formulario para referencia
- `autocomplete`: Controla el autocompletado del navegador (`on` u `off`)
- `novalidate`: Desactiva la validación automática del navegador
- `target`: Dónde mostrar la respuesta (`_self`, `_blank`, `_parent`, `_top`)
- `enctype`: Cómo codificar los datos (importante para subir archivos)

**Consideraciones importantes:**

- Sin un backend (servidor), los formularios no procesarán datos realmente
- Para principiantes, podemos enfocarnos en la estructura y validación del lado del cliente
- Más adelante, estos formularios se conectarán con tecnologías de backend

#### 1.2 Tipos de Campos de Entrada (`<input>`)

HTML5 introdujo muchos nuevos tipos de campos que ofrecen validación automática y mejoran la experiencia en dispositivos móviles.

```html
<!-- Campos de texto -->
<label for="nombre">Nombre:</label>
<input
  type="text"
  id="nombre"
  name="nombre"
  placeholder="Escribe tu nombre"
  required
/>

<label for="email">Email:</label>
<input
  type="email"
  id="email"
  name="email"
  placeholder="tu@ejemplo.com"
  required
/>

<label for="password">Contraseña:</label>
<input type="password" id="password" name="password" minlength="8" required />

<!-- Campos numéricos y fechas -->
<label for="edad">Edad:</label>
<input type="number" id="edad" name="edad" min="18" max="120" />

<label for="nacimiento">Fecha de nacimiento:</label>
<input type="date" id="nacimiento" name="nacimiento" />

<label for="hora">Hora de la cita:</label>
<input type="time" id="hora" name="hora" />

<!-- Selección -->
<label for="color">Color favorito:</label>
<input type="color" id="color" name="color" />

<label for="satisfaccion">Nivel de satisfacción:</label>
<input
  type="range"
  id="satisfaccion"
  name="satisfaccion"
  min="0"
  max="10"
  step="1"
/>

<!-- Archivos -->
<label for="archivo">Sube tu CV:</label>
<input type="file" id="archivo" name="archivo" accept=".pdf,.doc,.docx" />

<!-- Campos especiales -->
<label for="busqueda">Buscar:</label>
<input type="search" id="busqueda" name="busqueda" />

<label for="sitio">Tu sitio web:</label>
<input type="url" id="sitio" name="sitio" placeholder="https://ejemplo.com" />

<label for="telefono">Teléfono:</label>
<input
  type="tel"
  id="telefono"
  name="telefono"
  pattern="[0-9]{9}"
  placeholder="123456789"
/>
```

**Ventajas de usar tipos específicos:**

- Validación automática del navegador
- Teclados adaptados en dispositivos móviles (numérico para `type="number"`, email para `type="email"`, etc.)
- Facilidad de uso y mejor experiencia de usuario
- Accesibilidad mejorada

#### 1.3 Otros Elementos de Formulario

**Área de texto:**

```html
<label for="comentario">Comentarios:</label>
<textarea
  id="comentario"
  name="comentario"
  rows="5"
  cols="30"
  placeholder="Escribe tus comentarios aquí"
></textarea>
```

**Listas desplegables:**

```html
<label for="pais">País:</label>
<select id="pais" name="pais">
  <option value="">Selecciona un país</option>
  <option value="es">España</option>
  <option value="mx">México</option>
  <option value="ar">Argentina</option>
  <option value="co">Colombia</option>
  <option value="pe">Perú</option>
</select>
```

**Grupos de opciones en listas desplegables:**

```html
<label for="ciudad">Ciudad:</label>
<select id="ciudad" name="ciudad">
  <optgroup label="Europa">
    <option value="madrid">Madrid</option>
    <option value="paris">París</option>
    <option value="roma">Roma</option>
  </optgroup>
  <optgroup label="América">
    <option value="nueva-york">Nueva York</option>
    <option value="mexico-df">Ciudad de México</option>
    <option value="buenos-aires">Buenos Aires</option>
  </optgroup>
</select>
```

**Cajas de verificación:**

```html
<fieldset>
  <legend>Intereses:</legend>
  <input type="checkbox" id="deporte" name="intereses" value="deporte" />
  <label for="deporte">Deportes</label><br />

  <input type="checkbox" id="musica" name="intereses" value="musica" />
  <label for="musica">Música</label><br />

  <input type="checkbox" id="cine" name="intereses" value="cine" />
  <label for="cine">Cine</label>
</fieldset>
```

**Botones de radio:**

```html
<fieldset>
  <legend>Género:</legend>
  <input type="radio" id="hombre" name="genero" value="hombre" />
  <label for="hombre">Hombre</label><br />

  <input type="radio" id="mujer" name="genero" value="mujer" />
  <label for="mujer">Mujer</label><br />

  <input type="radio" id="otro" name="genero" value="otro" />
  <label for="otro">Otro</label>
</fieldset>
```

**Botones:**

```html
<button type="submit">Enviar formulario</button>
<button type="reset">Restablecer</button>
<button type="button" onclick="alert('¡Hola!')">Botón JavaScript</button>
```

**Lista de datos (datalist):**

```html
<label for="navegador">¿Qué navegador usas?</label>
<input list="navegadores" id="navegador" name="navegador" />
<datalist id="navegadores">
  <option value="Chrome"></option>
  <option value="Firefox"></option>
  <option value="Safari"></option>
  <option value="Edge"></option>
  <option value="Opera"></option>
</datalist>
```

#### 1.4 Atributos de Validación y Estado

HTML5 incluye atributos para validación del lado del cliente:

```html
<input type="text" required />
<!-- Campo obligatorio -->
<input type="text" minlength="3" maxlength="50" />
<!-- Longitud mínima y máxima -->
<input type="number" min="0" max="100" />
<!-- Valor mínimo y máximo -->
<input type="text" pattern="[A-Za-z]{3}" />
<!-- Patrón de expresión regular -->

<!-- Atributos de estado -->
<input type="text" disabled />
<!-- Deshabilitado, no se puede editar ni enviar -->
<input type="text" readonly />
<!-- Solo lectura, no se puede editar pero sí enviar -->
```

#### 1.5 Agrupación y Organización de Formularios

**Fieldset y Legend:**

```html
<fieldset>
  <legend>Información personal</legend>
  <label for="nombre">Nombre:</label>
  <input type="text" id="nombre" name="nombre" /><br />

  <label for="apellido">Apellido:</label>
  <input type="text" id="apellido" name="apellido" />
</fieldset>

<fieldset>
  <legend>Información de contacto</legend>
  <label for="email">Email:</label>
  <input type="email" id="email" name="email" /><br />

  <label for="telefono">Teléfono:</label>
  <input type="tel" id="telefono" name="telefono" />
</fieldset>
```

#### 1.6 Ejercicio Práctico: Formulario de Registro

**Ejercicio:** Crear un formulario de registro completo que incluya:

- Datos personales (nombre, apellido, fecha de nacimiento)
- Información de contacto (email, teléfono)
- Preferencias de usuario (intereses mediante checkboxes)
- Validación básica (campos requeridos, formato de email)
- Agrupación lógica con fieldset y legend
- Botones de envío y reseteo

### 2. Tablas HTML Avanzadas

#### 2.1 Estructura Completa de Tablas

Las tablas se utilizan para presentar datos tabulares de manera organizada.

```html
<table border="1">
  <caption>
    Resultados Trimestrales 2025
  </caption>

  <colgroup>
    <col style="background-color: #f2f2f2" />
    <!-- Estilo para la primera columna -->
    <col span="4" style="background-color: #e6f7ff" />
    <!-- Estilo para las siguientes 4 columnas -->
  </colgroup>

  <thead>
    <tr>
      <th scope="col">Departamento</th>
      <th scope="col">Q1</th>
      <th scope="col">Q2</th>
      <th scope="col">Q3</th>
      <th scope="col">Q4</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <th scope="row">Marketing</th>
      <td>10,000€</td>
      <td>12,500€</td>
      <td>15,000€</td>
      <td>18,000€</td>
    </tr>
    <tr>
      <th scope="row">Ventas</th>
      <td>15,000€</td>
      <td>22,500€</td>
      <td>25,000€</td>
      <td>30,000€</td>
    </tr>
  </tbody>

  <tfoot>
    <tr>
      <th scope="row">Total</th>
      <td>25,000€</td>
      <td>35,000€</td>
      <td>40,000€</td>
      <td>48,000€</td>
    </tr>
  </tfoot>
</table>
```

**Elementos explicados:**

- `<caption>`: Título descriptivo de la tabla
- `<colgroup>` y `<col>`: Define grupos de columnas para aplicar estilos
- `<thead>`: Agrupa las filas de encabezado
- `<tbody>`: Agrupa el contenido principal de la tabla
- `<tfoot>`: Agrupa las filas de pie (totales, resúmenes)
- `<th scope="col|row">`: Define celdas de encabezado, especificando si son para columna o fila

#### 2.2 Combinación de Celdas

**Combinando celdas horizontalmente (colspan):**

```html
<tr>
  <th>Nombre</th>
  <th colspan="2">Teléfono</th>
</tr>
<tr>
  <td>Juan Pérez</td>
  <td>555-1234</td>
  <td>555-5678</td>
</tr>
```

**Combinando celdas verticalmente (rowspan):**

```html
<tr>
  <th>Nombre</th>
  <td>Juan Pérez</td>
</tr>
<tr>
  <th rowspan="2">Teléfonos</th>
  <td>555-1234</td>
</tr>
<tr>
  <td>555-5678</td>
</tr>
```

#### 2.3 Tablas para Accesibilidad

```html
<table>
  <caption>
    Horario de Clases
  </caption>
  <thead>
    <tr>
      <th scope="col">Hora</th>
      <th scope="col">Lunes</th>
      <th scope="col">Martes</th>
      <th scope="col">Miércoles</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">9:00 - 10:00</th>
      <td>Matemáticas</td>
      <td>Historia</td>
      <td>Ciencias</td>
    </tr>
    <tr>
      <th scope="row">10:00 - 11:00</th>
      <td>Literatura</td>
      <td>Física</td>
      <td>Inglés</td>
    </tr>
  </tbody>
</table>
```

**Buenas prácticas para tablas accesibles:**

- Usar `<caption>` para describir el propósito de la tabla
- Utilizar `<th>` para celdas de encabezado
- Especificar `scope="col"` o `scope="row"` en los encabezados
- Estructurar correctamente con `<thead>`, `<tbody>` y `<tfoot>`
- Evitar diseños complejos que dificulten la lectura por tecnologías asistivas

#### 2.4 Ejercicio Práctico: Horario Semanal

**Ejercicio:** Crear un horario semanal con:

- Encabezados para los días de la semana
- Encabezados para las horas del día
- Combinación de celdas para actividades que ocupan más de una hora
- Uso adecuado de los elementos `<thead>`, `<tbody>`, `<th scope="col|row">`
- Incluir una leyenda explicativa con `<caption>`

### 3. Elementos HTML5 Semánticos Avanzados

#### 3.1 Navegación y Estructura

**Elemento `<nav>`:**

```html
<nav>
  <ul>
    <li><a href="index.html">Inicio</a></li>
    <li><a href="servicios.html">Servicios</a></li>
    <li><a href="nosotros.html">Sobre nosotros</a></li>
    <li><a href="contacto.html">Contacto</a></li>
  </ul>
</nav>
```

**Elemento `<main>`:**

```html
<main>
  <h1>Título principal de la página</h1>
  <p>
    Contenido principal de la página. Este es el contenido único que no se
    repite en otras páginas.
  </p>

  <article>
    <h2>Artículo destacado</h2>
    <p>Contenido del artículo...</p>
  </article>
</main>
```

**Elemento `<aside>`:**

```html
<aside>
  <h3>Artículos relacionados</h3>
  <ul>
    <li><a href="#">Artículo 1</a></li>
    <li><a href="#">Artículo 2</a></li>
    <li><a href="#">Artículo 3</a></li>
  </ul>
</aside>
```

**Elemento `<figure>` y `<figcaption>`:**

```html
<figure>
  <img src="grafico-ventas.jpg" alt="Gráfico de ventas del año 2025" />
  <figcaption>Figura 1: Análisis de ventas del primer semestre 2025</figcaption>
</figure>
```

#### 3.2 Estructura de Página Completa con HTML5 Semántico

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Sitio Web Semántico</title>
</head>
<body>
    <header>
        <h1>Mi Sitio Web</h1>
        <nav>
            <ul>
                <li><a href="#inicio">Inicio</a></li>
                <li><a href="#blog">Blog</a></li>
                <li><a href="#servicios">Servicios</a></li>
                <li><a href="#contacto">Contacto</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section id="destacados">
            <h2>Contenido Destacado</h2>
            <article>
                <h3>Artículo 1</h3>
                <p>Resumen del artículo...</p>
                <figure>
                    <img src="imagen.jpg" alt="Descripción de la imagen">
                    <figcaption>Imagen relacionada con el artículo</figcaption>
                </figure>
            </article>
        </section>

        <section id="blog">
            <h2>Blog</h2>
            <article>
                <header>
                    <h3>Título del Post</h3>
                    <p>Publicado por <address>Juan Pérez</address> el <time datetime="2025-04-09">9 de abril de 2025</time></p>
                </header>
                <p>Contenido del post...</p>
                <footer>
                    <p>Etiquetas: <mark>HTML5</mark>, <mark>Web</mark></p>
                </footer>
            </article>
        </section>
    </main>

    <aside>
        <h2>Contenido Relacionado</h2>
        <section>
            <h3>Posts populares</h3>
            <ul>
                <li><a href="#">Post 1</a></li>
                <li><a href="#">Post 2</a></li>
            </ul>
        </section>
    </aside>

    <footer>
        <p>&copy; 2025 Mi Sitio Web</p>
        <address>
            Contacto: <a href="mailto:info@misitio.com">info@misitio.com</a>
        </address>
        <nav>
            <ul>
                <li><a href="privacidad.html">Política de privacidad</a></li>
                <li><a href="terminos.html">Términos de uso</a></li>
            </ul>
        </nav>
    </footer>
</body>
</html>
```

**Ventajas de usar elementos semánticos:**

- Mejora la accesibilidad para personas con discapacidades
- Facilita el SEO (posicionamiento en buscadores)
- Hace el código más legible y mantenible
- Proporciona consistencia entre diferentes páginas y sitios web
- Ayuda a los navegadores y lectores de pantalla a interpretar el contenido

#### 3.3 Elementos de Texto Semánticos

```html
<address>
  Empresa S.A.<br />
  Calle Principal, 123<br />
  Ciudad, País<br />
  <a href="mailto:info@empresa.com">info@empresa.com</a>
</address>

<time datetime="2025-04-09T15:30:00">9 de abril de 2025, 15:30</time>

<mark>Texto resaltado</mark>

<details>
  <summary>Haz clic para más información</summary>
  <p>
    Este es el contenido detallado que se muestra al hacer clic en el resumen.
  </p>
</details>

<abbr title="HyperText Markup Language">HTML</abbr>

<cite>El Quijote</cite> de Miguel de Cervantes

<blockquote cite="https://fuente.com/cita">
  <p>Esta es una cita extensa de otra fuente.</p>
  <footer>— Autor de la cita</footer>
</blockquote>

<q cite="https://fuente.com/cita">Esta es una cita corta en línea.</q>
```

#### 3.4 Ejercicio Práctico: Página Web Semántica

**Ejercicio:** Crear una página web completamente semántica sobre un tema de interés que incluya:

- Encabezado con logo y navegación
- Contenido principal con varias secciones y artículos
- Barra lateral con contenido relacionado
- Pie de página con información de contacto
- Uso correcto de todos los elementos semánticos vistos

### 4. Multimedia y Elementos Embebidos

#### 4.1 Audio y Video

HTML5 introdujo los elementos `<audio>` y `<video>` para reproducir contenido multimedia sin necesidad de plugins.

**Audio:**

```html
<audio controls autoplay muted loop>
  <source src="audio.mp3" type="audio/mpeg" />
  <source src="audio.ogg" type="audio/ogg" />
  Tu navegador no soporta el elemento de audio.
</audio>
```

**Video:**

```html
<video width="640" height="360" controls poster="imagen-previa.jpg">
  <source src="video.mp4" type="video/mp4" />
  <source src="video.webm" type="video/webm" />
  <track
    src="subtitulos-es.vtt"
    kind="subtitles"
    srclang="es"
    label="Español"
  />
  <track
    src="subtitulos-en.vtt"
    kind="subtitles"
    srclang="en"
    label="English"
  />
  Tu navegador no soporta el elemento de video.
</video>
```

**Atributos importantes:**

- `controls`: Muestra los controles de reproducción
- `autoplay`: Inicia la reproducción automáticamente (no recomendado por accesibilidad)
- `muted`: Silencia el audio inicialmente
- `loop`: Reproduce en bucle
- `poster`: Imagen que se muestra antes de reproducir el video
- `preload`: Sugiere si debe precargarse (`auto`, `metadata`, `none`)
- `width` y `height`: Dimensiones del reproductor

**El elemento `<track>`:**

- Permite añadir subtítulos, descripciones o capítulos
- Usa archivos WebVTT (extensión .vtt)
- Atributos: `kind` (subtitles, captions, descriptions, chapters, metadata), `srclang`, `label`

#### 4.2 Iframes

Los iframes permiten incorporar contenido de otros sitios web dentro de tu página.

```html
<iframe
  src="https://www.youtube.com/embed/video_id"
  width="560"
  height="315"
  title="Video de YouTube"
  frameborder="0"
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
  allowfullscreen
>
</iframe>
```

**Consideraciones de seguridad:**

- Usar el atributo `sandbox` para restringir permisos
- Siempre incluir el atributo `title` para accesibilidad
- Ser consciente de que los iframes pueden ralentizar la carga de la página
- Tener cuidado con el contenido de terceros por motivos de privacidad y seguridad

**Ejemplos comunes de uso:**

- Videos de YouTube, Vimeo, etc.
- Mapas de Google Maps
- Widgets de redes sociales
- Contenido embebido de otros sitios

#### 4.3 Elementos Canvas y SVG

HTML5 introdujo capacidades gráficas con `<canvas>` y soporte mejorado para `<svg>`.

**Canvas (para gráficos generados por JavaScript):**

```html
<canvas id="miCanvas" width="500" height="300">
  Tu navegador no soporta el elemento canvas.
</canvas>
```

**SVG (gráficos vectoriales escalables):**

```html
<svg width="200" height="200" viewBox="0 0 200 200">
  <rect x="50" y="50" width="100" height="100" fill="blue" />
  <circle cx="100" cy="100" r="50" fill="red" />
</svg>
```

#### 4.4 Ejercicio Práctico: Página Multimedia

**Ejercicio:** Crear una página web que incluya:

- Un reproductor de audio con controles
- Un reproductor de video con controles y poster
- Un mapa embebido usando iframe
- Un SVG simple con formas básicas

### 5. HTML para Accesibilidad Web

#### 5.1 Principios Básicos de Accesibilidad

La accesibilidad web asegura que las personas con discapacidades puedan percibir, entender, navegar e interactuar con la web.

**Principios POUR (Perceptible, Operable, Comprensible, Robusto):**

1. **Perceptible:** La información debe ser presentada de manera que los usuarios puedan percibirla
2. **Operable:** Los usuarios deben poder operar la interfaz
3. **Comprensible:** El contenido y la operación deben ser comprensibles
4. **Robusto:** El contenido debe ser suficientemente robusto para funcionar con tecnologías actuales y futuras

#### 5.2 Atributos de Accesibilidad

**Atributo `alt` para imágenes:**

```html
<!-- Imagen informativa -->
<img
  src="grafico-ventas.jpg"
  alt="Gráfico de ventas mostrando un aumento del 25% en el último trimestre"
/>

<!-- Imagen decorativa -->
<img src="decoracion.jpg" alt="" />
```

**Atributo `lang`:**

```html
<html lang="es">
  <!-- Fragmento en otro idioma -->
  <p>Como dijo Shakespeare: <span lang="en">To be or not to be</span></p>
</html>
```

**Atributos `aria-*`:**

```html
<button aria-expanded="false" aria-controls="menu">Menú</button>
<div id="menu" aria-hidden="true">
  <!-- Contenido del menú -->
</div>
```

**Etiquetado de formularios:**

```html
<!-- Usando el atributo for -->
<label for="nombre">Nombre:</label>
<input type="text" id="nombre" name="nombre" />

<!-- Usando aria-labelledby -->
<div id="instrucciones">Ingresa tu nombre completo</div>
<input type="text" aria-labelledby="instrucciones" />

<!-- Usando aria-label -->
<input type="search" aria-label="Buscar en el sitio" />
```

#### 5.3 Estructura de Página Accesible

```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Página Accesible</title>
  </head>
  <body>
    <header>
      <h1>Título Principal</h1>
      <nav aria-label="Navegación principal">
        <ul>
          <li>
            <a href="#contenido" class="skip-link"
              >Saltar al contenido principal</a
            >
          </li>
          <li><a href="#inicio">Inicio</a></li>
          <li><a href="#servicios">Servicios</a></li>
        </ul>
      </nav>
    </header>

    <main id="contenido" tabindex="-1">
      <section id="servicios" aria-labelledby="servicios-titulo">
        <h2 id="servicios-titulo">Nuestros Servicios</h2>
        <!-- Contenido de la sección -->
      </section>
    </main>

    <footer role="contentinfo">
      <p>Derechos reservados &copy; 2025</p>
    </footer>
  </body>
</html>
```

**Buenas prácticas:**

- Incluir enlaces para saltar al contenido principal
- Usar correctamente los encabezados (`<h1>` a `<h6>`) para estructurar el contenido
- Asegurar que la página sea navegable por teclado usando `tabindex`
- Utilizar atributos ARIA cuando sea necesario
- Mantener un contraste adecuado entre texto y fondo

#### 5.4 Ejercicio Práctico: Mejorar la Accesibilidad

**Ejercicio:** Tomar una página previamente creada y mejorar su accesibilidad:

- Añadir descripciones alt a todas las imágenes
- Verificar la estructura de encabezados
- Asegurar que todos los formularios tengan etiquetas asociadas
- Añadir enlaces para saltar al contenido principal
- Verificar que se puede navegar por la página usando solo el teclado

### 6. HTML y Metadatos

#### 6.1 La Sección `<head>` en Detalle

La sección `<head>` contiene metadatos que no se muestran en la página pero son esenciales para SEO, redes sociales y configuración del navegador.

```html
<head>
  <!-- Codificación de caracteres -->
  <meta charset="UTF-8" />

  <!-- Viewport para dispositivos móviles -->
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <!-- Título de la página (aparece en la pestaña del navegador) -->
  <title>Título completo y descriptivo de la página</title>

  <!-- Descripción para motores de búsqueda -->
  <meta
    name="description"
    content="Descripción concisa de la página para mostrar en resultados de búsqueda. Máximo 150-160 caracteres."
  />

  <!-- Palabras clave (menos relevante actualmente para SEO) -->
  <meta name="keywords" content="html, tutorial, web, desarrollo" />

  <!-- Autor -->
  <meta name="author" content="Nombre del Autor" />

  <!-- Control de robots de búsqueda -->
  <meta name="robots" content="index, follow" />
  <!-- Alternativas: noindex, nofollow, none, noarchive -->

  <!-- Favicon (icono de la pestaña) -->
  <link rel="icon" href="favicon.ico" type="image/x-icon" />
  <link rel="shortcut icon" href="favicon.ico" type="image/x-icon" />

  <!-- Favicon moderno para diferentes dispositivos -->
  <link rel="apple-touch-icon" sizes="180x180" href="/apple-touch-icon.png" />
  <link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png" />
  <link rel="icon" type="image/png" sizes="16x16" href="/favicon-16x16.png" />
  <link rel="manifest" href="/site.webmanifest" />

  <!-- Hojas de estilo (cuando aprendamos CSS) -->
  <link rel="stylesheet" href="styles.css" />

  <!-- Scripts (cuando aprendamos JavaScript) -->
  <script src="script.js" defer></script>
</head>
```

#### 6.2 Metadatos para Redes Sociales

**Open Graph (para Facebook, LinkedIn, etc.):**

```html
<meta property="og:title" content="Título para compartir en redes sociales" />
<meta
  property="og:description"
  content="Descripción que aparecerá cuando se comparta en redes sociales."
/>
<meta property="og:image" content="https://misitio.com/imagen-compartir.jpg" />
<meta property="og:url" content="https://misitio.com/pagina.html" />
<meta property="og:type" content="website" />
```

**Twitter Card:**

```html
<meta name="twitter:card" content="summary_large_image" />
<meta name="twitter:site" content="@nombreusuario" />
<meta name="twitter:title" content="Título para Twitter" />
<meta name="twitter:description" content="Descripción para Twitter." />
<meta name="twitter:image" content="https://misitio.com/imagen-twitter.jpg" />
```

#### 6.3 Favicons y Configuración de Página

**Favicon tradicional:**

```html
<link rel="icon" href="favicon.ico" type="image/x-icon" />
```

**Favicon moderno con varios tamaños:**

```html
<link rel="apple-touch-icon" sizes="180x180" href="/apple-touch-icon.png" />
<link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png" />
<link rel="icon" type="image/png" sizes="16x16" href="/favicon-16x16.png" />
<link rel="manifest" href="/site.webmanifest" />
<link rel="mask-icon" href="/safari-pinned-tab.svg" color="#5bbad5" />
<meta name="msapplication-TileColor" content="#da532c" />
<meta name="theme-color" content="#ffffff" />
```

**Configuración de tema de color:**

```html
<meta name="theme-color" content="#4285f4" />
```

#### 6.4 Ejercicio Práctico: Configuración de Metadatos

**Ejercicio:** Crear una página HTML con metadatos completos:

- Título, descripción y palabras clave
- Configuración de Open Graph para compartir en redes
- Favicons básicos
- Configuración de robots
- Viewport para dispositivos móviles

### 7. HTML y Características Avanzadas

#### 7.1 Atributos de datos personalizados

Los atributos `data-*` permiten almacenar información adicional en elementos HTML.

```html
<article
  data-id="12345"
  data-categoria="tecnologia"
  data-autor="juan"
  data-fecha="2025-04-09"
>
  <h2>Título del artículo</h2>
  <p>Contenido del artículo...</p>
</article>
```

**Uso:**

- Guardar datos para ser utilizados por JavaScript
- No afectan la presentación visual
- Útiles para APIs, filtros, ordenación, etc.
- Comienzan siempre con `data-` seguido de un nombre descriptivo

#### 7.2 Microdatos y Schema.org

Los microdatos ayudan a los motores de búsqueda a entender el contenido de la página.

```html
<div itemscope itemtype="https://schema.org/Person">
  <h2 itemprop="name">María Gómez</h2>
  <p>Profesión: <span itemprop="jobTitle">Desarrolladora Web</span></p>
  <p>
    Compañía:
    <span
      itemprop="worksFor"
      itemscope
      itemtype="https://schema.org/Organization"
    >
      <span itemprop="name">Web Solutions S.A.</span>
    </span>
  </p>
  <p>
    Email:
    <a href="mailto:maria@ejemplo.com" itemprop="email">maria@ejemplo.com</a>
  </p>
</div>
```

**Atributos de microdatos:**

- `itemscope`: Define un nuevo elemento
- `itemtype`: Especifica el tipo según schema.org
- `itemprop`: Define una propiedad del elemento

**Tipos comunes de Schema.org:**

- Person
- Organization
- Product
- Event
- Recipe
- Article
- LocalBusiness
- Review

#### 7.3 Atributos Avanzados

**Atributo `contenteditable`:**

```html
<div contenteditable="true">Este texto puede ser editado por el usuario.</div>
```

**Atributo `spellcheck`:**

```html
<textarea spellcheck="true">
    El corrector ortográfico estará activado para este texto.
</textarea>
```

**Atributo `draggable`:**

```html
<div draggable="true">
  Este elemento se puede arrastrar (requiere JavaScript para funcionalidad
  completa).
</div>
```

**Atributo `hidden`:**

```html
<div hidden>Este contenido está oculto.</div>
```

**Atributo `tabindex`:**

```html
<div tabindex="0">Este elemento puede recibir el foco del teclado.</div>
<div tabindex="-1">
  Este elemento puede recibir el foco mediante JavaScript, pero no al navegar
  con Tab.
</div>
<div tabindex="1">Este elemento será el primero en el orden de tabulación.</div>
```

#### 7.4 Ejercicio Práctico: Usar Características Avanzadas

**Ejercicio:** Crear una página web que incluya:

- Elementos con atributos data personalizados
- Implementación de Schema.org para una receta o producto
- Uso de contenteditable para un área editable
- Implementación adecuada de tabindex para navegación de teclado

### 8. Estructura de Proyecto Web

#### 8.1 Organización de Archivos y Carpetas

Una buena estructura de proyecto facilita el mantenimiento y escalabilidad.

```
proyecto/
├── index.html           # Página principal
├── pages/               # Otras páginas
│   ├── contacto.html
│   ├── servicios.html
│   └── nosotros.html
├── assets/              # Recursos estáticos
│   ├── images/          # Imágenes
│   │   ├── logo.png
│   │   └── banner.jpg
│   ├── css/            # Estilos (para más adelante)
│   │   └── styles.css
│   ├── js/             # Scripts (para más adelante)
│   │   └── main.js
│   └── fonts/          # Fuentes personalizadas
├── favicon.ico          # Favicon principal
└── README.md            # Documentación del proyecto
```

#### 8.2 Nomenclatura y Mejores Prácticas

**Nombres de archivos:**

- Usar minúsculas para evitar problemas con servidores que distinguen mayúsculas/minúsculas
- Evitar espacios (usar guiones o guiones bajos)
- Ser descriptivo pero conciso
- Ser consistente con la extensión (.html, no .htm)

**Ejemplo:**

```
✅ pagina-de-contacto.html
✅ servicios_principales.html
❌ PáginaDeContacto.html
❌ página contacto.html
```

**Estructura interna del HTML:**

- Mantener una indentación consistente (2 o 4 espacios)
- Organizar el código en secciones lógicas con comentarios
- Priorizar la legibilidad

#### 8.3 Sitios Multipágina vs. Página Única

**Sitio multipágina:**

- Separar el contenido en varias páginas HTML independientes
- Navegar entre ellas mediante enlaces
- Ejemplo: `index.html`, `productos.html`, `contacto.html`

```html
<nav>
  <ul>
    <li><a href="index.html">Inicio</a></li>
    <li><a href="productos.html">Productos</a></li>
    <li><a href="contacto.html">Contacto</a></li>
  </ul>
</nav>
```

**Sitio de página única:**

- Todo el contenido en una sola página HTML
- Navegación mediante enlaces a secciones (anclas)
- Ejemplo: `index.html` con secciones `#inicio`, `#productos`, `#contacto`

```html
<nav>
  <ul>
    <li><a href="#inicio">Inicio</a></li>
    <li><a href="#productos">Productos</a></li>
    <li><a href="#contacto">Contacto</a></li>
  </ul>
</nav>

<section id="inicio">...</section>
<section id="productos">...</section>
<section id="contacto">...</section>
```

#### 8.4 Ejercicio Práctico: Proyecto Web Completo

**Ejercicio:** Crear un sitio web completo con múltiples páginas:

- Página de inicio
- Página "Sobre nosotros"
- Página de servicios o productos
- Página de contacto con formulario
- Estructura de carpetas organizada
- Navegación entre todas las páginas
- Implementar todas las prácticas aprendidas en el curso

### 9. Validación y Depuración HTML

#### 9.1 Herramientas de Validación

**Validador de W3C:**

- Visitar [https://validator.w3.org/](https://validator.w3.org/)
- Validar por URL, subiendo un archivo o pegando el código
- Corregir todos los errores y advertencias

**Extensiones de navegador:**

- HTML Validator (disponible para Chrome, Firefox)
- Lighthouse (para Chrome, evalúa performance, accesibilidad, SEO)

#### 9.2 Errores Comunes en HTML

**Anidamiento incorrecto:**

```html
<!-- Incorrecto -->
<p>Este es un texto <strong>en negrita con <em>énfasis</strong></em>.</p>

<!-- Correcto -->
<p>Este es un texto <strong>en negrita con <em>énfasis</em></strong>.</p>
```

**Etiquetas no cerradas:**

```html
<!-- Incorrecto -->
<div>
  <p>Este párrafo no está cerrado.</p>
  <p>Esto causa problemas de estructura.</p>
</div>

<!-- Correcto -->
<div>
  <p>Este párrafo está correctamente cerrado.</p>
  <p>Así como este.</p>
</div>
```

**Atributos sin comillas:**

```html
<!-- Incorrecto -->
<a href=https://ejemplo.com>Enlace</a>

<!-- Correcto -->
<a href="https://ejemplo.com">Enlace</a>
```

**IDs duplicados:**

```html
<!-- Incorrecto -->
<div id="seccion1">Contenido</div>
<div id="seccion1">Otro contenido</div>

<!-- Correcto -->
<div id="seccion1">Contenido</div>
<div id="seccion2">Otro contenido</div>
```

#### 9.3 Depuración con las Herramientas de Desarrollador

Los navegadores modernos incluyen herramientas de desarrollador que permiten inspeccionar y depurar código HTML:

1. Abrir las herramientas de desarrollador:

   - Chrome/Edge: F12 o Ctrl+Shift+I (Cmd+Option+I en Mac)
   - Firefox: F12 o Ctrl+Shift+I
   - Safari: Cmd+Option+I

2. Usar la pestaña "Elements" o "Inspector" para:
   - Ver la estructura del DOM
   - Identificar problemas de estructura
   - Hacer cambios temporales para probar soluciones

#### 9.4 Ejercicio Práctico: Validación de Código

**Ejercicio:** Tomar una página previamente creada y:

1. Ejecutar el validador W3C
2. Identificar y corregir todos los errores
3. Revisar y mejorar según las advertencias
4. Volver a validar hasta que no haya errores

### 10. Preparación para CSS y JavaScript

#### 10.1 Integración de CSS (Conceptos Básicos)

Aunque CSS se verá en detalle en el siguiente módulo, es importante entender cómo se relaciona con HTML:

**CSS en línea:**

```html
<p style="color: blue; font-size: 16px;">Este texto tiene estilo en línea.</p>
```

**CSS interno:**

```html
<head>
  <style>
    p {
      color: blue;
      font-size: 16px;
    }
  </style>
</head>
```

**CSS externo (recomendado):**

```html
<head>
  <link rel="stylesheet" href="css/styles.css" />
</head>
```

#### 10.2 Preparación para JavaScript (Conceptos Básicos)

De manera similar, JavaScript se verá en un módulo posterior, pero es útil entender cómo se integra:

**JavaScript en línea:**

```html
<button onclick="alert('¡Hola mundo!')">Haz clic</button>
```

**JavaScript interno:**

```html
<head>
  <script>
    function saludar() {
      alert("¡Hola mundo!");
    }
  </script>
</head>
<body>
  <button onclick="saludar()">Haz clic</button>
</body>
```

**JavaScript externo (recomendado):**

```html
<head>
  <script src="js/script.js" defer></script>
</head>
```

**Atributos importantes:**

- `defer`: Retrasa la ejecución hasta que el HTML esté completamente cargado
- `async`: Ejecuta el script de forma asíncrona mientras se carga la página

#### 10.3 Atributos de Clase e ID

Los atributos `class` e `id` son fundamentales para CSS y JavaScript:

```html
<div id="cabecera" class="seccion destacado">
  Este elemento tiene un ID único "cabecera" y dos clases: "seccion" y
  "destacado".
</div>
```

**Reglas para IDs:**

- Deben ser únicos en la página
- No deben comenzar con un número
- Pueden usarse para:
  - Vincular con anclas (`<a href="#cabecera">`)
  - Seleccionar elementos específicos con CSS (`#cabecera { ... }`)
  - Seleccionar elementos con JavaScript (`document.getElementById('cabecera')`)

**Reglas para clases:**

- Pueden repetirse en múltiples elementos
- No deben comenzar con un número
- Pueden usarse para:
  - Aplicar estilos a grupos de elementos (`.destacado { ... }`)
  - Seleccionar grupos de elementos con JavaScript (`document.getElementsByClassName('destacado')`)

#### 10.4 Ejercicio Práctico: Preparación para CSS

**Ejercicio:** Preparar una página HTML para la futura aplicación de CSS y JavaScript:

1. Añadir IDs a los elementos principales (header, main, footer, etc.)
2. Añadir clases a elementos que compartirán estilos
3. Preparar la estructura de carpetas para incluir archivos CSS y JS
4. Vincular un archivo CSS externo vacío
5. Vincular un archivo JavaScript externo vacío con el atributo defer

### 11. Proyecto Final: Sitio Web Completo

#### 11.1 Especificaciones del Proyecto

**Objetivo:** Crear un sitio web completo de múltiples páginas sobre un tema de interés personal o profesional.

**Requisitos:**

- Al menos 4 páginas HTML (inicio, información, servicios/productos, contacto)
- Estructura semántica correcta
- Navegación clara entre páginas
- Formulario de contacto
- Tablas para presentar información cuando sea apropiado
- Elementos multimedia (audio, video o iframe)
- Accesibilidad básica implementada
- Metadatos correctamente configurados
- Estructura de carpetas ordenada
- Validación sin errores

#### 11.2 Etapas de Desarrollo

1. **Planificación:**

   - Definir el tema y objetivo del sitio
   - Crear un mapa del sitio (páginas y navegación)
   - Planificar la estructura de cada página

2. **Estructura HTML:**

   - Crear páginas con estructura semántica
   - Implementar navegación entre páginas
   - Añadir contenido básico

3. **Elementos Avanzados:**

   - Agregar formularios, tablas, etc.
   - Incorporar elementos multimedia
   - Implementar características avanzadas (microdatos, etc.)

4. **Optimización:**

   - Revisar y mejorar accesibilidad
   - Optimizar metadatos para SEO
   - Validar el código

5. **Entrega:**
   - Revisión final y correcciones
   - Documentación del proyecto

#### 11.3 Recursos y Referencias

**Documentación oficial:**

- [MDN Web Docs - HTML](https://developer.mozilla.org/es/docs/Web/HTML)
- [W3C HTML Specification](https://html.spec.whatwg.org/)
- [W3Schools HTML Tutorial](https://www.w3schools.com/html/)

**Herramientas:**

- [HTML Validator](https://validator.w3.org/)
- [WAVE Web Accessibility Evaluation Tool](https://wave.webaim.org/)
- [Schema.org](https://schema.org/)

**Inspiración:**

- [Awwwards](https://www.awwwards.com/) (para ver diseños modernos)
- [CodePen](https://codepen.io/) (para ejemplos de código)

### 12. Apéndice: Próximos Pasos

#### 12.1 Introducción a CSS

CSS (Cascading Style Sheets) es el lenguaje usado para definir la presentación visual de una página HTML.

**Lo que aprenderás en el módulo de CSS:**

- Selectores y propiedades
- Box model (modelo de caja)
- Diseño y posicionamiento
- Responsive design (diseño adaptable)
- Transiciones y animaciones

#### 12.2 Introducción a JavaScript

JavaScript es el lenguaje de programación que permite hacer interactivas las páginas web.

**Lo que aprenderás en el módulo de JavaScript:**

- Sintaxis básica
- Manipulación del DOM
- Eventos y manejo de formularios
- Peticiones AJAX
- APIs web

#### 12.3 Frameworks y Bibliotecas

Una vez domines HTML, CSS y JavaScript, podrás explorar:

- Frameworks CSS: Bootstrap, Tailwind CSS
- Frameworks JavaScript: React, Angular, Vue.js
- Sistemas de gestión de contenido: WordPress, Drupal

#### 12.4 Consejos para Continuar Aprendiendo

- Practica regularmente construyendo pequeños proyectos
- Participa en comunidades de desarrollo web
- Sigue blogs y canales de YouTube especializados
- Contribuye a proyectos de código abierto
- Mantente actualizado con las nuevas especificaciones y estándares
