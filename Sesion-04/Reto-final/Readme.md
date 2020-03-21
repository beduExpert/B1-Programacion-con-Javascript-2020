[`Programación con JavaScript`](../../Readme.md) > [`Sesión 04`](../Readme.md) > `Reto Final`

---

## Reto Final

### Objetivo

Revisar las variables creadas en el prework de la sesión anterior y cambiar el tipo de dato si es necesario.

#### Desarrollo

Ahora que hemos visto tipos de datos más complejos como arreglos y objetos podemos revisar nuevamente tanto las funciones como las variables que creamos en el postwork de la sesión anterior. Seguramente encontrarás que no todas las variables cuentan con el tipo de dato más adecuado.

Siguiendo el ejemplo de la aplicación para crear tareas, vemos que teníamos una variable para representar el estado de una tarea, es decir, si se encuentra completada o no.

```javascript
var isCompleted = false;
```

Esta variable por sí sola no es suficiente para representar una tarea, ya que también necesitamos la descripción de la tarea en sí.

```javascript
var description = 'Some task to do';
var isCompleted = false;
```

Estas variables en conjunto representan la información necesaria de una tarea, sin embargo, manejar esta información por separado es más complejo, especialmente cuando estemos jugando con más de una tarea. En este caso, un objeto es la mejor forma de lograr lo que queremos.

```javascript
var task = {
  description: 'Some task to do',
  isCompleted: false
}
```

Ahora sí, el objeto `task` es lo que buscamos para representar una tarea. Sabemos que cuando queramos acceder a la información de `task` sólo tenemos que escribir el nombre de la variable seguida por un punto y el nombre de la propiedad.

```javascript
console.log( task.description );  // 'Some task to do'

console.log( task.isCompleted );  // false
```

¿Qué pasa cuando el usuario empieza a crear varias tareas?

```javascript
var task1 = {
  description: 'Some task to do',
  isCompleted: false
}

var task2 = {
  description: 'Another task to do',
  isCompleted: false
}

var task3 = {
  description: 'One more task to do',
  isCompleted: false
}
```

Definitivamente crear una variable por cada tarea no es la mejor opción, podemos terminar con miles de variables y un código difícil de mantener. Una mejor alternativa es agrupar todas nuestras tareas en un arreglo, recuerda que los arreglos pueden contener cualquier tipo de dato, incluyendo objetos.

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

Mucho mejor, ahora tenemos todas las tareas en una misma variable y podemos acceder a cualquiera de ellas mediante el `index` del arreglo.

```javascript
console.log( tasks[0].description );  // 'Some task to do'

console.log( tasks[1].description );  // 'Another task to do'

console.log( tasks[2].description );  // 'One more task to do'
```

Ahora puedes implementar la misma lógica en tu proyecto, revisa qué información tienes que pueda ser representada en un objeto y qué variables es mejor agrupar dentro de un arreglo.
