---
id: 587d778d367417b2b2512aaa
title: Mache Elemente nur für einen Screenreader sichtbar, indem du selbsterstelltes CSS nutzt
challengeType: 0
videoUrl: 'https://scrimba.com/c/cJ8QGkhJ'
forumTopicId: 301020
dashedName: make-elements-only-visible-to-a-screen-reader-by-using-custom-css
---

# --description--

Have you noticed that all of the applied accessibility challenges so far haven't used any CSS? This shows the importance of using a logical document outline and semantically meaningful tags around your content before introducing the visual design aspect.

Allerdings kannst du mit der Magie von CSS auch die Barrierefreiheit deiner Seite verbessern, wenn du Inhalte visuell verbergen willst, die nur für Screenreader gedacht sind. Dies ist der Fall, wenn sich Informationen in einem visuellen Format befinden (wie einem Diagramm), wohingegen Screenreader eine alternative Präsentation benötigen (wie eine Tabelle), um auf die Daten zuzugreifen. CSS wird verwendet, um die ausschließlich für Screenreader bestimmten Elemente außerhalb des sichtbaren Bereichs des Browserfensters zu positionieren.

Hier ist ein Beispiel für die CSS-Regeln, mit denen dies erreicht wird:

```css
.sr-only {
  position: absolute;
  left: -10000px;
  width: 1px;
  height: 1px;
  top: auto;
  overflow: hidden;
}
```

**Hinweis:** Die folgenden CSS-Ansätze werden NICHT dasselbe tun:

<ul>
<li><code>display: none;</code> or <code>visibility: hidden;</code> hides content for everyone, including screen reader users</li>
<li>Nullwerte für Pixelgrößen; z. B. <code>width: 0px; height: 0px;</code> entfernt dieses Element aus dem Fluss deines Dokuments, d. h. Screenreader werden es ignorieren</li>
</ul>

# --instructions--

Camper Cat hat für seine Trainingsseite ein wirklich cooles gestapeltes Balkendiagramm kreiert und eine Tabelle der Daten für Sehbehinderte bereitgestellt. Die Tabelle hat bereits eine `sr-only` ("nur Screenreader") Klasse, aber die CSS-Regeln sind noch nicht ausgefüllt. Gib der `position` einen `absolute` Wert. Setze den Wert für `left` auf `-10000px` und für `width` und `height` je auf `1px`.

# --hints--

Dein Code sollte die Eigenschaft `position` der `sr-only` Klasse auf einen Wert von `absolute` setzen.

```js
const srOnly = document.querySelector('.sr-only');
const position = window.getComputedStyle(srOnly).position; 
assert.equal(position, 'absolute');
```

Dein Code sollte die Eigenschaft `left` der `sr-only` Klasse auf einen Wert von `-10000px` setzen.

```js
const srOnly = document.querySelector('.sr-only');
const left = window.getComputedStyle(srOnly).left;
assert.equal(left, '-10000px');
```

Dein Code sollte die Eigenschaft `width` der `sr-only` Klasse auf einen Wert von `1` Pixel setzen.

```js
assert.match(code , /width:\s*?1px/gi);
```

Dein Code sollte die Eigenschaft `height` der `sr-only` Klasse auf einen Wert von `1` Pixel setzen.

```js
assert.match(code , /height:\s*?1px/gi);
```

# --seed--

## --seed-contents--

