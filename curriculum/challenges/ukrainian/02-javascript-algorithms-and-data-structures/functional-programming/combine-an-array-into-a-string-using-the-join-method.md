---
id: 587d7daa367417b2b2512b6c
title: Об’єднання масиву в рядок за допомогою методу join
challengeType: 1
forumTopicId: 18221
dashedName: combine-an-array-into-a-string-using-the-join-method
---

# --description--

The `join` method is used to join the elements of an array together to create a string. It takes an argument for the delimiter that is used to separate the array elements in the string.

Ось приклад:

```js
const arr = ["Hello", "World"];
const str = arr.join(" ");
```

`str` матиме значення рядка `Hello World`.
# --instructions--

Використайте метод `join` (з-поміж інших) всередині функції `sentensify`, щоб створити речення зі слів у рядку `str`. Функція повинна повертати рядок. Наприклад, `I-like-Star-Wars` буде перетворено в `I like Star Wars`. Не використовуйте метод `replace` у цьому завданні.

# --hints--

Ваш код повинен використовувати метод `join`.

```js
assert(__helpers.removeJSComments(code).match(/\.join/g));
```

Ваш код не повинен використовувати метод `replace`.

```js
assert(!__helpers.removeJSComments(code).match(/\.?[\s\S]*?replace/g));
```

`sentensify("May-the-force-be-with-you")` має повертати рядок.

```js
assert(typeof sentensify('May-the-force-be-with-you') === 'string');
```

`sentensify("May-the-force-be-with-you")` має повертати рядок `May the force be with you`.

```js
assert(sentensify('May-the-force-be-with-you') === 'May the force be with you');
```

`sentensify("The.force.is.strong.with.this.one")` має повертати рядок `The force is strong with this one`.

```js
assert(
  sentensify('The.force.is.strong.with.this.one') ===
    'The force is strong with this one'
);
```

`sentensify("There,has,been,an,awakening")` має повертати рядок `There has been an awakening`.

```js
assert(
  sentensify('There,has,been,an,awakening') === 'There has been an awakening'
);
```

# --seed--

## --seed-contents--

```js
function sentensify(str) {
  // Only change code below this line


  // Only change code above this line
}

sentensify("May-the-force-be-with-you");
```

# --solutions--

```js
function sentensify(str) {
  return str.split(/\W/).join(' ');
}
```
