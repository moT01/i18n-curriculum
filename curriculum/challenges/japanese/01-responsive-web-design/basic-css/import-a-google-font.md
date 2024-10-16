---
id: bad87fee1348bd9aedf08807
title: Google フォントをインポートする
challengeType: 0
videoUrl: 'https://scrimba.com/c/cM9MRsJ'
forumTopicId: 18200
dashedName: import-a-google-font
---

# --description--

In addition to specifying common fonts that are found on most operating systems, we can also specify non-standard, custom web fonts for use on our website. There are many sources for web fonts on the Internet. For this example we will focus on the Google Fonts library.

Google Fonts は無料の Web フォントのライブラリで、フォントの URL を参照することによって CSS の中で使用できます。

では、Google フォントをインポートして適用してみましょう (もしあなたの国で Google がブロックされている場合は、このチャレンジを飛ばしてください) 。

Google フォントをインポートするには、Google Fonts のライブラリからフォントの URL をコピーしてあなたの HTML に貼り付けます。 このチャレンジでは、`Lobster` フォントをインポートしてみましょう。 そうするには、次のコードスニペットをコピーしてコードエディタの一番上に貼り付けます ( `style` 要素の前に):

```html
<link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
```

これで、あなたの CSS で `Lobster` フォントが使えるようになりました。下記の例の FAMILY_NAME の部分に `Lobster` を使うことができます:

```css
font-family: FAMILY_NAME, GENERIC_NAME;
```

GENERIC_NAME は必須ではなく、他の指定したフォントが使用できない場合に備えるフォールバックフォントです。 これは次のチャレンジで学習します。

ファミリー名は大文字と小文字が区別され、名前にスペースがある場合は引用符で囲む必要があります。 例えば、`"Open Sans"` フォントを使用するには引用符が必要ですが、`Lobster` フォントの場合は必要ではありません。

# --instructions--

あなたの Web ページに `Lobster` フォントをインポートしてください。 次に、要素セレクターを使用して `h2` 要素の `font-family` を`Lobster` に設定してください。

# --hints--

`Lobster` フォントをインポートする必要があります。

```js
assert($('link[href*="googleapis" i]').length);
```

`h2` 要素はフォント `Lobster` を使用する必要があります。

```js
assert(
  $('h2')
    .css('font-family')
    .match(/lobster/i)
);
```

フォントを変更するために `h2` 要素セレクターのみを使用してください。

```js
assert(
  /\s*[^\.]h2\s*\{\s*font-family\s*:\s*('|"|)Lobster\1\s*(,\s*('|"|)[a-z -]+\3\s*)?(;\s*\}|\})/gi.test(
    code
  )
);
```

`p` 要素は変わらず、フォント `monospace` を使用する必要があります。

```js
assert(
  $('p')
    .css('font-family')
    .match(/monospace/i)
);
```

# --seed--

## --seed-contents--

```html
<style>
  .red-text {
    color: red;
  }

  p {
    font-size: 16px;
    font-family: monospace;
  }
</style>

<h2 class="red-text">CatPhotoApp</h2>
<main>
  <p class="red-text">Click here to view more <a href="#">cat photos</a>.</p>

  <a href="#"><img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

  <div>
    <p>Things cats love:</p>
    <ul>
      <li>catnip</li>
      <li>laser pointers</li>
      <li>lasagna</li>
    </ul>
    <p>Top 3 things cats hate:</p>
    <ol>
      <li>flea treatment</li>
      <li>thunder</li>
      <li>other cats</li>
    </ol>
  </div>

  <form action="https://freecatphotoapp.com/submit-cat-photo">
    <label><input type="radio" name="indoor-outdoor" checked> Indoor</label>
    <label><input type="radio" name="indoor-outdoor"> Outdoor</label><br>
    <label><input type="checkbox" name="personality" checked> Loving</label>
    <label><input type="checkbox" name="personality"> Lazy</label>
    <label><input type="checkbox" name="personality"> Energetic</label><br>
    <input type="text" placeholder="cat photo URL" required>
    <button type="submit">Submit</button>
  </form>
</main>
```

# --solutions--

```html
<link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
<style>
  .red-text {
    color: red;
  }

  p {
    font-size: 16px;
    font-family: monospace;
  }

  h2 {
    font-family: Lobster;
  }
</style>

<h2 class="red-text">CatPhotoApp</h2>
<main>
  <p class="red-text">Click here to view more <a href="#">cat photos</a>.</p>

  <a href="#"><img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

  <div>
    <p>Things cats love:</p>
    <ul>
      <li>catnip</li>
      <li>laser pointers</li>
      <li>lasagna</li>
    </ul>
    <p>Top 3 things cats hate:</p>
    <ol>
      <li>flea treatment</li>
      <li>thunder</li>
      <li>other cats</li>
    </ol>
  </div>

  <form action="https://freecatphotoapp.com/submit-cat-photo">
    <label><input type="radio" name="indoor-outdoor" checked> Indoor</label>
    <label><input type="radio" name="indoor-outdoor"> Outdoor</label><br>
    <label><input type="checkbox" name="personality" checked> Loving</label>
    <label><input type="checkbox" name="personality"> Lazy</label>
    <label><input type="checkbox" name="personality"> Energetic</label><br>
    <input type="text" placeholder="cat photo URL" required>
    <button type="submit">Submit</button>
  </form>
</main>
```
