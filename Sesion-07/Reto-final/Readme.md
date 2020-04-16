[`Programación con JavaScript`](../../Readme.md) > [`Sesión 07`](../Readme.md) > `Reto Final`

---

## Reto Final

### Objetivo

Integrar funciones que faciliten la creación de elementos del DOM en el proyecto.

#### Desarrollo

En el [ejemplo 3](../Ejemplo-03) desarrollamos una función que nos permite crear elementos del DOM
con facilidad.

```javascript
function createNode(type, child) {
  var node = document.createElement(type);

  if(typeof child === "string") {
    var text = document.createTextNode(child);
    node.appendChild(text);
  } else {
    node.appendChild(child);
  }

  return node;
}

var title = createNode('h1', 'Hello World');
console.log(title); // <h1>Hello World</h1>
```

Vamos a extender la funcionalidad de `createNode` para que reciba un objeto cuyas propiedades serán los atributos del elemento. Así no los tenemos que agregar manualmente después de crear el nodo.

```javascript
function createNode(type, child, attrs) {
  var node = document.createElement(type);

  if(attrs) {
    Object.keys(attrs).map(function(attr) {
      node[attr] = attrs[attr];
    });
  }

  if(typeof child === "string") {
    node.appendChild(document.createTextNode(child));
  } else {
    node.appendChild(child);
  }

  return node;
}
```

Revisamos primero que `attrs` esté definido, es decir, podemos no pasar el tercer argumento si el elemento que queremos crear no necesita atributos. El método `Object.keys()` retorna un arreglo con todas las propiedades de un objeto, después aplicamos una función a cada elemento de ese arreglo con `map()`. Recuerda que también se pueden acceder a las propiedades de un objeto con la sintaxis similar a un arreglo.

```javascript
var title = createNode('h1', 'Hello World');
console.log(title); // <h1>Hello World</h1>

var p = createNode('p', 'Hello World', { className: 'subtitle' });
console.log(p); // <p class="subtitle">Hello World</p>
```

Si queremos agregar estos dos elementos como hijo de otro nodo debemos usar `appendChild` dos veces.

```javascript
var container = document.createElement('div');

container.appendChild(title);
container.appendChild(p);
```

Podemos hacer una función que reciba un nodo y un arreglo de nodos para agregar como hijos.

```javascript
function appendChildren(node, children) {
  var documentFragment = document.createDocumentFragment();

  children.forEach(function(child) {
    documentFragment.appendChild(child);
  })

  node.appendChild(documentFragment);
}
```

`DocumentFragment` representa un objeto del DOM que no tiene padre. Como no forma parte del documento los cambios que se hagan sobre este objeto no afectan la estructura del árbol. Normalmente se usa para _armar_ o preparar un elemento antes de insertarlo en el DOM.

```javascript
appendChildren(container, [title, p]);
```

No es obligatorio incluir `createNode` y `appendChildren` en tu proyecto, sin embargo, las puedes considerar como funciones auxiliares que te permitirán crear nodos sin realizar tantos pasos.
