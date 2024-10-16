---
id: bad87fee1348bd9aedf08820
title: تحويل صورة إلى رابط
challengeType: 0
videoUrl: 'https://scrimba.com/p/pVMPUv/cRdBnUr'
forumTopicId: 18327
dashedName: turn-an-image-into-a-link
---

# --description--

You can make elements into links by nesting them within an `a` element.

ضع صورتك داخل عنصر `a`. وهذا مثال على ذلك:

```html
<a href="#"><img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="Three kittens running towards the camera."></a>
```

تذكر استخدام `#` كقيمة لخاصية `href` للعنصر `a` لتحويله الى رابط غير فعال.

# --instructions--

ضع عنصر الصورة داخل عنصر `a` (*anchor*) الحالي.

بمجرد أن تقوم بذلك، قم بالمرور على الصورة بالمؤشر. مؤشرك العادي يجب أن يصبح مؤشر النقر على رابط. الصورة الآن تحتوي رابط.

# --hints--

يجب أن يوضع عنصر <`img` داخل عنصر `a`.

```js
assert($('a').children('img').length > 0);
```

Your `a` element should be a dead link with an `href` attribute set to `#`.

```js
assert(new RegExp('#').test($('a').children('img').parent().attr('href')));
```

كل عنصر من عناصر ال `a` يجب أن يحتوي على علامة الإغلاق (closing tag).

```js
assert(
  code.match(/<\/a>/g) &&
    code.match(/<a/g) &&
    code.match(/<\/a>/g).length === code.match(/<a/g).length
);
```

# --seed--

## --seed-contents--

```html
<h2>CatPhotoApp</h2>
<main>
  <p>Click here to view more <a href="#">cat photos</a>.</p>

  <img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back.">

  <p>Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
  <p>Purr jump eat the grass rip the couch scratched sunbathe, shed everywhere rip the couch sleep in the sink fluffy fur catnip scratched.</p>
</main>
```

# --solutions--

```html
<h2>CatPhotoApp</h2>
<main>
  <p>Click here to view more <a href="#">cat photos</a>.</p>

  <a href="#"><img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

  <p>Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
  <p>Purr jump eat the grass rip the couch scratched sunbathe, shed everywhere rip the couch sleep in the sink fluffy fur catnip scratched.</p>
</main>
```
