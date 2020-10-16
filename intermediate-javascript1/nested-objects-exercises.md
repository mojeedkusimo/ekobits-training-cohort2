# { NESTED OBJECTS EXERCISES. }
Given the following nested object:

```javascript
{
    let nestedData = {
    innerData: {
        order: ["first", "second", "third"],
        snacks: ["chips", "fruit", "crackers"],
        numberData: {
            primeNumbers: [2,3,5,7,11],
            fibonnaci: [1,1,2,3,5,8,13]
        },
        addSnack: function(snack){
            this.snacks.push(snack);
            return this;
            }
        }
    }
}
```
Using a for loop, console.log all of the numbers in the primeNumbers array.
### ans: 
```javascript
{
    let primeNumbers = nestedData.innerData.numberData.primeNumbers;
    for (let primeNumber of primeNumbers) {
        console.log(primeNumber);
    }
}
```

Using a for loop, console.log all of the even Fibonnaci numbers.
### ans: 
```javascript
{
    let fibonnaciNumbers = nestedData.innerData.numberData.fibonnaci;
    for (let fibonnaciNumber of fibonnaciNumbers) {
        console.log(fibonnaciNumber);
    }
}
```

Console.log the value "second" inside the order array.
### ans: 
```javascript
{
    console.log(nestedData.innerData.order[1]);
}
```

Invoke the addSnack function and add the snack "chocolate".
### ans: 
```javascript
{
    nestedData.innerData.addSnack("chockolate");
}
```

Inside of the addSnack function there is a special keyword called this. What does the word this refer to inside the addSnack function?
### ans: The nestedData object.

Given the following nested object:

```javascript
{
    let nestedObject = {
        speakers: [{name:"Elie"},{name:"Tim"},{name:"Matt"}],
        data: {
            continents: {
            europe: {
                countries: {
                switzerland: {
                    capital: "Bern",
                    population: 8000000
                }
                }
            }
            },
            languages: {
            spanish: {
                hello: "Hola"
            },
            french: {
                hello: "Bonjour"
            }
            }
        }
    }
}
```
Write a function addSpeaker to add a speaker to the array of speakers. The speaker you add must be an object with a key of name and a value of whatever you'd like.
### ans: 
```javascript
{
    // Accept a single parameter, name of speaker
    // Check if speaker is in collection
        // if present
            // return a message, "Already listed"
        // if not
            // add speaker in collection
    function addSpeaker(name) {
        for (let i = 0; i < nestedObject.speakers.length; i++) {
            if (nestedObject.speakers[i].name === name) {
                return "Speaker is already listed";
            }
        }
            nestedObject.speakers.push({name});
            return "Speaker was added successfully";
        }
}
```

Write a function addLanguage that adds a language to the languages object. The language object you add should have a key with the name of the language and the value of another object with a key of "hello" and a value of however you spell "hello" in the language you add.
### ans: 
```javascript
{
    // Accept two parameters, name of language and "hello" in tha language
    // Check if language is in collection
        // if present
            // return a message, "Already listed"
        // if not
            // add language to collection
    function addLanguage(newLang, newHello) {
        for (let language in nestedObject.data.languages) {
            if (language === newLang) {
                return "Already listed";
            }
        }
        nestedObject.data.languages[newLang] = { hello : newHello};
        return `${newLang} was added`;
    }
}
```

Write a function addCountry that adds a European country to the countries object (inside of the continents object, inside of the countries object). The country you add should be an object with the key as name of the country and the value as an object with the keys of "capital" and "population" and their respective values.
### ans: 
```javascript
{
    // Accept three parameters, name of country, capital, and population
    // Check if country is in collection
        // if present
            // return a message, "Already listed"
        // if not
            // add country in collection
    function addCountry(newCountry, newCapital, newPopulation) {
        for (let country in nestedObject.data.continents.europe.countries) {
            if (country === newCountry) {
                return "Already listed";
            }
        }
        nestedObject.data.continents.europe.countries[newCountry] = { capital: newCapital, population: newPopulation};
        return `${newCountry} was added`;
    }
}
```