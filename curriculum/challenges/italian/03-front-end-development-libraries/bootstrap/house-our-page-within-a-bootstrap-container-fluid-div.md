---
id: bad87fee1348bd9aec908746
title: Accomodare la pagina all'interno di un div container-fluid di Bootstrap
challengeType: 0
forumTopicId: 18198
dashedName: house-our-page-within-a-bootstrap-container-fluid-div
---

# --description--

Now let's make sure all the content on your page is mobile-responsive.

Nidifichiamo l'elemento `h3` all'interno di un elemento `div` di classe `container-fluid`.

# --hints--

Il tuo elemento `div` dovrebbe avere la classe `container-fluid`.

```js
assert.isTrue(document.querySelector('div')?.classList?.contains('container-fluid'));
```

Ognuno dei tuoi elementi `div` dovrebbe avere un tag di chiusura.

```js
assert.match(code,/<\/div>/g);
assert.match(code,/<div/g);

assert.equal(code.match(/<\/div>/g).length ,code.match(/<div/g).length);
```

Il tuo elemento `h3` dovrebbe essere annidato all'interno di un elemento `div`.

```js
const divElement = document.querySelector('div');
const divChildren = divElement?.querySelectorAll(`:scope ${'h3'}`)
assert.lengthOf(divChildren,1);
```

# --seed--

## --seed-contents--

```html
<h3 class="text-primary text-center">jQuery Playground</h3>
```

# --solutions--

```html
<div class="container-fluid">
    <h3 class="text-primary text-center">jQuery Playground</h3>
</div>
```
