
# Part I
## Write down what the following statements will return. Try to figure this out before putting the commands in the chrome console.

### 1. 2 == "2";
### ans: true.
### 2. 2 === 2;
### ans: true.
### 3. 10 % 3;
### ans: 1.
### 4. 10 % 3 === 1;
### ans: true.
### 5. true && false;
### ans: false.
### 6. false || true;
### ans: true.
### 7. true || false;
### ans: true.

# Part II
## Answer the following questions about this code block:

```javascript
{
    let isLearning = true;
    if (isLearning) {
        console.log("Keep it up!");
    } else {
        console.log("Pretty sure you are learning...");
    }
}
```

### 1. What should the above code console.log?
### ans: Keep it up!
### 2. Why do we not need to specify ==if(isLearning === true)==? Why does if(isLearning) work on its own?
### ans: This is because the value of varaiable "isLearning" is NOT any of the 6 falsey values (namely: 0, "", null, undefined, false, NaN.) in Javascript. Thus the variable "isLearning" is coerced into the boolean value of "true" since it is expecting a boolean value in the if condition.

```javascript
{
    let firstvariable;
    let secondvariable = "";
    let thirdvariable = 1;
    let secretMessage = "Shh!";

    if(firstvariable){
        console.log("first");
    } else if(firstvariable || secondvariable){
        console.log("second");
    } else if(firstvariable || thirdvariable){
        console.log("third");
    } else {
        console.log("fourth");
    }
}
```

### What should the above code console.log? Why?
### ans 1: third.
### ans 2: This is because the first two conditions are evaluated to false, thus not executed. 
### What is the value of firstvariable when it is initialized?
### ans: undefined.
### Is the value of firstvariable a "truthy" value? Why?
### ans 1: No, it is a falsey value.
### ans 2: This is because it's value is undefined, and undefined is one of the 6 falsey values in javascript namely: 0, "", null, undefined, false, NaN. 
### Is the value of secondvariable a "truthy" value? Why?
### ans 1: No, it is a falsey value.
### ans 2: This is because it is an empty string, and it is one of the 6 falsey values in javascript namely: 0, "", null, undefined, false, NaN. 
### Is the value of thirdvariable a "truthy" value? Why?
### ans 1: Yes, it is a truthy value.
### ans 2: This is because it is not one of the 6 falsey values in javascript namely: 0, "", null, undefined, false, NaN.

# Part III
### Research Math.random here and write an if statement that console.log's "Over 0.5" if Math.random returns a number greater than 0.5. Otherwise console.log "Under 0.5".
### ans: 
```javascript
{
    if (Math.random() > 0.5) {
        console.log("Over 0.5");
    } else {
        console.log("Under 0.5");
    }
}
```
### What is a falsey value? List all the falsey values in JavaScript.
### ans 1: Falsey values are values that Javascript coerces to a value of "false" anywhere it expects a boolean value
### ans 2: Falsey values are: 0, "", null, undefined, false, NaN.