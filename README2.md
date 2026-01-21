# Documentación Completa: Calculadora Interactiva

## Tabla de Contenidos
1. [Introducción General](#introducción-general)
2. [Estructura HTML](#estructura-html)
3. [Estilos CSS](#estilos-css)
4. [Lógica JavaScript](#lógica-javascript)
5. [Ejercicios Propuestos](#ejercicios-propuestos)
6. [Recursos Adicionales](#recursos-adicionales)

---

## Introducción General

### Descripción del Proyecto
```
CALCULADORA INTERACTIVA - VERSIÓN EDUCATIVA COMENTADA
=====================================================
Este proyecto es una calculadora completa creada con HTML, CSS y JavaScript.
Perfecta para estudiantes que están aprendiendo desarrollo web frontend.

ESTRUCTURA DEL PROYECTO:
1. HTML: Define la estructura y elementos de la página
2. CSS: Define los estilos visuales y animaciones
3. JavaScript: Maneja la lógica y funcionalidad de la calculadora

TECNOLOGÍAS UTILIZADAS:
- HTML5: Para la estructura semántica
- CSS3: Para estilos avanzados con animaciones y gradientes
- JavaScript ES6: Para la lógica de programación
- Google Fonts: Para tipografías personalizadas
```

---

## Estructura HTML

### Etiqueta `<html>`
```
Etiqueta <html>: Es el contenedor raíz de todo el documento HTML
El atributo "lang" especifica el idioma del contenido (español en este caso)
Esto ayuda a los navegadores y motores de búsqueda a entender el idioma
```

### Etiqueta `<head>`
```
Etiqueta <head>: Contiene metadatos e información sobre el documento
No es visible para el usuario, pero es esencial para el navegador
```

### Meta Charset
```
Define la codificación de caracteres del documento
UTF-8 permite usar cualquier carácter (español, emojis, símbolos, etc.)
ALTERNATIVA: charset="ISO-8859-1" (solo caracteres latinos básicos)
```

### Meta Viewport
```
Hace que la página sea responsive (se adapte a móviles y tablets)
width=device-width: El ancho de la página = ancho del dispositivo
initial-scale=1.0: Zoom inicial al 100%
SIN ESTO, la página se vería muy pequeña en móviles
```

### Title
```
Etiqueta <title>: Define el título que aparece en la pestaña del navegador
EJERCICIO: Cambia el título a "Mi Primera Calculadora"
```

### Importación de Fuentes
```
rel="preconnect": Establece una conexión anticipada con Google Fonts
Esto mejora el rendimiento al cargar las fuentes más rápido
BENEFICIO: La página carga más rápido porque se conecta antes

Importa dos familias de fuentes personalizadas:
1. Orbitron: Fuente futurista para números y títulos
2. IBM Plex Mono: Fuente monoespaciada para texto técnico

EJERCICIO ALTERNATIVO: Prueba otras fuentes como:
- Roboto (moderna y limpia)
- Montserrat (elegante)
- Source Code Pro (estilo código)
Visita: https://fonts.google.com para explorar más fuentes
```

### Estructura del Body

#### Contenedor Principal
```
<div>: Contenedor genérico (division)
class="calculator": Le asigna la clase para aplicar los estilos CSS
```

#### Marca/Logo
```
Marca o logo de la calculadora
EJERCICIO: Cambia "CALC.NEXT" por tu propio nombre
```

#### Pantalla de Visualización
```
Contenedor de la pantalla de la calculadora

Muestra la operación anterior (ej: "5 +")
id="previous": Identificador único para acceder desde JavaScript
Contenido vacío inicialmente, se llena con JavaScript

Muestra el número actual o resultado
Comienza mostrando "0"
```

#### Botones

**Botón AC (All Clear)**
```
Botón "All Clear" (limpiar todo)
class="clear": Aplica estilos específicos (ocupa 2 columnas)
onclick="clearDisplay()": Llama a la función clearDisplay() al hacer clic
AC: Texto visible en el botón

EXPLICACIÓN onclick:
Es un atributo HTML que ejecuta código JavaScript cuando se hace clic
Conecta el HTML con la funcionalidad JavaScript
```

**Botón DEL (Delete)**
```
Botón "Delete" (borrar último dígito)
FUNCIONALIDAD: Como la tecla Backspace en una calculadora
```

**Botón de División**
```
Botón de división
onclick="appendOperator('÷')": Llama a la función con el símbolo ÷
NOTA: Usamos ÷ en vez de / para que se vea más elegante
```

**Botones Numéricos**
```
Botón numérico
appendNumber('7'): Añade el número 7 a la pantalla
```

**Botón de Multiplicación**
```
Multiplicación (usamos × en vez de * para mejor apariencia)
```

**Botones de Operadores Básicos**
```
Resta
Suma
```

**Botón Punto Decimal**
```
Punto decimal para números decimales
FUNCIONALIDAD: Permite escribir 3.14, 0.5, etc.
```

**Botón Igual**
```
Botón de igual (calcula el resultado)
class="equals": Estilos especiales (ocupa 2 columnas, color destacado)
```

---

## Estilos CSS

### Introducción a CSS
```
=================================================================
SECCIÓN CSS: ESTILOS Y DISEÑO VISUAL
=================================================================
CSS (Cascading Style Sheets) controla cómo se ve el HTML
Estructura: selector { propiedad: valor; }
```

### Variables CSS
```
VARIABLES CSS: Definen colores reutilizables

:root es un selector especial que apunta al elemento raíz (html)
Las variables CSS (--nombre) se pueden usar en todo el código
VENTAJA: Cambiar un color aquí lo cambia en toda la página

--primary: Color principal: Azul oscuro casi negro para el fondo de la pantalla
--secondary: Color secundario: Azul oscuro para el fondo de la calculadora
--accent: Color de acento: Cian brillante para detalles destacados
--accent-glow: Color de brillo: Verde-cian para efectos de luminosidad
--text: Color del texto principal: Blanco azulado
--text-dim: Color del texto atenuado: Gris azulado para texto secundario
--button-bg: Color de fondo de botones normales: Azul medio
--button-hover: Color de botones al pasar el mouse: Azul más claro
--operator: Color de botones de operadores: Rosa/rojo
--operator-hover: Color de operadores al hover: Rosa más claro

EJERCICIO 1: Crea un tema diferente cambiando estos colores
- Tema claro: Fondos blancos, texto oscuro
- Tema verde matrix: Negros y verdes fosforescentes
- Tema retro: Naranjas y marrones de los 70s
```

### Reset Universal
```
RESET UNIVERSAL: Elimina estilos predeterminados del navegador

El asterisco (*) selecciona TODOS los elementos
margin: 0; Elimina el margen externo de todos los elementos
padding: 0; Elimina el relleno interno de todos los elementos

box-sizing: border-box;
Hace que padding y border se incluyan en el ancho/alto total
SIN ESTO: width: 100px + padding: 10px = 110px total
CON ESTO: width: 100px (incluye los 10px de padding)
BENEFICIO: Cálculos más predecibles y fáciles
```

### Estilos del Body
```
ESTILOS DEL BODY: Configuración de la página completa

font-family: Define la fuente principal del documento
Si 'IBM Plex Mono' no carga, usa 'monospace' (fuente genérica)

background: linear-gradient()
Gradiente de fondo diagonal (135 grados)
Comienza en azul oscuro, pasa por azul medio, termina en azul-negro
0%, 50%, 100% son las posiciones donde cambian los colores
EJERCICIO: Cambia el ángulo a 90deg para gradiente vertical

min-height: 100vh;
Altura mínima = 100% del viewport (altura visible de la ventana)
vh = viewport height (1vh = 1% de la altura de la ventana)
BENEFICIO: La página siempre ocupa toda la pantalla

display: flex;
Activa Flexbox, un sistema de diseño moderno y potente
Permite alinear y distribuir elementos fácilmente

justify-content: center; Centra horizontalmente los elementos hijos
align-items: center; Centra verticalmente los elementos hijos
padding: 20px; Añade 20px de espacio interior en todos los lados

position: relative;
Hace que el body sea el punto de referencia para elementos absolutos
Los elementos hijos con position: absolute se posicionarán respecto al body

overflow: hidden;
Oculta cualquier contenido que se salga del body
ÚTIL: Para que las animaciones de fondo no creen scroll
```

### Efectos de Fondo Animados
```
EFECTO DE FONDO ANIMADO 1: Círculo luminoso superior derecho

::before es un pseudo-elemento que crea contenido antes del body
Se usa para añadir elementos decorativos sin modificar el HTML

content: '';
Obligatorio para que ::before funcione
Vacío porque solo queremos el efecto visual, no texto

position: absolute;
Posicionamiento absoluto respecto al body (que tiene position: relative)
Permite mover el elemento libremente con top, right, bottom, left

width/height: Tamaño del círculo luminoso

background: radial-gradient()
Gradiente radial (circular) desde el centro
Comienza con cian semi-transparente (0.15 = 15% opacidad)
Se desvanece a transparente en el 70% del radio
RESULTADO: Efecto de luz difusa

top: -200px; right: -200px;
Posiciona el círculo parcialmente fuera de la pantalla
Valores negativos lo mueven hacia arriba y derecha
EFECTO: Solo se ve parte del círculo, creando ambiente

border-radius: 50%;
Hace que el cuadrado sea un círculo perfecto
50% = radio igual a la mitad del ancho/alto

animation: pulse 8s ease-in-out infinite;
Aplica la animación 'pulse' (definida más abajo)
8s = duración de 8 segundos
ease-in-out = aceleración suave al inicio y final
infinite = se repite para siempre

EFECTO DE FONDO ANIMADO 2: Círculo luminoso inferior izquierdo

::after crea contenido después del body
Similar a ::before pero para decoración posterior

animation: reverse
Reproduce la animación en dirección contraria
EFECTO: Los dos círculos pulsan de forma diferente
```

### Animación Pulse
```
DEFINICIÓN DE LA ANIMACIÓN PULSE

@keyframes define una animación personalizada
'pulse' es el nombre que le dimos para reutilizarla

0%, 100%: Estado inicial (0%) y final (100%)
transform: scale(1); Tamaño normal (100%)
opacity: 0.5; Semi-transparente (50%)

50%: Punto medio de la animación
transform: scale(1.1); 10% más grande
opacity: 0.8; Más visible (80%)

RESULTADO: El círculo crece y se hace más visible,
luego vuelve a su estado original, creando un "pulso"

EJERCICIO: Cambia scale(1.1) a scale(1.3) para un efecto más dramático
```

### Contenedor de la Calculadora
```
CONTENEDOR DE LA CALCULADORA

El punto (.) selecciona elementos por su clase
Cualquier elemento con class="calculator" tendrá estos estilos

background: var(--secondary);
Usa la variable CSS definida en :root
var() permite acceder a variables CSS

border-radius: 24px;
Esquinas redondeadas con radio de 24px
MAYOR número = esquinas más redondeadas
EJERCICIO: Prueba con 0px (cuadrado) o 50px (muy redondeado)

padding: 32px;
Espacio interior de 32px en todos los lados
Separa el contenido de los bordes

box-shadow: Múltiples sombras apiladas:
1. Sombra principal: 20px hacia abajo, 60px de difuminado, negro 50%
2. Borde sutil: 1px blanco semi-transparente
3. Luz interior (inset): Reflejo blanco en la parte superior

Sintaxis: offset-x offset-y blur spread color
EFECTO: Profundidad 3D y apariencia de cristal

max-width: 380px;
Ancho máximo de 380px
En pantallas grandes, la calculadora no crecerá más

width: 100%;
En pantallas pequeñas, usa todo el ancho disponible
Combinado con max-width, hace la calculadora responsive

position: relative; Punto de referencia para elementos hijos absolutos

z-index: 1;
Índice de apilamiento (profundidad)
Números mayores aparecen encima de números menores
AQUÍ: Asegura que la calculadora esté sobre los círculos de fondo

animation: slideIn 0.6s cubic-bezier(0.34, 1.56, 0.64, 1);
Animación de entrada cuando se carga la página
0.6s = 600 milisegundos
cubic-bezier = curva de aceleración personalizada (con rebote)
```

### Animación SlideIn
```
ANIMACIÓN DE ENTRADA: La calculadora desliza desde abajo

from: Estado inicial de la animación
opacity: 0; Completamente invisible
transform: translateY(30px) scale(0.9);
  translateY: Desplaza 30px hacia abajo
  scale: Reduce a 90% del tamaño

to: Estado final de la animación
opacity: 1; Completamente visible
transform: translateY(0) scale(1);
  translateY(0): Posición original (sin desplazamiento)
  scale(1): Tamaño normal (100%)

EFECTO: La calculadora aparece deslizándose hacia arriba
mientras se hace visible y crece al tamaño normal
```

### Barra Decorativa Superior
```
BARRA DECORATIVA SUPERIOR DE LA CALCULADORA

Pseudo-elemento antes del contenido de .calculator

position: absolute;
Se posiciona respecto a .calculator (que tiene position: relative)

top: 0; left: 0; right: 0;
Posiciona en la parte superior y ocupa todo el ancho
left: 0 y right: 0 hace que se estire horizontalmente

height: 4px; Altura de la barra: 4 píxeles

background: linear-gradient(90deg, ...)
Gradiente horizontal (90deg)
Cian → Verde-cian → Cian
EFECTO: Barra luminosa con centro más brillante

border-radius: 24px 24px 0 0;
Solo redondea las esquinas superiores
Formato: superior-izq superior-der inferior-der inferior-izq
0 = sin redondeo en las esquinas inferiores

box-shadow: 0 0 20px var(--accent);
Sombra difusa sin offset (0 0)
Difuminado de 20px en color cian
EFECTO: Resplandor neón alrededor de la barra
```

### Marca/Logo
```
MARCA O LOGO DE LA CALCULADORA

font-family: 'Orbitron', sans-serif;
Fuente futurista importada de Google Fonts

font-weight: 900;
Grosor máximo de la fuente (ultra-negrita)
Rango: 100 (fino) a 900 (muy grueso)

font-size: 14px; Tamaño pequeño para la marca

letter-spacing: 3px;
Espacio entre letras de 3px
EFECTO: Texto más espaciado y elegante

color: var(--accent); Color cian brillante
text-transform: uppercase; Convierte todo el texto a MAYÚSCULAS
margin-bottom: 24px; Espacio de 24px debajo del elemento
text-align: center; Centra el texto horizontalmente

text-shadow: 0 0 10px var(--accent);
Sombra de texto con resplandor
Sin offset (0 0), difuminado 10px
EFECTO: Texto brillante tipo neón
```

### Pantalla de la Calculadora
```
PANTALLA DE LA CALCULADORA

background: var(--primary); Fondo azul muy oscuro
border-radius: 16px; Esquinas redondeadas
padding: 24px; Espacio interior
margin-bottom: 24px; Espacio debajo antes de los botones

min-height: 100px;
Altura mínima de 100px
Garantiza espacio suficiente incluso sin números

display: flex; Activa Flexbox para organizar el contenido

flex-direction: column;
Organiza los elementos hijos en columna (vertical)
Por defecto Flexbox es horizontal (row)

justify-content: flex-end;
Alinea el contenido al final (abajo) del contenedor
EFECTO: Los números aparecen en la parte inferior

align-items: flex-end;
Alinea el contenido a la derecha
EFECTO: Los números están alineados a la derecha
(como en calculadoras reales)

border: 1px solid rgba(0, 217, 255, 0.2);
Borde de 1px en color cian semi-transparente (20%)
EFECTO: Contorno sutil brillante

position: relative; Para posicionar el pseudo-elemento ::before

overflow: hidden;
Recorta cualquier contenido que sobresalga
NECESARIO: Para que el gradiente decorativo no se salga
```

### Gradiente Decorativo de la Pantalla
```
GRADIENTE DECORATIVO DENTRO DE LA PANTALLA

content: '';
position: absolute;
top: 0; left: 0; right: 0; bottom: 0;
Ocupa toda la pantalla (se estira a todos los bordes)

background: linear-gradient(135deg, transparent 0%, rgba(0, 217, 255, 0.03) 100%);
Gradiente diagonal desde transparente a cian muy sutil
EFECTO: Brillo sutil en una esquina

pointer-events: none;
IMPORTANTE: El elemento no interfiere con clics del mouse
Los clics atraviesan este elemento decorativo
```

### Líneas de Texto en la Pantalla
```
LÍNEA SUPERIOR DE LA PANTALLA: Operación anterior

font-family: 'IBM Plex Mono', monospace;
Fuente monoespaciada para números

font-size: 16px; Tamaño más pequeño que el número actual
color: var(--text-dim); Color gris atenuado
margin-bottom: 8px; Espacio debajo antes del número actual

word-break: break-all;
Rompe palabras largas para que no se salgan
break-all: Rompe en cualquier carácter si es necesario
BENEFICIO: Evita que números largos rompan el diseño

font-weight: 300; Peso ligero de la fuente

LÍNEA PRINCIPAL DE LA PANTALLA: Número actual

font-family: 'Orbitron', sans-serif;
Fuente futurista para destacar

font-size: 40px; Tamaño grande y legible
font-weight: 700; Negrita
color: var(--text); Color blanco azulado
word-break: break-all; Rompe números largos si es necesario

text-shadow: 0 0 20px rgba(0, 217, 255, 0.3);
Resplandor cian alrededor de los números
EFECTO: Números brillantes tipo pantalla LED

line-height: 1.2;
Altura de línea = 120% del tamaño de fuente
Controla el espacio vertical entre líneas de texto
```

### Cuadrícula de Botones
```
CUADRÍCULA DE BOTONES

display: grid;
CSS Grid: Sistema de diseño en cuadrícula (filas y columnas)
Más potente que Flexbox para diseños bidimensionales

grid-template-columns: repeat(4, 1fr);
Crea 4 columnas de igual tamaño
repeat(4, 1fr) = cuatro columnas, cada una con 1 fracción del espacio
1fr = 1 fracción flexible del espacio disponible
RESULTADO: 4 columnas iguales que ocupan todo el ancho

EJERCICIO: Cambia a repeat(5, 1fr) para 5 columnas

gap: 12px;
Espacio entre elementos del grid
12px de separación entre todos los botones
VENTAJA: No necesitas margin en cada botón
```

### Estilos de Botones
```
ESTILOS BASE DE TODOS LOS BOTONES

font-family: 'Orbitron', sans-serif;
font-size: 20px;
font-weight: 700;
padding: 24px; Espacio interior: hace los botones más grandes y fáciles de tocar

border: none;
Elimina el borde predeterminado del navegador
Los botones HTML tienen un borde feo por defecto

border-radius: 12px; Esquinas redondeadas
background: var(--button-bg); Color de fondo azul medio
color: var(--text); Color del texto

cursor: pointer;
Cambia el cursor a una mano al pasar sobre el botón
Indica que es clickeable

transition: all 0.2s cubic-bezier(0.34, 1.56, 0.64, 1);
Anima TODAS las propiedades que cambien
0.2s = 200 milisegundos (rápido pero visible)
cubic-bezier = curva personalizada con efecto de rebote
EFECTO: Transiciones suaves al hacer hover

position: relative; Para el efecto de onda ::before
overflow: hidden; Recorta el efecto de onda dentro del botón

box-shadow: Dos sombras:
1. Sombra exterior: profundidad
2. Sombra interior (inset): reflejo de luz en la parte superior

display: flex; Flexbox para centrar el contenido
align-items: center; Centra verticalmente
justify-content: center; Centra horizontalmente

IMPORTANTE: Esto centra el texto/número perfectamente
Sin esto, el punto decimal podría verse desalineado
```

### Efecto de Onda en Botones
```
EFECTO DE ONDA AL HACER CLIC EN UN BOTÓN

content: '';
position: absolute;
top: 50%; left: 50%; Comienza en el centro del botón

width: 0; height: 0; Inicialmente invisible (sin tamaño)
border-radius: 50%; Forma circular
background: rgba(255, 255, 255, 0.1); Blanco semi-transparente (10%)

transform: translate(-50%, -50%);
Centra el elemento en el punto de origen
-50% mueve el elemento hacia atrás la mitad de su tamaño
NECESARIO: Para que el círculo crezca desde el centro

transition: width 0.6s, height 0.6s;
Anima el crecimiento del círculo
0.6s = 600 milisegundos (animación media-lenta)

ACTIVA EL EFECTO DE ONDA AL HACER CLIC

:active se activa mientras se mantiene presionado el botón
::before es el pseudo-elemento que creamos arriba

width: 300px; height: 300px;
El círculo crece a 300px x 300px
EFECTO: Onda que se expande desde el punto de clic
La transition hace que el crecimiento sea animado
```

### Estados de Botones
```
EFECTO HOVER: Cuando pasas el mouse sobre un botón

:hover se activa al pasar el mouse sobre el elemento

background: var(--button-hover); Cambia a un color más claro

transform: translateY(-2px);
Mueve el botón 2px hacia arriba
EFECTO: El botón "se eleva" al pasar el mouse

box-shadow: Sombra más grande y más oscura
EFECTO: El botón parece estar más alto

EFECTO AL HACER CLIC: Botón presionado

:active se activa mientras el botón está siendo presionado

transform: translateY(0);
Vuelve a la posición original
EFECTO: El botón "se hunde" al hacer clic
Retroalimentación táctil visual
```

### Botones Especiales
```
BOTONES DE OPERADORES (+, -, ×, ÷)

background: var(--operator); Color rosa/rojo distintivo
box-shadow: Sombra rosa para combinar con el color

HOVER EN OPERADORES
background: var(--operator-hover); Rosa más claro
box-shadow: Sombra rosa más intensa

BOTÓN DE IGUAL (=)

background: linear-gradient(135deg, ...)
Gradiente diagonal cian → verde-cian
EFECTO: Botón destacado y llamativo

color: var(--primary); Texto oscuro para contraste sobre fondo claro

grid-column: span 2;
Ocupa 2 columnas en el grid
EFECTO: Botón más ancho que los demás
SINTAXIS: span 2 = "expandirse 2 columnas"

box-shadow: Sombra cian brillante

HOVER EN BOTÓN DE IGUAL

filter: brightness(1.1);
Aumenta el brillo al 110%
EFECTO: El gradiente se ve más brillante
ALTERNATIVA: filter: saturate(1.2) aumenta la saturación

BOTÓN DE LIMPIAR (AC)

background: linear-gradient(135deg, #ff3366 0%, #ff6b9d 100%);
Gradiente diagonal rosa → rosa claro

grid-column: span 2; Ocupa 2 columnas (igual que el botón =)
```

### Media Query
```
MEDIA QUERY: ESTILOS PARA PANTALLAS PEQUEÑAS

@media permite aplicar estilos solo en ciertas condiciones
max-width: 480px = pantallas de 480px o menos (móviles)
BENEFICIO: Diseño responsive que se adapta al dispositivo

.calculator { padding: 24px; }
Reduce el padding en móviles (ahorra espacio)

.current { font-size: 32px; }
Números más pequeños en móviles

button { padding: 20px; font-size: 18px; }
Botones más compactos en móviles

EJERCICIO: Añade más breakpoints para tablets
@media (max-width: 768px) { ... }
```

### Animación de Botones
```
ANIMACIÓN DE ENTRADA PARA CADA BOTÓN

animation: fadeInButton 0.4s cubic-bezier(0.34, 1.56, 0.64, 1) backwards;
fadeInButton: animación definida abajo
0.4s: duración
cubic-bezier: curva con rebote
backwards: aplica el estado "from" antes de que empiece la animación

DEFINICIÓN DE LA ANIMACIÓN DE APARICIÓN DE BOTONES

from:
opacity: 0; Invisible
transform: scale(0.8); 80% del tamaño normal

to:
opacity: 1; Visible
transform: scale(1); Tamaño normal

EFECTO: Los botones aparecen creciendo suavemente

RETRASOS ESCALONADOS PARA CADA BOTÓN

Cada botón tiene un retraso (delay) ligeramente diferente
EFECTO: Los botones aparecen en secuencia, no todos a la vez
Crea una animación más dinámica y profesional

nth-child(1) selecciona el primer hijo (botón)
0.05s = 50 milisegundos de retraso antes de animar

EJERCICIO: Prueba aumentar los retrasos para un efecto más lento
O usa un bucle en JavaScript para generar estos estilos dinámicamente
```

---

## Lógica JavaScript

### Introducción
```
=================================================================
SECCIÓN JAVASCRIPT: LÓGICA Y FUNCIONALIDAD
=================================================================
JavaScript hace que la calculadora sea interactiva y funcional

CONCEPTOS CLAVE:
- Variables: Almacenan datos (números, texto, etc.)
- Funciones: Bloques de código reutilizables
- Eventos: Respuestas a acciones del usuario (clics, teclas)
- DOM: Permite modificar el HTML desde JavaScript
```

### Variables Globales
```
============================================================
VARIABLES GLOBALES: Almacenan el estado de la calculadora
============================================================

let currentValue = '0';
Almacena el número que el usuario está escribiendo actualmente
'let' declara una variable que puede cambiar
'0' es el valor inicial (la calculadora empieza mostrando 0)

EJEMPLO DE USO:
Usuario escribe 5 → currentValue = '5'
Usuario escribe 8 → currentValue = '58'

let previousValue = '';
Almacena el primer número de la operación
'' = string vacío (no hay operación previa al inicio)

EJEMPLO:
Usuario escribe "5 +" → previousValue = '5 +'

let operation = null;
Almacena el operador matemático (+, -, ×, ÷)
null = sin valor (no hay operación activa)

EJEMPLO:
Usuario hace clic en "+" → operation = '+'

let shouldResetScreen = false;
Bandera (flag) booleana que indica si debemos resetear la pantalla
false = no resetear
true = resetear en el próximo número

USO: Después de hacer clic en un operador, el siguiente número
debe empezar desde cero en vez de añadirse al actual

EJEMPLO:
Usuario: 5 + (ahora shouldResetScreen = true)
Usuario escribe 3 → pantalla muestra "3" (no "53")
```

### Referencias al DOM
```
============================================================
REFERENCIAS AL DOM: Acceso a elementos HTML
============================================================

const currentDisplay = document.getElementById('current');
document: Objeto global que representa toda la página HTML
getElementById('current'): Busca el elemento con id="current"

RESULTADO: currentDisplay ahora "apunta" al <div id="current">
Podemos usarlo para modificar lo que se muestra en pantalla

'const' = constante (la referencia no cambiará)
Aunque la referencia es constante, SÍ podemos modificar el contenido del elemento

const previousDisplay = document.getElementById('previous');
Similar al anterior, pero para el elemento con id="previous"
Muestra la operación anterior (ej: "5 +")
```

### Función updateDisplay
```
============================================================
FUNCIÓN: Actualizar la pantalla
============================================================

function updateDisplay()
'function' declara una función (bloque de código reutilizable)
updateDisplay es el nombre que le dimos
() = sin parámetros (no necesita datos de entrada)

PROPÓSITO: Sincronizar las variables JavaScript con lo que ve el usuario

currentDisplay.textContent = currentValue;
textContent: Propiedad que contiene el texto de un elemento
= (asignación): Establece el texto

EFECTO: Muestra el valor de currentValue en la pantalla principal

EJEMPLO:
Si currentValue = '42', la pantalla mostrará: 42

previousDisplay.textContent = previousValue;
Similar al anterior, actualiza la línea superior con previousValue
```

### Función appendNumber
```
============================================================
FUNCIÓN: Añadir un número a la pantalla
============================================================

function appendNumber(number)
(number) = parámetro de la función
Cuando llamamos appendNumber('7'), number tendrá el valor '7'

if (shouldResetScreen)
if = condicional (ejecuta código solo si la condición es verdadera)
Verifica si debemos resetear la pantalla

currentValue = '0';
Resetea el valor actual a '0'
Esto pasa después de hacer clic en un operador

shouldResetScreen = false;
Desactiva la bandera (ya reseteamos)

Validación: Evita múltiples puntos decimales

if (number === '.' && currentValue.includes('.')) return;

===: Operador de comparación estricta (verifica valor y tipo)
&&: Operador lógico AND (ambas condiciones deben ser verdaderas)
includes('.'): Método que verifica si el string contiene un punto
return: Sale de la función inmediatamente (no ejecuta más código)

LÓGICA: Si el usuario intenta añadir un punto Y ya hay un punto,
no hacer nada (evita números como 3.14.15)

EJERCICIO: Añade validación similar para evitar múltiples ceros al inicio

if (currentValue === '0' && number !== '.')
Reemplaza el '0' inicial si el usuario escribe un número
PERO no lo reemplaza si escribe '.' (permite 0.5)

!==: No es igual (operador de desigualdad estricta)

currentValue = number;
EJEMPLO:
Pantalla: "0" → Usuario escribe 5 → Pantalla: "5"
(No queremos que diga "05")

else:
else: Se ejecuta si la condición del 'if' es falsa

currentValue += number;
+= operador de concatenación (para strings) o suma (para números)
Añade el nuevo dígito al final del número actual

EJEMPLO:
currentValue = '12'
number = '3'
currentValue += '3' → currentValue ahora es '123'

updateDisplay();
Llama a la función para actualizar lo que se ve en pantalla
IMPORTANTE: Sin esto, los cambios solo estarían en memoria,
el usuario no vería nada
```

### Función appendOperator
```
============================================================
FUNCIÓN: Añadir un operador matemático
============================================================

function appendOperator(op)
op = operador ('+', '-', '×', '÷')

if (operation !== null) calculate();
Si ya hay una operación en curso, calcúlala primero

EJEMPLO:
Usuario: 5 + 3 +
Al hacer clic en el segundo +, calcula 5+3=8
Luego establece la nueva operación

BENEFICIO: Permite encadenar operaciones (5 + 3 + 2 + 1)

operation = op;
Guarda el operador para usarlo después en calculate()

previousValue = currentValue + ' ' + op;
Guarda el número actual y el operador en la línea superior
+ ' ' + añade un espacio para mejor legibilidad

EJEMPLO:
currentValue = '42'
op = '+'
previousValue = '42 +'

shouldResetScreen = true;
Activa la bandera: el siguiente número debe empezar desde cero
RAZÓN: Si el usuario escribió 5 +, el siguiente dígito debe
ser el inicio de un nuevo número, no añadirse al 5

updateDisplay();
Actualiza la pantalla para mostrar la operación
```

### Función calculate
```
============================================================
FUNCIÓN: Calcular el resultado
============================================================

function calculate()
Esta es la función más compleja
Realiza la operación matemática y muestra el resultado

if (operation === null || shouldResetScreen) return;
Validaciones:
1. Si no hay operación (operation === null), no hay nada que calcular
2. Si shouldResetScreen es true, significa que acabamos de hacer
   clic en un operador y no hay un segundo número todavía

||: Operador lógico OR (si cualquiera es verdadero, ejecuta return)
return: Sale de la función sin hacer nada

const prev = parseFloat(previousValue);
parseFloat(): Convierte un string a número decimal

EJEMPLO:
previousValue = '5.5 +'
parseFloat('5.5 +') = 5.5 (ignora caracteres no numéricos)

NOTA: Aunque previousValue incluye el operador, parseFloat
extrae solo la parte numérica del inicio

const current = parseFloat(currentValue);
Convierte el número actual a formato numérico

if (isNaN(prev) || isNaN(current)) return;
isNaN(): Verifica si algo "No es un Número" (is Not a Number)

VALIDACIÓN: Si alguna conversión falló, no continuar
Esto previene errores si el usuario hizo algo inesperado

let result;
Declaramos una variable para almacenar el resultado
No le damos valor inicial porque dependerá de la operación

switch (operation)
switch: Estructura de control que ejecuta diferentes códigos
según el valor de una variable

Es como múltiples if-else, pero más legible para muchas opciones

SINTAXIS:
switch (variable) {
    case valor1:
        código si variable === valor1
        break;
    case valor2:
        código si variable === valor2
        break;
    default:
        código si ningún case coincide
}

case '+': Si operation es '+'
result = prev + current; Suma los dos números
break; Sale del switch (no ejecuta los otros casos)
SIN break, el código continuaría ejecutando los siguientes casos

case '-': result = prev - current; Resta
case '×': result = prev * current; Multiplicación

NOTA: En JavaScript, * es el operador de multiplicación
Pero mostramos × al usuario porque es más claro

case '÷': División

if (current === 0)
VALIDACIÓN CRÍTICA: División por cero
No se puede dividir por 0 en matemáticas

currentValue = 'Error'; Muestra mensaje de error
previousValue = ''; Limpia la operación anterior
operation = null; Resetea el operador
updateDisplay(); Actualiza la pantalla para mostrar "Error"
return; Sale de la función sin hacer más cálculos

result = prev / current;
Si no es división por cero, divide normalmente

default:
Se ejecuta si operation no coincide con ningún caso
(no debería pasar, pero es buena práctica incluirlo)
return; Sale de la función sin hacer nada

result = Math.round(result * 100000000) / 100000000;
Redondeo para evitar errores de precisión de punto flotante

PROBLEMA: En computadoras, 0.1 + 0.2 = 0.30000000000000004
(limitaciones de cómo se almacenan números decimales)

SOLUCIÓN:
1. Multiplica por 100,000,000 (mueve 8 decimales a la izquierda)
2. Math.round() redondea al entero más cercano
3. Divide por 100,000,000 (regresa los decimales)

RESULTADO: Máximo 8 decimales de precisión, sin números raros

EJERCICIO: Prueba sin esta línea: calcula 0.1 + 0.2 y ve el resultado

currentValue = result.toString();
.toString(): Convierte el número a string (texto)
NECESARIO: currentValue debe ser string para mostrarlo y
para que appendNumber() funcione correctamente

previousValue = ''; Limpia la operación anterior
operation = null; Resetea el operador (operación completada)

shouldResetScreen = true;
Activa la bandera: si el usuario escribe otro número,
debe empezar uno nuevo (no añadirse al resultado)

EJEMPLO:
Usuario: 5 + 3 = (resultado: 8)
Usuario escribe 2 → pantalla debe mostrar "2", no "82"

updateDisplay(); Actualiza la pantalla con el resultado
```

### Función clearDisplay
```
============================================================
FUNCIÓN: Limpiar todo (botón AC)
============================================================

function clearDisplay()
Resetea la calculadora al estado inicial
Como si acabaras de abrir la página

currentValue = '0'; Pantalla principal vuelve a 0
previousValue = ''; Borra la operación anterior
operation = null; Sin operador activo
shouldResetScreen = false; Desactiva la bandera
updateDisplay(); Actualiza la pantalla

EJERCICIO: Añade un efecto de animación al limpiar
Pista: Usa setTimeout() y una clase CSS temporal
```

### Función deleteDigit
```
============================================================
FUNCIÓN: Borrar último dígito (botón DEL)
============================================================

function deleteDigit()
Borra el último carácter del número actual
Similar a la tecla Backspace

if (currentValue.length === 1)
.length: Propiedad que devuelve la cantidad de caracteres
=== 1: Si solo hay un carácter

currentValue = '0';
No dejamos la pantalla vacía, vuelve a '0'
RAZÓN: Una calculadora siempre debe mostrar algo

else: Si hay más de un carácter

currentValue = currentValue.slice(0, -1);
.slice(inicio, fin): Extrae una porción de un string
0: Desde el principio
-1: Hasta el penúltimo carácter (excluyendo el último)

EJEMPLO:
currentValue = '123'
currentValue.slice(0, -1) = '12'

ALTERNATIVA: 
currentValue = currentValue.substring(0, currentValue.length - 1)

updateDisplay(); Actualiza la pantalla
```

### Event Listener de Teclado
```
============================================================
EVENT LISTENER: Soporte para teclado
============================================================

document.addEventListener('keydown', (e) => {...})

addEventListener: Escucha eventos del usuario
'keydown': Evento que se dispara cuando se presiona una tecla
(e) => {...}: Función flecha (arrow function) de ES6
e: Objeto de evento que contiene información sobre la tecla presionada

BENEFICIO: Permite usar la calculadora con el teclado,
no solo con clics del mouse

SINTAXIS TRADICIONAL (hace lo mismo):
function(e) {
    // código
}

if (e.key >= '0' && e.key <= '9') appendNumber(e.key);
e.key: Propiedad que contiene la tecla presionada
>= y <=: Comparadores (mayor/igual y menor/igual)

LÓGICA: Si la tecla está entre '0' y '9', es un número
Llama a appendNumber con ese número

NOTA: Los strings se pueden comparar alfabéticamente
'0' < '5' < '9' es verdadero

if (e.key === '.') appendNumber('.');
Si presiona punto, añade punto decimal

if (e.key === '+' || e.key === '-') appendOperator(e.key);
Si presiona + o -, añade ese operador

if (e.key === '*') appendOperator('×');
Si presiona *, traduce a ×
RAZÓN: * está en el teclado, pero × se ve mejor

if (e.key === '/')
e.preventDefault();
preventDefault(): Previene el comportamiento predeterminado
RAZÓN: En navegadores, / abre la búsqueda rápida
Esto lo desactiva para que solo añada división

appendOperator('÷'); Traduce / a ÷

if (e.key === 'Enter' || e.key === '=')
Si presiona Enter o =, calcula el resultado

e.preventDefault();
Previene que Enter haga scroll o active botones

calculate();

if (e.key === 'Escape') clearDisplay();
Tecla Escape limpia todo
CONVENIENTE: Es común en calculadoras físicas y software

if (e.key === 'Backspace') deleteDigit();
Backspace borra el último dígito

EJERCICIO AVANZADO: Añade soporte para:
- Ctrl+C: Copiar resultado al portapapeles
- Ctrl+V: Pegar número desde portapapeles
Pista: Usa e.ctrlKey para detectar si Ctrl está presionado
```

---

## Ejercicios Propuestos

### Nivel Principiante

```
1. Añade un botón de porcentaje (%)
   Pista: result = prev * (current / 100)

2. Añade un botón de cambio de signo (+/-)
   Pista: currentValue = (parseFloat(currentValue) * -1).toString()

3. Cambia los colores del tema a tu gusto
   Pista: Modifica las variables CSS en :root

4. Añade un historial de operaciones
   Pista: Usa un array para guardar cada cálculo
```

### Nivel Intermedio

```
5. Añade funciones científicas (sin, cos, tan, raíz cuadrada)
   Pista: Usa Math.sin(), Math.cos(), Math.tan(), Math.sqrt()

6. Añade memoria (M+, M-, MR, MC)
   Pista: Crea una variable global 'memory' para almacenar valores

7. Añade soporte para paréntesis
   Pista: Necesitarás una pila (stack) para evaluar expresiones

8. Guarda el tema del usuario (claro/oscuro) en localStorage
   Pista: localStorage.setItem() y localStorage.getItem()
```

### Nivel Avanzado

```
9. Convierte a PWA (Progressive Web App) para instalarla
   Pista: Necesitas un manifest.json y un service worker

10. Añade reconocimiento de voz para dictar operaciones
    Pista: Usa la Web Speech API (speechRecognition)

11. Añade un modo de gráficas para funciones matemáticas
    Pista: Usa Canvas API o una librería como Chart.js

12. Añade conversión de unidades (km a millas, °C a °F, etc.)
    Pista: Crea funciones de conversión y botones para seleccionar unidades
```

---

## Recursos Adicionales

### Conceptos Importantes para Investigar

```
- DOM (Document Object Model): Cómo JavaScript interactúa con HTML
- Event Listeners: Responder a acciones del usuario
- CSS Grid y Flexbox: Sistemas de diseño moderno
- CSS Variables: Temas y estilos reutilizables
- Funciones puras: Funciones que siempre dan el mismo resultado
- Inmutabilidad: No modificar datos originales
- Programación defensiva: Validar todas las entradas
- Accesibilidad web (a11y): Hacer apps usables para todos
```

### Recursos Recomendados

```
- MDN Web Docs: https://developer.mozilla.org (Documentación oficial)
- CSS-Tricks: https://css-tricks.com (Trucos y tutoriales de CSS)
- JavaScript.info: https://javascript.info (Tutorial completo de JS)
- Can I Use: https://caniuse.com (Compatibilidad de navegadores)
```

---

## Notas Finales

Esta documentación está diseñada para ser leída junto con el código fuente de la calculadora. Cada comentario explica no solo **qué** hace el código, sino también **por qué** está escrito de esa manera y **qué alternativas** existen.

Se recomienda:
1. Leer un concepto en esta documentación
2. Ver el código correspondiente en el archivo HTML
3. Experimentar modificando valores
4. Intentar implementar los ejercicios propuestos

¡Feliz aprendizaje! 🚀
