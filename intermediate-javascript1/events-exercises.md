# { EVENTS EXERCISES. }

Given the following HTML, create a script.js file to complete the first two parts.

### ans:
```html
{
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>DOM Exercise</title>
        <style>
            div {
            width: 50px;
            height: 50px;
            display: inline-block;
            }
            .brown{
            background-color: brown;
            }
            .green{
            background-color: green;
            }
            .blue{
            background-color: blue;
            }
            .purple{
            background-color: purple;
            }
            .yellow{
            background-color: yellow;
            }
            .car1 {
            background-color: #8C9C12;
            }
            .car2 {
            background-color: #1DA788;
            }
            .car1, .car2 {
                margin-left: 0;
            }
        </style>
    </head>
    <body>
        <h1 id="change_heading">Change Me!</h1>
        SELECTED COLOR <span class="selected">None!</span>
        <section>
            <div class="brown"></div>
            <div class="green"></div>
            <div class="blue"></div>
            <div class="yellow"></div>
        </section>
        <h2>Race!</h2>
        <button>Start the race!</button>
        <br>
        <div class="car1"></div>
        <br>
        <div class="car2"></div>
        <script src="script.js"></script>
    </body>
    </html>
}
```

## Part 1

1. Add the necessary code to wait for the DOM to load to make sure that anything you manipulate in the DOM has loaded. You can do this either using window.onload or adding an event listener for DOMContentLoaded.

### ans:
```javascript
{
    window.onload = function(event) {
        // other javascript code
    };
    // or
    window.addEventListener('load', (event) => {
        // other javascript code
    });
}
```

2. Replace the text "Change me" with "Hello World!".

### ans:
```javascript
{
    document.querySelector("#change_heading").textContent = "Hello World!";
}
```

3. When a user hovers over one of the colored boxes change the text to display the color that is being hovered over.
### ans:
```javascript
{
    let selectedColor = document.querySelector(".selected");
    let colors = document.querySelectorAll("section div");
    for (let color of colors) {
    color.addEventListener("mouseover", function(event) {
       selectedColor.textContent = event.target.classList[0];
    });
}
```

4. Create a new div element.
### ans:
```javascript
{
    let newElem = document.createElement("div");
}
```

5. Give your new div a class of purple and style it so that it has a background color of purple.
### ans:
```javascript
{
    newElem.classList.add("purple");
}
```

6. Append your new div to the page to the section tag.
### ans:
```javascript
{
    document.querySelector("section").appendChild(newElem);
}
```

## Part 2

Create a racing game with the two cars. When the race button is pressed, the two cars should move across the screen until one of them is at the end of the screen. When one of the blocks reaches the end - you should alert "winner!"

### ans:
```javascript
{
    let button = document.querySelector("button");
    button.addEventListener("click", startRace);


    let carOne = document.querySelector(".car1");
    let carTwo = document.querySelector(".car2");

    function startRace () {
        let marginValue = [0,0];
        let veiwPort = window.innerWidth;
        let incrementTimerID = setInterval(increment, 100);

        function increment() {
            marginValue[0] += 2;
            marginValue[1] += 1;
            carOne.style.marginLeft = `${marginValue[0]}px`;
            carTwo.style.marginLeft = `${marginValue[1]}px`;
            console.log(marginValue);
            console.log(window.innerWidth);
            if ((marginValue[0] || marginValue[1]) === veiwPort - 58) {
                clearTimeout(incrementTimerID);
                alert("winner!");
            }
        }
    }
}
```
### Demo of part 1 and 2 can be found [here](https://mojeedkusimo.github.io/ekobits-mini-projects/event-exercise-part1-and-part2/)

## Part 3
For this assignment you will be combining your knowledge of DOM access and events to build a todo app!

As a user, you should be able to:

