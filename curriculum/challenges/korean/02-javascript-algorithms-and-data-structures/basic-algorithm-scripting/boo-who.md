---
id: a77dbc43c33f39daa4429b4f
title: 원시 타입 불리언 찾기
challengeType: 1
forumTopicId: 16000
dashedName: boo-who
---

# --description--

Check if a value is classified as a boolean primitive. Return `true` or `false`.

불리언 원시 값의 종류로는 `true`와 `false`가 있습니다.

# --hints--

`booWho(true)`는 `true`를 반환해야 합니다.

```js
assert.strictEqual(booWho(true), true);
```

`booWho(false)`는 `true`를 반환해야 합니다.

```js
assert.strictEqual(booWho(false), true);
```

`booWho([1, 2, 3])`은 `false`를 반환해야 합니다.

```js
assert.strictEqual(booWho([1, 2, 3]), false);
```

`booWho([].slice)`은 `false`를 반환합니다.

```js
assert.strictEqual(booWho([].slice), false);
```

`booWho({ "a": 1 })`는 `false`를 반환합니다.

```js
assert.strictEqual(booWho({ a: 1 }), false);
```

`booWho(1)`는 `false`를 반환해야 합니다.

```js
assert.strictEqual(booWho(1), false);
```

`booWho(NaN)`는 `false`를 반환합니다.

```js
assert.strictEqual(booWho(NaN), false);
```

`booWho("a")`는 `false`를 반환해야 합니다.

```js
assert.strictEqual(booWho('a'), false);
```

`booWho("true")`는 `false`를 반환해야 합니다.

```js
assert.strictEqual(booWho('true'), false);
```

`booWho("false")`는 `false`를 반환해야 합니다.

```js
assert.strictEqual(booWho('false'), false);
```

# --seed--

## --seed-contents--

```js
function booWho(bool) {
  return bool;
}

booWho(null);
```

# --solutions--

```js
function booWho(bool) {
  return typeof bool === "boolean";
}

booWho(null);
```
