---
id: 587d7b8c367417b2b2512b55
title: Reutilizar código JavaScript usando import
challengeType: 1
forumTopicId: 301208
dashedName: reuse-javascript-code-using-import
---

# --description--

`import` allows you to choose which parts of a file or module to load. In the previous lesson, the examples exported `add` from the `math_functions.js` file. Here's how you can import it to use in another file:

```js
import { add } from './math_functions.js';
```

Aqui, `import` encontrará a função `add` no arquivo `math_functions.js`, importar apenas essa função e ignorar o resto. O `./` diz ao import para procurar pelo arquivo `math_functions.js` no mesmo diretório que o arquivo atual. O caminho relativo do arquivo (`./`) e a extensão do arquivo (`.js`) são necessários ao usar import dessa forma.

Você pode importar mais de um item do arquivo ao adicioná-los na instrução `import` dessa forma:

```js
import { add, subtract } from './math_functions.js';
```

# --instructions--

Adicione a instrução `import` apropriada que permitirá o arquivo atual usar as funções `uppercaseString` e `lowercaseString` que você exportou na lição anterior. As funções estão em um arquivo chamado `string_functions.js`, o qual está no mesmo diretório que o arquivo atual.

# --hints--

Você deve importar a função `uppercaseString`.

```js
assert(
  __helpers.removeJSComments(code).match(
    /import\s*{\s*(uppercaseString[^}]*|[^,]*,\s*uppercaseString\s*)}\s+from\s+('|")\.\/string_functions\.js\2/g
  )
);
```

Você deve importar a função `lowercaseString`.

```js
assert(
  __helpers.removeJSComments(code).match(
    /import\s*{\s*(lowercaseString[^}]*|[^,]*,\s*lowercaseString\s*)}\s+from\s+('|")\.\/string_functions\.js\2/g
  )
);
```

# --seed--

## --seed-contents--

```js

// Only change code above this line

uppercaseString("hello");
lowercaseString("WORLD!");
```

# --solutions--

```js
import { uppercaseString, lowercaseString } from './string_functions.js';

uppercaseString("hello");
lowercaseString("WORLD!");
```
