[`Programación con JavaScript`](../../Readme.md) > [`Sesión 03`](../Readme.md) > `Postwork`

---

## Postwork

### Objetivo

Crear variables y funciones que se pueden integrar al proyecto postwork. Poner en práctica conceptos utilizados en sesiones anteriores.     

#### Desarrollo

Del ejemplo anterior se tomarán los tres primeros user stories:  

* Como usuario quiero agregar nuevas tareas a la lista.  
* Como usuario quiero marcar una tarea como completada.  
* Como usuario quiero eliminar una tarea para que no utilice espacio.  

Las otras tres son muy buenas ideas también pero pueden ser implementadas como mejoras. Lo más importante para que la App funcione es que el usuario pueda crear, eliminar y marcar notas como completadas.  

Con lo que hemos visto hasta ahora podemos empezar a definir los tipos de datos que vamos a utilizar y pensar en nuestras primeras funciones. Por ejemplo, las tareas son el texto que el usuario ingresa por lo que un String es el tipo de dato más adecuado. Además, las tareas cuentan con dos estados, completado y no completado, esto es un Booleano.  

```javascript
var isCompleted = false;

function markTaskAsCompleted() {
	isCompleted = true;
}
```  

Inicializo isCompleted en false porque las tareas no están completadas al momento de ser creadas. markTaskAsCompleted() es una función que me va a ayudar a cambiar este estado de completo o incompleto. Sin embargo, no me sirve para regresar isCompleted a false. Necesitaría una segunda función que haga lo opuesto o bien, podemos jugar con esta misma función para que haga ambas cosas.  

```javascript

function martTaskAsCompleted() {
	isCompleted = !isCompleted;
}
```  

Con esto podemos cambiar de true a false y viceversa. La función asignará a isCompleted su opuesto, es decir, si en ese momento es false lo guardará como true.  

Lo último que hace falta es cambiar el nombre de la función ya hace más de lo que su nombre indica.  

```javascript
function toggleTaskCompleted() {
	isCompleted = !isCompleted;
}
```  

Recuerda que el nombre tanto de tus variables como funciones deben ser descriptivas, con sólo leer el nombre otro desarrollador debe poder darse una idea de qué hace una función o de qué contiene una variable.  

Este es un ejemplo de cómo puedes ir integrando lo visto hasta ahora en tu proyecto. Puedes ir creando las variables que consideres necesarias y tus primeras funciones que deban manipular un valor.  

#### Opcional

Para reforzar lo visto en clase se recomienda leer el [capítulo 3](https://eloquentjavascript.net/03_functions.html) del siguiente libro interactivo:

**[Eloquent JavaScript](https://eloquentjavascript.net/)**

En este capítulo se abordan las funciones, cómo declararlas, expresiones de funciones y funciones recursivas. Al final del capítulo encontrarás 3 ejercicios que pueden ser resueltos en la misma página.
