# { FUNCTIONS EXERCISES. }

Your assignment is to write the following functions in the descriptions below - good luck!

## Part 1
### difference
this function takes in two parameters and returns the difference of the two;
```javascript
{
    difference(2,2); // 0
    difference(0,2); // -2
}
```
### ans:
```javascript
{
    // Accept two parameters, firstValue and secondValue
    // return the result of the subtraction of the secondValue from the firstValue
    function difference (firstValue, secondValue) {
        return firstValue - secondValue;
    }
}
``` 

### product
this function takes in two parameters and returns the product of the two;
```javascript
{
    product(2,2); // 4
    product(0,2); // 0
}
```
### ans: 
```javascript
{
    // Accept two parameters, firstValue and secondValue
    // return the result of the multiplication of the secondValue and the firstValue
    function product (firstValue, secondValue) {
        return firstValue * secondValue;
    }
}
``` 


### printDay
this function takes in one parameter (a number from 1-7) and returns the day of the week (1 is Sunday, 2 is Monday, 3 is Tuesday etc.). If the number is less than 1 or greater than 7, the function should return undefined;
```javascript
{
    printDay(4); // "Wednesday"
    printDay(41); // undefined
}
```
### ans:
```javascript
{
    // Accept a single parameter, noOfDayOfTheWeek
    // Initialize an object, daysOfTheWeek to contain keys as 1 - 7 and corresponding values Sunday - Saturaday
    // Check if the parameter is available in the object
        // If true
            // return the corresponding day of the week
        // If false
            // return undefined
    function printDay (noOfDayOfTheWeek) {
        let daysOfTheWeek = {
            1: "Sunday", 2: "Monday", 3: "Tuesday", 4: "Wednesday", 5: "Thursday", 6: "Friday", 7: "Saturday"
        };
        if (noOfDayOfTheWeek in daysOfTheWeek) {
            return daysOfTheWeek[noOfDayOfTheWeek];
        }
        return undefined;
    };
}
``` 

### lastElement
this function takes in one parameter (an array) and returns the last value in the array. It should return undefined if the array is empty.
```javascript
{
    lastElement([1,2,3,4]); // 4
    lastElement([]); // undefined
}
```
### ans:
```javascript
{
    // Accept a single parameter (an array) called inputedArray
    // Check if inputedArray is empty
        // if true
            // return undefined
        // if false
            // Store the index of the last element in a variable lastIndex
            // return the corresponding element
    function lastElement (inputedArray) {
        if (inputedArray === []) {
            return undefined;
        }
        let lastIndex = inputedArray.length - 1;
        return inputedArray[lastIndex];
    } 
}
```

### numberCompare
this function takes in two parameters (both numbers). If the first is greater than the second, this function returns "First is greater". If the second number is greater than the first, the function returns "Second is greater". Otherwise the function returns "Numbers are equal"
```javascript
{
    numberCompare(1,1); // "Numbers are equal"
    numberCompare(2,1); // "First is greater"
    numberCompare(1,2); // "Second is greater"
}
```
### ans:
```javascript
{
    // Accept two parameters, firstValue and secondValue
    // Check if the firstValue and secondValue are equal
        // if true
            // return a message, Numbers are equal
        // if false
            // check if firstValue is greater than the secondValue
                // if true
                    // return a message, First is greater
                // if false
                    // return a message, Second is greater
    function numberCompare(firstValue, secondValue) {
        if (firstValue === secondValue) {
            return "Numbers are equal";
        }
        if (firstValue > secondValue) {
            return "First is greater";
        }
        return "Second is greater";
    }
}
```

### singleLetterCount
this function takes in two parameters (two strings). The first parameter should be a word and the second should be a letter. The function returns the number of times that letter appears in the word. The function should be case insensitive (does not matter if the input is lowercase or uppercase). If the letter is not found in the word, the function should return 0.
```javascript
{
    singleLetterCount('amazing','A'); // 2
    singleLetterCount('Inf-Paces School','o'); // 2
}
```
### ans:
```javascript
{
    // Accept two parameters, word and letter
    // Initialize a variable wordInLowercase to hold word being converted to lowercase
    // Initialize a variable letterInLowercase to hold letter being converted to lowercase
    // Initialize an accumulator variable, noOfLetterInWord to zero
    // Loop through the wordInLowercase
        // Check if letterInLowercase is equivalent to wordInLowercase character
            // if true
                // increment noOfLetterInWord by 1
            // if false
                // do nothing
    // return noOfLetterInWord
    function singleLetterCount(word, letter) {
        let wordInLowercase = word.toLowerCase();
        let letterInLowercase = letter.toLowerCase();
        let noOfLetterInWord = 0;
        for (let character of wordInLowercase) {
            if (letterInLowercase === character) {
                noOfLetterInWord++;
            }
        }
        return noOfLetterInWord;
    } 
}
```

