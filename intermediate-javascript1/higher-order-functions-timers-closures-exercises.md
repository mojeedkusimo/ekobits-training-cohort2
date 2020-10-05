# { HIGHER ORDER FUNCTIONS, TIMERS, AND CLOSURES EXERCISES. }

## countdown
Write a function called countdown that accepts a number as a parameter and every 1000 milliseconds decrements the value and console.logs it. Once the value is 0 it should log "DONE!" and stop.

```javascript
{
    countDown(4);
    // 3
    // 2
    // 1
    // "DONE!"
}
```
### ans: 
```javascript
{
    // Accept a single parameter, a number
    // Decrease the number by 1 every 1s and log it out
    // log out "DONE!", once its zero
    function countdown(num) {
        let timeoutID = setTimeout(function() {
            console.log("DONE!");
            clearTimeout(countdownID);
        }, num * 1000);
        let countdownID = setInterval(function() {
                console.log(--num);
        }, 1000);
    }
}
```

## randomGame

Write a function called randomGame that selects a random number between 0 and 1 every 1000 milliseconds and each time that a random number is picked, add 1 to a counter. If the number is greater than .75, stop the timer and return the number of tries it took before we found a number greater than .75.

### ans:
```javascript
{
    // No parameter is accepted
    // Select a random number everey second
    // Create an accumulator counter for all picks
    // Check if randomNum is greater that 0.75
        // if true
            // stop timer and return counter
        // if not
            // continue to pick
    function randomGame() {
        let noOfPicks = 0;
        let randomNum;
        let pickID = setInterval(function() {
            randomNum = Math.random();
            noOfPicks++;
            if (randomNum > 0.75) {
                clearInterval(pickID);
                console.log(noOfPicks);
            }
        }, 1000);
    }
}
```

## isEven
Write a function called isEven which takes in a number and returns true if the number is even and returns false if it is not.
```javascript
{
    isEven(2); // true
    isEven(3); // false
}
```
### ans:
```javascript
{
    // Accept one parameter, a number
    // check if number is even
    // return result of check

    function isEven(num) {
        return num % 2 === 0;
    }
}
```

## isOdd
Write a function called isOdd which takes in a number and returns true if the number is odd and returns false if it is not
```javascript
{
    isOdd(3); // true
    isOdd(14); // false
}
```
### ans:
```javascript
{
    // Accept one parameter, a number
    // check if number is odd
    // return result of check

    function isOdd(num) {
        return num % 2 !== 0;
    }
}
```
## isPrime
Write a function called isPrime which takes in a number and returns true if the number is a prime number (is greater than 1 and can only be divided in whole by itself and 1), otherwise returns false.

```javascript
{
    isPrime(8); // false
    isPrime(17); // true
}
```
### ans:
```javascript
{
    // Accept a parameter, a number
    // Check if number is divisible by 2, 3, or 5
        // if true
            //return false
        // if not
            // return true

    function isPrime(num) {
        if (num !== 2 && num % 2 === 0) {
            return false;
        } else if (num !== 3 && num % 3 === 0) {
            return false;
        } else if (num !== 5 && num % 5 === 0) {
            return false;
        } else {
            return true;
        }
    }
}
```

## numberFact
Write a function called numberFact which takes in a number and a callback and returns the result of the callback with the number passed to it.
```javascript
{
    numberFact(59,isEven); // false
    numberFact(59,isOdd); // true
    numberFact(59,isPrime); // true
}
```
### ans:
```javascript
{
    // Accept two parameters, a number and a callback
    // Store callback execution on number in callbackResult
    // return callbackResult

    function numberFact(number, callback) {
        let callbackResult = callback(number);
        return callbackResult;
    }
}
```

## find
Write a function called find. It should take in an array and a callback and return the first value found in the array that matches the condition.
```javascript
{
    find([8,11,4,27], function(val){return val >= 10}); // 11
    find([8,11,4,27], function(val){return val === 5}); // undefined
}
```
### ans:
```javascript
{
    // Accept two parameters, an array and a callback
    // Test the callback on every element of the array
    // Store all elements that pass in an array
    // return the first element of the passArray
    function find(array, callback) {
        let passArr = array.filter(callback);
        return passArr[0];
    }
}
```

## findIndex
Write a function called findIndex. It should take in an array and a callback and return the index of first value found in the array that matches the condition.
```javascript
{
    // returns 1 (index of the first value greater than or equal to 10)
    findIndex([8,11,4,27], function(val){return val >= 10});

    findIndex([8,11,4,27], function(val){return val === 7}); // undefined
}
```
### ans:
```javascript
{
    // Accept two parameters, an array and a callback
    // Test the callback on every element of the array
    // Store all elements that pass in an array
    // return the index of the first element of the passArray in the given array
    function find(array, callback) {
        let passArr = array.filter(callback);
        return array.indexOf(passArr[0]);
    }
}
```

## specialMultiply

Write a function called specialMultiply which accepts two parameters. If the function is passed both parameters, it should return the product of the two. If the function is only passed one parameter - it should return a function which can later be passed another parameter to return the product. You will have to use closure and arguments to solve this.
```javascript
{
    specialMultiply(3,4); // 12
    specialMultiply(3)(4); // 12
    specialMultiply(3); // returns a function 
}
```
### ans:
```javascript
{
    // Accept two parameters, two integers
    // Check number of arguments passed in
        // if one
            // return a function that can accept another parameter to multiply
        // if two
            // return the product of the two numbers

    function specialMultiply() {
        let firstNum = arguments[0];
        let secondNum = arguments[1];
        if (arguments.length > 1) {
                return firstNum * secondNum;
        }
        return function innerMultiply(secondNum) {
            return firstNum * secondNum;
        }
    }
}
```