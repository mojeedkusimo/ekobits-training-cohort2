# { ES2015 EXERCISES. }

Convert the following es5 code blocks into es2015 code:

1. 
```javascript
{
    var person = {
        fullName: "Harry Potter",
        sayHi: function(){
            setTimeout(function(){
                console.log("Your name is " + this.fullName)
            }.bind(this),1000)
        }
    }
}
```

### ans:
```javascript
{
    let person = {
        fullName: "Harry Potter",
        sayHi() {
            setTimeout(() => {
                console.log(`Your name is ${this.fullName}`)
            },1000)
        }
    }
}
```

2. 
```javascript
{
    var name = "Josie"
    console.log("When " + name + " comes home, so good")
}
```

### ans:
```javascript
{
    let name = "Josie";
    console.log(`When ${name} comes home, so good`);
}
```

3. 
```javascript
{
    var DO_NOT_CHANGE = 42;
    DO_NOT_CHANGE = 50; // stop me from doing this
}
```

### ans:
```javascript
{
    const DO_NOT_CHANGE = 42;
}
```

```javascript
{
    var arr = [1,2]
    var temp = arr[0]
    arr[0] = arr[1]
    arr[1] = temp
}
```

### ans:
```javascript
{
    let arr1 = [1,2];
    let [firstNum, secondNum] = arr1;
    [firstNum, secondNum] = [secondNum, firstNum];
}
```

```javascript
{
    function double(arr){
        return arr.map(function(val){
            return val*2
        });
    }
}
```

### ans:
```javascript
{
    let double = arr => arr.map(val => val * 2);
}
```


```javascript
{
    var obj = {
        numbers: {
            a: 1,
            b: 2
        } 
    }

    var a = obj.numbers.a;
    var b = obj.numbers.b;
}
```


### ans:
```javascript
{
    let obj = {
        numbers: {
            a: 1,
            b: 2
        } 
    }

    let { numbers: { a, b } } = obj;
}
```

```javascript
{
    function add(a,b){
        if(a === 0) a = 0
        else {
            a = a || 10    
        }
        if(b === 0) b = 0
        else {
            b = b || 10    
        }
        return a+b
    }
}
```


### ans:
```javascript
{
    let add = ( a=10, b=10 ) => a + b;
}
```
