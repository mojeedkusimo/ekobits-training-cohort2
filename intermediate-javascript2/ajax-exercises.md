# { AJAX EXERCISES. }

It's time to build something fun with your knowledge of jQuery and AJAX! For this exercise we will be using the Giphy API! This will require you to use an API key and understand some of the documentation about the API, which you can see here.

Here is what the URL would look like for search term of "hilarious" - http://api.giphy.com/v1/gifs/search?q=hilarious&api_key=dc6zaTOxFJmzC. You can click on this URL and see the JSON you will get back. To view this in a nicer format, we highly recommend using the JSON Viewer chrome extension.

Your application should do the following:

Allow the user to search for a GIF and when the form is submitted, make an AJAX request to the Giphy API and return a single GIF
Once the Giphy API has responded with data, append the GIF to the page
Allow the user to search for as many GIFs as they would like and keep appending them to the page
Allow the user to remove all of the GIFs by clicking a button
Here is an example of what the application might look like:

https://gyazo.com/f1a248f4f04e1ab5d747f4ff84264176



### ans:
```html
{
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="initial-scale=1.0">
        <title>Gif Display App with vanilla JS</title>
        <style>
            * {
                margin: 0;
                padding: 0;
                box-sizing: border-box;
            }

            #delete-gifs {
                background-color: red;
                color: white;
            }

            #gif-displays .gifs{
                margin-right: 5px;
                margin-top: 20px;
            }

            #gif-displays {
                display: flex;
                flex-wrap: wrap;
            }
        </style>
    </head>
    <body>
        <main>
            <section id="search-section">
                <h1>Gif Display App with vanilla JS</h1>
                <form action="">
                    <input type="text" name="searchInput" id="searchInput">
                    <button type="submit" id="submit-search">Search Expression</button>
                </form>
                <button type="submit" id="delete-gifs">Delete All Gifs</button>
            </section>
        </main>
        <script>
            let form = document.querySelector("form"),
                newGifPhrase = document.querySelector("input"),
                mainDiv = document.querySelector("main"),
                deleteAllgGifsButton = document.querySelector("#delete-gifs");

            form.addEventListener("submit", getGif);
            deleteAllgGifsButton.addEventListener("click", deleteAll);

            function getGif(e) {
                e.preventDefault();
                let XHR = new XMLHttpRequest();
                if (newGifPhrase.value === "") {
                    alert("Please enter an expression");
                } else {
                    XHR.onreadystatechange = function() {
                        if (XHR.readyState === 4 && XHR.status === 200) {

                            let responseObj = JSON.parse(XHR.responseText);
                            if (responseObj.data.length < 1) {
                                alert("Unable to fetch gif, Please enter another expression");
                            } else {
                                let randomNum = Math.floor(Math.random() * 50);
                                let gifSource = responseObj.data[randomNum].images.original.url;
                                displayGifInDOM(newGifPhrase.value, gifSource);
                                console.log(responseObj);
                            }
                        }
                    };
                    XHR.open("GET", `http://api.giphy.com/v1/gifs/search?q=${newGifPhrase.value}&api_key=guHXsN0bwpEyzbxRosmqk04IhcPpjI7k`);
                    XHR.send();    
                }
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

            function displayGifInDOM(phrase, image) {

                let [gifSecElem, gifDivElem, gifImageElem] = elementFactory("section", "div", "img");

                gifSecElem.setAttribute("id", "gif-displays");

                if (mainDiv.childElementCount < 2) {
                    mainDiv.appendChild(gifSecElem);
                }
                    gifDivElem.classList.add("gifs");
                    mainDiv.children[1].appendChild(gifDivElem);
                    gifImageElem.setAttribute("alt", `${phrase}`);
                    gifImageElem.setAttribute("src", `${image}`);
                    gifImageElem.setAttribute("height", `200px`);
                    gifImageElem.setAttribute("width", `200px`);
                    gifDivElem.appendChild(gifImageElem);


            }

            function deleteAll() {
                if (mainDiv.childElementCount > 1) {
                    mainDiv.removeChild(mainDiv.children[1]);
                }
            }
        </script>
    </body>
    </html>
}
```