---
id: 5900f3ae1000cf542c50fec1
title: 'Problema 66: Ecuación diofántica'
challengeType: 1
forumTopicId: 302178
dashedName: problem-66-diophantine-equation
---

# --description--

Considere las ecuaciones cuadráticas diofánticas del formulario:

<div style='text-align: center;'>x<sup>2</sup> – Dy<sup>2</sup> = 1</div>

Por ejemplo, cuando D=13, la solución mínima en x es 649<sup>2</sup> – 13×180<sup>2</sup> = 1.

Se puede asumir que no hay soluciones en enteros positivos cuando D es un cuadrado.

Al encontrar soluciones mínimas en x para D = {2, 3, 5, 6, 7}, obtenemos lo siguiente:

<div style='margin-left: 2em;'>
  3<sup>2</sup> – 2×2<sup>2</sup> = 1<br>
  2<sup>2</sup> – 3×1<sup>2</sup> = 1<br>
  <strong><span style='color: red;'>9</span></strong><sup>2</sup> – 5×4<sup>2</sup> = 1<br>
  5<sup>2</sup> – 6×2<sup>2</sup> = 1<br>
  8<sup>2</sup> – 7×3<sup>2</sup> = 1<br>
</div>

Por lo tanto, al considerar soluciones mínimas en `x` para D ≤ 7, el mayor `x` se obtiene cuando D=5.

Encuentra el valor de D ≤ `n` en las soluciones mínimas de `x` para las cuales se obtiene el mayor valor de `x`.

# --hints--

`diophantineEquation(7)` debe devolver un número.

```js
assert(typeof diophantineEquation(7) === 'number');
```

`diophantineEquation(7)` debe devolver `5`.

```js
assert.strictEqual(diophantineEquation(7), 5);
```

`diophantineEquation(100)` debe devolver `61`.

```js
assert.strictEqual(diophantineEquation(100), 61);
```

`diophantineEquation(409)` debe devolver `409`.

```js
assert.strictEqual(diophantineEquation(409), 409);
```

`diophantineEquation(500)` debe devolver `421`.

```js
assert.strictEqual(diophantineEquation(500), 421);
```

`diophantineEquation(1000)` debe devolver `661`.

```js
assert.strictEqual(diophantineEquation(1000), 661);
```

# --seed--

## --seed-contents--

```js
function diophantineEquation(n) {

  return true;
}

diophantineEquation(7);
```

# --solutions--

```js
function diophantineEquation(n) {
  // Based on https://www.mathblog.dk/project-euler-66-diophantine-equation/
  function isSolution(D, numerator, denominator) {
    return numerator * numerator - BigInt(D) * denominator * denominator === 1n;
  }

  let result = 0;
  let biggestX = 0;

  for (let D = 2; D <= n; D++) {
    let boundary = Math.floor(Math.sqrt(D));
    if (boundary ** 2 === D) {
      continue;
    }

    let m = 0n;
    let d = 1n;
    let a = BigInt(boundary);

    let [numerator, prevNumerator] = [a, 1n];

    let [denominator, prevDenominator] = [1n, 0n];

    while (!isSolution(D, numerator, denominator)) {
      m = d * a - m;
      d = (BigInt(D) - m * m) / d;
      a = (BigInt(boundary) + m) / d;

      [numerator, prevNumerator] = [a * numerator + prevNumerator, numerator];
      [denominator, prevDenominator] = [
        a * denominator + prevDenominator,
        denominator
      ];
    }

    if (numerator > biggestX) {
      biggestX = numerator;
      result = D;
    }
  }
  return result;
}
```