1. Add a new todo (by submitting a form)
2. Mark a todo as completed (cross out the text of the todo)
3. Remove a todo
### ans:
```html
{
   <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="initial-scale=1.0">
        <title>Todo App with vanilla JS</title>
        <style>
            * {
                margin: 0;
                box-sizing: border-box;
            }

            h1 {
                margin: 30px 0px;
            }
            #todos-list h1, #completed-todos h1 {
                margin-top: 30px;
                margin-bottom: 0;
            }

            .listed-todos span {
                margin-right: 30px;
            }
            p {
                color: red;
                font-style: italic;
            }

            #completed-todos span {
                color: green;
            }

            #todos-list span {
                color: brown;
            }
        </style>
    </head>
    <body>
        <main>
            <section id="add-todos">
                <h1>Todo App with vanilla JS</h1>
                <form action="">
                    <input type="text" name="newTodo" id="newTodo">
                    <button type="submit" id="submit-todos">Add Todo</button>
                </form>
            </section>
            <section id="completed-todos">

            </section>
            <section id="todos-list">

            </section>    
        </main>
        <script>
            let form = document.querySelector("form"),
                newTodo = document.querySelector("input#newTodo"),
                todoListing = document.querySelector("#todos-list"),
                completedTodosListing = document.querySelector("#completed-todos");

                form.addEventListener("submit", addTodo);

            function addTodo(e) {
                e.preventDefault();

                if (newTodo.value == "") {
                    alert("Please enter a todo");
                } else {

                let newTodoElem = document.createElement("div"),
                    newTodoSpan = document.createElement("span"),
                    titleOfNewTodos = document.createElement("h1"),
                    completedTodoButton = document.createElement("button"),
                    deleteTodoButton = document.createElement("button");

                    completedTodoButton.addEventListener("click", completedTodos);
                    deleteTodoButton.addEventListener("click", deleteTodos);

                titleOfNewTodos.textContent = "Pending Todos";
                newTodoSpan.textContent = newTodo.value;
                completedTodoButton.textContent = "Mark as Completed";
                deleteTodoButton.textContent = "Delete";


                if (todoListing.childElementCount < 1) {
                    todoListing.appendChild(titleOfNewTodos);
                }

                newTodoElem.classList.add("listed-todos");
                todoListing.appendChild(newTodoElem);
                newTodoElem.appendChild(newTodoSpan);
                newTodoElem.appendChild(completedTodoButton);
                newTodoElem.appendChild(deleteTodoButton);
                newTodo.value = "";
                }

                if (todoListing.children[1].textContent == "No pending tasks") {
                    todoListing.removeChild(todoListing.children[1]);
                }

            }

            function completedTodos(event) {

                let titleOfCompletedTodos = document.createElement("h1"),
                    noTodosPara = document.createElement("p");

                titleOfCompletedTodos.textContent = "Completed Todos";
                noTodosPara.textContent = "No pending tasks";

                if (completedTodosListing.childElementCount < 1) {
                    completedTodosListing.appendChild(titleOfCompletedTodos);
                }

                todoListing.removeChild(event.target.parentElement);
                completedTodosListing.appendChild(event.target.parentElement);
                event.target.parentElement.removeChild(event.target.parentElement.children[1]);

                if (todoListing.childElementCount < 2) {
                    todoListing.appendChild(noTodosPara);
                }

                if (completedTodosListing.children[1].textContent == "No completed tasks left") {
                    completedTodosListing.removeChild(completedTodosListing.children[1]);
                }
            }

            function deleteTodos(event) {
                try {
                    todoListing.removeChild(event.target.parentElement);
                }
                catch {
                    completedTodosListing.removeChild(event.target.parentElement);
                }

                let noCompletedTodosPara = document.createElement("p");
                
                noCompletedTodosPara.textContent = "No completed tasks left";

                if (completedTodosListing.childElementCount < 2) {
                    completedTodosListing.appendChild(noCompletedTodosPara);
                }

            }

        </script>
    </body>
    </html> 
}
```
### Demo of 3 can be found [here](https://mojeedkusimo.github.io/ekobits-mini-projects/event-exercise-part3-and-part4/part3.html)

