---
id: 587d78a6367417b2b2512ade
title: إنشاء شكل أكثر تعقيداً بواسطة HTML و CSS
challengeType: 0
videoUrl: 'https://scrimba.com/c/cPpz4fr'
forumTopicId: 301050
dashedName: create-a-more-complex-shape-using-css-and-html
---

# --description--

One of the most popular shapes in the world is the heart shape, and in this challenge you'll create one using pure CSS. But first, you need to understand the `::before` and `::after` pseudo-elements. `::before` creates a pseudo-element that is the first child of the selected element; `::after` creates a pseudo-element that is the last child of the selected element. In the following example, a `::before` pseudo-element is used to add a rectangle to an element with the class `heart`:

```css
.heart::before {
  content: "";
  background-color: yellow;
  border-radius: 25%;
  position: absolute;
  height: 50px;
  width: 70px;
  top: -50px;
  left: 5px;
}
```

لتعمل العناصر المستعارة `::before` و `::after` بشكل صحيح، يجب أن تملك خاصية المحتوى `content` بشكل محددة. هذه الخاصية تستخدم عادة لإضافة أشياء مثل صورة أو نص إلى العنصر المحدد. عندما تستخدم العناصر المستعارة `::before` و `::after` لصنع أشكال، خاصية المحتوى `content` لا تزال مطلوبة، لكنها تكون مضبوطة إلى سلسلة فارغة. في المثال الوارد أعلاه، يحتوى العنصر مع الكلاس `heart` على الخاصية المستعارة `::before` التي تنتج مستطيلاً أصفر بعرض `50px` و طول `70px` على التوالي. This rectangle has round corners due to its 25% `border-radius` and is positioned absolutely at `5px` from the left and `50px` above the top of the element.

# --instructions--

قم بتحويل العنصر على الشاشة إلى قلب. In the `.heart::after` selector, change the `background-color` to `pink` and the `border-radius` to 50%.

Next, target the element with the class `heart` (just `heart`) and fill in the `transform` property. Use the `rotate()` function with -45 degrees.

Finally, in the `.heart::before` selector, set its `content` property to an empty string.

# --hints--

The `background-color` property of the `.heart::after` selector should be `pink`.

```js
const heartAfter = code.match(/\.heart::after\s*{[\s\S]+?[^\}]}/g)?.[0];
assert.match(heartAfter, /({|;)\s*background-color\s*:\s*pink\s*(;|})/g);
```

The `border-radius` of the `.heart::after` selector should be 50%.

```js
assert.lengthOf(code.match(/border-radius\s*?:\s*?50%/gi),2);
```

The `transform` property for the `heart` class should use a `rotate()` function set to -45 degrees.

```js
assert.match(code,/transform\s*?:\s*?rotate\(\s*?-45deg\s*?\)/gi);
```

The `content` of the `.heart::before` selector should be an empty string.

```js
assert.match(code,/\.heart::before\s*?{\s*?content\s*?:\s*?("|')\1\s*?;/gi);
```

# --seed--

## --seed-contents--

```html
<style>
  .heart {
    position: absolute;
    margin: auto;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    background-color: pink;
    height: 50px;
    width: 50px;
    transform: ;
  }
  .heart::after {
    background-color: blue;
    content: "";
    border-radius: 25%;
    position: absolute;
    width: 50px;
    height: 50px;
    top: 0px;
    left: 25px;
  }
  .heart::before {
    content: ;
    background-color: pink;
    border-radius: 50%;
    position: absolute;
    width: 50px;
    height: 50px;
    top: -25px;
    left: 0px;
  }
</style>
<div class="heart"></div>
```

# --solutions--

```html
<style>
  .heart {
    position: absolute;
    margin: auto;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    background-color: pink;
    height: 50px;
    width: 50px;
    transform: rotate(-45deg);
  }
  .heart::after {
    background-color: pink;
    content: "";
    border-radius: 50%;
    position: absolute;
    width: 50px;
    height: 50px;
    top: 0px;
    left: 25px;
  }
  .heart::before {
    content: "";
    background-color: pink;
    border-radius: 50%;
    position: absolute;
    width: 50px;
    height: 50px;
    top: -25px;
    left: 0px;
  }
</style>
<div class="heart"></div>
```
