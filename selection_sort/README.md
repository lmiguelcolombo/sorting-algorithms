# Selection Sort

## 📝 Explanation

Selection sort is a sorting algorithm which find the **smallest element** in the array and swaps this element with the one in the first place. Organically, the process is:

1. Find the **smallest element** in the array;
2. Swap it with the first element;
3. Find the second smallest element in the array;
4. Swap it with the second element;
5. Repeat this process (finding the next smallest element and swaping it into the correct position) until the array is sorted.

<!-- ### Number of key comparisons

Always `N(N − 1)/2`. -->

## 🤔 Do you think it's so simple?

You're right! Let's look at a **visual animation** 👇🏼

![](https://upload.wikimedia.org/wikipedia/commons/9/94/Selection-Sort-Animation.gif)

In this GIF:

1. The number with red background is the smallest found in the iteration;
2. The blue represents each iteration/comparison;
3. The yellow is the [already] sorted part.

## 💻 Code example (JavaScript)

```js
function selectionSort(arr) {
  for (let i = 0; i < arr.length - 1; i++) {
    let min = i;
    for (let el = i + 1; el < arr.length; el++) {
      if (arr[el] < arr[min]) {
        min = el;
      }
    }
    if (min !== i) {
      swap(arr, i, min);
    }
  }
  return arr;
}

function swap(arr, x, y) {
  const temporary = arr[x]; // store in memory
  arr[x] = arr[y];
  arr[y] = temporary;
}

const arr = [12, 11, 13, 5, 6];
console.log('Unsorted array:', arr);
const sortedArr = selectionSort(arr);
console.log('Sorted array:', sortedArr);
```

## 🌐 Use cases

The best case is

- when the amount of data isn't too large. So if you have **small datasets**, this algorithm will be a good fit;
- when your memory is limited, for example on a **memory-constrained environments**;
- when the data is **nearly sorted**
