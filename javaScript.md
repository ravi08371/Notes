<h1>JavaScript Notes</h1>

<h2>code for chess board using JS</h2>

```javascript
 var center = document.createElement('center');
 
        var ChessTable = document.createElement('table');
        for (var i = 0; i < 8; i++) {
            var tr = document.createElement('tr');
            for (var j = 0; j < 8; j++) {
                var td = document.createElement('td');
                // If the sum of cell coordinates is even
                // then color the cell white
                if ((i + j) % 2 == 0) {
                    // Create a class attribute for all white cells
                    td.setAttribute('class', 'cell whitecell');
                    tr.appendChild(td);
             }// If the sum of cell coordinates is odd thencolor the cell black
                else {
                    // Create a class attribute for all black cells
                    td.setAttribute('class', 'cell blackcell');
                    // Append the cell to its row
                    tr.appendChild(td);
                }
            }
            ChessTable.appendChild(tr);
        }
        center.appendChild(ChessTable);
        ChessTable.setAttribute('cellspacing', '0');
        ChessTable.setAttribute('width', '270px');
        document.body.appendChild(center);
 ```
 
 
 <h2>What is Synchronous and Asynchronous code</h2>
 <p><b>Synchronous: </b>ynchronous code runs in sequence. This means that each operation must wait for the previous one to complete before executing.</p>
 
 ```javascript
 console.log('One');
console.log('Two');
console.log('Three');
// LOGS: 'One', 'Two', 'Three'
```
<p><b>Asynchronous: </b>Asynchronous code runs in parallel. This means that an operation can occur while another one is still being processed.</p>

```javascript
console.log('One');
setTimeout(() => console.log('Two'), 100);
console.log('Three');
// LOGS: 'One', 'Three', 'Two'
```

<h2>Hoisting</h2>
<p>JavaScript Hoisting refers to the process whereby the interpreter appears to move the declaration of functions, variables or classes to the top of their scope, prior to execution of the code.</p>

<h2>Closure</h2>
<p>A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment). In other words, a closure gives you access to an outer function's scope from an inner function.</p>

<h2>Primitive data types</h2>
<p> The predefined data types provided by JavaScript language are known as primitive data types. Primitive data types are also known as in-built data types.</p>

<h2>Non-primitive data types</h2>
<p>The data types that are derived from primitive data types of the JavaScript language are known as non-primitive data types. It is also known as derived data types or reference data types.</p>

<h2>Currying</h2>
<p>Currying simply means evaluating functions with multiple arguments and decomposing them into a sequence of functions with a single argument.</p>

```javascript
Noncurried version//
const add = (a, b, c)=>{
    return a+ b + c
}
console.log(add(2, 3, 5)) // 10

Curried version//
const addCurry =(a) => {
    return (b)=>{
        return (c)=>{
            return a+b+c
        }
    }
}
console.log(addCurry(2)(3)(5)) // 10
```


















