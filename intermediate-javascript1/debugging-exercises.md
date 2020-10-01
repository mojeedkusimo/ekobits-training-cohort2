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