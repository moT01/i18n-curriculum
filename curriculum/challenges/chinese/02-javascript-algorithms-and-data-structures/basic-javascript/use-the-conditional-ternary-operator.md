---
id: 587d7b7e367417b2b2512b24
title: 使用三元运算符
challengeType: 1
forumTopicId: 301181
dashedName: use-the-conditional-ternary-operator
---

# --description--

The <dfn>conditional operator</dfn>, also called the <dfn>ternary operator</dfn>, can be used as a one line if-else expression.

语法是 `a ？ b: c`，其中 `a` 是条件，`b` 是条件返回 `true` 时要运行的代码，`c` 是条件返回 `false` 时要运行的代码。

以下函数使用 `if/else` 语句来检查条件：

```js
function findGreater(a, b) {
  if(a > b) {
    return "a is greater";
  }
  else {
    return "b is greater or equal";
  }
}
```

这可以使用三元运算符重写：

```js
function findGreater(a, b) {
  return a > b ? "a is greater" : "b is greater or equal";
}
```

# --instructions--

在 `checkEqual` 函数中使用三元运算符检查两个数字是否相等。 函数应该返回 `Equal` 或字符串 `Not Equal`。

# --hints--

`checkEqual` 应该使用条件运算符。

```js
assert(/.+?\s*?\?\s*?.+?\s*?:\s*?.+?/.test(__helpers.removeJSComments(code)));
```

`checkEqual(1, 2)` 应该返回字符串 `Not Equal`

```js
assert(checkEqual(1, 2) === 'Not Equal');
```

`checkEqual(1, 1)` 应该返回字符串 `Equal`

```js
assert(checkEqual(1, 1) === 'Equal');
```

`checkEqual(1, -1)` 应该返回字符串 `Not Equal`

```js
assert(checkEqual(1, -1) === 'Not Equal');
```

# --seed--

## --seed-contents--

```js
function checkEqual(a, b) {

}

checkEqual(1, 2);
```

# --solutions--

```js
function checkEqual(a, b) {
  return a === b ? "Equal" : "Not Equal";
}
```
