---
id: 587d7fa7367417b2b2512bc6
title: إضافة تصميم مضمن إلى العناصر
challengeType: 6
forumTopicId: 301475
dashedName: add-inline-styling-to-elements
---

# --description--

D3 lets you add inline CSS styles on dynamic elements with the `style()` method.

طريقة `style()` تأخذ زوج القيمة المفتاحية (key-value pairs) مفصولة بفاصلة كمعطى. إليك مثال لتعيين لون النص المحدد إلى اللون الأزرق:

```js
selection.style("color","blue");
```

# --instructions--

أضف تصميم `style()` إلى الكود في المحرر لجعل كل نص معروض يكون له `font-family` من `verdana`.

# --hints--

يجب أن يكون للعنصر `h2` الخاص بك `font-family` بقيمة `verdana`.

```js
assert($('h2').css('font-family') == 'verdana');
```

يجب أن يستخدم كودك طريقة `style()`.

```js
assert(code.match(/\.style/g));
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
      .style("font-family", "verdana")

  </script>
</body>
```
