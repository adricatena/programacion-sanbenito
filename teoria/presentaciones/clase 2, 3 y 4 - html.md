# Curso de Introducción a HTML para Principiantes

## Módulo HTML - Estructura y Fundamentos

### 1. Introducción a HTML

#### 1.1 ¿Qué es HTML?
HTML (HyperText Markup Language) es el lenguaje estándar utilizado para crear y estructurar páginas web. Es la piedra angular de cualquier sitio web y define la estructura básica de una página. HTML no es un lenguaje de programación tradicional, sino un lenguaje de marcado que utiliza etiquetas para definir diferentes elementos en una página web.

**Puntos clave:**
- HTML significa "Lenguaje de Marcado de Hipertexto"
- Fue creado en 1993 por Tim Berners-Lee
- Es el componente más básico y fundamental de la web
- Los archivos HTML tienen la extensión .html o .htm
- HTML describe la estructura y el contenido de una página web, no su apariencia (para eso se usa CSS)
- Es interpretado por los navegadores web (Chrome, Firefox, Safari, etc.) para mostrar contenido al usuario

**Analogía para principiantes:** Si pensamos en una página web como una casa, HTML sería los planos y la estructura de la casa - las paredes, puertas, ventanas y habitaciones. No determina de qué color son las paredes o qué muebles hay (eso sería CSS y JavaScript), sino dónde están ubicados los elementos y cómo se organizan.

#### 1.2 Estructura básica de un documento HTML
Todo documento HTML sigue una estructura básica que incluye ciertos elementos obligatorios.

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi primera página web</title>
</head>
<body>
    <!-- El contenido visible de la página va aquí -->
    <h1>¡Hola Mundo!</h1>
    <p>Esta es mi primera página web.</p>
</body>
</html>
```

**Elementos esenciales:**
- `<!DOCTYPE html>`: Declara que el documento es HTML5
- `<html>`: El elemento raíz que contiene todo el documento HTML
- `<head>`: Contiene metadatos, título y enlaces a recursos externos
- `<meta charset="UTF-8">`: Define la codificación de caracteres
- `<meta name="viewport">`: Ayuda con la visualización en dispositivos móviles
- `<title>`: Define el título que aparece en la pestaña del navegador
- `<body>`: Contiene todo el contenido visible de la página

**Ejercicio práctico sugerido:** Crear un archivo HTML simple con esta estructura básica y visualizarlo en el navegador.

#### 1.3 Etiquetas y elementos
En HTML, las etiquetas son la forma en que marcamos diferentes partes del contenido para definir su estructura.

**Conceptos clave:**
- **Elemento HTML**: Compuesto por una etiqueta de apertura, contenido y una etiqueta de cierre
- **Etiqueta de apertura**: `<nombre-etiqueta>`
- **Etiqueta de cierre**: `</nombre-etiqueta>`
- **Contenido**: Lo que va entre las etiquetas de apertura y cierre
- **Elementos vacíos**: Algunas etiquetas no necesitan cierre porque no contienen contenido (ej: `<img>`, `<br>`, `<hr>`)
- **Atributos**: Información adicional sobre los elementos (ej: `<a href="https://ejemplo.com">`)

**Ejemplo:**
```html
<p>Esto es un párrafo</p>
```
- `<p>` es la etiqueta de apertura
- `Esto es un párrafo` es el contenido
- `</p>` es la etiqueta de cierre
- Todo junto forma un elemento HTML de párrafo

**Anidamiento de elementos:** Los elementos HTML pueden contener otros elementos HTML.
```html
<div>
    <h1>Título principal</h1>
    <p>Este es un <strong>párrafo importante</strong> dentro de un div.</p>
