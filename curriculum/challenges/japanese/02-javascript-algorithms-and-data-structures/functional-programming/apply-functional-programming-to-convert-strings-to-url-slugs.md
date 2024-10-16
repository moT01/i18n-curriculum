---
id: 587d7dab367417b2b2512b6d
title: 関数型プログラミングを適用して文字列を URL スラッグに変換する
challengeType: 1
forumTopicId: 301227
dashedName: apply-functional-programming-to-convert-strings-to-url-slugs
---

# --description--

The last several challenges covered a number of useful array and string methods that follow functional programming principles. We've also learned about `reduce`, which is a powerful method used to reduce problems to simpler forms. From computing averages to sorting, any array operation can be achieved by applying it. Recall that `map` and `filter` are special cases of `reduce`.

ここまで学んだことを駆使して、実際の問題を解決してみましょう。

多くのコンテンツ管理サイト (CMS) では、ブックマークを簡単に付けられるように、投稿のタイトルが URL の一部に追加されています。 たとえば、Medium で `Stop Using Reduce` というタイトルの記事を書いた場合、その URL にはタイトル文字列が何らかの形で含まれる可能性が高くなります (`.../stop-using-reduce`)。 すでに freeCodeCamp サイトで気づいている方もいらっしゃるかもしれません。

# --instructions--

文字列 `title` を変換して、ハイフンつなぎの URL を返す、`urlSlug` 関数を記述してください。 このセクションで取り上げたすべてのメソッドを使用できますが、`replace` は使用しないでください。 要件は次のとおりです。

入力は、スペースとタイトルケースの単語を含む文字列

出力は、単語間のスペースをハイフン (`-`) に置き換えた文字列

出力はすべて小文字

出力にはスペースを含めない

# --hints--

このチャレンジに `replace` メソッドを使用しないでください。

```js
assert(!__helpers.removeJSComments(code).match(/\.?[\s\S]*?replace/g));
```

`urlSlug("Winter Is Coming")` は文字列 `winter-is-coming` を返す必要があります。

```js
assert(urlSlug('Winter Is Coming') === 'winter-is-coming');
```

`urlSlug(" Winter Is  Coming")` は文字列 `winter-is-coming` を返す必要があります。

```js
assert(urlSlug(' Winter Is  Coming') === 'winter-is-coming');
```

`urlSlug("A Mind Needs Books Like A Sword Needs A Whetstone")` は文字列 `a-mind-needs-books-like-a-sword-needs-a-whetstone` を返す必要があります。

```js
assert(
  urlSlug('A Mind Needs Books Like A Sword Needs A Whetstone') ===
    'a-mind-needs-books-like-a-sword-needs-a-whetstone'
);
```

`urlSlug("Hold The Door")` は文字列 `hold-the-door` を返す必要があります。

```js
assert(urlSlug('Hold The Door') === 'hold-the-door');
```

# --seed--

## --seed-contents--

```js
// Only change code below this line
function urlSlug(title) {


}
// Only change code above this line
urlSlug("A Mind Needs Books Like A Sword Needs A Whetstone");
```

# --solutions--

```js
function urlSlug(title) {
  return title.trim().split(/\s+/).join("-").toLowerCase();
}
```
