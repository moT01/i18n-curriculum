---
id: 587d78ae367417b2b2512aff
title: استخدم خاصية order لإعادة ترتيب العناصر
challengeType: 0
videoUrl: 'https://scrimba.com/p/pVaDAv/cMbvNAG'
forumTopicId: 301116
dashedName: use-the-order-property-to-rearrange-items
---

# --description--

The `order` property is used to tell CSS the order of how flex items appear in the flex container. By default, items will appear in the same order they come in the source HTML. The property takes numbers as values, and negative numbers can be used.

# --instructions--

أضف خاصية CSS `order` لدى كل من `#box-1` و `#box-2`. أعط `#box-1` قيمة `2` و أعط `#box-2` قيمة `1`.

# --hints--

العنصر `#box-1` يحصل على خاصية `order` و يعطى قيمة `2`.

```js
assert($('#box-1').css('order') == '2');
```

العنصر `#box-2` يجب أن يحصل على خاصية `order` بتعيين قيمته إلى `1`.

```js
assert($('#box-2').css('order') == '1');
```

# --seed--

## --seed-contents--

```html
<style>
  #box-container {
    display: flex;
    height: 500px;
  }
  #box-1 {
    background-color: dodgerblue;

    height: 200px;
    width: 200px;
  }

  #box-2 {
    background-color: orangered;

    height: 200px;
    width: 200px;
  }
</style>

<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
</div>
```

# --solutions--

```html
<style>
  #box-container {
    display: flex;
    height: 500px;
  }
  #box-1 {
    background-color: dodgerblue;
    order: 2;
    height: 200px;
    width: 200px;
  }

  #box-2 {
    background-color: orangered;
    order: 1;
    height: 200px;
    width: 200px;
  }
</style>

<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
</div>
```
