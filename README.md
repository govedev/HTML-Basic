
# 📚 Apuntes: Lenguajes de Marcas - Unidad 2 (HTML)

Resumen práctico para 1º DAW basado en los ejercicios de clase.

<hr>

## 1. Estructura Básica
Toda página HTML5 debe seguir esta estructura mínima:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8"> <!-- Caracteres especiales (ñ, tildes) -->
    <title>Título de la Pestaña</title>
</head>
<body>
    <!-- Todo el contenido visible va aquí -->
</body>
</html>
```

<hr>
## 2. Formato de Texto

Etiquetas para modificar la apariencia o semántica del texto.

### Encabezados

De mayor a menor importancia (`h1` a `h6`).

```html
<h1>Título Principal</h1> <h2>Subtítulo</h2>
```

### Estilos de Fuente

- **Negrita:** `<strong>Importante</strong>`
    
- Cursiva: `<i>Texto</i>
    
- Subrayado: `<u>Texto</u>
    
- Tachado: `<s>Texto</s>`
    
- Saltos de línea: `<br>` (Etiqueta vacía, no se cierra).
    
- Línea horizontal: `<hr>`
    

### Fórmulas (Superíndices y Subíndices)

- **Subíndice:** `H<sub>2</sub>O → `H₂O`
    
- **Superíndice:** `E = mc<sup>2</sup> `→ E = mc²
    

<hr>
## 3. Listas

Existen tres tipos principales. Se pueden anidar unas dentro de otras.

### Listas Ordenadas (`<ol>`)

Llevan numeración. Atributos:

- `type`: Cambia el contador (`1`,`a`,`A`, `i`, `I`).
    
- `star`: Número por el que empieza.

```html
<ol type="I"> <!-- Números Romanos -->
    <li>Primer elemento</li>
    <li>Segundo elemento</li>
</ol>
```

### Listas Desordenadas (`<ul>`)

Llevan viñetas (puntos). Atributos:

- `type`: Cambia el icono (`disc`, `circle`, `square`).

```html
<ul type="square">
    <li>Elemento con cuadrado</li>
    <li>Otro elemento</li>
</ul>
```

### Listas de Definición (`<dl>`)

Para diccionarios o glosarios. No llevan viñetas ni números.

- `<dt>`: Término a definir.
    
- `<dd>`: Definición (aparece indentada).


```html
<dl>
    <dt>HTML</dt>
    <dd>Lenguaje de marcado de hipertexto.</dd>
</dl>
```

<hr>

## 4. Enlaces e Imágenes

### Imágenes (`<img>`)

No tiene etiqueta de cierre.

- `src`: Ruta de la imagen (URL o local).
    
- `alt`: Texto alternativo si falla la imagen (importante para SEO/Accesibilidad).
    
- `width` / `height`: Tamaño en píxeles o porcentaje.

```html
<img src="logo.png" alt="Logotipo" width="100">
```

### Enlaces (`<a>`)

- `href`: Destino del enlace.
    
- `target="_blank"`: Abre en una pestaña nueva.

**Tipos de enlaces:**

1. **Web externa:** `<a href="https://google.com">Ir a Google</a>`
    
2. **Correo:** `<a href="mailto:nombre@correo.com">Enviar Email</a>`
    
3. **Ancla (Interno):**
	
	- Destino: `<a id="zona1"></a>`
	
	- Enlace: `<a href="#zona1">Ir a la Zona 1</a>`

4. **Imagen con enlace:**

```html
<a href="sitio.html"><img src="foto.jpg"></a>
```


<hr>

## 5. Tablas

Estructura cuadriculada de datos.

### Estructura Básica

- `<table>`: Contenedor (border="1" para ver bordes).
    
- `<thead>`: Cabecera de la tabla.
    
- `<tbody>`: Cuerpo de datos.
    
- `<tfoot>`: Pie de tabla.
    
- `<tr>`: Fila (Table Row).
    
- `<th>`: Celda de encabezado (negrita y centrada).
    
- `<td>`: Celda de datos normal.
    

### Fusión de Celdas (Importante)

- `rowspan="n"`: Ocupa `n` filas hacia abajo (vertical).
    
- `colspan="n"`: Ocupa `n` columnas hacia la derecha (horizontal).

**Ejemplo completo:**


```html
<table border="1">
    <thead>
        <tr>
            <th>Horario</th>
            <th>Lunes</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>9:00</td>
            <td rowspan="2">Asignatura de 2 horas</td>
        </tr>
        <tr>
            <td>10:00</td>
            <!-- Esta celda no se pone porque la ocupa el rowspan de arriba -->
        </tr>
        <tr>
            <td colspan="2">Descanso (ocupa todo el ancho)</td>
        </tr>
    </tbody>
</table>
```

---

## 6. Formularios

Recogida de datos del usuario.

### Etiqueta `<form>`

- `action`: Archivo que recibe los datos (ej: procesar.php).
    
- `method`: Cómo se envían. Normalmente GET (datos en URL) o POST (datos ocultos).

### Agrupación (`<fieldset>`)

Dibuja un recuadro alrededor de los campos.

- `<legend>`: Título integrado en el borde del fieldset.


```html
<fieldset>
    <legend>Datos Personales</legend>
    <!-- Inputs aquí -->
</fieldset>
```

### Tipos de Input

La mayoría usa la etiqueta `<input type="...">`. El atributo `name` es OBLIGATORIO para enviar datos.

|            |                                    |                                                       |
| ---------- | ---------------------------------- | ----------------------------------------------------- |
| Tipo       | Descripción                        | Ejemplo                                               |
| `text`     | Texto corto                        | `<input type="text" name="nombre">`                   |
| `password` | Contraseña (puntos)                | `<input type="password" name="clave">`                |
| `radio`    | Selección única. **Mismo `name`**. | `<input type="radio" name="sexo" value="M">`          |
| `checkbox` | Selección múltiple.                | `<input type="checkbox" name="hobbies" value="leer">` |
| `submit`   | Botón de envío                     | `<input type="submit" value="Enviar">`                |
| `reset`    | Botón de borrado                   | `<input type="reset" value="Limpiar">`                |
| `hidden`   | Campo oculto                       | `<input type="hidden" name="id_usuario" value="55">`  |

### Otros elementos de formulario

- **Select (Desplegable):**
  ```html
   <select name="ciudad">
	   <option value="mad">Madrid</option>
	   <option value="bcn" selected>Barcelona</option> <!-- selected: por defecto -->
   </select>
   ```

- **Textarea (Texto largo):**
```html
  <textarea name="comentarios" rows="5" cols="40">Texto inicial...</textarea>
   ```

- **Label (Etiqueta):** Mejora la usabilidad al hacer clic en el texto.
```html
<label for="usuario">Nombre:</label>
<input type="text" id="usuario" name="nom">
```

---

## 7. Etiquetas Semánticas (HTML5)

Organizan el contenido para buscadores y navegadores. No cambian el diseño por sí solas.

- `<header>`: Cabecera de la web (Logo, título principal).
- `<nav>`: Menú de navegación.
- `<main>`: Contenido principal (solo uno por página).
- `<section>`: Sección temática del contenido.
- `<article>`: Contenido independiente (ej: noticia, post).
- `<side>`: Contenido lateral o relacionado (barra lateral).
- `<footer>`: Pie de página (Copyright, contacto).