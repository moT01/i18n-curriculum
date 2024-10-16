---
id: 587d7dac367417b2b2512b74
title: استخدام رمز النقطة (Dot Notation) للحصول على خصائص الكائن (Object)
challengeType: 1
forumTopicId: 301333
dashedName: use-dot-notation-to-access-the-properties-of-an-object
---

# --description--

The last challenge created an object with various properties. Now you'll see how to access the values of those properties. إليك مثال:

```js
let duck = {
  name: "Aflac",
  numLegs: 2
};
console.log(duck.name);
```

تستخدم رمز النقطة (dot notation) على اسم الكائن `duck`، يليها اسم الخاصية `name`، للوصول إلى قيمة `Aflac`.

# --instructions--

أطبع خواص كائن `dog` إلى وحدتك التحكم (console).

# --hints--

يجب أن يستخدم كودك `console.log` لطباعة قيمة خاصية `name` لكائن `dog`.

```js
assert(/console.log\(.*dog\.name.*\)/g.test(__helpers.removeJSComments(code)));
```

يجب أن يستخدم كودك `console.log` لطباعة قيمة خاصية `numLegs` لكائن `dog`.

```js
assert(/console.log\(.*dog\.numLegs.*\)/g.test(__helpers.removeJSComments(code)));
```

# --seed--

## --seed-contents--

```js
let dog = {
  name: "Spot",
  numLegs: 4
};
// Only change code below this line
```

# --solutions--

```js
let dog = {
  name: "Spot",
  numLegs: 4
};
console.log(dog.name);
console.log(dog.numLegs);
```
