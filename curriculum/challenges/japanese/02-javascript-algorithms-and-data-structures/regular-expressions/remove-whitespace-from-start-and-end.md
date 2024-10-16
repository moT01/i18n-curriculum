---
id: 587d7dbb367417b2b2512bac
title: 先頭と末尾から空白を削除する
challengeType: 1
forumTopicId: 301362
dashedName: remove-whitespace-from-start-and-end
---

# --description--

Sometimes whitespace characters around strings are not wanted but are there. Typical processing of strings is to remove the whitespace at the start and end of it.

# --instructions--

正規表現で適切な文字列メソッドを使用して、文字列の先頭と末尾の空白を削除してください。

**注:** `String.prototype.trim()` メソッドもこの例では有効ですが、正規表現を使用してこのチャレンジを完了する必要があります。

# --hints--

`result` は文字列 `Hello, World!` と等しくなる必要があります。

```js
assert(result === 'Hello, World!');
```

解答では `String.prototype.trim()` メソッドを使用しないでください。

```js
assert(!__helpers.removeJSComments(code).match(/\.?[\s\S]*?trim/));
```

`result` 変数に文字列を直接設定しないでください。

```js
assert(!__helpers.removeJSComments(code).match(/result\s*=\s*["'`].*?["'`]/));
```

`hello` 変数の値は変更しないでください。

```js
assert(hello === '   Hello, World!  ');
```

# --seed--

## --seed-contents--

```js
let hello = "   Hello, World!  ";
let wsRegex = /change/; // Change this line
let result = hello; // Change this line
```

# --solutions--

```js
let hello = "   Hello, World!  ";
let wsRegex = /^(\s+)(.+[^\s])(\s+)$/;
let result = hello.replace(wsRegex, '$2');
```
