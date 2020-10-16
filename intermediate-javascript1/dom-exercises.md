# { DOM EXERCISES. }

Given the following HTML:

```html
{
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Document</title>
    </head>
    <body>
        <div class="header">
        </div>
        <section id="container">
            <ul>
                <li class="first">one</li>
                <li class="second">two</li>
                <li class="third">three</li>
            </ul>
            <ol>
                <li class="first">one</li>
                <li class="second">two</li>
                <li class="third">three</li>
            </ol>
        </section>
        <div class="footer">
        </div>
    </body>
    </html>
}
```

Write the code necessary to do the following:

1. Select the section with an id of container without using querySelector.
### ans:
```javascript
{
    document.getElementById("container");
}
```

2. Select the section with an id of container using querySelector.
### ans:
```javascript
{
    document.querySelector("#container");
}
```

3. Select all of the list items with a class of "second".
### ans:
```javascript
{
    document.querySelectorAll(".second");
}
```

4. Select a list item with a class of third, but only the list item inside of the ol tag.
### ans:
```javascript
{
    document.querySelector("ol li.third");
}
```

5. Give the section with an id of container the text "Hello!".
### ans:
```javascript
{
    document.querySelector("#container").textContent = "Hello!";
}
```

6. Add the class main to the div with a class of footer.
### ans:
```javascript
{
    document.querySelector(".footer").classList.add("main");
}
```

7. Remove the class main on the div with a class of footer.
### ans:
```javascript
{
    document.querySelector(".footer").classList.remove("main");
}
```

8. Create a new li element.
### ans:
```javascript
{
    let newList = document.createElement("li");
}
```

9. Give the li the text "four".
### ans:
```javascript
{
    newList.textContent = "four";
}
```

10. Append the li to the ul element.
### ans:
```javascript
{
    document.querySelector("ul").appendChild(newList);
}
```

11. Loop over all of the lis inside the ol tag and give them a background color of "green".
### ans:
```javascript
{
    let oLists = document.querySelectorAll("ol li");

    for (let list of oLists) {
        list.style["background-color"] = "green";   
    }
}
```

12. Remove the div with a class of footer.
### ans:
```javascript
{
    let footer = document.querySelector(".footer");
    document.querySelector("body").removeChild(footer);
}
```
