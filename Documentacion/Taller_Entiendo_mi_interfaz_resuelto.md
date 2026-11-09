# Taller: Entiendo mi interfaz de Google Stitch

## Alcance

Este análisis corresponde a `Vista/horarios.html.html`, pantalla de horarios
del torneo Valorant Masters 2025. El archivo combina HTML, clases utilitarias
de Tailwind, estilos propios y JavaScript en una sola página.

## Parte 1. Anatomía del HTML

### 1. Esqueleto del documento

El documento comienza con `<!DOCTYPE html>`, que activa el modo estándar de
HTML5. `<html lang="es">` contiene la página e informa que su idioma principal
es español. `<head>` reúne metadatos, título, fuentes y recursos de estilo;
`<body>` contiene la interfaz visible y sus controles.

Si se elimina `lang="es"`, los lectores de pantalla pueden pronunciar el texto
con una voz o reglas de otro idioma. También se dificulta que el navegador y
otras herramientas identifiquen correctamente el idioma de la página.

### 2. El `head`

- `meta charset="utf-8"` permite representar correctamente tildes y otros
  caracteres.
- El `meta viewport` adapta el ancho al dispositivo. En este archivo también
  limita el zoom (`maximum-scale=1.0`, `user-scalable=no`); conviene retirar
  esas restricciones para que el usuario pueda ampliar el contenido.
- `<title>` establece el título de la pestaña: “Game-Tournament - Horarios
  Oficiales”.
- No hay una etiqueta `meta name="description"`; se recomienda añadir una
  descripción breve de la pantalla.
- Los `<link>` cargan Space Grotesk, Space Mono e iconos Material Symbols
  desde Google Fonts.
- No hay una hoja CSS externa. Los estilos propios están en `<style>` y
  Tailwind se carga con un `<script>` de CDN y se configura en otro `<script>`.

### 3. Mapa de la página

```text
html (lang="es")
├── head
│   ├── charset, viewport y title
│   ├── enlaces a fuentes e iconos
│   ├── style (reglas base)
│   └── configuración y carga de Tailwind
└── body
    ├── header (torneo, notificaciones y perfil)
    ├── main
    │   ├── banner de estado y acciones
    │   ├── selector de días/fases
    │   ├── filtro de transmisiones
    │   ├── cronograma con cuatro tarjetas de partidos
    │   ├── resumen y sincronización de calendario
    │   ├── modal de publicación
    │   ├── toast de notificación
    │   └── script de interacciones
    └── nav (barra inferior de navegación)
```

La página usa `header`, `main` y `nav`, pero no contiene `section` ni
`footer`. Una mejora semántica sería reemplazar el contenedor genérico que
agrupa el cronograma por una sección con un título asociado:

```html
<section aria-labelledby="schedule-heading">
  <h2 id="schedule-heading">Cronograma operativo</h2>
  <!-- tarjetas de partidos -->
</section>
```

### 4. Semántica

- `header` identifica el encabezado del torneo.
- `main` delimita el contenido principal de la pantalla.
- `nav` identifica los enlaces de navegación persistente.

Estas etiquetas describen la función del contenido y ayudan a la navegación
asistida; un `<div>` solo crea un contenedor sin significado. La sección de
partidos es una candidata clara para `<section>` con un encabezado.

### 5. Elementos clave

- **Enlaces:** la barra inferior contiene `<a>` para Inscripciones, Brackets,
  Horarios y Torneo. Todos tienen `href="#"`, así que actualmente son destinos
  de ejemplo y no navegan a páginas reales.
- **Imágenes:** el logo superior tiene `src` y un `alt` descriptivo. El perfil
  usa `alt="Profile"`, que podría describirse mejor. Los logos de los equipos
  tienen `data-alt`, pero no `alt`; `data-alt` no sustituye el texto
  alternativo accesible. Se recomienda, por ejemplo,
  `alt="Logo del equipo KRÜ Academy"`.
- **Controles:** los selectores de fase y filtros son `<button>`. No hay
  `<ul>`/`<li>` ni un `<form>` en esta interfaz.
- **Etiqueta y campo:** `<label for="toggle-calendar-sync">` está asociado al
  checkbox `id="toggle-calendar-sync"`, lo que permite identificar el control.

El atributo `alt` proporciona una alternativa textual cuando una imagen no se
carga y permite que lectores de pantalla comuniquen su contenido.

### 6. `class` e `id`

`class` se repite para aplicar estilos/utilidades a varios elementos; por
ejemplo, `flex`, `p-4` o `text-primary-container`. `id` identifica un elemento
único; por ejemplo, `btn-publish-main` permite que JavaScript encuentre el
botón de publicación y `toggle-calendar-sync` conecta el checkbox con su
`label`. El mismo `id` no debe repetirse.

