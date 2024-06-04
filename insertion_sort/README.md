# Insertion Sort

## 📝 Explanation

Insertion sort is a type of _algorithm_ you can use to sort a given amount of elements, e.g.: an array of numbers.
This algorithm works in the following way:

1. Take the second element of the array (index = 1) and put it aside; this is the **key** of the process, the element that'll be compared.
2. Then the comparison starts, so it'll compare with the **previous** element (index = 0). If the previous is greater than the key, the key is _inserted_ into the right place (where the previous were).
3. After that, all the process restarts, but taking another key and comparing to _all the previous_ elements.
4. This process is repeated until the end of the array is reached.

## 🤔 A bit complicated?

Okay, let's look at a **visual animation** 👇🏼

![](https://upload.wikimedia.org/wikipedia/commons/9/9c/Insertion-sort-example.gif)

In this GIF:

- the **red square** means the **key**;
- the **black squares** mean the **previous** elements;

## 💻 Code example (JavaScript)

```js
function insertionSort(arr) {
  for (let i = 1; i < arr.length; i++) {
    let key = arr[i]; // value in position (i) of the array (arr)
    let previous = i - 1; // int
    while (previous >= 0 && arr[previous] > key) {
      arr[previous + 1] = arr[previous];
      previous = previous - 1;
    }
    arr[previous + 1] = key; // insert the key (the element being compared) in the correct place
    console.log('iteration: ' + i + ' | key: ' + key); // this code gives the number of the iteration and the key being used in this iteration
    console.log(arr);
  }
  return arr;
}

const arr = [12, 11, 13, 5, 6];
console.log('Unsorted array:', arr);
const sortedArr = insertionSort(arr);
console.log('Sorted array:', sortedArr);
```

## 🌐 Use cases

The _insertion sort_ algorithm becomes one of the **better** choices when the array is **nearly sorted**. And it's **not a good choice** when the array is **reversely sorted**.
