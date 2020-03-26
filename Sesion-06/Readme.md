
[`Programación con JavaScript`](../Readme.md) > `Sesión 06`

# Sesión 6: Programación funcional

## Objetivos

Crear constructores a partir de los cuales se puedan instanciar múltiples objetos.

---

## Tabla de Contenidos

- **[Programación funcional](#programación-funcional)**

- **[Inmutabilidad](#inmutabilidad)**

	- [Ejemplo 1: Function constructor](./Ejemplo-01)

- **[Herencia](#herencia)**

	- [Ejemplo 2: Heredando propiedades](./Ejemplo-02)

- **[Prototype](#prototype)**

	- [Ejemplo 3: Heredando métodos](./Ejemplo-03)

---

## Progamación funcional

Como vimos en la sesión anterior existen distintos paradigmas de programación. La programación funcional es un paradigma declarativo, es decir, se enfoca en el _qué_ se desea lograr sin preocuparse mucho en el _cómo_ (el lenguaje de programación se encarga de esta parte).

```javascript
var numbers = [1, 2, 3, 4, 5];
var doubles = [];

for(var i = 0; i < numbers.length; i++) {
	doubles.push(numbers[i] * 2);
}

console.log(numbers); // [1, 2, 3, 4, 5]
console.log(doubles); // [2, 4, 6, 8, 10]
```

Este es un ejemplo de código imperativo. Generalmente usar ciclos es programación imperativa pues queda del lado del programador controlar cuando iniciar, cuándo terminar y qué hacer en cada ciclo.

```javascript
var numbers = [1, 2, 3, 4, 5];
var doubles = numbers.map(function(number) {
	return number * 2;
});

console.log(numbers); // [1, 2, 3, 4, 5]
console.log(doubles); // [2, 4, 6, 8, 10]
```

Esta es la forma declarativa del mismo código. Ambos fragmentos de código hacen exactamente lo mismo, crear un arreglo `doubles` con el doble de cada elemento del arreglo `numbers`. La diferencia con el segundo ejemplo es que hacemos uso del método `map()`, el programador no se encarga de controlar cuándo y dónde terminar el ciclo, sólo se encarga del resultado, obtener el doble de cada elemento dentro de `numbers`.

> El método map() crea un nuevo array con los resultados de la llamada a la función indicada aplicados a cada uno de sus elementos.

---

## Inmutabilidad

Decimos que algo es mutable cuando puede ser cambiado o modificado. Por lo tanto, inmutable es algo que no puede ser alterado. En términos de programación, las variables inmutables nunca cambian su valor. Este es un principio muy importante en la programación funcional, de hecho, lenguajes de programación como Elixir o Erlang no permiten la mutación de variables.

En lugar de alterar una variable, creamos nuevos valores y reemplazamos los antiguos. Si bien JavaScript no es puramente funcional, es lo suficientemente flexible como para permitir o pretender serlo.

Para llevar este concepto a la práctica es importante siempre preferir crear una nueva variable en lugar de intentar modificar la original. Esto se puede llevar a cabo con métodos como `map()` que no altera el arreglo original, o bien creando tus propias funciones inmutables.

#### [Ejemplo 1: Mutando objetos](./Ejemplo-01)

---

## Herencia

En términos simples la herencia es cuando un objeto está basado en otro objeto, es decir, un objeto puede acceder a las propiedades y métodos de otro objeto.

![Inheritance](./assets/inheritance.png)

El constructor `Developer` tiene propiedades y métodos únicos cómo skills que domina, años de experiencia y el skill de su preferencia. Como `Developer` también es una persona, es decir, tambíen tiene nombre, edad y un empleo, el constructor `Developer` puede heredar del constructor `Person`, teniendo acceso a las mismas propiedades y métodos.

#### [Ejemplo 2: Heredando propiedades](./Ejemplo-02)

---

## Prototype

En JavaScript la herencia es posible gracias a una propiedad con la que cuentan todos los objetos llamada `Prototype`. Si queremos que las instancias hereden un método lo podemos colocar en el `Prototype` del constructor. Veamos un ejemplo con el constructo `Person` y la instancia `john` con la que hemos trabajado anteriormente.

![Prototype Chain](./assets/prototype-chain.png)

Como `john` es una instancia de `Person`, este tiene acceso al método `calculateAge()` aunque no se encuentre dentro del prototype de `john`. Cuando llamamos a un método, JavaScript busca primero en el prototype del objeto, si no lo encuentra busca en el prototype del constructor con el que fue instanciado, y así sucesivamente hasta llegar al constructor `Object`, del cuál se instancian todos los objetos en JavaScript y [contiene varios métodos](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/Object). A esto se le conoce como **prototype chain**.

#### [Ejemplo 3: Heredando métodos](./Ejemplo-03)