## Parte 2. CSS esencial

### 1. Dónde vive el estilo

Hay tres mecanismos:

1. **CSS externo:** se enlaza con `<link rel="stylesheet">`; facilita
   reutilizar y mantener estilos entre páginas. No se usa para los estilos
   propios de esta pantalla.
2. **Bloque `<style>` en el `head`:** sí se usa para reglas base como
   `html, body`, `.pb-safe` y `::-webkit-scrollbar`.
3. **Atributo `style`:** permitiría escribir CSS en un elemento concreto;
   no se observan atributos `style` en el HTML.

Además, Tailwind se carga desde un CDN y la mayoría de los estilos visuales se
expresan con clases en el atributo `class`.

### 2. Selectores

- Selector de etiqueta existente: `html, body { ... }`.
- Selector de clase existente: `.pb-safe { ... }`.
- Selector de id: no hay reglas CSS propias con `#id`. Como ejemplo de cómo se
  escribiría una, `#modal-publish-confirm { ... }` seleccionaría el modal.
  En el archivo el `id` del modal se usa desde JavaScript, no como selector CSS.

Las clases de Tailwind también se traducen a reglas CSS generadas por Tailwind;
por ejemplo, `p-4` aplica relleno y `flex` activa Flexbox.

### 3. Modelo de caja

Cada elemento se presenta como una caja con contenido, padding, borde y
margen. En las tarjetas, `p-4` separa el contenido de los bordes, `border`
dibuja el contorno y `rounded-xl` redondea las esquinas. Si se quita el
padding, los nombres y logos quedan pegados al borde de la tarjeta.

### 4. Colores y tipografía

- Fondo principal: `#111317`.
- Naranja de acción: `#ff5e00`, configurado como `primary-container`.
- Cian de apoyo: `#00eefc`.
- Superficies: tonos como `#1a1c20` y `#282a2e`.
- Tipografía de títulos y texto: Space Grotesk.
- Tipografía monoespaciada para etiquetas técnicas: Space Mono.

La paleta oscura con acentos naranja y cian da contraste visual a estados,
horarios y transmisiones.

### 5. Distribución (layout)

El archivo usa Flexbox en encabezados, botones y filas, por ejemplo
`flex items-center justify-between gap-3`. Usa CSS Grid en la distribución
de equipos (`grid-cols-[1fr_auto_1fr]`) y en datos de servidor/comentaristas
(`grid-cols-2`).

- `justify-content`/`justify-between` distribuye elementos en el eje principal.
- `align-items` los alinea en el eje transversal.
- `gap` define el espacio entre elementos sin agregar márgenes individuales.

### 6. Responsive

El `meta viewport`, `max-w-md` y la navegación fija inferior apuntan primero a
móvil. `sm:items-center` centra el modal a partir del breakpoint `sm` de
Tailwind (640 px por defecto); por debajo, `items-end` lo alinea al borde
inferior. No hay media queries propias ni un conjunto amplio de variantes
para tablet y escritorio. Además, `width:100vw` puede
provocar desbordamiento horizontal en algunos contextos. Una mejora sería
usar `width:100%`, limitar el contenido con un contenedor y probar variantes
`sm:`/`md:` con el inspector del navegador.

### 7. Estados

`hover:brightness-110` ilumina el botón de publicación al pasar el puntero;
`active:scale-[0.99]` lo reduce levemente al presionarlo. También aparecen
clases `hover:text-white` y `hover:border-*` en botones y enlaces. No se
observa una variante explícita `focus-visible`; conviene agregar un indicador
de foco visible para navegación con teclado.

### Tabla de evidencia: clase/regla, efecto y ubicación

| Clase o regla | Efecto | Ubicación |
|---|---|---:|
| `<!DOCTYPE html>` | Activa el modo estándar de HTML5 | 1 |
| `lang="es"` y `meta charset` | Declara idioma y codificación | 1 |
| `meta viewport` | Configura la vista en dispositivos móviles | 1 |
| `@layer base` | Agrupa estilos base propios | 1 |
| `.pb-safe` / `.pt-safe` | Respeta las áreas seguras del dispositivo | 1 |
| `primary-container: #ff5e00` | Define el color naranja de acento | 31 |
| `flex items-center justify-between` | Alinea y distribuye elementos en fila | 77 |
| `grid-cols-[1fr_auto_1fr]` | Ordena los dos equipos alrededor del indicador VS | 200 |
| `p-4` | Añade padding de 1 rem | 198 |
| `hover:brightness-110` | Aumenta el brillo al pasar el puntero | 94 |
| `active:scale-[0.99]` | Reduce el botón mientras se presiona | 94 |
| `max-w-md` | Limita el ancho del resumen flotante | 497 |
| `sm:items-center` | Cambia la alineación del modal en breakpoint `sm` | 526 |
| `id="btn-publish-main"` | Identifica el botón para el manejador JS | 94 |
| `label for` / `input id` | Asocia el texto con el checkbox | 513–515 |
| `::-webkit-scrollbar` | Oculta la barra de desplazamiento en WebKit | 1 |

