# Recursion
An exercise about the Fibonacci sequence and merge sort

## Links
- [Link to assignment](https://www.theodinproject.com/lessons/javascript-recursion)
- [Try Fibonacci here](https://TYLPHE.github.io/recursion/fibonacci/)
- [Try Merge Sort here](https://TYLPHE.github.io/recursion/merge-sort/)

## Summary
Recursion is split into two different folders. Both contain an html file with some javascript related to Fibonacci and Merge Sort. 

I decided to have some fun and let the user input values. The page then outputs the result as well as the formula I used to calculate it.

### Fibonacci
Fibonacci will have two outputs - one that uses iteration for its caluculation and the other is using recursion.
```javascript
function fibs(n) {
  let arr = [];
  let a = 0;
  let b = 1;
  for (let i = 0; i < n; i += 1) {
    arr.push(a);
    let c = a + b;
    a = b;
    b = c;
  }
}

function fibsRec(n) {
  if (n < 2) {
    return n;
  } else {
    return fib(n - 1) + fib(n - 2);
  }
}
```

### Merge Sort
Merge Sort asks the user to input numbers, followed by spaces. My script then converts the user's string of numbers and spaces and converts it into an array.

The user should see an array with sorted numbers on the web page, followed by the code I wrote to sort it.
```javascript
function mergeSortAlg(arr) {
  if (arr.length < 2) {
    return arr;
  }
  // split array into two
  const middle = Math.ceil(arr.length / 2);
  const left = arr.slice(0, middle);
  const right = arr.slice(middle);

  // merge left and right
  return merge(mergeSortAlg(left), mergeSortAlg(right));

  function merge(a, b) {
    const c = [];
    aIndex = 0;
    bIndex = 0;
    while (aIndex < a.length && bIndex < b.length) {
      if (a[aIndex] < b[bIndex]) {
        c.push(a[aIndex]);
        aIndex++;
      } else {
        c.push(b[bIndex]);
        bIndex++;
      }
    }
    while (a[aIndex]) {
      c.push(a[aIndex]);
      aIndex++;
    }
    while (b[bIndex]) {
      c.push(b[bIndex]);
      bIndex++;
    }
    return c;
  }
}
```
