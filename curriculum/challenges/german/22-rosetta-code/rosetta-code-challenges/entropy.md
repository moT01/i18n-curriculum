---
id: 599d15309e88c813a40baf58
title: Entropie
challengeType: 1
forumTopicId: 302254
dashedName: entropy
---

# --description--

Berechne die Shannon-Entropue H eines gegebenen Eingabestrings.

Bei einer diskreten Zufallsvariablen $X$, die ein String von $N$ "Symbolen" (insgesamt Zeichen) ist, die aus $n$ verschiedenen Zeichen (n=2 für binär) besteht, ist die Shannon-Entropie von X in Bits/Symbol:

$H_2(X) = -\\sum\_{i=1}^n \\frac{count_i}{N} \\log_2 \\left(\\frac{count_i}{N}\\right)$

wobei $count_i$ die Anzahl des Zeichens $n_i$ ist.

# --hints--

`entropy` sollte eine Funktion sein.

```js
assert(typeof entropy === 'function');
```

`entropy("0")` sollte `0` zurückgeben

```js
assert.equal(entropy('0'), 0);
```

`entropy("01")` sollte `1` zurückgeben

```js
assert.equal(entropy('01'), 1);
```

`entropy("0123")` sollte `2` zurückgeben

```js
assert.equal(entropy('0123'), 2);
```

`entropy("01234567")` sollte `3` zurückgeben

```js
assert.equal(entropy('01234567'), 3);
```

`entropy("0123456789abcdef")` sollte `4` zurückgeben

```js
assert.equal(entropy('0123456789abcdef'), 4);
```

`entropy("1223334444")` sollte `1.8464393446710154` zurückgeben

```js
assert.equal(entropy('1223334444'), 1.8464393446710154);
```

# --seed--

## --seed-contents--

```js
function entropy(s) {

}
```

# --solutions--

```js
function entropy(s) {
    // Create a dictionary of character frequencies and iterate over it.
  function process(s, evaluator) {
    let h = Object.create(null),
      k;
    s.split('').forEach(c => {
      h[c] && h[c]++ || (h[c] = 1); });
    if (evaluator) for (k in h) evaluator(k, h[k]);
    return h;
  }
    // Measure the entropy of a string in bits per symbol.

  let sum = 0,
    len = s.length;
  process(s, (k, f) => {
    const p = f / len;
    sum -= p * Math.log(p) / Math.log(2);
  });
  return sum;
}
```
