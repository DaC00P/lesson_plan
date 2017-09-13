## A short dive into algorithm 'design' and edge cases/pathological data

* An algo can also be extremely simple - and thus comes our first exercise. Everyone find a partner, and without any Googling, come up with the psuedocode for how to check if a number is odd or even. The function should be written in JS, and return `'odd'` for odd numbers and `'even'` for even numbers. Return `false` if the number is neither(or if the input isn't a number). Go forth and code!

## 'Ideal' Solution
```javascript
//check if the given value is a number, and if so, run helper methods to determine odd or even.
function oddOrEven(value){
  if(checkValue(value)){
    if(isEven(value)){
      return 'even';
    }
    else if(isOdd(value)){
      return 'odd';
    }
  }
  return false;
}
//helper method to ensure we only test numbers.
function checkValue(value){
  return !Number.isNaN(parseFloat(value)) && Number.isFinite(value);
}
//helper method to check if a number is even
function isEven(number) {
   return number % 2 === 0;
}
//helper method to check if a number is odd
function isOdd(number) {
   return Math.abs(number % 2) === 1;
}
//tests
console.log(oddOrEven(5));
console.log(oddOrEven({}));
console.log(oddOrEven(92));
console.log(oddOrEven(2132123123123124122));
console.log(oddOrEven('a'));
console.log(oddOrEven({1: 2}));
console.log(oddOrEven([1, 2, 3]));
console.log(oddOrEven(' '));
console.log(oddOrEven('  5'));
console.log(oddOrEven('5'));
```

### So, what gives? We wrote 22 lines of code where a simple ternary one-liner may have sufficed.
* In CS, we often have to design algorithms to work solo, outside of any control over input. This means we may run across what is known as pathological data - data that is designed to or will cause your algo to not function properly.
* For example, if we don't check our value first and we attempt to run `isEven` on an empty array, the function would return true when it should return false.

### You may also say, why so many separate functions? Would one not do?
* In computer science, we try to code through our lives by paying heed to the single responsibility principle (SRP). This means that we should encapsulate each action that our algorithm takes into a function. One function for checking if the given value is a proper number, one for checking even-ness, and one for checking odd-ness.
* This has the added benefit of re-usable code. Now, if 2 months down the line we need to check if a value is a number, we have a nice small snippet of code that we can turn into its own module, able to be used anywhere in our code.

-----------------------------------------

## Prime Number Checker in this format

------------------------------------------

* At this point, slack the following link out to all the students, and put it on the projector. http://bigocheatsheet.com/ is an AWESOME resource, but most of it will be too complex for students at this point.

---------------
