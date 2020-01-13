### 1. Write a function that asks the user for a string containing multiple words. Print back to the user the same string, except with the words in backwards order. 

For example, say I type the string: This is Valhalla 

Then I would see the string: Valhalla is this

```javascript
const reverseSentence = (sentence) => {
  return sentence.replace(/[^\w\s]/g, '').split(' ').reverse().join(' ');
}

console.log(reverseSentence('the quick brown fox jumps over the lazy dog.'));
// OUTPUT:
// dog lazy the over jumps fox brown quick the
```

### 2. Write a program that asks the user how many Fibonacci numbers to generate and then generates them. Take this opportunity to think about how you can use functions. Make sure to ask the user to enter the number of numbers in the sequence to generate.

```javascript
const fib = num => {
  let a = 1, b = 0, c;
  const array = [];

  while (num >= 0){
    array.push(b);
    c = a;
    a = a + b;
    b = c;
    num--;
  }

  return array;
};

console.log(fib(10));
// OUTPUT:
// [ 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55 ]
```

### 3. Create a function that will sort the given array.

Sample array : [34,7,23,32,5,62]

Sample output : [5, 7, 23, 32, 34, 62]

```javascript
const sort = (array) => {
  return array.sort((a,b) => { if (a > b) return 1;
    if (a < b) return -1;
    return 0;
  });
}

console.log(sort([34,8,23,32,5,62]));
// OUTPUT
// [ 5, 7, 23, 32, 34, 62 ]
```

### 4. Create a function that will get the First Recurring Character feeded by string
Sample inputs and outputs: 

“ABCA”=> “A”

“CABDBA”=> “B”

“CBAD” => null

```javascript
const firstRecurring = (string) => {
  const uniques = [];
  const duplicates = [];
  string.split('').forEach(c => {
    if (!uniques.includes(c)) {
      uniques.push(c);
    } else {
      duplicates.push(c);
    }
  })
  return duplicates[0] || null;
}

console.log(firstRecurring('ABCA')); // OUTPUT: A
console.log(firstRecurring('CABDBA')); // OUTPUT: B
console.log(firstRecurring('CBAD')); // OUTPUT: null
```

### 5. Create a function that will check an Array of numbers for all combinations of 2 numbers and tell if any combination is equal to 8.
Sample arrays:

[1,2,3,4] Sum = 8 No

[4,2,4,1] Sum = 8 Yes

[7,2,4,6,7] Sum = 8 Yes


```javascript
const equalToEight = (array) => {
  let answer = 'No';
  array.forEach((n1, i1) => {
    array.forEach((n2, i2) => {
      if (i1 === i2) {
        return;
      }
      if (n1 + n2 === 8) {
        answer = 'Yes';
      }
    })
  })
  return answer;
}

console.log(equalToEight([1,2,3,4])) // OUTPUT: No
console.log(equalToEight([4,2,4,1])) // OUTPUT: Yes
console.log(equalToEight([7,2,4,6,7])) // OUTPUT: Yes
```
