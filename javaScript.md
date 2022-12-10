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

<h2>code to find most frequent number in array</h2>

```javascript
const arr = [1,2,5,3,5,7,3,4,2,5,6,5,2,5,5,5,7];
//code to find most frequent number in array

var mf = 1;
var m = 0;
var item;
for (var i=0; i<arr.length; i++)
{
        for (var j=i; j<arr.length; j++)
        {
                if (arr[i] == arr[j])
                 m++;
                if (mf<m)
                {
                  mf=m; 
                  item = arr[i];
                }
        }
        m=0;
}
console.log(item+" ( " +mf +" times ) ") ;
```



<h2>What is JavsScript</h2>
<p>JavaScript is a dynamic computer programming language. It is lightweight and most commonly used as a part of web pages, whose implementations allow client-side script to interact with the user and make dynamic pages. It is an interpreted programming language with object-oriented capabilities.</p>

<h2>Advantages of JS</h2>

<ul>
 <li>JavaScript is a lightweight, interpreted programming language.</li>
 <li>Designed for creating network-centric applications.</li>
 <li>Complementary to and integrated with Java.</li>
 <li>Complementary to and integrated with HTML.</li>
 <li>Open and cross-platform</li>
 <li>Immediate feedback to the visitors </li>
 <li>Increased interactivity</li>
 <li>Richer interfaces</li>
</ul>

<h2>What is JavaScript class</h2>
<p>JavaScript Class is not an Object it is Template for JavaScript object. When we have class we can use class to create JavaScript object</p>
<h4>Thats how we can construct class</h4>

```javascript
class car{
  constructor(name,year){
    this.name = name;
    this.year = year;
  }
}

//and thats how we can use classs to create JS Object 

const car1 = new car("ford",2014);
```


<h2>Ques 1 : == vs ===</h2>
<p>Both ==  and === will check for type. == will first do the type conversion if the type are not same and then it will start to compare them but in === there is no type conversion</p>

<h2>Ques 2 : comaparision</h2>

```javascript
let arrayOne = [1,2,3];
let arrayTwo = [1,2,3];
 console.log(arrayOne == arrayTwo); // false
 console.log(arrayOne === arrayTwo); // false  
 //both anuswer false because it checks its reference
```

 



