---
id: 9d7123c8c441eeafaeb5bdef
title: Remueve elementos de un arreglo usando slice en lugar de splice
challengeType: 1
forumTopicId: 301236
dashedName: remove-elements-from-an-array-using-slice-instead-of-splice
---

# --description--

A common pattern while working with arrays is when you want to remove items and keep the rest of the array. JavaScript offers the `splice` method for this, which takes arguments for the index of where to start removing items, then the number of items to remove. If the second argument is not provided, the default is to remove items through the end. However, the `splice` method mutates the original array it is called on. Aquí hay un ejemplo:

```js
const cities = ["Chicago", "Delhi", "Islamabad", "London", "Berlin"];
cities.splice(3, 1);
```

Aquí `splice` devluelve la "string" `London` y la elimina del arreglo `cities`. `cities` tendrá el valor de `["Chicago", "Delhi", "Islamabad", "Berlin"]`.

Como vimos en el último desafío, el método `slice` no muta el arreglo original, pero devuelve uno nuevo que puede ser guardado en una variable. Recuerda que el método `slice` recibe dos argumentos para indicar el comienzo y el final del segmento (el final es no inclusivo) y retorna estos elementos en un nuevo arreglo. Usar el método `slice` en lugar de `splice` ayuda a prevenir cualquier efecto colateral de mutar un arreglo.

# --instructions--

Reescribe la función `nonMutatingSplice` usando `slice` en lugar de `splice`. Debe limitar el arreglo proporcionado `cities` a una longitud de 3 y devolver un nuevo arreglo con solo los primeros tres elementos.

No modifiques el arreglo original proporcionado en la función.

# --hints--

Tu código debe usar el método `slice`.

```js
assert(__helpers.removeJSComments(code).match(/\.slice/g));
```

Tu código no debe usar el método `splice`.

```js
assert(!__helpers.removeJSComments(code).match(/\.?[\s\S]*?splice/g));
```

No debes mutar el array original pasado a la función.

```js
assert.deepEqual(_inputCities, ["Chicago", "Delhi", "Islamabad", "London", "Berlin"]);
```

`nonMutatingSplice(["Chicago", "Delhi", "Islamabad", "London", "Berlin"])` debe devolver `["Chicago", "Delhi", "Islamabad"]`.

```js
assert.deepEqual(nonMutatingSplice(_inputCities), ["Chicago", "Delhi", "Islamabad"]);
```

# --seed--

## --seed-contents--

```js
function nonMutatingSplice(cities) {

  return cities.splice(3);
}
```

## --after-user-code--

```js
const _inputCities = ["Chicago", "Delhi", "Islamabad", "London", "Berlin"];
```

# --solutions--

```js
function nonMutatingSplice(cities) {
  return cities.slice(0,3);
}
```