Las líneas corresponden a `Vista/horarios.html.html`. Varias declaraciones
originales están minificadas en una sola línea; para exponer el código en la
sustentación, conviene abrir el archivo y mostrar la línea completa o usar un
editor con ajuste de línea.

## Parte 3. Modificar y romper a propósito

Estos son cambios de práctica con su resultado esperado. No se dejaron
aplicados en la pantalla final para evitar entregar la interfaz rota.

1. **Cambiar el color principal en un solo lugar.** Cambiar
   `primary-container: "#ff5e00"` por otro valor en la configuración de
   Tailwind (línea 31). Predicción: botones, etiquetas y estados que usan
   `text-primary-container`/`bg-primary-container` adoptarán el nuevo color.
   Verificación: recargar la página y revisar al menos un botón y un estado.
2. **Escribir una sección propia sin IA ni Stitch.** Esta consigna exige
   autoría personal, por eso no se redactó el contenido. Escríbela directamente
   en el editor: un título, un párrafo, una imagen con `alt` y un botón; luego
   agrega comentarios HTML propios que expliquen su función.
3. **Cambiar una fila a columna.** En una fila de controles que use
   `flex items-center justify-between`, agregar `flex-col` y ajustar la
   alineación, por ejemplo `flex flex-col items-start gap-2`. Predicción:
   los controles se apilan verticalmente y ocupan más alto; revierte el cambio
   después de registrar el resultado.
4. **Quitar padding y observar.** En una tarjeta de partido, quitar
   temporalmente `p-4`. Predicción: el texto y los logos quedan más cerca del
   borde, disminuye la separación y la tarjeta pierde legibilidad. Registra
   lo que observes en el navegador y vuelve a poner `p-4`.

| Reto | Predicción | Qué comprobar | Por qué | Cambio temporal |
|---|---|---|---|---|
| Color principal | Cambia el acento naranja de forma global | Botón, etiquetas y estados | Comparten el token `primary-container` | Línea 31 |
| Sección propia | Aparece un bloque semántico nuevo | Título, párrafo, imagen y botón | El contenido queda agrupado | La debe escribir el aprendiz |
| Fila a columna | Los controles quedan apilados | Espaciado y altura de la fila | `flex-col` cambia el eje principal | Añadir/quitar `flex-col` |
| Quitar padding | El contenido se acerca al borde | Separación y legibilidad | `p-4` controla el espacio interior | Quitar/restaurar `p-4` |

El reto sorpresa se realiza frente al instructor; no es posible anticipar cuál
se asignará. Completa una fila adicional con la predicción, el resultado real,
la explicación y la línea modificada después de hacerlo.

## Parte 4. Preparación de la sustentación

Para el recorrido de dos minutos, explica el documento desde `html` y `head`,
continúa por `header` y `main`, y termina en la navegación inferior. Para las
preguntas al azar, practica explicar `lang`, `meta viewport`, `p-4`,
`grid-cols-2`, `id` y `addEventListener`. En cada caso responde qué hace la
línea y qué cambia si se elimina.

### Reflexión final: borrador para personalizar

La interfaz presenta un cronograma de torneo con fases, filtros de
transmisión, partidos, servidores y acciones de publicación. Tailwind ayudó a
construir rápidamente la distribución y los estados visuales. Al revisar el
código identifiqué aspectos que conviene corregir, como completar los
atributos `alt` de los logos, añadir una descripción de página, permitir el
zoom y reemplazar enlaces `href="#"` por destinos funcionales. Aprendí que una
interfaz no se evalúa solo por su apariencia: también importan la semántica,
la accesibilidad, la adaptación a distintos anchos y comprender qué hace cada
clase. Personaliza esta reflexión con los cambios y pruebas que realmente
realices.

## Pendiente de entrega personal

El taller solicita además capturas de código comentado, un esquema del árbol
HTML dibujado o diagramado, evidencia del reto sorpresa, un PDF final y un
repositorio con al menos cinco commits y un `README.md`. Esta solución deja
el análisis y las respuestas por escrito; las capturas, el dibujo, la sección
que debe escribirse sin IA, el reto en vivo y los commits deben completarse
desde la cuenta y las pruebas reales del aprendiz.
