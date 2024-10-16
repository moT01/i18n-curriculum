---
id: 587d7b86367417b2b2512b3d
title: Prevenir bucles infinitos con una condición terminal válida
challengeType: 1
forumTopicId: 301192
dashedName: prevent-infinite-loops-with-a-valid-terminal-condition
---

# --description--

The final topic is the dreaded infinite loop. Loops are great tools when you need your program to run a code block a certain number of times or until a condition is met, but they need a terminal condition that ends the looping. Infinite loops are likely to freeze or crash the browser, and cause general program execution mayhem, which no one wants.

Había un ejemplo de un bucle infinito en la introducción de esta sección - no tenía ninguna condición terminal para salir del bucle `while` dentro de `loopy()`. ¡NO llames esta función!

```js
function loopy() {
  while(true) {
    console.log("Hello, world!");
  }
}
```

El trabajo del programador es asegurarse de que la condición terminal, que indica al programa cuándo debe salir del código del bucle, se alcance finalmente. Un error es incrementar o decrementar una variable de contador en la dirección incorrecta desde la condición terminal. Otra es reiniciar accidentalmente un contador o una variable de índice dentro del código del bucle, en lugar de incrementarlo o decrementarlo.

# --instructions--

La función `myFunc()` contiene un bucle infinito porque la condición terminal `i != 4` nunca se evaluará a `false` (y romperá el bucle) - `i` se incrementará en 2 en cada pasada, y saltará justo sobre 4, ya que `i` es impar para empezar. Corrige el operador de comparación en la condición terminal para que el bucle sólo se ejecute para `i` menor o igual a 4.

# --hints--

Tu código debe cambiar el operador de comparación en la condición terminal (la parte central) del bucle `for`.

```js
assert(__helpers.removeJSComments(code).match(/i\s*?<=\s*?4;/g).length == 1);
```

Tu código debe corregir el operador de comparación en la condición terminal del bucle.

```js
assert(!__helpers.removeJSComments(code).match(/i\s*?!=\s*?4;/g));
```

# --seed--

## --seed-contents--

```js
function myFunc() {
  for (let i = 1; i != 4; i += 2) {
    console.log("Still going!");
  }
}
```

# --solutions--

```js
function myFunc() {
 for (let i = 1; i <= 4; i += 2) {
   console.log("Still going!");
 }
}
```
