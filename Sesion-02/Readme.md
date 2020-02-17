[`Programación con JavaScript`](../Readme.md) > `Sesión 02`

---

# Sesión 1: Controles de flujo

## Objetivos

Conocer las estructuras que permiten controlar el flujo de ejecución de un programa o aplicación

---

## Tabla de Contenidos

- **[Condicionales](#condicionales)**

	- [Operadores lógicos](#operadores-lógicos)

	- [`if`/`else`](#if--else)

		- [Ejemplo 1: Primeras condicionales](./Ejemplo-01)

		- [Reto 1: Controles de flujo](./Reto-01)

---

## Condicionales

Las condicionales nos permiten cotrolar el flujo de un programa, es decir, podemos controlar las partes del código que se ejecutarán dependiendo de si una condición se cumple o no.

### Operadores lógicos

JavaScript nos proporciona varios operadores lógicos para que podamos realizar operaciones de comparación.

| Operador | Descripción                                                                                                       | Ejemplos                                                      |
|----------|-------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------|
| ==       | **Igualdad:** Devuelve `true` si ambos operandos son iguales                                                      | 3 == 3<br> 3 == "3"<br> "mike" == "mike"<br> var1 == true<br> |
| !=       | **Desigualdad:** Devuelve `true` si ambos operandos no son iguales                                                | 3 != 4                                                        |
| ===      | **Estrictamente iguales:**<br> Devuelve `true` si los operandos son igual<br> y tienen el mismo tipo.             | 3 === 3 <br><br> 3 === "3"<br> (Devuelve falso)               |
| !==      | **Estrictamente desiguales:** <br> Devuelve `true` si los operandos no son iguales<br> y/o no son del mismo tipo. | 3 !== "3"                                                     |
| >        | **Mayor que:** Devuelve `true` si el operando de la izquierda<br> es mayor que el operando de la derecha.         | 4 > 3                                                         |
| >=       | **Mayor o igual que:**                                                                                            | 4 >= 4                                                        |
| <        | **Menor que:** Devuelve `true` si el operando de la izquierda<br>  es menor que el operando de la derecha.        | 12 < 15                                                       |
| <=       | **Menor o igual que:**                                                                                            | 15 <= 15                                                      |
| &&       | **And:** Devuelve `true` si ambas condiciones se cumplen                                                          | 2 > 1 && 1 > 0                                                |
| \|\|       | **Or:** Devuelve `true` si una de las condiciones se cumplen                                                      | 2 > 1 || 1 < 0                                                |

### `if` / `else`

El tipo de condición más común de todos. Traducida literalmente del inglés, se la podría llamar la estructura *si...si no*, es decir, *si se cumple la condición, haz esto, y sino, haz esto otro*.

La sintaxis se compone de la siguiente forma:

```javascript
if ( /* Condición a evaluar */ ) {
	/* Código a ejecutar si la condición retorna true */
} else {
	/* Código a ejecutar si la condición retorna false */
}
```

- `if` - La palabra clave que indica que se va a realizar una condicional.
- `( ... )` - Dentro de los paréntesis se coloca la condición a evaluar, la cuál retorna un booleano, es decir, `true` o `false`.
- `{ ... }` - Dentro de las llaves va el texto a ejecutar en caso de que la condición sea `true`.
- `else` - Se utiliza para controlar el flujo en caso de que la condición sea `false`. Si se usa `else`, el código dentro de las llaves que le siguen se ejecuta sólo cuando la condición anterior no se cumplió.

#### [Ejemplo 1: Primeras condicionales](./Ejemplo-01)

#### [Reto 1: Controles de flujo](./Reto-01)
