---
id: 56533eb9ac21ba0edf2244d6
title: 小なり演算子による比較
challengeType: 1
videoUrl: 'https://scrimba.com/c/cNVRWtB'
forumTopicId: 16789
dashedName: comparison-with-the-less-than-operator
---

# --description--

The less than operator (`<`) compares the values of two numbers. If the number to the left is less than the number to the right, it returns `true`. Otherwise, it returns `false`. Like the equality operator, the less than operator converts data types while comparing.

**例**

```js
2   < 5 // true
'3' < 7 // true
5   < 5 // false
3   < 2 // false
'8' < 4 // false
```

# --instructions--

return ステートメントの意味が正しくなるように、指定された行に小なり演算子を追加してください。

# --hints--

`testLessThan(0)` は文字列 `Under 25` を返す必要があります。

```js
assert(testLessThan(0) === 'Under 25');
```

`testLessThan(24)` は文字列 `Under 25` を返す必要があります。

```js
assert(testLessThan(24) === 'Under 25');
```

`testLessThan(25)` は文字列 `Under 55` を返す必要があります。

```js
assert(testLessThan(25) === 'Under 55');
```

`testLessThan(54)` は文字列 `Under 55` を返す必要があります。

```js
assert(testLessThan(54) === 'Under 55');
```

`testLessThan(55)` は文字列 `55 or Over` を返す必要があります。

```js
assert(testLessThan(55) === '55 or Over');
```

`testLessThan(99)` は文字列 `55 or Over` を返す必要があります。

```js
assert(testLessThan(99) === '55 or Over');
```

`<` 演算子を 2 回以上使用してください。

```js
assert(__helpers.removeJSComments(code).match(/val\s*<\s*('|")*\d+('|")*/g).length > 1);
```

# --seed--

## --seed-contents--

```js
function testLessThan(val) {
  if (val) {  // Change this line
    return "Under 25";
  }

  if (val) {  // Change this line
    return "Under 55";
  }

  return "55 or Over";
}

testLessThan(10);
```

# --solutions--

```js
function testLessThan(val) {
  if (val < 25) {  // Change this line
    return "Under 25";
  }

  if (val < 55) {  // Change this line
    return "Under 55";
  }

  return "55 or Over";
}
```
