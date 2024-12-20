---
id: 587d825b367417b2b2512c8c
title: 用最小堆實現堆排序
challengeType: 1
forumTopicId: 301643
dashedName: implement-heap-sort-with-a-min-heap
---

# --description--

Now that we can add and remove elements let's see some of the applications heaps can be used for. Heaps are commonly used to implement priority queues because they always store an item of greatest or least value in first position. In addition, they are used to implement a sorting algorithm called heap sort. We'll see how to do this here. Heap sort uses a min heap, the reverse of a max heap. A min heap always stores the element of least value in the root position.

堆排序通過獲取未排序的數組，將數組中的每個項目添加到最小堆中，然後將最小堆中的每個項目提取到新數組中。 最小堆結構確保新數組將以最小到最大的順序包含原始項目。 這是最有效的排序算法之一，平均和最壞情況下的性能爲 O(nlog(n))。

# --instructions--

讓我們用最小堆實現堆排序。 您可以在此處調整最大堆代碼。 使用 `insert`、`remove` 和 `sort` 方法創建一個對象 `MinHeap`。 `sort` 方法應該返回最小堆中從最小到最大排序的所有元素的數組。

# --hints--

`MinHeap` 數據結構應該存在。

```js
assert(
  (function () {
    var test = false;
    if (typeof MinHeap !== 'undefined') {
      test = new MinHeap();
    }
    return typeof test == 'object';
  })()
);
```

`MinHeap` 應該有一個名爲 `insert` 的方法。

```js
assert(
  (function () {
    var test = false;
    if (typeof MinHeap !== 'undefined') {
      test = new MinHeap();
    } else {
      return false;
    }
    return typeof test.insert == 'function';
  })()
);
```

`MinHeap` 應該有一個名爲 `remove` 的方法。

```js
assert(
  (function () {
    var test = false;
    if (typeof MinHeap !== 'undefined') {
      test = new MinHeap();
    } else {
      return false;
    }
    return typeof test.remove == 'function';
  })()
);
```

MinHeap中應當包含一個叫做 sort的方法。

```js
assert(
  (function () {
    var test = false;
    if (typeof MinHeap !== 'undefined') {
      test = new MinHeap();
    } else {
      return false;
    }
    return typeof test.sort == 'function';
  })()
);
```

Sort方法應該返回一個數組，其中包含按排序順序添加到 min 堆中的所有項。

```js
assert(
  (() => {
    if (typeof MinHeap === 'undefined') {
      return false;
    }

    const heap = new MinHeap();
    const arr = createRandomArray(25);

    for (let i of arr) {
      heap.insert(i);
    }

    const result = heap.sort();
    arr.sort((a, b) => a - b);

    for (let i = 0; i < arr.length; i++) {
      if (arr[i] !== result[i]) {
        return false;
      }
    }
    return true;
  })()
);
```

# --seed--

## --seed-contents--

```js
function isSorted(a){
  for(let i = 0; i < a.length - 1; i++)
    if(a[i] > a[i + 1])
      return false;
  return true;
}
// Generate a randomly filled array
function createRandomArray(size = 5){
  let a = new Array(size);
  for(let i = 0; i < size; i++)
    a[i] = Math.floor(Math.random() * 100);

  return a;
}
const array = createRandomArray(25);

var MinHeap = function() {
  // Only change code below this line

  // Only change code above this line
};
```

# --solutions--

```js
// solution required
```
