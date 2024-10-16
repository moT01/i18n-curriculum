---
id: bad87fee1348bd9aec908846
title: إنشاء Headline بأسلوب Bootstrap
challengeType: 0
forumTopicId: 16812
dashedName: create-a-bootstrap-headline
---

# --description--

Now let's build something from scratch to practice our HTML, CSS and Bootstrap skills.

سوف تبني ملعب jQuery، الذي سوف نستخدمه قريبا في تحديات jQuery الخاصة بنا.

لبدء ذلك، أنشئ عنصر `h3` بنص `jQuery Playground`.

لون عنصر `h3` الخاص بك مع `text-primary`، وضعه في المنتصف مع فئة `text-center` بأسلوب Bootstrap.

# --hints--

يجب عليك إضافة عنصر `h3` إلى الصفحة الخاصة بك.

```js
assert.lengthOf(document.querySelectorAll('h3'),1);
```

يجب أن يحتوي العنصر `h3` على وسم إغلاق.

```js
assert.match(code,/<\/h3>/g);
assert.match(code,/<h3/g);
assert.equal( code.match(/<\/h3>/g).length , code.match(/<h3/g).length);
```

عنصر `h3` الخاص بك يجب أن يتمركز بتطبيق فئة `text-primary`

```js
assert.isTrue(document.querySelector('h3')?.classList?.contains('text-primary'));
```

عنصر `h3` الخاص بك يجب أن يتمركز بتطبيق فئة `text-center`

```js
assert.isTrue(document.querySelector('h3')?.classList?.contains('text-center'));
```

يجب أن يحتوي العنصر `h3` على النص `jQuery Playground`.

```js
assert.match(document.querySelector('h3')?.textContent, /jquery(\s)+playground/gi);
```

# --seed--

## --seed-contents--

```html

```

# --solutions--

```html
<h3 class="text-primary text-center">jQuery Playground</h3>
```