```html
<head>
  <style>
  .sr-only {
    position: ;
    left: ;
    width: ;
    height: ;
    top: auto;
    overflow: hidden;
  }
  </style>
</head>
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
  <section>
    <h2>Master Camper Cat's Beginner Three Week Training Program</h2>
    <figure>
      <!-- Stacked bar chart of weekly training -->
      <p>[Stacked bar chart]</p>
      <br />
      <figcaption>Breakdown per week of time to spend training in stealth, combat, and weapons.</figcaption>
    </figure>
    <table class="sr-only">
      <caption>Hours of Weekly Training in Stealth, Combat, and Weapons</caption>
      <thead>
        <tr>
          <th></th>
          <th scope="col">Stealth &amp; Agility</th>
          <th scope="col">Combat</th>
          <th scope="col">Weapons</th>
          <th scope="col">Total</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th scope="row">Week One</th>
          <td>3</td>
          <td>5</td>
          <td>2</td>
          <td>10</td>
        </tr>
        <tr>
          <th scope="row">Week Two</th>
          <td>4</td>
          <td>5</td>
          <td>3</td>
          <td>12</td>
        </tr>
        <tr>
          <th scope="row">Week Three</th>
          <td>4</td>
          <td>6</td>
          <td>3</td>
          <td>13</td>
        </tr>
      </tbody>
    </table>
  </section>
  <section id="stealth">
    <h2>Stealth &amp; Agility Training</h2>
    <article><h3>Climb foliage quickly using a minimum spanning tree approach</h3></article>
    <article><h3>No training is NP-complete without parkour</h3></article>
  </section>
  <section id="combat">
    <h2>Combat Training</h2>
    <article><h3>Dispatch multiple enemies with multithreaded tactics</h3></article>
    <article><h3>Goodbye, world: 5 proven ways to knock out an opponent</h3></article>
  </section>
  <section id="weapons">
    <h2>Weapons Training</h2>
    <article><h3>Swords: the best tool to literally divide and conquer</h3></article>
    <article><h3>Breadth-first or depth-first in multi-weapon training?</h3></article>
  </section>
  <footer>&copy; 2018 Camper Cat</footer>
</body>
```

# --solutions--

```html
<head>
  <style>
  .sr-only {
    position: absolute;
    left: -10000px;
    width: 1px;
    height: 1px;
    top: auto;
    overflow: hidden;
  }
  </style>
</head>
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
  <section>
    <h2>Master Camper Cat's Beginner Three Week Training Program</h2>
    <figure>
      <!-- Stacked bar chart of weekly training -->
      <p>[Stacked bar chart]</p>
      <br />
      <figcaption>Breakdown per week of time to spend training in stealth, combat, and weapons.</figcaption>
    </figure>
    <table class="sr-only">
      <caption>Hours of Weekly Training in Stealth, Combat, and Weapons</caption>
      <thead>
        <tr>
          <th></th>
          <th scope="col">Stealth &amp; Agility</th>
          <th scope="col">Combat</th>
          <th scope="col">Weapons</th>
          <th scope="col">Total</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th scope="row">Week One</th>
          <td>3</td>
          <td>5</td>
          <td>2</td>
          <td>10</td>
        </tr>
        <tr>
          <th scope="row">Week Two</th>
          <td>4</td>
          <td>5</td>
          <td>3</td>
          <td>12</td>
        </tr>
        <tr>
          <th scope="row">Week Three</th>
          <td>4</td>
          <td>6</td>
          <td>3</td>
          <td>13</td>
        </tr>
      </tbody>
    </table>
  </section>
  <section id="stealth">
    <h2>Stealth &amp; Agility Training</h2>
    <article><h3>Climb foliage quickly using a minimum spanning tree approach</h3></article>
    <article><h3>No training is NP-complete without parkour</h3></article>
  </section>
  <section id="combat">
    <h2>Combat Training</h2>
    <article><h3>Dispatch multiple enemies with multithreaded tactics</h3></article>
    <article><h3>Goodbye, world: 5 proven ways to knock out an opponent</h3></article>
  </section>
  <section id="weapons">
    <h2>Weapons Training</h2>
    <article><h3>Swords: the best tool to literally divide and conquer</h3></article>
    <article><h3>Breadth-first or depth-first in multi-weapon training?</h3></article>
  </section>
  <footer>&copy; 2018 Camper Cat</footer>
</body>
```
