---
id: 5900f39e1000cf542c50feb1
title: 'Problema 50: Suma de primos consecutivos'
challengeType: 1
forumTopicId: 302161
dashedName: problem-50-consecutive-prime-sum
---

# --description--

The prime 41, can be written as the sum of six consecutive primes:

<div style='text-align: center;'>41 = 2 + 3 + 5 + 7 + 11 + 13</div>

Esta es la suma más larga de primos consecutivos que suma un primo por debajo de cien.

La suma más larga de primos consecutivos debajo de una centena que suma a un primo, contiene 21 terminos, y es igual a 953.

Cuál primo, por debajo de un millón, puede escribirse como la suma de más primos consecutivos?

# --hints--

`consecutivePrimeSum(1000)` debería devolver un número.

```js
assert(typeof consecutivePrimeSum(1000) === 'number');
```

`consecutivePrimeSum(1000)` debería devolver 953.

```js
assert.strictEqual(consecutivePrimeSum(1000), 953);
```

`consecutivePrimeSum(1000000)` debería devolver 997651.

```js
assert.strictEqual(consecutivePrimeSum(1000000), 997651);
```

# --seed--

## --seed-contents--

```js
function consecutivePrimeSum(limit) {

  return true;
}

consecutivePrimeSum(1000000);
```

# --solutions--

```js
class PrimeSeive {
  constructor(num) {
    const seive = Array(Math.floor((num - 1) / 2)).fill(true);
    const primes = [2];
    const upper = Math.floor((num - 1) / 2);
    const sqrtUpper = Math.floor((Math.sqrt(num) - 1) / 2);

    for (let i = 0; i <= sqrtUpper; i++) {
      if (seive[i]) {
        // Mark value in seive array
        const prime = 2 * i + 3;
        primes.push(prime);
        // Mark all multiples of this number as false (not prime)
        const primeSquaredIndex = 2 * i ** 2 + 6 * i + 3;
        for (let j = primeSquaredIndex; j < upper; j += prime) {
          seive[j] = false;
        }
      }
    }
    for (let i = sqrtUpper + 1; i < upper; i++) {
      if (seive[i]) {
        primes.push(2 * i + 3);
      }
    }

    this._seive = seive;
    this._primes = primes;
  }

  isPrime(num) {
    return num === 2
      ? true
      : num % 2 === 0
        ? false
        : this.isOddPrime(num);
  }

  isOddPrime(num) {
    return this._seive[(num - 3) / 2];
  }

  get primes() {
    return this._primes;
  }
};

function consecutivePrimeSum(limit) {
  // Initialize seive
  const primeSeive = new PrimeSeive(limit);

  // Initialize for longest sum < 100
  let bestPrime = 41;
  let bestI = 0;
  let bestJ = 5;

  // Find longest sum < limit
  let sumOfCurrRange = 41;
  let i = 0, j = 5;
  // -- Loop while current some starting at i is < limit
  while (sumOfCurrRange < limit) {
    let currSum = sumOfCurrRange;
    // -- Loop while pushing j towards end of PRIMES list
    //      keeping sum under limit
    while (currSum < limit) {
      if (primeSeive.isPrime(currSum)) {
        bestPrime = sumOfCurrRange = currSum;
        bestI = i;
        bestJ = j;
      }
      // -- Increment inner loop
      j++;
      currSum += primeSeive.primes[j];
    }
    // -- Increment outer loop
    i++;
    j = i + (bestJ - bestI);
    sumOfCurrRange -= primeSeive.primes[i - 1];
    sumOfCurrRange += primeSeive.primes[j];
  }
  // Return
  return bestPrime;
}
```
