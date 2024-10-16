---
id: 587d7dbd367417b2b2512bb5
title: أدخال CSS مع Sass
challengeType: 0
forumTopicId: 301457
dashedName: nest-css-with-sass
---

# --description--

Sass allows nesting of CSS rules, which is a useful way of organizing a style sheet.

وعادة ما يكون كل عنصر مستهدفاً على خط مختلف لتصميمه، مثل:

```scss
article {
  height: 200px;
}

article p {
  color: white;
}

article ul {
  color: blue;
}
```

بالنسبة لمشروع كبير، سيكون مِلَفّ CSS يحتوي على العديد من الأسطر والقواعد. هنا حيث يمكن للتداخل أن يساعد في تنظيم التعليمات البرمجية الخاصة بك عن طريق وضع قواعد تصميم فرعي ضمن العناصر الرئيسية لكل منهما:

```scss
article {
  height: 200px;

  p {
    color: white;
  }

  ul {
    color: blue;
  }
}

```

# --instructions--

استخدم تقنية التعزيز المبينة أعلاه لإعادة تنظيم قواعد CSS لكلا الفرعين من عنصر `.blog-post`. لأغراض الاختبار، يجب أن يأتي `h1` قبل عنصر `p`.

# --hints--

يجب أن تعيد تعليماتك البرمجية تنظيم قواعد CSS بحيث يتم تداخل `h1` و `p` في عنصر الأساسي `.blog-post`.

```js
assert(
  code.match(
    /\.blog-post\s*?{\s*?h1\s*?{\s*?text-align:\s*?center;\s*?color:\s*?blue;\s*?}\s*?p\s*?{\s*?font-size:\s*?20px;\s*?}\s*?}/gi
  )
);
```

# --seed--

## --seed-contents--

```html
<style type='text/scss'>
  .blog-post {

  }
  h1 {
    text-align: center;
    color: blue;
  }
  p {
    font-size: 20px;
  }
</style>

<div class="blog-post">
  <h1>Blog Title</h1>
  <p>This is a paragraph</p>
</div>
```

# --solutions--

```html
<style type='text/scss'>
  .blog-post {
    h1 {
      text-align: center;
      color: blue;
    }
    p {
      font-size: 20px;
    }
  }
</style>

<div class="blog-post">
  <h1>Blog Title</h1>
  <p>This is a paragraph</p>
</div>
```
