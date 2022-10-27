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
