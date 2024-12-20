---
id: 587d7fa7367417b2b2512bc7
title: Змініть стилі на основі даних
challengeType: 6
forumTopicId: 301479
dashedName: change-styles-based-on-data
---

# --description--

D3 is about visualization and presentation of data. It's likely you'll want to change the styling of elements based on the data. For example, you may want to color a data point blue if it has a value less than 20, and red otherwise. You can use a callback function in the `style()` method and include the conditional logic. The callback function uses the `d` parameter to represent the data point:

```js
selection.style("color", (d) => {

});
```

Метод `style()` не обмежується лише властивістю `color`: його можна використати і з іншими властивостями CSS.

# --instructions--

Додайте метод `style()` до коду в редакторі, щоб встановити `color` елементів `h2` за умовою. Напишіть функцію зворотного виклику, щоб вона повернула червоний колір, якщо значення менше ніж 20, а в іншому випадку — зелений.

**Примітка:** ви можете використати логіку if-else або тернарний оператор.

# --hints--

Перший `h2` повинен мати червоний `color`.

```js
assert($('h2').eq(0).css('color') == 'rgb(255, 0, 0)');
```

Другий `h2` повинен мати зелений `color`.

```js
assert($('h2').eq(1).css('color') == 'rgb(0, 128, 0)');
```

Третій `h2` повинен мати зелений `color`.

```js
assert($('h2').eq(2).css('color') == 'rgb(0, 128, 0)');
```

Четвертий `h2` повинен мати червоний `color`.

```js
assert($('h2').eq(3).css('color') == 'rgb(255, 0, 0)');
```

П’ятий `h2` повинен мати зелений `color`.

```js
assert($('h2').eq(4).css('color') == 'rgb(0, 128, 0)');
```

Шостий `h2` повинен мати червоний `color`.

```js
assert($('h2').eq(5).css('color') == 'rgb(255, 0, 0)');
```

Сьомий `h2` повинен мати зелений `color`.

```js
assert($('h2').eq(6).css('color') == 'rgb(0, 128, 0)');
```

Восьмий `h2` повинен мати червоний `color`.

```js
assert($('h2').eq(7).css('color') == 'rgb(255, 0, 0)');
```

Дев’ятий `h2` повинен мати червоний `color`.

```js
assert($('h2').eq(8).css('color') == 'rgb(255, 0, 0)');
```

# --seed--

## --seed-contents--

```html
<body>
  <script>
    const dataset = [12, 31, 22, 17, 25, 18, 29, 14, 9];

    d3.select("body").selectAll("h2")
      .data(dataset)
      .enter()
      .append("h2")
      .text((d) => (d + " USD"))
      // Add your code below this line



      // Add your code above this line
  </script>
</body>
```

# --solutions--

```html
<body>
  <script>
    const dataset = [12, 31, 22, 17, 25, 18, 29, 14, 9];

    d3.select("body").selectAll("h2")
      .data(dataset)
      .enter()
      .append("h2")
      .text((d) => (d + " USD"))
      .style("color", (d) => d < 20 ? "red" : "green")
  </script>
</body>
```