</div>
```

### 2. Etiquetas fundamentales

#### 2.1 Encabezados
Los encabezados son utilizados para definir títulos y subtítulos en una página web. HTML ofrece seis niveles de encabezados, desde `<h1>` (el más importante) hasta `<h6>` (el menos importante).

```html
<h1>Este es un encabezado de nivel 1</h1>
<h2>Este es un encabezado de nivel 2</h2>
<h3>Este es un encabezado de nivel 3</h3>
<h4>Este es un encabezado de nivel 4</h4>
<h5>Este es un encabezado de nivel 5</h5>
<h6>Este es un encabezado de nivel 6</h6>
```

**Importancia y uso:**
- `<h1>` se usa típicamente para el título principal de la página
- Debe haber solo un `<h1>` por página (buena práctica para SEO)
- Los encabezados deben usarse en orden jerárquico
- No saltar niveles (por ejemplo, no pasar de `<h1>` a `<h3>` sin usar `<h2>`)
- Los encabezados son importantes para la accesibilidad, ya que los lectores de pantalla los utilizan para navegar

**Práctica recomendada:** Crear una página con diferentes niveles de encabezados sobre un tema de interés para los estudiantes.

#### 2.2 Párrafos
El elemento `<p>` se utiliza para definir párrafos de texto en HTML.

```html
<p>Este es un párrafo. Contiene texto y puede ser tan largo como sea necesario. Los navegadores automáticamente ajustan el flujo del texto según el tamaño de la ventana.</p>
<p>Este es otro párrafo separado del anterior.</p>
```

**Características:**
- Los navegadores automáticamente agregan espacio antes y después de cada párrafo
- Los saltos de línea dentro del código HTML no afectan la visualización
- Para crear un salto de línea forzado dentro de un párrafo, se usa el elemento `<br>`

**Ejemplos adicionales:**
```html
<p>Este párrafo tiene<br>un salto de línea en medio.</p>

<p>Los espacios    múltiples    en    HTML    son    tratados    como    un    solo    espacio.</p>
```

#### 2.3 Listas (ordenadas y desordenadas)
HTML ofrece tres tipos principales de listas:

**Listas no ordenadas (`<ul>`):** Usadas cuando el orden de los elementos no es importante.
```html
<ul>
    <li>Café</li>
    <li>Té</li>
    <li>Leche</li>
</ul>
```
Se muestra como:
- Café
- Té
- Leche

**Listas ordenadas (`<ol>`):** Usadas cuando el orden de los elementos es importante.
```html
<ol>
    <li>Primero, precalienta el horno.</li>
    <li>Segundo, mezcla los ingredientes.</li>
    <li>Tercero, hornea por 20 minutos.</li>
</ol>
```
Se muestra como:
1. Primero, precalienta el horno.
2. Segundo, mezcla los ingredientes.
3. Tercero, hornea por 20 minutos.

**Atributos útiles para listas ordenadas:**
- `type`: Define el tipo de marcador (`1`, `A`, `a`, `I`, `i`)
- `start`: Define el número de inicio (para listas numéricas)

```html
<ol type="A" start="3">
    <li>Este ítem será C</li>
    <li>Este ítem será D</li>
</ol>
```

**Listas de definición (`<dl>`):** Usadas para términos y sus definiciones.
```html
<dl>
    <dt>HTML</dt>
    <dd>Lenguaje de Marcado de Hipertexto, usado para estructurar páginas web.</dd>
    
    <dt>CSS</dt>
    <dd>Hojas de Estilo en Cascada, usado para estilizar páginas web.</dd>
</dl>
```

**Listas anidadas:** Las listas pueden contener otras listas.
```html
<ul>
    <li>Café
        <ul>
            <li>Espresso</li>
            <li>Cappuccino</li>
            <li>Americano</li>
        </ul>
    </li>
    <li>Té
        <ul>
            <li>Negro</li>
            <li>Verde</li>
            <li>Herbal</li>
        </ul>
    </li>
