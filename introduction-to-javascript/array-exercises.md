# { ARRAY EXERCISES. }
For each of the exercises below, assume you are starting with the following people array.
```javascript
{
    let people = ["Greg", "Mary", "Devon", "James"];
}
```

### 1. Using a loop, iterate through this array and console.log all of the people.
### ans: 
```javascript
{
    for (let person of people) {
        console.log(person);
    }
}
```
### 2. Write the command to remove "Greg" from the array.
### ans:
```javascript
{
    people.shift();
}
``` 
### 3. Write the command to remove "James" from the array.
### ans:
```javascript
{
    people.pop();
}
```  
### 4. Write the command to add "Matt" to the front of the array.
### ans:
```javascript
{
    people.unshift("Matt");
}
``` 
### 5. Write the command to add your name to the end of the array.
### ans:
```javascript
{
    people.push("Mojeed");
}
```  
### 6. Using a loop, iterate through this array and after console.log-ing "Mary", exit from the loop.
### ans:
```javascript
{
    for (let person of people) {
        console.log(person);
        if (person === "Mary"){
            break;
        }
    }
}
``` 
### 7. Write the command to make a copy of the array using slice. The copy should NOT include "Mary" or "Matt".
### ans: 
```javascript
{
    people.slice(2,4);
}
```  
### 8. Write the command that gives the indexOf where "Mary" is located.
### ans:
```javascript
{
    people.indexOf("Mary");
}
``` 
### 9. Write the command that gives the indexOf where "Foo" is located (this should return -1).
### ans: 
```javascript
{
    people.indexOf("Foo");
}
``` 
### 10. Redefine the people variable with the value you started with. Using the splice command, remove "Devon" from the array and add "Elizabeth" and "Artie". Your array should look like this when you are done ["Greg", "Mary", "Elizabeth", "Artie", "James"].
### ans: 
```javascript
{
    let people = ["Greg", "Mary", "Devon", "James"];
    people.splice(2,1,"Elizabeth","Artie");
}
```
### 11. Create a new variable called withBob and set it equal to the people array concatenated with the string of "Bob".
### ans:
```javascript
{
    let withBob = people.concat("Bob");
}
```  