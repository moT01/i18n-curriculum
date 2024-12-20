---
id: 587d7dbb367417b2b2512bac
title: Rimuovere gli spazi iniziali e finali
challengeType: 1
forumTopicId: 301362
dashedName: remove-whitespace-from-start-and-end
---

# --description--

Sometimes whitespace characters around strings are not wanted but are there. Typical processing of strings is to remove the whitespace at the start and end of it.

# --instructions--

Scrivi un'espressione regolare e usa i metodi stringa appropriati per rimuovere gli spazi bianchi all'inizio e alla fine delle stringhe.

**Nota:** Il metodo `String.prototype.trim()` funzionerebbe, ma dovrai completare questa sfida usando le espressioni regolari.

# --hints--

`result` dovrebbe essere uguale alla stringa `Hello, World!`

```js
assert(result === 'Hello, World!');
```

La tua soluzione non dovrebbe usare il metodo `String.prototype.trim()`.

```js
assert(!__helpers.removeJSComments(code).match(/\.?[\s\S]*?trim/));
```

La variabile `result` non dovrebbe essere impostata direttamente con una stringa

```js
assert(!__helpers.removeJSComments(code).match(/result\s*=\s*["'`].*?["'`]/));
```

Il valore della variabile `hello` non dovrebbe cambiare.

```js
assert(hello === '   Hello, World!  ');
```

# --seed--

## --seed-contents--

```js
let hello = "   Hello, World!  ";
let wsRegex = /change/; // Change this line
let result = hello; // Change this line
```

# --solutions--

```js
let hello = "   Hello, World!  ";
let wsRegex = /^(\s+)(.+[^\s])(\s+)$/;
let result = hello.replace(wsRegex, '$2');
```
