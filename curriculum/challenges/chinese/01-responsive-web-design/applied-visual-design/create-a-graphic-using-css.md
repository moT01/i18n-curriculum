---
id: 587d78a6367417b2b2512add
title: 使用 CSS 创建一个图形
challengeType: 0
videoUrl: 'https://scrimba.com/c/cEDWPs6'
forumTopicId: 301048
dashedName: create-a-graphic-using-css
---

# --description--

By manipulating different selectors and properties, you can make interesting shapes. One of the easier ones to try is a crescent moon shape. For this challenge you need to work with the `box-shadow` property that sets the shadow of an element, along with the `border-radius` property that controls the roundness of the element's corners.

首先我们来创建一个圆的、透明的图形，它具有模糊阴影并略微向两边递减。 如你所见，这个阴影其实就是新月形狀。

为了创建一个圆形的对象，`border-radius` 应该被设置成 50%。

你应该还记得之前关卡的 `box-shadow` 属性以及它的依次取值 `offset-x`、`offset-y`、`blur-radius`、`spread-radius` 和 `color` 值。 其中 `blur-radius` 和 `spread-radius` 是可选的。

# --instructions--

把编辑器里的正方形元素变成新月形状。 首先，把 `background-color` 改为 `transparent`，接着把 `border-radius` 属性设置成 50%，以创建一个圆形。 最后，更改 `box-shadow` 属性，使其 `offset-x` 为 25px，`offset-y` 为 10px，`blur-radius` 为 0，`spread-radius` 为 0，`color` 为 `blue`。

# --hints--

`background-color` 属性值应为 `transparent`。

```js
assert.match(code,/background-color:\s*?transparent;/gi);
```

`border-radius` 属性的值应该设置为 `50%`。

```js
assert.match(code,/border-radius:\s*?50%;/gi);
```

更改 `box-shadow` 属性，使其 `offset-x` 为 25px，`offset-y` 为 10px，`blur-radius` 为 0，`spread-radius` 为 0，`color` 为 `blue`。

```js
assert.match(code,/box-shadow:\s*?25px\s+?10px\s+?0(px)?\s+?0(px)?\s+?blue\s*?;/gi);
```

# --seed--

## --seed-contents--

```html
<style>
  .center {
    position: absolute;
    margin: auto;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    width: 100px;
    height: 100px;
    background-color: blue;
    border-radius: 0px;
    box-shadow: 25px 10px 10px 10px green;
  }

</style>
<div class="center"></div>
```

# --solutions--

```html
<style>
  .center {
    position: absolute;
    margin: auto;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    width: 100px;
    height: 100px;
    background-color: transparent;
    border-radius: 50%;
    box-shadow: 25px 10px 0 0 blue;
  }
</style>
<div class="center"></div>
```
