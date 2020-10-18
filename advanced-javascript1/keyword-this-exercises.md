# { KEYWORD "this" EXERCISES. }
Part 1

What is the value of the keyword this in the following example:

```javascript
{
    var data = this;
    console.log(data);
}
```

### ans: It is the window object



What does this function output? Why?

```javascript
{
    function logThis(){
        return this;
    }

    logThis(); // ?
}
```
### ans: It is the window object, this is because it is not located in any object thus takes the default global object (window object) as a result of the first rule.


What does this function output? Why?

```javascript
{
    var instructor = {
        firstName: 'Tim',
        sayHi: function(){
            console.log("Hello! " + this.firstName);
        }
    }

    instructor.sayHi() // ?
}
```
### ans: "Hello! Tim", this is because the nearest parent object it is used in is the "instructor" object (from rule 2 - implicit binding).


What does this function output? Why?

```javascript
{
    var instructor = {
        firstName: 'Tim',
        info: {
            catOwner: true,
            boatOwner: true
        },
        displayInfo: function(){
            console.log("Cat owner? " + this.catOwner);
        }
    }

    instructor.displayInfo() // ?
}
```
### ans: "Cat owner? undefined", this is because the this keyword is implicitly binded to the nearest parent object (i.e instructor object) which does not have a property "catOwner"


What does this function output? Why?

```javascript
{
    var instructor = {
        firstName: 'Tim',
        info: {
            catOwner: true,
            boatOwner: true,
            displayLocation: function(){
                return this.data.location;
            },
            data: {
                location: "Oakland"
            }
        },
    }

    instructor.info.displayLocation() // ?
}
```

What does this function output? Why?
### ans: "Oakland", this is because the this keyword is implicitly binded to the nearest parent object (i.e info object) whose data object can be accesible

```javascript
{
    var instructor = {
        firstName: 'Tim',
        info: {
            catOwner: true,
            boatOwner: true,
            displayLocation: function(){
                return this.location;
            },
            data: {
                location: "Oakland",
                logLocation: this.displayLocation
            }
        },
    }

    instructor.info.data.logLocation() // Why might we be getting an error her
}
```
### ans: "TypeError", this is because the this keyword in this context is implicitly binded to the data object since it is nearest parent object which does not have a displaLocation property.