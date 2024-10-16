---
id: 587d7dab367417b2b2512b6f
title: some メソッドを使用して、配列内のいずれかの要素が基準を満たしていることを確認する
challengeType: 1
forumTopicId: 301314
dashedName: use-the-some-method-to-check-that-any-elements-in-an-array-meet-a-criteria
---

# --description--

The `some` method works with arrays to check if *any* element passes a particular test. It returns a Boolean value - `true` if any of the values meet the criteria, `false` if not.

たとえば、次のコードは `numbers` 配列のいずれかの要素が 10 未満であるかどうかを調べます。

```js
const numbers = [10, 50, 8, 220, 110, 11];

numbers.some(function(currentValue) {
  return currentValue < 10;
});
```

`some` メソッドは `true` を返します。

# --instructions--

`checkPositive` 関数の中で `some` メソッドを使用して、`arr` 内のいずれかの要素が正かどうかを調べてください。 この関数はブール値を返す必要があります。

# --hints--

コードで `some` メソッドを使用する必要があります。

```js
assert(__helpers.removeJSComments(code).match(/\.some/g));
```

`checkPositive([1, 2, 3, -4, 5])` は `true` を返す必要があります。

```js
assert(checkPositive([1, 2, 3, -4, 5]));
```

`checkPositive([1, 2, 3, 4, 5])` は `true` を返す必要があります。

```js
assert(checkPositive([1, 2, 3, 4, 5]));
```

`checkPositive([-1, -2, -3, -4, -5])` は `false` を返す必要があります。

```js
assert(!checkPositive([-1, -2, -3, -4, -5]));
```

# --seed--

## --seed-contents--

```js
function checkPositive(arr) {
  // Only change code below this line


  // Only change code above this line
}

checkPositive([1, 2, 3, -4, 5]);
```

# --solutions--

```js
function checkPositive(arr) {
  return arr.some(elem => elem > 0);
}
```
