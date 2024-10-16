---
id: 587d825a367417b2b2512c8a
title: 要素を最大ヒープに挿入する
challengeType: 1
forumTopicId: 301703
dashedName: insert-an-element-into-a-max-heap
---

# --description--

Now we will move on to another tree data structure, the binary heap. A binary heap is a partially ordered binary tree which satisfies the heap property. The heap property specifies a relationship between parent and child nodes. You may have a max heap, in which all parent nodes are greater than or equal to their child nodes, or a min heap, in which the reverse is true. Binary heaps are also complete binary trees. This means that all levels of the tree are fully filled and if the last level is partially filled it is filled from left to right.

二分ヒープは、左右の参照を含むノードを持つツリー構造として実装できますが、ヒーププロパティに従って部分的に順序付けすれば、配列を使ってヒープを表現することができます。 ここでは親子関係に注目します。あらゆる親ノードの子と、あらゆる子ノードの親を、簡単な算術で計算することができます。

例えば、二分最小ヒープを次のような配列で表現することを考えてみましょう。

```js
[ 6, 22, 30, 37, 63, 48, 42, 76 ]
```

根ノードは最初の要素、`6` です。 根ノードの子は `22` と `30` です。 これらの値の配列インデックス間の関係を見てみると、`i` の子要素は `2 * i + 1` および `2 * i + 2` です。 同様に、インデックス `0` にある要素は、インデックス `1` と `2` にある 2 つの子の親です。 より一般的には、`Math.floor(i - 1) / 2)` を使用すれば、任意のインデックスにあるノードの親を見つけることができます。 二分木がどれほど大きくなってもこれらのパターンが当てはまります。 最後に、配列内の最初の要素をスキップするというわずかな調整で、この演算をさらに簡単にできます。 これを行うと、与えられたインデックス `i` にある任意の要素に対して次のような関係が作られます。

配列表現の例:

```js
[ null, 6, 22, 30, 37, 63, 48, 42, 76 ]
```

要素の左の子: `i * 2`

要素の右の子: `i * 2 + 1`

要素の親: `Math.floor(i / 2)`

この計算を理解してしまえば、配列表現を使うことは非常に便利です。なぜなら、子ノードへの参照を維持する必要がないので、この演算でノード位置が素早く決まり、メモリ使用量が減少するからです。

# --instructions--

手順: ここでは最大ヒープを作成してください。 まず、ヒープに要素を追加する `insert` メソッドを作成します。 挿入中は、ヒーププロパティを常に維持することが重要です。 つまり最大ヒープの場合、根要素は常に木の中で最大値を持ち、すべての親ノードは子ノードより大きくなければなりません。 ヒープの配列実装では、通常、これは次の 3 つのステップで実行されます。

<ol>
  <li>Add the new element to the end of the array.</li>
  <li>要素が親より大きい場合は、それらを交換します。</li>
  <li>新しい要素が親より小さくなるまで、または木の根に到達するまで、交換を続けます。</li>
</ol>

最後に、ヒープに追加されたすべての要素の配列を返す `print` メソッドを追加します。

# --hints--

`MaxHeap` データ構造を用意する必要があります。

```js
assert(
  (function () {
    var test = false;
    if (typeof MaxHeap !== 'undefined') {
      test = new MaxHeap();
    }
    return typeof test == 'object';
  })()
);
```

`MaxHeap` には `insert` というメソッドが必要です。

```js
assert(
  (function () {
    var test = false;
    if (typeof MaxHeap !== 'undefined') {
      test = new MaxHeap();
    } else {
      return false;
    }
    return typeof test.insert == 'function';
  })()
);
```

`MaxHeap` には `print` というメソッドが必要です。

```js
assert(
  (function () {
    var test = false;
    if (typeof MaxHeap !== 'undefined') {
      test = new MaxHeap();
    } else {
      return false;
    }
    return typeof test.print == 'function';
  })()
);
```

`insert` メソッドは最大ヒーププロパティに従って要素を追加する必要があります。

```js
assert(
  (function () {
    var test = false;
    if (typeof MaxHeap !== 'undefined') {
      test = new MaxHeap();
    } else {
      return false;
    }
    test.insert(50);
    test.insert(100);
    test.insert(700);
    test.insert(32);
    test.insert(51);
    test.insert(800);
    const result = test.print();
    const solution = JSON.stringify([null,800,51,700,32,50,100]);
    const solutionWithoutNull = JSON.stringify([800,51,700,32,50,100]);

    return (result.length == 6) ? (JSON.stringify(result) == solutionWithoutNull) : (JSON.stringify(result) == solution);
  })()
);
```

# --seed--

## --seed-contents--

```js
var MaxHeap = function() {
  // Only change code below this line

  // Only change code above this line
};
```

# --solutions--

```js
var MaxHeap = function() {
    // Only change code below this line
    this.heap = [];
    this.parent = index => {
      return Math.floor((index - 1) / 2);
    }
    this.insert = element => {
      this.heap.push(element);
      this.heapifyUp(this.heap.length - 1);
    }
    this.heapifyUp = index => {
      let currentIndex = index,
      parentIndex = this.parent(currentIndex);
      while (currentIndex > 0 && this.heap[currentIndex] > this.heap[parentIndex]) {
        this.swap(currentIndex, parentIndex);
        currentIndex = parentIndex;
        parentIndex = this.parent(parentIndex);
      }
    }
    this.swap = (index1, index2) => {
      [this.heap[index1], this.heap[index2]] = [this.heap[index2], this.heap[index1]];
    }
    this.print = () => {
      return this.heap;
    }
    // Only change code above this line
};
```
