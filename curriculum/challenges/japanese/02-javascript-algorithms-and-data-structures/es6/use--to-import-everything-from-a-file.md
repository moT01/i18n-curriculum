---
id: 587d7b8c367417b2b2512b57
title: '* を使用してファイルからすべてのものをインポートする'
challengeType: 1
forumTopicId: 301210
dashedName: use--to-import-everything-from-a-file
---

# --description--

Suppose you have a file and you wish to import all of its contents into the current file. This can be done with the `import * as` syntax. Here's an example where the contents of a file named `math_functions.js` are imported into a file in the same directory:

```js
import * as myMathModule from "./math_functions.js";
```

上記の `import` ステートメントでは、`myMathModule` というオブジェクトが作成されます。 これは変数名にすぎないため、好きな名前を付けることができます。 このオブジェクトには、`math_functions.js` からエクスポートされたすべてのものが格納されるため、他のオブジェクトプロパティと同じように関数にアクセスできます。 たとえば、インポートした `add` 関数と `subtract` 関数を次のように使用できます。

```js
myMathModule.add(2,3);
myMathModule.subtract(5,3);
```

# --instructions--

このファイル内のコードでは、ファイル `string_functions.js` の内容を必要としています。このファイルは現在のファイルと同じディレクトリにあります。 `import * as` 構文を使用してファイルのすべての内容を `stringFunctions` というオブジェクトにインポートしてください。

# --hints--

`import * as` 構文を正しく使用する必要があります。

```js
assert(
  __helpers.removeJSComments(code).match(
    /import\s*\*\s*as\s+stringFunctions\s+from\s*('|")\.\/string_functions\.js\1/g
  )
);
```

# --seed--

## --seed-contents--

```js

// Only change code above this line

stringFunctions.uppercaseString("hello");
stringFunctions.lowercaseString("WORLD!");
```

# --solutions--

```js
import * as stringFunctions from "./string_functions.js";

// add code above this line
stringFunctions.uppercaseString("hello");
stringFunctions.lowercaseString("WORLD!");
```
