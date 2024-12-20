---
id: 587d7dab367417b2b2512b6d
title: 應用函數式編程將字符串轉換爲URL片段
challengeType: 1
forumTopicId: 301227
dashedName: apply-functional-programming-to-convert-strings-to-url-slugs
---

# --description--

The last several challenges covered a number of useful array and string methods that follow functional programming principles. We've also learned about `reduce`, which is a powerful method used to reduce problems to simpler forms. From computing averages to sorting, any array operation can be achieved by applying it. Recall that `map` and `filter` are special cases of `reduce`.

讓我們把學到的知識結合起來解決一個實際問題。

許多內容管理站點（CMS）爲了讓添加書籤更簡單，會將帖子的標題添加到 URL 上。 舉個例子，如果你寫了一篇標題爲 `Stop Using Reduce` 的帖子，URL很可能會包含標題字符串的某種形式 (如：`.../stop-using-reduce`)。 你可能已經在 freeCodeCamp 網站上注意到了這一點。

# --instructions--

填寫 `urlSlug` 函數，將字符串 `title` 轉換成帶有連字符號的 URL。 您可以使用本節中介紹的任何方法，但不要用 `replace` 方法。 以下是本次挑戰的要求：

輸入包含空格和標題大小寫單詞的字符串

輸出字符串，單詞之間的空格用連字符 (`-`) 替換

輸出應該是小寫字母

輸出不應有任何空格

# --hints--

不能使用 `replace` 方法。

```js
assert(!__helpers.removeJSComments(code).match(/\.?[\s\S]*?replace/g));
```

`urlSlug("Winter Is Coming")` 應返回 `winter-is-coming`。

```js
assert(urlSlug('Winter Is Coming') === 'winter-is-coming');
```

`urlSlug(" Winter Is  Coming")` 應返回 `winter-is-coming`。

```js
assert(urlSlug(' Winter Is  Coming') === 'winter-is-coming');
```

`urlSlug("A Mind Needs Books Like A Sword Needs A Whetstone")` 應返回 `a-mind-needs-books-like-a-sword-needs-a-whetstone`。

```js
assert(
  urlSlug('A Mind Needs Books Like A Sword Needs A Whetstone') ===
    'a-mind-needs-books-like-a-sword-needs-a-whetstone'
);
```

`urlSlug("Hold The Door")` 應返回 `hold-the-door`。

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
