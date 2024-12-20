---
id: 587d781d367417b2b2512ac8
title: Зміна стану якірного тега при наведенні курсора
challengeType: 0
videoUrl: 'https://scrimba.com/c/cakRGcm'
forumTopicId: 301035
dashedName: adjust-the-hover-state-of-an-anchor-tag
---

# --description--

This challenge will touch on the usage of pseudo-classes. A pseudo-class is a keyword that can be added to selectors, in order to select a specific state of the element.

Наприклад, стиль якірного тега при наведенні курсора можна змінити за допомогою `:hover` селектора псевдокласу. Ось CSS для зміни властивості `color` якірного тегу на червоний при наведенні:

```css
a:hover {
  color: red;
}
```

# --instructions--

Редактор коду має правило CSS, щоб змінити колір усіх тегів `a` на чорний. Додайте таке правило, щоб при наведенні користувачем курсора на тег `a` його колір `color` ставав синім.

# --hints--

Колір якірного тегу `color` має залишатися чорним, додайте правила CSS лише для стану `:hover`.

```js
const anchorElement = document.querySelector("a"); 
const anchorStyle = window.getComputedStyle(anchorElement);
assert.equal(anchorStyle?.color, 'rgb(0, 0, 0)');
```

Колір якірного тега має ставати синім `color` при наведенні.

```js
assert.match(code,
    /a:hover\s*?{\s*?color:\s*?(blue|rgba\(\s*?0\s*?,\s*?0\s*?,\s*?255\s*?,\s*?1\s*?\)|#00F|rgb\(\s*?0\s*?,\s*?0\s*?,\s*?255\s*?\))\s*?;\s*?}/gi
  );
```

# --seed--

## --seed-contents--

```html
<style>
  a {
    color: #000;
  }



</style>
<a href="https://freecatphotoapp.com/" target="_blank">CatPhotoApp</a>
```

# --solutions--

```html
<style>
  a {
    color: #000;
  }
  a:hover {
    color: rgba(0,0,255,1);
  }
</style>
<a href="https://freecatphotoapp.com/" target="_blank">CatPhotoApp</a>
```
