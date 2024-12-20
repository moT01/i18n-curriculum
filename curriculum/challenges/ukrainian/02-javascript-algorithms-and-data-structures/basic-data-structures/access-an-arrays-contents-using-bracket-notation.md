---
id: 5a661e0f1068aca922b3ef17
title: Доступ до вмісту масиву за допомогою дужкової нотації
challengeType: 1
forumTopicId: 301149
dashedName: access-an-arrays-contents-using-bracket-notation
---

# --description--

The fundamental feature of any data structure is, of course, the ability to not only store data, but to be able to retrieve that data on command. So, now that we've learned how to create an array, let's begin to think about how we can access that array's information.

Коли ми визначаємо простий масив як показано нижче, в ньому є 3 елементи:

```js
let ourArray = ["a", "b", "c"];
```

Кожен елемент масиву має <dfn>індекс</dfn>. Цей індекс подвоюється як позиція цього елемента в масиві і як ви на нього посилаєтесь. Проте важливо зазначити, що масиви JavaScript мають <dfn>нульовий індекс</dfn>, тобто перший елемент масиву фактично знаходиться в ***нульовій*** позиції, а не в першій. Щоб отримати елемент з масиву, ми можемо помістити індекс в дужки і додати його в кінець масиву або, що відбувається частіше, до змінної, яка посилається на об’єкт масиву. Такий спосіб називають <dfn>дужковою нотацією</dfn>. Наприклад, якщо ми хочемо отримати `a` з `ourArray` та призначити його до змінної, ми можемо зробити це за допомогою такого коду:

```js
let ourVariable = ourArray[0];
```

Тепер `ourVariable` має значення `a`.

Крім доступу до значення, пов’язаного з індексом, ви також можете *встановити* індекс на значення, використовуючи таку ж нотацію:

```js
ourArray[1] = "not b anymore";
```

Використовуючи дужкову нотацію, ми скинули елемент з індексом 1 з рядка `b` на `not b anymore`. Тепер `ourArray` є `["a", "not b anymore", "c"]`.

# --instructions--

Щоб виконати це завдання, встановіть другу позицію (індекс `1`) для `myArray` на будь-що, окрім букви `b`.

# --hints--

`myArray[0]` повинен дорівнювати букві `a`

```js
assert.strictEqual(myArray[0], 'a');
```

`myArray[1]` не повинен дорівнювати букві `b`

```js
assert.notStrictEqual(myArray[1], 'b');
```

`myArray[2]` повинен дорівнювати букві `c`

```js
assert.strictEqual(myArray[2], 'c');
```

`myArray[3]` повинен дорівнювати букві `d`

```js
assert.strictEqual(myArray[3], 'd');
```

# --seed--

## --seed-contents--

```js
let myArray = ["a", "b", "c", "d"];
// Only change code below this line

// Only change code above this line
console.log(myArray);
```

# --solutions--

```js
let myArray = ["a", "b", "c", "d"];
myArray[1] = "e";
```
