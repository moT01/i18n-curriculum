---
id: 587d7fa7367417b2b2512bc7
title: データに基づいてスタイルを変更する
challengeType: 6
forumTopicId: 301479
dashedName: change-styles-based-on-data
---

# --description--

D3 is about visualization and presentation of data. It's likely you'll want to change the styling of elements based on the data. For example, you may want to color a data point blue if it has a value less than 20, and red otherwise. You can use a callback function in the `style()` method and include the conditional logic. The callback function uses the `d` parameter to represent the data point:

```js
selection.style("color", (d) => {

});
```

`style()` メソッドは `color` の設定に限定されるものではありません 。他の CSS プロパティでも使用できます。

# --instructions--

`style()` メソッドをエディタ内のコードに追加して、`h2` 要素の `color` を条件付きで設定してください。 データ値が 20 未満の場合は赤を返し、そうでない場合は緑を返すようなコールバック関数を記述してください。

**注:** if-else ロジックまたは三項演算子を使用できます。

# --hints--

最初の `h2` の `color` を赤にする必要があります。

```js
assert($('h2').eq(0).css('color') == 'rgb(255, 0, 0)');
```

2 番目の `h2` の `color` を緑にする必要があります。

```js
assert($('h2').eq(1).css('color') == 'rgb(0, 128, 0)');
```

3 番目の `h2` の `color` を緑にする必要があります。

```js
assert($('h2').eq(2).css('color') == 'rgb(0, 128, 0)');
```

4 番目の `h2` の `color` を赤にする必要があります。

```js
assert($('h2').eq(3).css('color') == 'rgb(255, 0, 0)');
```

5 番目の `h2` の `color` を緑にする必要があります。

```js
assert($('h2').eq(4).css('color') == 'rgb(0, 128, 0)');
```

6 番目の `h2` の `color` を赤にする必要があります。

```js
assert($('h2').eq(5).css('color') == 'rgb(255, 0, 0)');
```

7 番目の `h2` の `color` を緑にする必要があります。

```js
assert($('h2').eq(6).css('color') == 'rgb(0, 128, 0)');
```

8 番目の `h2` の `color` を赤にする必要があります。

```js
assert($('h2').eq(7).css('color') == 'rgb(255, 0, 0)');
```

9 番目の `h2` の `color` を赤にする必要があります。

```js
assert($('h2').eq(8).css('color') == 'rgb(255, 0, 0)');
```

# --seed--

## --seed-contents--

```html
<body>
  <script>
    const dataset = [12, 31, 22, 17, 25, 18, 29, 14, 9];

    d3.select("body").selectAll("h2")
      .data(dataset)
      .enter()
      .append("h2")
      .text((d) => (d + " USD"))
      // Add your code below this line



      // Add your code above this line
  </script>
</body>
```

# --solutions--

```html
<body>
  <script>
    const dataset = [12, 31, 22, 17, 25, 18, 29, 14, 9];

    d3.select("body").selectAll("h2")
      .data(dataset)
      .enter()
      .append("h2")
      .text((d) => (d + " USD"))
      .style("color", (d) => d < 20 ? "red" : "green")
  </script>
</body>
```
