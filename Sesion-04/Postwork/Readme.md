[`Programación con JavaScript`](../../Readme.md) > [`Sesión 04`](../Readme.md) > `Postwork`

---

## Postwork

### Objetivo

Modificar las funciones creadas hasta el momento para que sean compatibles con los cambios realizados en el Reto Final.

#### Desarrollo

Después de haber cambiado variables por objetos y arreglos las funciones creadas anteriomente dejarán de trabajar como esperamos.

```javascript
var isCompleted = false;

function toggleTaskCompleted() {
	isCompleted = !isCompleted;
}
```

La función `toggleTaskCompleted()` invertía el valor de `isCompleted` pero esta variable aislada ya no existe, ahora es parte de un arreglo de objetos.

```javascript
var tasks = [
  {
    description: 'Some task to do',
    isCompleted: false
  },
  {
    description: 'Another task to do',
    isCompleted: false
  },
  {
    description: 'One more task to do',
    isCompleted: false
  }
]
```

La lógica de la función seguirá siendo la misma. El ajuste que debemos hacer es pasarle un `index` para que la función sepa qué tarea es la que debe modificar.

```javascript
function toggleTaskCompleted(index) {
	tasks[index].isCompleted = !tasks[index].isCompleted;
}
```

Con esto podemos utilizar la misma función para modificar la propiedad `isCompleted` de cualquier tarea que se encuentre dentro del arreglo.

```javascript
toggleTaskCompleted(0);

toggleTaskCompleted(2);

console.log( tasks );

/*
[
  {
    description: 'Some task to do',
    isCompleted: true
  },
  {
    description: 'Another task to do',
    isCompleted: false
  },
  {
    description: 'One more task to do',
    isCompleted: true
  }
]
*/
```

Ahora que sabemos cómo modificar un arreglo y las propiedades de un objeto podemos avanzar con otra de los user stories: _Como usuario quiero eliminar una tarea._

```javascript
function deleteTask(index) {
	tasks.splice(index, 1);
}
```

El método `splice()` cambia el contenido de un arreglo eliminando elementos existentes. El primer argumento es el index a partir de donde se quiere comenzar a eliminar, el segundo argumento es la cantidad de elementos a eliminar. Este caso sólo queremos elimiar una tarea cada que llamemos a la función.

```javascript
deleteTask(1);

console.log( tasks );

/*
[
  {
    description: 'Some task to do',
    isCompleted: true
  },
  {
    description: 'One more task to do',
    isCompleted: true
  }
]
*/
```

Ahora puedes hacer los cambios necesarios para que las funciones que creaste en la sesión anterior sigan trabajando de forma esperada después de las modificiones hechas en el reto final.
