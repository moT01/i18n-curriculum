---
id: 587d778a367417b2b2512aa5
title: Як покращити доступність графіків за допомогою Елемента figure
challengeType: 0
videoUrl: 'https://scrimba.com/c/cGJMqtE'
forumTopicId: 301015
dashedName: improve-chart-accessibility-with-the-figure-element
---

# --description--

HTML5 introduced the `figure` element and the related `figcaption`. Used together, these items wrap a visual representation (like an image, diagram, or chart) along with its caption. Wrapping these elements together gives a two-fold accessibility boost by semantically grouping related content and providing a text alternative explaining the `figure`.

Для візуалізації даних на кшталт графіків можна використовувати підпис із короткими відмітками прогнозів чи висновків для користувачів із вадами зору. Ще одна проблема полягає в тому, щоб перемістити табличні дані графіку за межі екрану (за допомогою CSS) для користувачів зчитувачів з екрану.

Ось приклад - зверніть увагу не те, що `figcaption` знаходиться всередині теґів `figure` і може поєднуватися з іншими елементами:

```html
<figure>
  <img src="roundhouseDestruction.jpeg" alt="Photo of Camper Cat executing a roundhouse kick">
  <br>
  <figcaption>
    Master Camper Cat demonstrates proper form of a roundhouse kick.
  </figcaption>
</figure>
```

# --instructions--

Кіт Кампер сумлінно працює над створенням гістограми з накопиченням, яка показує кількість часу на тиждень, що відводиться на тренування невловимості, бойових мистецв та володіння зброєю. Допоможіть йому краще структурувати сторінку, змінивши теґ `div`, який він використав, на теґ `figure`, а теґ the `p`, що оточує заголовок, на теґ `figcaption`.

# --hints--

Ваш код повинен містити один теґ `figure`.

```js
assert.lengthOf(document.querySelectorAll('figure') , 1);
```

Ваш код повинен містити один теґ `figcaption`.

```js
assert.lengthOf(document.querySelectorAll('figcaption') , 1);
```

Ваш код не повинен містити жодних тегів `div`.

```js
assert.lengthOf(document.querySelectorAll('div'), 0);
```

Ваш код не повинен містити жодних теґів `p`.

```js
assert.lengthOf(document.querySelectorAll('p') , 0);
```

Теґ `figcaption` має бути дочірнім елементом теґу `figure`.

```js
const figure = document.querySelector('figure');
const children = figure?.querySelectorAll(`:scope ${'figcaption'}`);
assert.lengthOf(children, 1);
```

Елемент `figure` повинен мати кінцевий тег.

```js
assert.isTrue(
    code.match(/<\/figure>/g)?.length === code.match(/<figure>/g)?.length
);
```

# --seed--

## --seed-contents--

```html
<body>
  <header>
    <h1>Training</h1>
    <nav>
      <ul>
        <li><a href="#stealth">Stealth &amp; Agility</a></li>
        <li><a href="#combat">Combat</a></li>
        <li><a href="#weapons">Weapons</a></li>
      </ul>
    </nav>
  </header>
  <main>
    <section>

      <!-- Only change code below this line -->
      <div>
        <!-- Stacked bar chart will go here -->
        <br>
        <p>Breakdown per week of time to spend training in stealth, combat, and weapons.</p>
      </div>
      <!-- Only change code above this line -->

    </section>
    <section id="stealth">
      <h2>Stealth &amp; Agility Training</h2>
      <article><h3>Climb foliage quickly using a minimum spanning tree approach</h3></article>
      <article><h3>No training is NP-complete without parkour</h3></article>
    </section>
    <section id="combat">
      <h2>Combat Training</h2>
      <article><h3>Dispatch multiple enemies with multithreaded tactics</h3></article>
      <article><h3>Goodbye world: 5 proven ways to knock out an opponent</h3></article>
    </section>
    <section id="weapons">
      <h2>Weapons Training</h2>
      <article><h3>Swords: the best tool to literally divide and conquer</h3></article>
      <article><h3>Breadth-first or depth-first in multi-weapon training?</h3></article>
    </section>
  </main>
  <footer>&copy; 2018 Camper Cat</footer>
</body>
```

# --solutions--

```html
<body>
  <header>
    <h1>Training</h1>
    <nav>
      <ul>
        <li><a href="#stealth">Stealth &amp; Agility</a></li>
        <li><a href="#combat">Combat</a></li>
        <li><a href="#weapons">Weapons</a></li>
      </ul>
    </nav>
  </header>
  <main>
    <section>
      <figure>
        <!-- Stacked bar chart will go here -->
        <br>
        <figcaption>Breakdown per week of time to spend training in stealth, combat, and weapons.</figcaption>
      </figure>
    </section>
    <section id="stealth">
      <h2>Stealth &amp; Agility Training</h2>
      <article><h3>Climb foliage quickly using a minimum spanning tree approach</h3></article>
      <article><h3>No training is NP-complete without parkour</h3></article>
    </section>
    <section id="combat">
      <h2>Combat Training</h2>
      <article><h3>Dispatch multiple enemies with multithreaded tactics</h3></article>
      <article><h3>Goodbye world: 5 proven ways to knock out an opponent</h3></article>
    </section>
    <section id="weapons">
      <h2>Weapons Training</h2>
      <article><h3>Swords: the best tool to literally divide and conquer</h3></article>
      <article><h3>Breadth-first or depth-first in multi-weapon training?</h3></article>
    </section>
  </main>
  <footer>&copy; 2018 Camper Cat</footer>
</body>
```