## Part 2
### multipleLetterCount
this function takes in one parameter (a string) and returns an object with the keys being the letters and the values being the count of the letter.
```javascript
{
    multipleLetterCount("hello"); // {h:1, e: 1, l: 2, o:1}
    multipleLetterCount("person"); // {p:1, e: 1, r: 1, s:1, o:1, n:1}
}
```
### ans:
```javascript
{
    // Accept a single parameter, inputedString
    // Initialize a variable, inputedStringInLowerCase to hold lowerCase of inputedString
    // Initialize an accumulator object, noOfLetterInString
    // Loop through inputedStringInLowerCase
        // Check if inputedStringInLowerCase character is a key in noOfLetterInString
            // if true
                // increment value of character by 1
            // if false
                // initialize the character key with a value of 1
    // return noOfLetterInString
    function multipleLetterCount(inputedString) {
        let inputedStringInLowerCase = inputedString.toLowerCase();
        let noOfLetterInString = {};
        for (let character of inputedStringInLowerCase) {
            if (character in noOfLetterInString) {
                noOfLetterInString[character]++;
            } else {
                noOfLetterInString[character] = 1;
            }
        }
        return noOfLetterInString;
    }
}
```

### arrayManipulation
this function should take in at most four parameters (an array, command, location, and value):
    If the command is "remove" and the location is "end", the function should remove the last value in the array and return the value removed. (In this case, the function only needs three arguments.)
    If the command is "remove" and the location is "beginning", the function should remove the first value in the array and return the value removed. (In this case, the function only needs three arguments.)
    If the command is "add" and the location is "beginning", the function should add the value (fourth parameter) to the beginning of the array and return the array.
    If the command is "add" and the location is "end", the function should add the value (fourth parameter) to the end of the array and return the array.
    
```javascript
{
    arrayManipulation([1,2,3], "remove", "end"); // 3
    arrayManipulation([1,2,3], "remove", "beginning"); // 1
    arrayManipulation([1,2,3], "add", "beginning", 20); // [20,1,2,3]
    arrayManipulation([1,2,3], "add", "end", 30); // [1,2,3,30]

}
```
### ans:
```javascript
{
    // Accept four parameters, an array, a command(string), a location(string), and a value(any primitive)
    // Check if command is "remove" and the location is "end"
        // if true
            // remove the last value in the array
            // return the value removed
        // if false
            // do nothing
    // Check if command is "remove" and the location is "beginning"
        // if true
            // remove the first value in the array
            // return the value removed
        // if false
            // do nothing
    // Check if command is "add" and the location is "beginning"
        // if true
            // add the value to the beginning of the array
            // return the array
        // if false
            // do nothing
    // Check if command is "add" and the location is "end"
        // if true
            // add the value to the end of the array
            // return the array
        // if false
            // do nothing
    function arrayManipulation (array, command, location, value) {
        if (command === "remove" && location === "end") {
            return array.pop();
        }
        if (command === "remove" && location === "beginning") {
            return array.shift();
        }
        if (command === "add" && location === "beginning") {
            array.unshift(value);
            return array;
        }
        if (command === "add" && location === "end") {
            array.push(value);
            return array;
        }
    }
}
```

### isPalindrome
A Palindrome is a word, phrase, number, or other sequence of characters which reads the same backward or forward. This function should take in one parameter and returns true or false if it is a palindrome. As a bonus, allow your function to ignore whitespace and capitalization so that isPalindrome('a man a plan a canal Panama'); returns true
```javascript
{
    isPalindrome('testing'); // false
    isPalindrome('tacocat'); // true
    isPalindrome('hannah'); // true
    isPalindrome('robert'); // false
}
```
### ans:
```javascript
{
    // Accept one parameter, a string
    // Copy the inputed string into a newString
    // Get rid of any whitespace and convert to lowerCase
    // Create a new variable revString
    // Loop through the string from the end and populate the revString with the characters
    // Compare both revSrting and newString
        // if equal
            // return true
        // if not
            // return false
    function isPalindrome (string) {
        let copyString = string.replace(/[^A-Z]/gi, '').toLowerCase();
        let revString = '';

        for (let i = copyString.length - 1; i > -1; i--) {
            revString += copyString[i]
        }

        if (copyString === revString) {
            return true;
        }
        else {
            return false;
        }
    }
}
```

## Part 3
### Rock / Paper / Scissor
using your knowledge so far, build a game of Rock/Paper/Scissor where through the use of the prompt function, a user can enter their choice and based on a random selection - they can either tie/win or lose against a computer.

### ans:
```javascript
{
    // Accept no parameter
    // Ask a user to choose from the options: rock, paper, scissor and store response in lowerCase in a varaible
    // Initialize an array, options with elements: rock,paper,scissor
    // Initialize a variable computerChoice to randomly pick from options
    // Check if userChoice is equal to computerChoice
        // if true
            // return a message, You Win
        // if false
            // return a message, You Lose
    function rockPaperScissorGame () {
        let userChoice = prompt("Chose from the options: Rock, Paper, Scissor").toLowerCase();
        const options = ["rock", "paper", "scissor"];
        let randomNum = Math.floor(3 * Math.random());
        let computerChoice = options[randomNum];

        if (userChoice === computerChoice) {
            alert("You Win");
        } else {
            alert("You Lose");
            alert(computerChoice);
        }
    }
}
```
