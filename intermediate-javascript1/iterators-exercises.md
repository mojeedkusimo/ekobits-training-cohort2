# { ITERATORS EXERCISES. }

## Part I
Use the following object for this set of questions:

```javascript
{
    let users = [
    {
        username: 'larry',
        email: 'larry@foo.com',
        yearsExperience: 22.1,
        favoriteLanguages: ['Perl', 'Java', 'C++'],
        favoriteEditor: 'Vim',
        hobbies: ['Fishing', 'Sailing', 'Hiking'],
        hometown: {
        city: 'San Francisco',
        state: 'CA'
        }
    },
    {
        username: 'jane',
        email: 'jane@test.com',
        yearsExperience: 33.9,
        favoriteLanguages: ['Haskell', 'Clojure', 'PHP'],
        favoriteEditor: 'Emacs',
        hobbies: ['Swimming', 'Biking', 'Hiking'],
        hometown: {
        city: 'New York',
        state: 'NY'
        }
    },
    {
        username: 'sam',
        email: 'sam@test.com',
        yearsExperience: 8.2,
        favoriteLanguages: ['JavaScript', 'Ruby', 'Python', 'Go'],
        favoriteEditor: 'Atom',
        hobbies: ['Golf', 'Cooking', 'Archery'],
        hometown: {
        city: 'Fargo',
        state: 'SD'
        }
    },
    {
        username: 'anne',
        email: 'anne@test.com',
        yearsExperience: 4,
        favoriteLanguages: ['C#', 'C++', 'F#'],
        favoriteEditor: 'Visual Studio Code',
        hobbies: ['Tennis', 'Biking', 'Archery'],
        hometown: {
        city: 'Albany',
        state: 'NY'
        }
    },
    {
        username: 'david',
        email: 'david@test.com',
        yearsExperience: 12.5,
        favoriteLanguages: ['JavaScript', 'C#', 'Swift'],
        favoriteEditor: 'VS Code',
        hobbies: ['Volunteering', 'Biking', 'Coding'],
        hometown: {
        city: 'Los Angeles',
        state: 'CA'
        }
    }
    ];
}
```

Write a function called printEmails which console.log's each email for the users.

```javascript
{
    printEmails();
    // larry@foo.com
    // jane@test.com
    // sam@test.com
    // anne@test.com
    // david@test.com
}
```
### ans
```javascript
{
    function printEmails() {
        users.forEach(function(user) {
            console.log(user.email);
        });
    }
}
```

Write a function called printHobbies which console.log's each hobby for each user.

```javascript
{
    printHobbies();
    // "Fishing",
    // "Sailing",
    // "Hiking",
    // "Swimming",
    // "Biking",
    // "Hiking",
    // "Golf",
    // "Cooking",
    // "Archery",
    // "Tennis",
    // "Biking",
    // "Archery",
    // "Volunteering",
    // "Biking",
    // "Coding",
}
```

### ans
```javascript
{
    function printHobbies() {
        users.forEach(function(user) {
            user.hobbies.forEach(function(hobby) {
                console.log(hobby);
            });
        });
    }
}
```

Write a function called findHometownByState which returns the first user which has a hometown of the state that is passed in

```javascript
{
    findHometownByState('CA');
    /*/
    {
        username: "larry",
        email: "larry@foo.com",
        years_experience: 22.1,
        favorite_languages: ["Perl", "Scala", "C++"],
        favorite_editor: "Vim",
        hobbies: ["Fishing", "Sailing", "Hiking"],
        hometown: {
            city: "San Francisco",
            state: "CA"
        }
    }
    /*/
}
```

### ans
```javascript
{
    function findHometownByState(state) {
        return users.find(function(user) {
            return user.hometown.state === state;
        });
    }
}
```

Write a function called allLanguages which returns an array of all of the unique values

```javascript
{
    allLanguages();
    // ["Perl", "Scala", "C++","Haskell", "PHP","JavaScript","Ruby", "Python", "Go","C#", "F#", "Swift"]
}
```

### ans
```javascript
{
    function allLanguages() {
        let arrLang = [];
        users.forEach(function(user) {
            user.favoriteLanguages.forEach(function(language) {
                if (!arrLang.includes(language)) {
                    arrLang.push(language);
                }
            })
        });
        return arrLang;
    }
}
```

Write a function called hasFavoriteEditor which returns a boolean if any of the users have the editor passed in

```javascript
{
    hasFavoriteEditor('VS Code'); // true
    hasFavoriteEditor('Eclipse'); // false
}
```

### ans
```javascript
{
    function haveFavoriteEditor(editor) {
        return users.some(function(user) {
            return user.favoriteEditor === editor;
        });
    }
}
```


Write a function called findByUsername which takes in a string and returns an object in the users array that has that username

```javascript
{
    findByUsername('david');
    /*/
    {
        username: "david",
        email: "david@test.com",
        years_experience: 12.5,
        favorite_languages: ["JavaScript", "C#", "Swift"],
        favorite_editor: "VS Code",
        hobbies: ["Volunteering", "Biking", "Coding"],
        hometown: {
            city: "Los Angeles",
            state: "CA"
        }
    }
    /*/
}
```

### ans
```javascript
{
    function findByUsername(username) {
        return users.find(function(user) {
            return user.username === username;
        });
    }
}
```

## Part II

Write a function called vowelCount that accepts a string and returns an object with each key being the vowel and the value being the number of times the vowel occurs in the string (the order of keys in the object does not matter).

```javascript
{
    vowelCount('incredible');
    // {i:2, e: 2}
    vowelCount('awesome');
    // {a:1, e:2, o:1}
}
```

### ans
```javascript
{
    function vowelCount(string) {
        let vowels = "aeiou";
        let vowelCount = {};
        for (let letter of string) {
            if (vowels.includes(letter) && !(letter in vowelCount)) {
                vowelCount[letter] = 1; 
            } else if (vowels.includes(letter)) {
                vowelCount[letter]++; 
            }
        }
        return vowelCount;
    }}
}
```


Write a function called removeVowels that accepts a string and returns an array of each character that is not a vowel (y should not count as a vowel for this function).

```javascript
{
    removeVowels('amazing'); // ["m","z","n","g"]
    removeVowels('fun'); // ["f","n"]
    removeVowels('silly'); // ["s","l","l","y"]
}
```

### ans
```javascript
{
    function removeVowels(string) {
        let vowels = "aeiou";
        let consonantsArray = [];
        for (let letter of string) {
            if (!vowels.includes(letter)) {
                consonantsArray.push(letter);
            }
        }
        return consonantsArray;
    }
}
```
