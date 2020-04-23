
[`Programación con JavaScript`](../Readme.md) > `Sesión 08`

# Sesión 8: Manipulación del DOM

## Objetivos

Generar scripts que permitan la manipulación e interacción con la web.

---

## Tabla de Contenidos

- **[Event handlers](#event-handlers)**

- **[Eventos y nodos del DOM](#eventos-y-nodos-del-dom)**

	- [Ejemplo 1: Eventos en nodos del DOM](./Ejemplo-01)

- **[Event object](#event-object)**

		- [Ejemplo 2: Usando event object](./Ejemplo-02)

- **[Reto final](./Reto-final)**

- **[Postwork](./Postwork)**

---

## Event handlers

Manipular el DOM creando nodos y modificando sus atributos carece de sentido si el usuario no tiene la posibildad de interactuar con nuestra aplicación o sitio web. El usuario en algún momento va a presionar una tecla, hacer click en un botón, o ingresar un valor en un input y espera que la interfaz reaccione de alguna forma en el momento que se realiza cualquiera de esas acciones.

Los navegadores son capaces de notificar o avisar a nuestro código cuando un evento sucede. En este contexto un evento es cuando el usuario o el navegador mismo manipula la página. Cuando el usuario hace click en un botón, cuando la página carga, o incluso cuando una ventana se cierra son ejemplos de eventos. El navegador nos permite registrar funciones conocidas como _handlers_ que se ejecutan cuando un evento en específico sucede.

```javascript
window.addEventListener("click", function() {
  console.log("Hello World!");
});
```

`window` es un objeto que representa la ventana del navegador donde se carga `document`. Al llamar el método `addEventListener` se registra el segundo argumento para ser llamado cuando el evento descrito en el primer argumento sucede. Como resultado, al hacer click (evento) en cualquier parte de la ventana se mostrará en consola un mensaje `Hello World!` (handler).

---

## Eventos y nodos del DOM

Todos los event handlers son registrados en un contexto. En el ejemplo anterior llamamos `addEventListener` en el objeto `window` por lo que el handler se registra para toda la ventana. Los elementos del DOM también cuentan con este método.

```html
<p>No handler here.</p>

<button>Click me</button>

<p>No handler here.</p>

<script>
  var button = document.querySelector("button");

  button.addEventListener("click", () => {
    console.log("Button clicked.");
  });
</script>
```

> El método `querySelector` retorna el primer elemento del DOM que hace match con el selector de CSS especificado.

Este handler está vinculado al elemento `button`. Lo clicks en el botón ejecutarán la función handler pero los clicks en los párrafos (o cualquier parte del documento) no.

Usar el atributo `onclick` tiene el mismo efecto, sin embargo, los nodos sólo pueden tener un atributo `onclick` por lo que sólo se puede registrar un handler de esta manera. Usando el método `addEventListener` se pueden registrar múltiples handlers sobre un mismo nodo.

También podemos eliminar handlers que hayamos creado con anterioridad usando el método `removeEventListener`.

```html
<button>Click me</button>

<script>
  var button = document.querySelector("button");

  function once() {
    console.log("Click once");
    button.removeEventListener("click", once);
  }

  button.addEventListener("click", once);
</script>
```

La función que le pasemos a `removeEventListener` debe ser la misma que se le dió a `addEventListener`. En este caso se debe definir una función y darle un nombre, de esta forma podemos pasar la funicón a ambos métodos.

#### [Ejemplo 1: Eventos en nodos del DOM](./Ejemplo-01)

---

## Event object

La función de un event handler recibe un argumento `event`. Este es un objeto con toda la información referente al evento. Por ejemplo, si quisiéramos saber cuál botón del mouse fue presionado podemos leer la propiedad `button` del event object.

```html
<button>Click Here</button>

<script>
  var button = document.querySelector("button");

  button.addEventListener("mousedown", function(event) {
    if (event.button == 0) {
      console.log("Left button");
    } else if (event.button == 1) {
      console.log("Middle button");
    } else if (event.button == 2) {
      console.log("Right button");
    }
  });
</script>
```

La información contenida en el event object puede variar dependiendo del tipo de evento.

#### [Ejemplo 2: Usando event object](./Ejemplo-02)
