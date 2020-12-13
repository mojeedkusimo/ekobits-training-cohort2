# { EXPRESS.JS EXERCISES. }

For this exercise we will be building a simple application where we will store a shopping list. You should use an array to store your items in the shopping list.

Our application should have the following routes:

1. GET /items - this should respond with a list of shopping items.

2. POST /items - this route should accept form data and add it to the shopping list.

3. GET /items/:id - this route should display a single item's name and price.

4. PATCH /items/:id - this route should accept edits to existing items.

5. DELETE /items/:id - this route should allow you to delete a specific item from the array.

### main.js

```javascript
{

    const express = require("express");
    const app = express();
    const bodyParser = require("body-parser");
    const appRoutes = require("./router");


    app.use(bodyParser.json());

    app.get("/", (req, res) => {
        res.send("Welcome to XYZ Shop!");
    });

    app.use("/items", appRoutes);

    app.listen(5000, () => {
        console.log("Server running on port 5000");
    });

}
```

### router.js

```javascript
{

    const express = require("express");
    const router = express.Router();

    let shoppingItems = [];
    let id = 0;

    router
        .route("/")
        .get((req, res) => {
            res.json(shoppingItems);
        })
        .post((req, res) => {
            const name = req.body.name;
            const price = req.body.price;
            shoppingItems.push({
                id: ++id,
                name,
                price
            });

            res.json({
                message: "Item was added successfully"
            })
        })

    router
        .route("/:id")
        .get((req, res) => {
            const item = shoppingItems.find(item => item.id === Number(req.params.id));
            res.json(item);
        })
        .patch((req, res) => {
            let item = shoppingItems.find(item => item.id === Number(req.params.id));
            item.name = req.body.name;

            res.json({
                message: "Item was updated successfully"
            });
        })
        .delete((req, res) => {
            const itemIndex = shoppingItems.findIndex(item => item.id === Number(req.params.id));
            shoppingItems.splice(itemIndex, 1);

            res.json({
                message: "Item was deleted successfully"
            });

        })

    module.exports = router;
    
}
```