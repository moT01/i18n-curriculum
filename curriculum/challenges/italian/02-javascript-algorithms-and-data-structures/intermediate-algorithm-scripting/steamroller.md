---
id: ab306dbdcc907c7ddfc30830
title: Rullo compressore
challengeType: 1
forumTopicId: 16079
dashedName: steamroller
---

# --description--

Flatten a nested array. You must account for varying levels of nesting.

# --hints--

`steamrollArray([[["a"]], [["b"]]])` dovrebbe restituire `["a", "b"]`.

```js
assert.deepEqual(steamrollArray([[['a']], [['b']]]), ['a', 'b']);
```

`steamrollArray([1, [2], [3, [[4]]]])` dovrebbe restituire `[1, 2, 3, 4]`.

```js
assert.deepEqual(steamrollArray([1, [2], [3, [[4]]]]), [1, 2, 3, 4]);
```

`steamrollArray([1, [], [3, [[4]]]])` dovrebbe restituire `[1, 3, 4]`.

```js
assert.deepEqual(steamrollArray([1, [], [3, [[4]]]]), [1, 3, 4]);
```

`steamrollArray([1, {}, [3, [[4]]]])` dovrebbe restituire `[1, {}, 3, 4]`.

```js
assert.deepEqual(steamrollArray([1, {}, [3, [[4]]]]), [1, {}, 3, 4]);
```

La tua soluzione non dovrebbe utilizzare i metodi `Array.prototype.flat()` o `Array.prototype.flatMap()`.

```js
assert(!__helpers.removeJSComments(code).match(/\.\s*flat\s*\(/) && !__helpers.removeJSComments(code).match(/\.\s*flatMap\s*\(/));
```

Le variabili globali non dovrebbero essere utilizzate.

```js
steamrollArray([1, {}, [3, [[4]]]])
assert.deepEqual(steamrollArray([1, {}, [3, [[4]]]]), [1, {}, 3, 4])
```

# --seed--

## --seed-contents--

```js
function steamrollArray(arr) {
  return arr;
}

steamrollArray([1, [2], [3, [[4]]]]);
```

# --solutions--

```js
function steamrollArray(arr) {
  if (!Array.isArray(arr)) {
    return [arr];
  }
  var out = [];
  arr.forEach(function(e) {
    steamrollArray(e).forEach(function(v) {
      out.push(v);
    });
  });
  return out;
}
```
