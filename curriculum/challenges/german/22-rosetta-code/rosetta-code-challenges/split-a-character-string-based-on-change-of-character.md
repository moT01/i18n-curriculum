---
id: 5a23c84252665b21eecc801d
title: Aufteilung einer Zeichenkette aufgrund eines Zeichenwechsels
challengeType: 1
forumTopicId: 302322
dashedName: split-a-character-string-based-on-change-of-character
---

# --description--

Aufteilung einer (Zeichen-) Zeichenkette in durch Komma (plus Leerzeichen) getrennte Zeichenketten auf der Grundlage eines Zeichenwechsels (von links nach rechts). Leerzeichen sollten wie jedes andere Zeichen behandelt werden (mit der Ausnahme, dass es problematisch ist, sie deutlich darzustellen). Dasselbe gilt für Kommas. Zum Beispiel: die Zeichenkette:

<pre>
"gHHH5YY++///\\"
</pre>

sollte so aufgeteilt werden:

<pre>
["g", "HHH", "5", "YY", "++", "///", "\\" ];
</pre>

# --hints--

`split` sollte eine Funktion sein.

```js
assert(typeof split == 'function');
```

`split("hello")` sollte ein Array zurückgeben.

```js
assert(Array.isArray(split('hello')));
```

`split("hello")` sollte `["h", "e", "ll", "o"]` zurückgeben.

```js
assert.deepEqual(split('hello'), ['h', 'e', 'll', 'o']);
```

`split("commission")` sollte `["c", "o", "mm", "i", "ss", "i", "o", "n"]` zurückgeben.

```js
assert.deepEqual(split('commission'), [
  'c',
  'o',
  'mm',
  'i',
  'ss',
  'i',
  'o',
  'n'
]);
```

`split("ssss----====llloooo")` sollte `["ssss", "----", "====", "lll", "oooo"]` zurückgeben.

```js
assert.deepEqual(split('ssss----====llloooo'), [
  'ssss',
  '----',
  '====',
  'lll',
  'oooo'
]);
```

`split("sssmmmaaammmaaat")` sollte `["sss", "mmm", "aaa", "mmm", "aaa", "t"]` zurückgeben.

```js
assert.deepEqual(split('sssmmmaaammmaaat'), [
  'sss',
  'mmm',
  'aaa',
  'mmm',
  'aaa',
  't'
]);
```

`split("gHHH5YY++///\\")` sollte `["g", "HHH", "5", "YY", "++", "///", "\\"]` zurückgeben.

```js
assert.deepEqual(split('gHHH5YY++///\\'), [
  'g',
  'HHH',
  '5',
  'YY',
  '++',
  '///',
  '\\'
]);
```

# --seed--

## --seed-contents--

```js
function split(str) {

}
```

# --solutions--

```js
function split(str) {
  const concat = xs =>
    xs.length > 0
      ? (() => {
          const unit = typeof xs[0] === 'string' ? '' : [];
          return unit.concat.apply(unit, xs);
        })()
      : [];

  const group = xs => groupBy((a, b) => a === b, xs);

  const groupBy = (f, xs) => {
    const dct = xs.slice(1).reduce(
      (a, x) => {
        const h = a.active.length > 0 ? a.active[0] : undefined,
          blnGroup = h !== undefined && f(h, x);
        return {
          active: blnGroup ? a.active.concat([x]) : [x],
          sofar: blnGroup ? a.sofar : a.sofar.concat([a.active])
        };
      },
      {
        active: xs.length > 0 ? [xs[0]] : [],
        sofar: []
      }
    );
    return dct.sofar.concat(dct.active.length > 0 ? [dct.active] : []);
  };

  const map = (f, xs) => xs.map(f);

  const stringChars = s => s.split('');

  return map(concat, group(stringChars(str)));
}
```
