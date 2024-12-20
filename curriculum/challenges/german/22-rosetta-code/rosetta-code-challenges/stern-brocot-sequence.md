---
id: 5a23c84252665b21eecc8028
title: Stern-Brocot-Sequenz
challengeType: 1
forumTopicId: 302324
dashedName: stern-brocot-sequence
---

# --description--

Für diese Aufgabe soll die Stern-Brocot-Sequenz durch einen ähnlichen Algorithmus erzeugt werden wie bei der Generierung der <a href="https://rosettacode.org/wiki/Fibonacci_sequence" target="_blank" rel="noopener noreferrer nofollow">Fibonacci-Sequenz</a>.

<ol>
  <li>Die ersten und zweiten Mitglieder der Sequenz sind beide 1:</li>
    <ul><li>1, 1</li></ul>
  <li>Beginne, indem du das zweite Mitglied der Sequenz in Erwägung ziehst</li>
  <li>Summiere das betrachtete Mitglied der Sequenz mit seinem Vorgänger auf, (1 + 1) = 2, und füge es zum Ende der Sequenz hinzu:</li>
    <ul><li>1, 1, 2</li></ul>
  <li>Füge das betrachtete Mitglied der Sequenz an das Ende der Sequenz hinzu:</li>
    <ul><li>1, 1, 2, 1</li></ul>
  <li>Betrachte das nächste Mitglied der Serie, (das dritte Mitglied, d. h. 2)</li>
  <li>Gehe zu 3 </li>
    <ul>
      <li></li>
      <li> ─── Erweitert man eine weitere Schleife, erhält man: ───</li>
      <li></li>
    </ul>
  <li>Summiere das betrachtete Mitglied der Sequenz mit seinem Vorgänger auf, (2 + 1) = 3, und füge es zum Ende der
    -Sequenz hinzu:</li>
    <ul><li>1, 1, 2, 1, 3</li></ul>
  <li>Füge das betrachtete Mitglied der Sequenz an das Ende der Sequenz hinzu:</li>
    <ul><li>1, 1, 2, 1, 3, 2</li></ul>
  <li>Betrachte das nächste Mitglied der Serie, (das vierte Mitglied, d. h. 1)</li>
</ol>

# --instructions--

Erstelle eine Funktion, die die Position in der Stern-Brocot-Sequenz zurückgibt, bei der $ n $ zuerst gefunden wird, wobei die Sequenz mit der oben beschriebenen Methode erzeugt wird. Beachte, dass diese Sequenz eine auf 1 basierende Indexierung verwendet.

# --hints--

`sternBrocot` sollte eine Funktion sein.

```js
assert(typeof sternBrocot == 'function');
```

`sternBrocot(2)` sollte eine Zahl zurückgeben.

```js
assert(typeof sternBrocot(2) == 'number');
```

`sternBrocot(2)` sollte `3` zurückgeben.

```js
assert.equal(sternBrocot(2), 3);
```

`sternBrocot(3)` sollte `5` zurückgeben.

```js
assert.equal(sternBrocot(3), 5);
```

`sternBrocot(5)` sollte `11` zurückgeben.

```js
assert.equal(sternBrocot(5), 11);
```

`sternBrocot(7)` sollte `19` zurückgeben.

```js
assert.equal(sternBrocot(7), 19);
```

`sternBrocot(10)` sollte `39` zurückgeben.

```js
assert.equal(sternBrocot(10), 39);
```

# --seed--

## --seed-contents--

```js
function sternBrocot(num) {

}
```

# --solutions--

```js
function sternBrocot(num) {
  function f(n) {
    return n < 2
      ? n
      : n & 1
      ? f(Math.floor(n / 2)) + f(Math.floor(n / 2 + 1))
      : f(Math.floor(n / 2));
  }

  function gcd(a, b) {
    return a ? (a < b ? gcd(b % a, a) : gcd(a % b, b)) : b;
  }
  var n;
  for (n = 1; f(n) != num; n++);
  return n;
}
```
