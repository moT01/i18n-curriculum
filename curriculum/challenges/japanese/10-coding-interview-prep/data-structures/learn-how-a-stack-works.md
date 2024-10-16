---
id: 587d8250367417b2b2512c5e
title: スタックの仕組みを学ぶ
challengeType: 1
forumTopicId: 301705
dashedName: learn-how-a-stack-works
---

# --description--

You are probably familiar with stack of books on your table. You have likely used the undo feature of a text editor. You are also probably used to hitting the back button on your phone to go back to the previous view in your app.

そのすべてに共通する点は何でしょうか？ それらはすべて、後方に走査できるようにデータを格納しています。

本の山の一番上にある本は、最後に置かれた本でした。 山の一番上からその本を取り除くと、最後の本より先に置かれた本が見え、本を取り除くたびに同じことが起こります。

そう考えると、上のすべての例で<dfn>後入れ先出し</dfn>タイプのサービスを受けていることになります。 これをコードを使って再現してみましょう。

このようなデータ保存は<dfn>スタック</dfn>と呼ばれます。 具体的には、JavaScript オブジェクトをスタックの一番上にプッシュする `push()` メソッドと、現在スタックの一番上にある JavaScript オブジェクトを削除する `pop()` メソッドを実装する必要があります。

# --instructions--

ここでは、配列で表現された宿題のスタックがあります。`"BIO12"` (生物 12) はスタックの一番下、`"PSY44"` (物理 44) は一番上です。

与えられた配列を変更し、上述の JavaScript メソッドを使用してそれを `stack` のように扱ってください。 一番上の要素 `"PSY44"` をスタックから削除します。 次に、スタックの新しい一番上の要素として `"CS50"` (コンピュータサイエンス 50) を追加します。

# --hints--

`homeworkStack` には 4 つの要素のみが含まれている必要があります。

```js
assert(homeworkStack.length === 4);
```

`homeworkStack` の最後の要素は `"CS50"` でなければなりません。

```js
assert(homeworkStack[3] === 'CS50');
```

`homeworkStack` に `"PSY44"` を含めることはできません。

```js
assert(homeworkStack.indexOf('PSY44') === -1);
```

`homeworkStack` の最初の宣言は変更しないでください。

```js
assert(
  __helpers.removeJSComments(code).match(/=/g).length === 1 &&
    /homeworkStack\s*=\s*\["BIO12"\s*,\s*"HIS80"\s*,\s*"MAT122"\s*,\s*"PSY44"\]/.test(
      __helpers.removeJSComments(code)
    )
);
```

# --seed--

## --seed-contents--

```js
var homeworkStack = ["BIO12","HIS80","MAT122","PSY44"];
// Only change code below this line
```

# --solutions--

```js
// solution required
```
