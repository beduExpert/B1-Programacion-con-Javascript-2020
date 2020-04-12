
[`Programación con JavaScript`](../Readme.md) > `Sesión 07`

# Sesión 7: Introducción al DOM

## Objetivos

Identificar el rol de JavaScript en el desarrollo web al permitir interactividad entre el usuario y la página web.

---

## Tabla de Contenidos

- **[DOM](#dom)**

	- [Ejemplo 1: Inspeccionando el DOM](./Ejemplo-01)

- **[Estructura de datos de árbol](#estructura-de-datos-de-árbol)**

- **[Reto final](./Reto-final)**

- **[Postwork](./Postwork)**

---

## ¿Qué es el DOM?

Cuando abres una página web el navegador obtiene el código HTML y lo analiza para construir un modelo de la estructura del documento, este modelo le permite al navegador mostrar la página en la pantalla.

A esto se le conoce como DOM (Document Object Model), una representación del documento que se muestra en el navegador. Esta estructura puede ser leída y modificada en tiempo real, es decir, cualquier cambio que se haga a este modelo será reflejada en la pantalla en el momento.

Un documento HTML es como una serie de cajas anidadas. Las etiquetas como `<body> </body>` encierran otras etiquetas, y estas a su vez envuelven otras etiquetas o texto. Tomemos como ejemplo el siguiente documento HTML:

```html
<!doctype html>
<html>
  <head>
    <title>DOM</title>
  </head>
  <body>
    <h1>Document Object Model</h1>
    <p>Hello World!</p>
    <p>Here is a
      <a href="#">link</a>
    </p>
  </body>
</html>
```

Esta es la estructura de esa página:

![DOM](./assets/document.png)

Para cada una de estas cajas existe un objeto en JavaScript con el que podemos interactuar para saber qué etiqueta HTML representa y qué otras cajas o texto contiene. La variable global `document` nos da acceso a todos estos objetos.

> `document` es una variable global, es decir, se puede acceder a ella desde cualquier parte del script o código. Todas las funciones que hagas pueden hacer referencia a esta variable.

#### [Ejemplo 1: Inspeccionando el DOM](./Ejemplo-01)

---

## Estructura de datos de árbol
