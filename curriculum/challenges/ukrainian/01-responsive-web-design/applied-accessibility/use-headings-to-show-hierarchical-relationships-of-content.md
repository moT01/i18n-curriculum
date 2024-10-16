---
id: 587d774d367417b2b2512a9e
title: Використовуйте заголовки для того, щоб показати ієрархічні зв'язки вмісту
challengeType: 0
videoUrl: 'https://scrimba.com/c/cqVEktm'
forumTopicId: 301026
dashedName: use-headings-to-show-hierarchical-relationships-of-content
---

# --description--

Headings (`h1` through `h6` elements) are workhorse tags that help provide structure and labeling to your content. Screen readers can be set to read only the headings on a page so the user gets a summary. This means it is important for the heading tags in your markup to have semantic meaning and relate to each other, not be picked merely for their size values.

*Semantic meaning* означає, що тег, який ви використовуєте разом із вмістом, вказує на тип інформації, яку він містить.

Якби вам довелось писати роботу із вступом, головною частиною і висновками, то, напевно, було б недоречно розміщувати висновки в основній частині вашої роботи. Це має бути як окремий розділ. Аналогічна ситуація також із заголовками тегів на веб-сторінці, які повинні йти в правильному порядку і вказувати на ієрархічні зв'язки вашого контенту.

Заголовки з рівним (або вищим) статусом започатковують нові запропоновані розділи, а заголовки із нижчим статусом - починають підрозділи попередніх.

Наприклад, сторінка з елементом `h2`, яка супроводжується декількома підрозділами позначена тегом `h4` заплутає користувача, який використовує програму зчитування з екрану. Є шість варіантів. Ми радимо скористатися тегом, адже він виглядає ліпше у браузері, хоча ви також можете використовувати CSS, щоб редагувати відносний порядок за розміром.

І під кінець, кожна сторінка повинна зажди мати один (і тільки один) елемент `h1`, який є ключовим об'єктом вашого контенту. Цей та інші заголовки частково використовуються пошуковими системами, щоб зрозуміти тему сторінки.

# --instructions--

Camper Cat хоче мати сторінку, яка призначена для того, щоб допомогти йому стати ніндзею. Допоможіть йому справитися із заголовками в такий спосіб, щоб розмітка надала оте семантичне значення до контенту і вказала на коректний тісний зв'язок з його розділами. Змініть всі `h5` теги на правильний рівень заголовка, щоб показати, що вони є підрозділами цих кодів `h2`. Використовуйте теги `h3` за потреби.

# --hints--

Ваш код повинен налічувати 6 `h3` елементів.

```js
assert.lengthOf(document.querySelectorAll('h3') , 6);
```

Ваш код має містити 6 тегів `h3`.

```js
assert.lengthOf((code.match(/\/h3/g) || []) ,6);
```

Ваш код не повинен містити жодних елементів `h5`.

```js
assert.isEmpty(document.querySelectorAll('h5'));
```

Ваш код не повинен містити жодних тегів `h5`.

```js
assert.notMatch(code, /\/h5/);
```

# --seed--

## --seed-contents--

```html
<h1>How to Become a Ninja</h1>
<main>
  <h2>Learn the Art of Moving Stealthily</h2>
  <h5>How to Hide in Plain Sight</h5>
  <h5>How to Climb a Wall</h5>

  <h2>Learn the Art of Battle</h2>
  <h5>How to Strengthen your Body</h5>
  <h5>How to Fight like a Ninja</h5>

  <h2>Learn the Art of Living with Honor</h2>
  <h5>How to Breathe Properly</h5>
  <h5>How to Simplify your Life</h5>
</main>
```

# --solutions--

```html
<h1>How to Become a Ninja</h1>
<main>
  <h2>Learn the Art of Moving Stealthily</h2>
  <h3>How to Hide in Plain Sight</h3>
  <h3>How to Climb a Wall</h3>

  <h2>Learn the Art of Battle</h2>
  <h3>How to Strengthen your Body</h3>
  <h3>How to Fight like a Ninja</h3>

  <h2>Learn the Art of Living with Honor</h2>
  <h3>How to Breathe Properly</h3>
  <h3>How to Simplify your Life</h3>
</main>
```
