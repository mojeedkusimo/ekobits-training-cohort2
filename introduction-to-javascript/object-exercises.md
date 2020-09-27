# { OBJECT EXERCISES. }

For each of the exercises below, assume you are starting with the following programming object.

```javascript
{
    let programming = {
        languages: ["JavaScript", "Python", "Ruby"],
        isChallenging: true,
        isRewarding: true,
        difficulty: 8,
        jokes: "http://stackoverflow.com/questions/234075/what-is-your-best-programmer-joke"
    };
}
``` 
1. Write the command to add the language "Go" to the end of the languages array.
### ans: 
```javascript
{
    programming.languages.push("Go");
}
``` 
2. Change the difficulty to the value of 7.
### ans: 
```javascript
{
    programming.difficulty = 7;
}
``` 
3. Using the delete keyword, write the command to remove the jokes key from the programming object.
### ans:
```javascript
{
   delete programming.jokes;
}
```  
4. Write the command to add a new key called isFun and a value of true to the programming object.
### ans:
```javascript
{
    programming.isFun = true;
}
```  
5. Using a loop, iterate through the languages array and console.log all of the languages.
### ans:
```javascript
{
    for (let programmingLanguage of programming.languages) {
        console.log(programmingLanguage);
    }
}
``` 
6. Using a loop, console.log all of the keys in the programming object.
### ans:
```javascript
{
    for (let keys in programming) {
        console.log(keys);
    }
}
``` 
7. Using a loop, console.log all of the values in the programming object.
### ans:
```javascript
{
    for (let keys in programming) {
        console.log(programming[keys]);
    }
}
``` 