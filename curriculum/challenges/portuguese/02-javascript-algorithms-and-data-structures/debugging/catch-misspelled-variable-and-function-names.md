---
id: 587d7b84367417b2b2512b35
title: Capturar nomes de variáveis e funções com erros ortográficos
challengeType: 1
forumTopicId: 301186
dashedName: catch-misspelled-variable-and-function-names
---

# --description--

The `console.log()` and `typeof` methods are the two primary ways to check intermediate values and types of program output. Now it's time to get into the common forms that bugs take. One syntax-level issue that fast typers can commiserate with is the humble spelling error.

Caracteres deslocados, faltando ou capitalizados erroneamente em um nome de variável ou função farão com que o navegador procure por um objeto que não existe - e reclame na forma de um erro de referência. Variáveis e funções JavaScript são sensíveis a caracteres maiúsculos e minúsculos.

# --instructions--

Corrija os dois erros de ortografia no código para que o cálculo `netWorkingCapital` funcione.

# --hints--

Verifique a ortografia das duas variáveis usadas no cálculo de netWorkingCapital, a saída do console deve mostrar que "Net working capital is: 2".

```js
assert(netWorkingCapital === 2);
```

Não deve haver instâncias de variáveis com ortografia incorreta no código.

```js
assert(!__helpers.removeJSComments(code).match(/recievables/g));
```

A variável `receivables` deve ser declarada e usada corretamente no código.

```js
assert(__helpers.removeJSComments(code).match(/receivables/g).length == 2);
```

Não deve haver instâncias de variáveis com ortografia incorreta no código.

```js
assert(!__helpers.removeJSComments(code).match(/payable;/g));
```

A variável `payables` deve ser declarada e usada corretamente no código.

```js
assert(__helpers.removeJSComments(code).match(/payables/g).length == 2);
```

# --seed--

## --seed-contents--

```js
let receivables = 10;
let payables = 8;
let netWorkingCapital = recievables - payable;
console.log(`Net working capital is: ${netWorkingCapital}`);
```

# --solutions--

```js
let receivables = 10;
let payables = 8;
let netWorkingCapital = receivables - payables;
console.log(`Net working capital is: ${netWorkingCapital}`);
```
