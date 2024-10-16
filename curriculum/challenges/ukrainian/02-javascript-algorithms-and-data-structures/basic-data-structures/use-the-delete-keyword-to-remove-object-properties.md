---
id: 587d7b7c367417b2b2512b1b
title: Ключове слово delete для видалення властивостей об’єкта
challengeType: 1
forumTopicId: 301168
dashedName: use-the-delete-keyword-to-remove-object-properties
---

# --description--

Now you know what objects are and their basic features and advantages. In short, they are key-value stores which provide a flexible, intuitive way to structure data, ***and***, they provide very fast lookup time. Throughout the rest of these challenges, we will describe several common operations you can perform on objects so you can become comfortable applying these useful data structures in your programs.

У попередніх завданнях ми додавали пари ключ-значення до об’єкта та змінювали їх. Тепер ми розглянемо, як *видалити* пару ключ-значення з об’єкта.

Повернемося до нашого об’єкта `foods` востаннє. Якщо ми хочемо видалити ключ `apples`, ми можемо зробити це за допомогою ключового слова `delete`:

```js
delete foods.apples;
```

# --instructions--

Використайте ключове слово delete, щоб видалити ключі `oranges`, `plums` та `strawberries` з об’єкта `foods`.

# --hints--

Об’єкт `foods` повинен мати три ключі: `apples`, `grapes` та `bananas`.

```js
assert(
  !foods.hasOwnProperty('oranges') &&
    !foods.hasOwnProperty('plums') &&
    !foods.hasOwnProperty('strawberries') &&
    Object.keys(foods).length === 3
);
```

Ключі `oranges`, `plums` та `strawberries` потрібно видалити, використавши `delete`.

```js
assert(
  __helpers.removeJSComments(code).search(/oranges:/) !== -1 &&
    __helpers.removeJSComments(code).search(/plums:/) !== -1 &&
    __helpers.removeJSComments(code).search(/strawberries:/) !== -1
);
```

# --seed--

## --seed-contents--

```js
let foods = {
  apples: 25,
  oranges: 32,
  plums: 28,
  bananas: 13,
  grapes: 35,
  strawberries: 27
};

// Only change code below this line

// Only change code above this line

console.log(foods);
```

# --solutions--

```js
let foods = {
  apples: 25,
  oranges: 32,
  plums: 28,
  bananas: 13,
  grapes: 35,
  strawberries: 27
};

delete foods.oranges;
delete foods.plums;
delete foods.strawberries;

console.log(foods);
```