</ul>
```

**Ejercicio sugerido:** Crear una receta con una lista ordenada para los pasos y una lista no ordenada para los ingredientes.

#### 2.4 Vínculos
Los enlaces o hipervínculos son fundamentales en HTML y se crean con la etiqueta `<a>` (anchor).

```html
<a href="https://www.ejemplo.com">Visita Ejemplo.com</a>
```

**Atributos importantes:**
- `href`: La URL de destino del enlace
- `target`: Especifica dónde abrir el enlace (`_blank` para nueva pestaña, `_self` para la misma ventana)
- `title`: Texto descriptivo que aparece al pasar el cursor

**Tipos de enlaces:**
1. **Enlaces externos** (a otros sitios web):
   ```html
   <a href="https://www.google.com" target="_blank">Ir a Google</a>
   ```

2. **Enlaces internos** (a otras páginas del mismo sitio):
   ```html
   <a href="contacto.html">Ir a la página de contacto</a>
   ```

3. **Enlaces a secciones de la misma página** (usando IDs):
   ```html
   <!-- Enlace al marcador -->
   <a href="#seccion1">Ir a la Sección 1</a>
   
   <!-- Más adelante en la página -->
   <h2 id="seccion1">Sección 1</h2>
   ```

4. **Enlaces a correos electrónicos**:
   ```html
   <a href="mailto:ejemplo@correo.com">Enviar email</a>
   ```

5. **Enlaces a números telefónicos**:
   ```html
   <a href="tel:+123456789">Llamar al servicio técnico</a>
   ```

**Consideraciones:**
- Los enlaces por defecto se muestran subrayados y en color azul
- Los enlaces visitados suelen mostrarse en color púrpura
- Estas apariencias pueden cambiarse con CSS posteriormente

**Ejercicio práctico:** Crear una página con diferentes tipos de enlaces (externos, internos, anclas, email).

#### 2.5 Imágenes
Las imágenes se insertan en HTML con la etiqueta `<img>`, que es un elemento vacío (no tiene etiqueta de cierre).

```html
<img src="ruta/a/la/imagen.jpg" alt="Descripción de la imagen">
```

**Atributos esenciales:**
- `src`: La ruta o URL de la imagen
- `alt`: Texto alternativo que describe la imagen (importante para accesibilidad)

**Atributos opcionales pero útiles:**
- `width`: Ancho de la imagen en píxeles o porcentaje
- `height`: Alto de la imagen en píxeles o porcentaje
- `title`: Texto que aparece al pasar el cursor sobre la imagen

**Tipos de rutas:**
1. **Ruta absoluta** (URL completa):
   ```html
   <img src="https://ejemplo.com/imagenes/foto.jpg" alt="Una fotografía">
   ```

2. **Ruta relativa** (desde la ubicación del archivo HTML):
   ```html
   <!-- Si la imagen está en la misma carpeta que el archivo HTML -->
   <img src="foto.jpg" alt="Una fotografía">
   
   <!-- Si la imagen está en una subcarpeta -->
   <img src="imagenes/foto.jpg" alt="Una fotografía">
   
   <!-- Si la imagen está en una carpeta superior -->
   <img src="../foto.jpg" alt="Una fotografía">
   ```

**Formatos de imagen comunes para web:**
- **JPG/JPEG**: Ideal para fotografías con muchos colores
- **PNG**: Mejor para imágenes con transparencia o con pocos colores
- **GIF**: Para animaciones simples
- **SVG**: Gráficos vectoriales que se escalan sin perder calidad
- **WebP**: Formato moderno con mejor compresión

**Buenas prácticas:**
- Siempre incluir el atributo `alt` (incluso vacío si la imagen es decorativa)
- Optimizar las imágenes para web (tamaño y peso)
- No usar imágenes excesivamente grandes
- Mantener una estructura de carpetas ordenada para las imágenes

**Imágenes como enlaces:**
```html
<a href="pagina.html">
    <img src="boton.png" alt="Ir a la página">
</a>
```

**Ejercicio recomendado:** Crear una pequeña galería de imágenes con diferentes formatos y enlaces.

### 3. Estructura semántica

#### 3.1 Secciones

HTML5 introdujo elementos semánticos que dan significado a las diferentes secciones de una página web. El elemento `<section>` representa una sección genérica de contenido.

```html
<section>
    <h2>Noticias recientes</h2>
    <p>Contenido de la sección de noticias...</p>
</section>

<section>
    <h2>Eventos próximos</h2>
    <p>Contenido de la sección de eventos...</p>
