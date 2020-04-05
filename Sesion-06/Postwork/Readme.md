[`Programación con JavaScript`](../../Readme.md) > [`Sesión 06`](../Readme.md) > `Postwork`

---

## Postwork

### Objetivo

Integrar principios de programación funcional en el proyecto.

#### Desarrollo

Como ya no estamos usando el constructor `Task` no podemos asignar `toggleCompleted` al prototype:

```javascript
Task.prototype.toggleCompleted = function() {
  this.isCompleted = !this.isCompleted;
}
```

Por lo que podemos retomar la función original y hacer los cambios necesarios para que sea una función pura.

```javascript
function toggleTaskCompleted(index) {
	tasks[index].isCompleted = !tasks[index].isCompleted;
}
```

Al igual que con `addTask()` debemos pasar `tasks`, crear una copia para modificar la propiedad `isCompleted` y después actualizar el arreglo original.

```javascript
function toggleTaskCompleted(tasks, index) {
  var newTasks = [].concat(tasks);

  newTasks[index].isCompleted = !newTasks[index].isCompleted;

  return newTasks;
}
```

Una mejora que podemos hacer en esta función es validar el index de `tasks`. Si sólo tenemos una tarea en el arreglo y pasamos `2` como index tendremos un error porque `tasks[2]` es `undefined`, es decir, no existe esa tarea.

```javascript
function toggleTaskCompleted(tasks, index) {
  var newTasks = [].concat(tasks);

  if(newTasks[index]) {
    newTasks[index].isCompleted = !newTasks[index].isCompleted;
  }

  return newTasks;
}
```

Otra función que debemos modificar es `deleteTask()`:

```javascript
function deleteTask(index) {
  tasks.splice(index, 1);
}
```

Al igual que con las funciones anteriores debemos pasar `tasks` para hacer una copia. Por otro lado, podemos usar la función de alto orden `filter()` en lugar del método `splice()`.

```javascript
function deleteTask(tasks, index) {
  var newTasks = tasks.filter(function(task, i) {
    return i !== index;
  })

  return newTasks;
}
```

> No es necesario usar `concat()` ya que `filter()` retorna un nuevo arreglo. El parámetro `i` representa el index de `task`.

```javascript
var tasks = [];

function addTask(tasks, description, isCompleted = false) {
  var newTasks = [].concat(tasks);

  newTasks.push({
    description: description,
    isCompleted: isCompleted
  });

  return newTasks;
}

function toggleTaskCompleted(tasks, index) {
  var newTasks = [].concat(tasks);

  if(newTasks[index]) {
    newTasks[index].isCompleted = !newTasks[index].isCompleted;
  }

  return newTasks;
}

function deleteTask(tasks, index) {
  var newTasks = tasks.filter(function(task, i) {
    return i !== index;
  })

  return newTasks;
}
```

No todas las funciones de tu proyecto deben ser puras, en ocasiones es necesario tener funciones que produzcan efectos secundarios. Lo importante es conocer ambos paradigmas de programación, tanto programación orientada a objetos como programación funcional, e implementar los conceptos de la mejor forma posible para solucionar un problema.
