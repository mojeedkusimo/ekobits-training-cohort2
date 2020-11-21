# { NODE.JS EXERCISES. }

For this exercise, we are going to build a simple command line tool which allows us to make a request to an API and store the data in a text file! We will be using the following modules:

fs - for reading and writing to a file
process - for gathering arguments from the command line
request - for making API requests (this is an external module)

This application should accept a command line argument using process.argv. The command line argument should be a search term and your application should make an API request to the dad joke API to search for a joke based on the search term. If it finds jokes matching the term, it should output a random joke, and should also save the joke to a file called jokes.txt. If it doesn't find a joke, it should log a message to the console telling the user that no jokes were found for that search term.

Bonus
Use the prompt module to ask a user for some input instead of having to pass in an argument from the command line.
Your program should accept a command line argument called leaderboard. If that command line argument is passed in, your application should return the most popular joke based on how many times it appears in jokes.txt

```javascript
{
const fs = require("fs");
const curl = new (require("curl-request"))();
const prompt = require("prompt");

prompt.start();

prompt.get(["searchTerm"], (error, result) => {
    if (error) throw error;
    findJoke(result.searchTerm);
})

let findJoke = (searchTerm) => {
    curl.setHeaders([
        "Accept: application/json"
    ])
    .get(`https://icanhazdadjoke.com/search?term=${searchTerm}`)
    .then(({statusCode, body, headers}) => {
        let jokesArray = body.results;
    
        if (jokesArray.length === 0) {
            console.log("I am sorry no joke was found for the word you entered, please try another word.");
        } else{
    
            let randomNum = Math.floor(Math.random()*jokesArray.length);
            let randomJoke = jokesArray[randomNum].joke;
            
            fs.appendFile("jokes.txt", `\n${randomJoke}`, (error) => {
                if (error) throw error;
                console.log("joke.txt has been updated!");
            });
        }
    })
    .catch((e) => {
        console.log(e);
    });    
}

}
```