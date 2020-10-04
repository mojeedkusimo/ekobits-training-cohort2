# { NESTED ARRAY EXERCISES. }
Write a function called rotate which takes an array and a number, and moves each element however many spaces the number is to the right. For the value at the end of the array, rotate should move it back to the beginning.

```javascript
{
    rotate([1,2,3], 1) // [3,1,2]
    rotate([1,2,3], 2) // [2,3,1]
    rotate([1,2,3], 3) // [1,2,3]
}
```
### ans:
```javascript
{
    // Accept two parameters, an array and a number
    // Initialize a variable to hold the newFirstElem
    // Store the elements after the newFirstElem of the array in a variable
    // Loop through the array
        // update the new array with elements of index less than the newFirstElem
    // return new array

    function rotate(array, number) {
        let newFirstElemIndex = array.length - number;
        let rotatedArr = array.slice(newFirstElemIndex,);
        for (let elem of array) {
            if (array.indexOf(elem) < newFirstElemIndex) {
                rotatedArr.push(elem);          
            }
        }
        return rotatedArr;
    }
}
```

Write a function called makeXOGrid which takes in two parameters, rows and columns, and returns an array of arrays with the number of values in each subarray equal to the columns parameter and the number of subarrays equal to the rows parameter. The values in the sub-arrays should switch between "X" and "O".

```javascript
{
    makeXOGrid(1,4) 

    /*/
    [["X","O","X","O"]]
    /*/

    makeXOGrid(3,2) 

    /*/
    [["X","O"],["X","O"],["X","O"]]
    /*/

    makeXOGrid(3,3) 
    /*/
    [["X","O","X"],["O","X","O"],["X","O","X"]]
    /*/
}
```
### ans:
```javascript
{
    // Accept two parameters, number of subarrays, number of elements in subarray
    // Initialize a gridArr
    // Populate the gridArr with the inputed number of subarrays
    // Populate subarrays with the number of X and O inputed

    function makeXOGrid(noOfSubArr, noOfSubElem) {
        let gridArr = [];
        for (let i = 0; i < noOfSubArr; i++ ) {
            gridArr.push([]);
            for (let j = 0; j < noOfSubElem; j++) {
                if (j % 2 === 0) {
                    gridArr[i].push("X");
                } else {
                gridArr[i].push("O");
                }
            }
        }
        return gridArr;
    }
}
```