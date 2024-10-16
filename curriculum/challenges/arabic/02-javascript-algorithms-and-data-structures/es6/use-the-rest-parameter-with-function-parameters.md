---
id: 587d7b88367417b2b2512b47
title: استخدام وسائط Rest مع وسائط الوظيفة
challengeType: 1
forumTopicId: 301221
dashedName: use-the-rest-parameter-with-function-parameters
---

# --description--

In order to help us create more flexible functions, ES6 introduces the <dfn>rest parameter</dfn> for function parameters. With the rest parameter, you can create functions that take a variable number of arguments. These arguments are stored in an array that can be accessed later from inside the function.

تحقق من هذا الكود:

```js
function howMany(...args) {
  return "You have passed " + args.length + " arguments.";
}
console.log(howMany(0, 1, 2));
console.log(howMany("string", null, [1, 2, 3], { }));
```

ستعرض وحدة التحكم السلاسل `You have passed 3 arguments.` و `You have passed 4 arguments.`.

The rest parameter eliminates the need to use the `arguments` object and allows us to use array methods on the array of parameters passed to the function `howMany`.

# --instructions--

عدل وظيفة `sum` باستخدام وسيط rest بطريقة تجعل الوظيفة `sum` قادرة على أخذ أي عدد من المعطيات وإنتاج مجموعها.

# --hints--

نتيجة `sum(0,1,2)` يجب أن تكون 3

```js
assert(sum(0, 1, 2) === 3);
```

نتيجة `sum(1,2,3,4)` يجب ان تكون 10

```js
assert(sum(1, 2, 3, 4) === 10);
```

نتيجة `sum(5)` يجب أن تكون 5

```js
assert(sum(5) === 5);
```

نتيجة `sum()` يجب أن تكون 0

```js
assert(sum() === 0);
```

يجب أن تكون `sum` وظيفة السهم, التي تستخدم تشكيل وسيط rest الآتي (`...`) على وسيط `args`.

```js
assert(__helpers.removeWhiteSpace(__helpers.removeJSComments(code)).match(/sum=\(\.\.\.args\)=>/));
```

# --seed--

## --seed-contents--

```js
const sum = (x, y, z) => {
  const args = [x, y, z];
  let total = 0;
  for (let i = 0; i < args.length; i++) {
    total += args[i];
  }
  return total;
}
```

# --solutions--

```js
const sum = (...args) => {
  let total = 0;
  for (let i = 0; i < args.length; i++) {
    total += args[i];
  }
  return total;
}
```