</section>
```

**Características y uso:**
- Representa una sección temática del contenido
- Generalmente incluye un encabezado (`<h1>` - `<h6>`)
- Ayuda a estructurar el documento en partes lógicas
- Mejora la accesibilidad y SEO
- No usar simplemente como contenedor para estilizar (para eso está `<div>`)

**Elemento `<div>` vs `<section>`:**
- `<div>`: No tiene significado semántico, solo agrupa contenido para styling o manipulación
- `<section>`: Representa una sección temática específica del documento

#### 3.2 Artículos

El elemento `<article>` representa contenido independiente y autocontenido que podría distribuirse o reutilizarse de forma independiente.

```html
<article>
    <h2>Cómo aprender HTML en 30 días</h2>
    <p>Publicado por <em>María García</em> el <time datetime="2025-04-01">1 de abril de 2025</time></p>
    <p>HTML puede parecer intimidante al principio, pero con práctica constante...</p>
    <!-- Más contenido del artículo -->
</article>
```

**Características y uso:**
- Representa contenido que tiene sentido por sí mismo
- Adecuado para entradas de blog, noticias, comentarios, posts en redes sociales
- Puede contener su propia estructura con encabezados, secciones, etc.
- Puede anidarse (un artículo dentro de otro)

**Ejemplos de uso apropiado:**
- Entradas de blog
- Artículos de noticias
- Comentarios de usuarios
- Reseñas de productos
- Publicaciones en foros

**Estructura típica de un artículo:**
```html
<article>
    <header>
        <h2>Título del artículo</h2>
        <p>Autor y fecha</p>
    </header>
    
    <p>Contenido del artículo...</p>
    
    <footer>
        <p>Información de copyright, enlaces relacionados, etc.</p>
    </footer>
</article>
```

#### 3.3 Headers y footers

Los elementos `<header>` y `<footer>` representan el encabezado y pie de página de una sección o de todo el documento.

**Header (`<header>`):**
```html
<header>
    <h1>Mi Sitio Web</h1>
    <nav>
        <ul>
            <li><a href="index.html">Inicio</a></li>
            <li><a href="acerca.html">Acerca de</a></li>
            <li><a href="contacto.html">Contacto</a></li>
        </ul>
    </nav>
</header>
```

**Características del `<header>`:**
- Puede contener elementos introductorios o de navegación
- Típicamente incluye el logo, título del sitio, menú de navegación
- Puede haber varios `<header>` en una página (uno principal y otros dentro de secciones)
- No confundir con el elemento `<head>` que contiene metadatos

**Footer (`<footer>`):**
```html
<footer>
    <p>&copy; 2025 Mi Sitio Web. Todos los derechos reservados.</p>
    <address>
        Contacto: <a href="mailto:info@misitio.com">info@misitio.com</a>
    </address>
    <nav>
        <ul>
            <li><a href="terminos.html">Términos de uso</a></li>
            <li><a href="privacidad.html">Política de privacidad</a></li>
        </ul>
    </nav>
</footer>
```

**Características del `<footer>`:**
- Contiene información sobre la sección o documento
- Típicamente incluye información de copyright, enlaces a políticas, contacto
- Puede haber múltiples `<footer>` en una página
- Puede contener información del autor, enlaces relacionados, etc.

### 4. Elementos adicionales importantes para principiantes

#### 4.1 Texto y formato básico
```html
<strong>Texto en negrita y con importancia semántica</strong>
<b>Texto en negrita sin importancia semántica</b>
<em>Texto en cursiva y con énfasis semántico</em>
<i>Texto en cursiva sin énfasis semántico</i>
<mark>Texto resaltado</mark>
<small>Texto pequeño (para comentarios o aclaraciones)</small>
<del>Texto eliminado</del>
<ins>Texto insertado</ins>
<sub>Texto subíndice</sub>
<sup>Texto superíndice</sup>
<code>Fragmento de código</code>
<pre>Texto preformateado 
   que    conserva    espacios
   y saltos de línea</pre>
