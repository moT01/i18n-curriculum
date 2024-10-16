---
id: 587d7db4367417b2b2512b92
title: 提取匹配項
challengeType: 1
forumTopicId: 301340
dashedName: extract-matches
---

# --description--

So far, you have only been checking if a pattern exists or not within a string. You can also extract the actual matches you found with the `.match()` method.

可以使用字符串來調用 `.match()` 方法，並在括號內傳入正則表達式。

請看下面的舉例：

```js
"Hello, World!".match(/Hello/);
let ourStr = "Regular expressions";
let ourRegex = /expressions/;
ourStr.match(ourRegex);
```

這裏第一個 `match` 將返回 `["Hello"]` 第二個將返回 `["expressions"]`。

請注意， `.match` 語法是目前爲止一直使用的 `.test` 方法中的“反向”：

```js
'string'.match(/regex/);
/regex/.test('string');
```

# --instructions--

利用 `.match()` 方法提取單詞 `coding`。

# --hints--

`result` 應該有字符串 `coding`

```js
assert(result.join() === 'coding');
```

您的 regex `codingRegex` 應該搜索字符串 `coding`

```js
assert(codingRegex.source === 'coding');
```

您應該使用 `.match()` 方法。

```js
assert(__helpers.removeJSComments(code).match(/\.match\(.*\)/));
```

# --seed--

## --seed-contents--

```js
let extractStr = "Extract the word 'coding' from this string.";
let codingRegex = /change/; // Change this line
let result = extractStr; // Change this line
```

# --solutions--

```js
let extractStr = "Extract the word 'coding' from this string.";
let codingRegex = /coding/; // Change this line
let result = extractStr.match(codingRegex); // Change this line
```
