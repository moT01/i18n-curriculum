---
id: 56533eb9ac21ba0edf2244ad
title: Decrementa un número con JavaScript
challengeType: 1
videoUrl: 'https://scrimba.com/c/cM2KeS2'
forumTopicId: 17558
dashedName: decrement-a-number-with-javascript
---

# --description--

You can easily <dfn>decrement</dfn> or decrease a variable by one with the `--` operator.

```js
i--;
```

es equivalente a

```js
i = i - 1;
```

**Nota:** La linea se convierte en `i--;`, eliminando la necesidad del signo igual.

# --instructions--

Cambia el código para usar el operador `--` en `myVar`.

# --hints--

`myVar` debe ser igual a `10`.

```js
assert(myVar === 10);
```

`myVar = myVar - 1;` debe cambiarse.

```js
assert(!__helpers.removeJSComments(code).match(/myVar\s*=\s*myVar\s*[-]\s*1.*?;?/));
```

No debes asignar `myVar` con `10`.

```js
assert(!__helpers.removeJSComments(code).match(/myVar\s*=\s*10.*?;?/));
```

Debes usar el operador `--` en `myVar`.

```js
assert(/[-]{2}\s*myVar|myVar\s*[-]{2}/.test(__helpers.removeJSComments(code)));
```

No debes cambiar el código por encima del comentario especificado.

```js
assert(/let myVar = 11;/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --after-user-code--

```js
(function(z){return 'myVar = ' + z;})(myVar);
```

## --seed-contents--

```js
let myVar = 11;

// Only change code below this line
myVar = myVar - 1;
```

# --solutions--

```js
let myVar = 11;
myVar--;
```