```

#### 4.2 Tablas básicas
Las tablas se utilizan para presentar datos tabulares.

```html
<table border="1">
    <caption>Horario de clases</caption>
    <thead>
        <tr>
            <th>Hora</th>
            <th>Lunes</th>
            <th>Martes</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>9:00</td>
            <td>Matemáticas</td>
            <td>Historia</td>
        </tr>
        <tr>
            <td>10:00</td>
            <td>Ciencias</td>
            <td>Literatura</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td colspan="3">Horario sujeto a cambios</td>
        </tr>
    </tfoot>
</table>
```

**Elementos de tabla:**
- `<table>`: Define una tabla
- `<caption>`: Título de la tabla
- `<thead>`: Agrupa el contenido del encabezado
- `<tbody>`: Agrupa el contenido principal
- `<tfoot>`: Agrupa el contenido del pie
- `<tr>`: Define una fila
- `<th>`: Define una celda de encabezado
- `<td>`: Define una celda de datos

#### 4.3 Formularios simples
Los formularios permiten a los usuarios enviar datos.

```html
<form action="/procesar.php" method="post">
    <label for="nombre">Nombre:</label>
    <input type="text" id="nombre" name="nombre" required><br><br>
    
    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required><br><br>
    
    <label for="mensaje">Mensaje:</label><br>
    <textarea id="mensaje" name="mensaje" rows="4" cols="30"></textarea><br><br>
    
    <input type="submit" value="Enviar">
    <input type="reset" value="Limpiar">
</form>
```

**Elementos de formulario básicos:**
- `<form>`: Define un formulario
- `<label>`: Etiqueta para un elemento de formulario
- `<input>`: Campo de entrada (muchos tipos: text, email, password, checkbox, radio, etc.)
- `<textarea>`: Área de texto multilínea
- `<select>` y `<option>`: Lista desplegable
- `<button>`: Botón personalizable

#### 4.4 Comentarios en HTML
Los comentarios permiten incluir notas en el código que no se muestran en el navegador.

```html
<!-- Este es un comentario en HTML. No se muestra en el navegador. -->
<!-- Los comentarios pueden ocupar
     múltiples líneas -->
```

#### 4.5 Caracteres especiales
Para mostrar caracteres especiales en HTML se utilizan entidades HTML.

```html
&lt; representa <
&gt; representa >
&amp; representa &
&copy; representa ©
&quot; representa "
&apos; representa '
&nbsp; representa un espacio no rompible
```

### 5. HTML5 y navegadores

#### 5.1 Compatibilidad con navegadores
- HTML5 es compatible con todos los navegadores modernos
- Es importante probar las páginas en diferentes navegadores
- Algunos elementos o atributos nuevos pueden no funcionar en navegadores muy antiguos

#### 5.2 Validación de HTML
- Es importante escribir HTML válido siguiendo los estándares
- Existen herramientas online como el [Validador del W3C](https://validator.w3.org/) para verificar el código HTML
- Los errores de sintaxis pueden causar problemas de visualización

### 6. Ejercicios prácticos sugeridos

1. **Mi primera página web**: Crear una página personal simple con encabezados, párrafos, listas e imágenes.
2. **Mini blog**: Crear una página con varios artículos usando elementos semánticos.
3. **Recetario**: Crear una página de recetas con listas ordenadas para instrucciones y no ordenadas para ingredientes.
4. **Enlaces útiles**: Crear una página con enlaces a recursos de aprendizaje web.
5. **Formulario de contacto**: Diseñar un formulario simple para recopilar información de contacto.

### 7. Recursos adicionales para estudiantes

- [Mozilla Developer Network (MDN)](https://developer.mozilla.org/es/docs/Web/HTML) - Documentación completa sobre HTML
- [W3Schools](https://www.w3schools.com/html/) - Tutoriales y ejemplos interactivos
- [HTML5 Doctor](http://html5doctor.com/) - Guía sobre el uso de elementos HTML5
- [Codecademy](https://www.codecademy.com/learn/learn-html) - Curso interactivo de HTML
- [FreeCodeCamp](https://www.freecodecamp.org/) - Cursos gratuitos de desarrollo web
