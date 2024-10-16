---
id: 587d78a9367417b2b2512ae9
title: Використання кривої Безьє для переміщення графіка
challengeType: 0
videoUrl: 'https://scrimba.com/c/c6bnRCK'
forumTopicId: 301071
dashedName: use-a-bezier-curve-to-move-a-graphic
---

# --description--

A previous challenge discussed the `ease-out` keyword that describes an animation change that speeds up first and then slows down at the end of the animation. On the right, the difference between the `ease-out` keyword (for the blue element) and `linear` keyword (for the red element) is demonstrated. Similar animation progressions to the `ease-out` keyword can be achieved by using a custom cubic Bezier curve function.

Загалом зміна точок прив'язки `p1` та `p2` керує створенням різних кривих Безьє, що контролює розвиток анімації в часі. Ось приклад кривої Безьє, створеної за допомогою значень для імітації стилю `ease-out`:

```css
animation-timing-function: cubic-bezier(0, 0, 0.58, 1);
```

Пам'ятайте, що всі функції `cubic-bezier` починаються з `p0` на точці (0, 0) та закінчуються `p3` на точці (1, 1). У цьому прикладі крива рухається швидше по осі Y (починається з 0, тоді рухається до `p1`, y має значення 0, тоді рухається до `p2`, y має значення 1), ніж по осі X (0 на початку, тоді 0 для `p1`, до 0.58 для `p2`). У результаті зміна анімованих елементів відбувається швидше ніж час анімації для даного сегменту. Під кінець кривої зв'язок між зміною значень x та у змінюється на протилежне: значення у переходить від 1 до 1 (без змін), а значення x зміщуються з 0.58 до 1, завдяки чому зміна анімації відбувається повільніше у порівнянні з тривалістю анімації.

# --instructions--

Щоб побачити результат цієї кривої Безьє в дії, змініть `animation-timing-function` елемента з ідентифікацією `red` на функцію `cubic-bezier` зі значеннями х1, y1, x2, y2, які вказані відповідно до `0, 0, 0.58, 1`. Завдяки цьому обидва елементи будуть однаково просуватися по анімації.

# --hints--

Значення властивості `animation-timing-function` для елемента з ідентифікацією `red` повинно бути функцією `cubic-bezier` зі значеннями x1, y1, x2, y2, які вказані відповідно до 0, 0, 0.58, 1 .

```js
const redElement = document.querySelector('#red');
const redStyle = window.getComputedStyle(redElement);
assert.equal(
  redStyle?.animationTimingFunction, 'cubic-bezier(0, 0, 0.58, 1)'
);
```

Елемент з ідентифікацією `red` більше не повинен мати властивість `animation-timing-function` коду `linear`.

```js
const redElement = document.querySelector('#red');
const redStyle = window.getComputedStyle(redElement);
assert.notEqual(redStyle?.animationTimingFunction, 'linear');
```

Значення властивості `animation-timing-function` для елемента з ідентифікацією `blue` не повинно змінюватися.

```js
const blueElement = document.querySelector('#blue');
const blueStyle = window.getComputedStyle( blueElement);
const blueBallAnimation = __helpers.removeWhiteSpace(
  blueStyle?.animationTimingFunction
);
assert.isTrue(
  blueBallAnimation == 'ease-out' ||
    blueBallAnimation == 'cubic-bezier(0,0,0.58,1)'
);
```

# --seed--

## --seed-contents--

```html
<style>
  .balls{
    border-radius: 50%;
    position: fixed;
    width: 50px;
    height: 50px;
    margin-top: 50px;
    animation-name: bounce;
    animation-duration: 2s;
    animation-iteration-count: infinite;
  }
  #red {
    background: red;
    left: 27%;
    animation-timing-function: linear;
  }
  #blue {
    background: blue;
    left: 56%;
    animation-timing-function: ease-out;
  }
  @keyframes bounce {
    0% {
      top: 0px;
    }
    100% {
      top: 249px;
    }
  }
</style>
<div class="balls" id= "red"></div>
<div class="balls" id= "blue"></div>
```

# --solutions--

```html
<style>
  .balls{
    border-radius: 50%;
    position: fixed;
    width: 50px;
    height: 50px;
    margin-top: 50px;
    animation-name: bounce;
    animation-duration: 2s;
    animation-iteration-count: infinite;
  }
  #red {
    background: red;
    left: 27%;
    animation-timing-function: cubic-bezier(0, 0, 0.58, 1);
  }
  #blue {
    background: blue;
    left: 56%;
    animation-timing-function: ease-out;
  }
  @keyframes bounce {
    0% {
      top: 0px;
    }
    100% {
      top: 249px;
    }
  }
</style>
<div class="balls" id= "red"></div>
<div class="balls" id= "blue"></div>
```