## Part 4
Using localStorage, try to store your todos so that if you refresh the page you do not lose what you have added to the list! As a super bonus, try to also save todos that you have marked as complete!
### ans:
```html
{
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="initial-scale=1.0">
        <link rel="stylesheet" href="style.css">
        <title>Todo App with vanilla JS</title>
        <style>
            * {
                margin: 0;
                padding: 0;
                box-sizing: border-box;
            }

            h1 {
                margin: 30px 0px;
            }
            #pending-todos h1, #completed-todos h1 {
                margin-top: 30px;
                margin-bottom: 0;
            }

            .pending-todo span {
                margin-right: 30px;
            }
            p {
                color: red;
                font-style: italic;
            }

            #completed-todos span {
                color: green;
                text-decoration: line-through;
            }

            #pending-todos span {
                color: brown;
            }
            .delete-all {
                background-color: red;
                color: white;
            }
        </style>
    </head>
    <body>
        <main>
            <button id="clear-storage">Clear Storage</button>
            <section id="add-todos">
                <h1>Todo App with vanilla JS</h1>
                <form action="">
                    <input type="text" name="newTodo" id="newTodo">
                    <button type="submit" id="submit-todos">Add Todo</button>
                </form>
            </section>
            <section id="completed-todos">

            </section>
            <section id="pending-todos">

            </section>    
        </main>
        <script>
            let form = document.querySelector("form"),
            newTodo = document.querySelector("input"),
            clearStorage = document.querySelector("button#clear-storage"),
            actionOnButtonClick = "",
            pendingTodosList = document.querySelector("section#pending-todos"),
            completedTodosList = document.querySelector("section#completed-todos");

            form.addEventListener("submit", addTodo);
            clearStorage.addEventListener("click", function() {
                localStorage.clear();
                location.reload();
            });

            function addTodo(event) {
                event.preventDefault();
                if (newTodo.value === "") {
                    alert("Please enter a task!");
                } else {
                    localStorageQuery();
                    displayPendingTodoInDOM(newTodo.value);
                    newTodo.value = "";    
                }

                if (pendingTodosList.children[1] === undefined) {
                    console.log(getPendingTodosFromStorage());
                }
                else if (pendingTodosList.children[1].textContent === "No pending tasks") {
                    pendingTodosList.removeChild(pendingTodosList.children[1]);
                }
            }


            function localStorageQuery(event) {
                if (getPendingTodosFromStorage() === null) {
                    let pendingTodosArray = [];
                    setPendingTodosInStorage(pendingTodosArray, newTodo.value);

                } else if (newTodo.value !== "") {
                    let pendingTodosArray = getPendingTodosFromStorage();
                    setPendingTodosInStorage(pendingTodosArray, newTodo.value);

                } else if (actionOnButtonClick === "Completed a Todo") {
                    let markedCompletedTodo = event.target.parentElement.children[0].textContent;
                    let pendingTodosArray = getPendingTodosFromStorage();
                    updatedPendingTodosArray = pendingTodosArray.filter(function(todo) {
                        return markedCompletedTodo !== todo;
                    });

                    setPendingTodosInStorage(updatedPendingTodosArray);
                    console.log(getPendingTodosFromStorage());
                    if (getCompletedTodosFromStorage() === null) {
                        let completedTodosArray = [];
                        setCompletedTodosInStorage(completedTodosArray, markedCompletedTodo);
                    } else if (markedCompletedTodo !== "") {
                        let completedTodosArray = getCompletedTodosFromStorage();
                        setCompletedTodosInStorage(completedTodosArray, markedCompletedTodo);
                    }
                } else {
                    if ( actionOnButtonClick === "Delete from Pending Todos" ) {
                        let deletedTodo = event.target.parentElement.children[0].textContent;
                        let pendingTodosArray = getPendingTodosFromStorage();

                        updatedPendingTodosArray = pendingTodosArray.filter(function(todo) {
                            return deletedTodo !== todo;
                        });
                        setPendingTodosInStorage(updatedPendingTodosArray);

                    } else {
                        let deletedTodo = event.target.parentElement.children[0].textContent;
                        let completedTodosArray = getCompletedTodosFromStorage();

                        updatedCompletedTodosArray = completedTodosArray.filter(function(todo) {
                            return deletedTodo !== todo;
                        });
                        setCompletedTodosInStorage(updatedCompletedTodosArray);
                    }
                }

            }

            function getPendingTodosFromStorage() {
                return JSON.parse(localStorage.getItem("pendingTodosArray"));
            }

            function getCompletedTodosFromStorage() {
                return JSON.parse(localStorage.getItem("completedTodosArray"));
            }

            function setPendingTodosInStorage() {

                if (arguments.length < 2  ) {
                    localStorage.setItem("pendingTodosArray", JSON.stringify(arguments[0]));       
                } else {
                    arguments[0].push(arguments[1]);
                    localStorage.setItem("pendingTodosArray", JSON.stringify(arguments[0]));
                } 
            }

            function setCompletedTodosInStorage() {

                if (arguments.length < 2  ) {
                    localStorage.setItem("completedTodosArray", JSON.stringify(arguments[0]));       
                } else {
                    arguments[0].push(arguments[1]);
                    localStorage.setItem("completedTodosArray", JSON.stringify(arguments[0]));
                }
            }

            function displayPendingTodoInDOM(pendingTodo) {
                let [pendingTodoElem, pendingTodoSpan, titleOfPendingTodos, completedTodoButton] = elementFactory("div", "span", "h1", "button"),
                    deleteTodoButton = elementFactory("button");
                    completedTodoButton.addEventListener("click", completedTodos);
                    deleteTodoButton.addEventListener("click", deleteTodos);

                titleOfPendingTodos.textContent = "Pending Todos";
                pendingTodoSpan.textContent = pendingTodo;
                completedTodoButton.textContent = "Completed";
                deleteTodoButton.textContent = "Delete";

                if (pendingTodosList.childElementCount < 1) {
                    pendingTodosList.appendChild(titleOfPendingTodos);
                }

                pendingTodoElem.classList.add("pending-todo");
                pendingTodosList.appendChild(pendingTodoElem);
                pendingTodoElem.appendChild(pendingTodoSpan);
                pendingTodoElem.appendChild(completedTodoButton);
                pendingTodoElem.appendChild(deleteTodoButton);    
            }

            function elementFactory() {

                if (arguments.length < 2) {
                    return document.createElement(arguments[0]);
                }

                let factoryProducts = [];
                for (let elem of arguments) {
                    factoryProducts.push(document.createElement(elem));
                }
                return factoryProducts;
            }

            function completedTodos(event) {

                actionOnButtonClick = "Completed a Todo";
                localStorageQuery(event);
                displayCompletedTodosInDOM(event);

                if (completedTodosList.children[1].textContent == "No completed tasks left") {
                    completedTodosList.removeChild(completedTodosList.children[1]);
                }
            }


            function displayCompletedTodosInDOM(event) {
                let [titleOfCompletedTodos, noTodosPara, deleteAllCompletedTodosButton] = elementFactory("h1","p","button");

                titleOfCompletedTodos.textContent = "Completed Todos";
                noTodosPara.textContent = "No pending tasks";

                if (completedTodosList.childElementCount < 1) {
                    completedTodosList.appendChild(titleOfCompletedTodos);
                }

                pendingTodosList.removeChild(event.target.parentElement);
                completedTodosList.appendChild(event.target.parentElement);
                event.target.parentElement.removeChild(event.target.parentElement.children[1]);
            }

            function displayCompletedTodosFromStorageInDOM(completedTodo) {
                let [completedTodoElem, completedTodoSpan, titleOfCompletedTodos, deleteTodoButton] = elementFactory("div", "span", "h1", "button");

                deleteTodoButton.addEventListener("click", deleteTodos);

                titleOfCompletedTodos.textContent = "Completed Todos";
                completedTodoSpan.textContent = completedTodo;
                deleteTodoButton.textContent = "Delete";

                if (completedTodosList.childElementCount < 1) {
                    completedTodosList.appendChild(titleOfCompletedTodos);
                }

                completedTodoElem.classList.add("pending-todo");
                completedTodosList.appendChild(completedTodoElem);
                completedTodoElem.appendChild(completedTodoSpan);
                completedTodoElem.appendChild(deleteTodoButton);   
            }

            function deleteTodos(event) {

                try {
                    actionOnButtonClick = "Delete from Pending Todos";
                    pendingTodosList.removeChild(event.target.parentElement);
                    let noTodosPara = document.createElement("p");

                    noTodosPara.textContent = "No pending tasks";
                
                    if (pendingTodosList.childElementCount < 2) {
                        pendingTodosList.appendChild(noTodosPara);
                    }
                    localStorageQuery(event);
                }
                catch {
                    actionOnButtonClick = "Delete from Complete Todos";
                    completedTodosList.removeChild(event.target.parentElement);

                    let noCompletedTodosPara = document.createElement("p");

                    noCompletedTodosPara.textContent = "No completed tasks left";
                
                    if (completedTodosList.childElementCount < 2) {
                        completedTodosList.appendChild(noCompletedTodosPara);
                    }
                    localStorageQuery(event);
                }
            }
                
            if (getPendingTodosFromStorage() !== null ) {
                getPendingTodosFromStorage().forEach(function(pendingTodo) {
                    displayPendingTodoInDOM(pendingTodo);
                });
            }

            if (getCompletedTodosFromStorage() !== null ) {
                getCompletedTodosFromStorage().forEach(function(completedTodo) {
                    displayCompletedTodosFromStorageInDOM(completedTodo);
                });
            }
        </script>
    </body>
    </html>
}
```
### Demo of 4 can be found [here](https://mojeedkusimo.github.io/ekobits-mini-projects/event-exercise-part3-and-part4/part4.html)