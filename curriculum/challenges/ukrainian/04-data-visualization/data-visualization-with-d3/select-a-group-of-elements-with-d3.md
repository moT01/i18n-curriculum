---
id: 587d7fa6367417b2b2512bc3
title: Вибір групи елементів за допомогою D3
challengeType: 6
forumTopicId: 301490
dashedName: select-a-group-of-elements-with-d3
---

# --description--

D3 also has the `selectAll()` method to select a group of elements. It returns an array of HTML nodes for all the items in the document that match the input string. Here's an example to select all the anchor tags in a document:

```js
const anchors = d3.selectAll("a");
```

Як і метод `select()`, `selectAll()` підтримує ланцюжок методів, і ви можете використовувати його з іншими методами.

# --instructions--

Виберіть всі теги `li` в документі та змініть їхній текст на рядок `list item`, приєднавши метод `.text()`.

# --hints--

На сторінці має бути 3 елементи `li`, а текстом кожного з них має бути `list item`. Великі літери та пробіли повинні точно збігатися.

```js
assert(
  $('li')
    .text()
    .match(/list item/g).length == 3
);
```

Код повинен отримати доступ до об’єкта `d3`.

```js
assert(code.match(/d3/g));
```

Код має використати метод `selectAll`.

```js
assert(code.match(/\.selectAll/g));
```

# --seed--

## --seed-contents--

```html
<body>
  <ul>
    <li>Example</li>
    <li>Example</li>
    <li>Example</li>
  </ul>
  <script>
    // Add your code below this line



    // Add your code above this line
  </script>
</body>
```

# --solutions--

```html
<body>
  <ul>
    <li>Example</li>
    <li>Example</li>
    <li>Example</li>
  </ul>
  <script>
    d3.selectAll("li")
      .text("list item")
  </script>
</body>
```
