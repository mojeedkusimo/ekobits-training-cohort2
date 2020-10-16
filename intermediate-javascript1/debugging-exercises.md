# { DEBUGGING EXERCISES. }


Answer the following questions:

What does the throw keyword do?
### ans: It returns an error when something is done incorrectly in an application and stops code execution.

What does the finally keyword do?
### ans: It is used next to a block of code we want to run regardeless of an error being thrown.

What is the difference between a TypeError and ReferenceError?
### ans: The TypeError occurs when one makes an inappropriate use of types in javascript while ReferenceError occurs when one tries to access a variable that does not exist in that scope.

How do you create a snippet in the Chrome dev tools?
### ans: This is acheievd by selecting the "Sources" tab and then clicking on "+ New snippet". Then give it a name.

In the Chrome dev tools, on the right hand side of the sources tab, there is a "pause" button which allows you to "pause on caught exceptions." What is an exception?
### ans: These are errors generated when code is executed in javascript.

How do we "catch" errors in JavaScript? Give an example with code for what that might look like.
### ans: 
```javascript
{
    try {
        let num = Math.floor(99 * Math.random());
        if (num % 2 === 0) {
            throw "I am sorry, ", num," is an even number";
        }
        console.log(num);
    } catch(e) {
        console.log("The error is", e)
    }
}
```

Explain what type of error will be thrown, why the error is occuring, and how to fix it:

1.
```javascript
{
    person;
}
```
### ans: 
### Type of error: ReferenceError
### Reason for occurence: Variable person has not being declared yet.
### Fix: Declare variable person with let or const keywords.

2.
```javascript
{
    let data = {};
    data.displayInfo();
}
```
### ans: 
### Type of error: TypeError
### Reason for occurence: displayInfo is not a function.
### Fix: A function, displayInfo should be declared in the data object.

3.
```javascript
{
    let data = {};
    data.displayInfo.foo = "bar";
}
```
### ans: 
### Type of error: TypeError
### Reason for occurence: displayInfo in undefined and cannot be given a value.
### Fix: displayInfo object should be declared in the data object.

4.
```javascript
{
    function data(){
        let thing = "foo";
    }
    data();
    thing;
}
```
### ans: 
### Type of error: ReferenceError
### Reason for occurence: thing is not declared in the global scope.
### Fix: displayInfo object should be declared in the data object.

## Part II
Fix the broken code and explain what was wrong:

1.
```javascript
{
    for(let i=0; i > 5; i++){
        console.log(i);
    }
}
```
### ans 
```javascript
{
    for(let i=0; i < 5; i++){
        console.log(i);
    }
}
```
### Explanation: In the code snippet given, the loop is to run as long as i greater than 5. But i was initialized to zero, so it is never going to run.

2.
```javascript
{
    function addIfEven(num){
        if(num % 2 = 0){
            return num + 5;
        }
        return num;
    }
}
```
### ans 
```javascript
{
    function addIfEven(num){
        if(num % 2 == 0){
            return num + 5;
        }
        return num;
    }
}
```
### Explanation: The condition in if statement is an invalid assignment operation with, = instead of an equality operation using (== or !=)

3.
```javascript
{
    function loopToFive(){
        for(let i=0, i < 5, i++){
            console.log(i);
        }
    }
}
```
### ans 
```javascript
{
    function loopToFive(){
        for(let i=0; i < 5; i++){
            console.log(i);
        }
    }
}
```
### Explanation: There is syntax error in the conditions of the for loop("," instead of ";")

4.
```javascript
{
    function displayEvenNumbers(){
        let numbers = [1,2,3,4,5,6,7,8];
        let evenNumbers = [];
        for(let i=0; i<numbers.length-1; i++;){
            if(numbers % 2 = 0); {
                evenNumbers.push(i);
            }
            return evenNumbers;
        }
    }
    displayEvenNumbers(); // should return [2,4,6,8]

    // HINT - eight things need to be changed here for this to work!
    // Start by fixing the syntax errors and then run the function to see what your output is.
}
```
### ans 
```javascript
{
    function displayEvenNumbers(){
        let numbers = [1,2,3,4,5,6,7,8];
        let evenNumbers = [];
        for(let i=0; i<numbers.length; i++){
            if(numbers[i] % 2 === 0) {
                evenNumbers.push(numbers[i]);
            }
        }
        return evenNumbers;
    }
    displayEvenNumbers();
}
```
### Explanation: 
### 1. There was a syntax error at the end of the condition statement of the if-block (";" coming after i++).
### 2. The condition in if statement is an invalid assignment operation with, = instead of an equality operation using (==, ===, !== or !=)
### 3. The if statement stops execution immediately after setting the condition, because of the ";" after the ")" at the end of the condition description
### 4. The condition in the if statement is finding the remainder of the whole "numbers" array divided by 2 instead of each element of the "numbers" array.
### 5. In the if-block, it is the value of i, (iteration number) that is set to be pushed to the "numbers" array
### 6. The for loop is stopping execution on the first iteration because of the return statement inside the loop.
### 7. The for loop is only running up to 1 less the rquired number of iterations