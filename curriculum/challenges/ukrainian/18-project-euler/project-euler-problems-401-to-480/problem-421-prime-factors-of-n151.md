---
id: 5900f5131000cf542c510024
title: 'Завдання 421: прості множники числа n^15+1'
challengeType: 1
forumTopicId: 302091
dashedName: problem-421-prime-factors-of-n151
---

# --description--

Числа вигляду $n^{15} + 1$ є складеними для будь-якого цілого значення $n > 1$.

Визначимо $s(n, m)$ для натуральних чисел $n$ та $m$ як суму різних простих множників числа $n^{15} + 1$, не перевищуючи $m$.

Наприклад: $2^{15} + 1 = 3 × 3 × 11 × 331$.

Отже, $s(2, 10) = 3$ та $s(2, 1000) = 3 + 11 + 331 = 345$.

Також ${10}^{15} + 1 = 7 × 11 × 13 × 211 × 241 × 2161 × 9091$.

Отже, $s(10, 100) = 31$ та $s(10, 1000) = 483$.

Знайдіть $\sum s(n, {10}^8)$ за умови $1 ≤ n ≤ {10}^{11}$.

# --hints--

`primeFactorsOfN15Plus1()` має повернути `2304215802083466200`.

```js
assert.strictEqual(primeFactorsOfN15Plus1(), 2304215802083466200);
```

# --seed--

## --seed-contents--

```js
function primeFactorsOfN15Plus1() {

  return true;
}

primeFactorsOfN15Plus1();
```

# --solutions--

```js
// solution required
```
