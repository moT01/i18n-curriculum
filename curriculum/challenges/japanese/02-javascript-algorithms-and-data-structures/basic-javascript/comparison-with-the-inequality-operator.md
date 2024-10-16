---
id: 56533eb9ac21ba0edf2244d2
title: 不等価演算子による比較
challengeType: 1
videoUrl: 'https://scrimba.com/c/cdBm9Sr'
forumTopicId: 16787
dashedName: comparison-with-the-inequality-operator
---

# --description--

The inequality operator (`!=`) is the opposite of the equality operator. Inequality means not equal. The inequality operator returns `false` when the equality operator would return `true` and *vice versa*. Like the equality operator, the inequality operator will convert data types of values while comparing.

**例**

```js
1 !=  2    // true
1 != "1"   // false
1 != '1'   // false
1 != true  // false
0 != false // false
```

# --instructions--

`val` が `99` と等しくない場合に関数が文字列 `Not Equal` を返すように、`if` ステートメントに不等価演算子 `!=` を追加してください。

# --hints--

`testNotEqual(99)` は文字列 `Equal` を返す必要があります。

```js
assert(testNotEqual(99) === 'Equal');
```

`testNotEqual("99")` は文字列 `Equal` を返す必要があります。

```js
assert(testNotEqual('99') === 'Equal');
```

`testNotEqual(12)` は文字列 `Not Equal` を返す必要があります。

```js
assert(testNotEqual(12) === 'Not Equal');
```

`testNotEqual("12")` は文字列 `Not Equal` を返す必要があります。

```js
assert(testNotEqual('12') === 'Not Equal');
```

`testNotEqual("bob")` は文字列 `Not Equal` を返す必要があります。

```js
assert(testNotEqual('bob') === 'Not Equal');
```

`!=` 演算子を使用してください。

```js
assert(__helpers.removeJSComments(code).match(/(?!!==)!=/));
```

# --seed--

## --seed-contents--

```js
// Setup
function testNotEqual(val) {
  if (val) { // Change this line
    return "Not Equal";
  }
  return "Equal";
}

testNotEqual(10);
```

# --solutions--

```js
function testNotEqual(val) {
  if (val != 99) {
    return "Not Equal";
  }
  return "Equal";
}
```
