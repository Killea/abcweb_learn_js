Check the code: 

https://github.com/Killea/html-test0/blob/main/index.html

(1) how to change the label of a button

(2) how to call an API from a back-end



```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Tic tac toe</title>
    <link rel="stylesheet" href="ttt-style.css" />
  </head>
  <body>
   <h3>Tic tac toe</h3>
   <h4 id ="message"></h4>
    <div class="wrapper">
      <div class="cell" id="1" onclick="cellClick(1)">
      </div>

      <div class="cell" id="2" onclick="cellClick(2)">
      </div>
      <div class="cell" id="3" onclick="cellClick(3)">
      </div>

      <div class="cell" id="4" onclick="cellClick(4)">
      </div>

      <div class="cell" id="5" onclick="cellClick(5)">
      </div>

      <div class="cell" id="6" onclick="cellClick(6)">
      </div>

      <div class="cell" id="7" onclick="cellClick(7)">
      </div>

      <div class="cell" id="8" onclick="cellClick(8)">
      </div>

      <div class="cell" id="9" onclick="cellClick(9)">
      </div>
    </div>
    <script src="ttt-script.js" type="text/javascript"></script>
  </body>
</html>
```

ttt-style.css
```css  

.wrapper {
    display: grid;
    grid-template-columns:repeat(3,1fr);
    grid-template-rows: repeat(3,1fr);
    height: 80px;
    width: 80px;
    grid-gap: 1px;
    margin: auto;
}

.cell{
    text-align: center;
    background: rgb(23, 179, 226); 
}
```


```js
const emptyCell = "";
const board = [
  // 1st line
  emptyCell, // index 0
  emptyCell, // index 1
  emptyCell, // index 2
  // 2nd line
  emptyCell, // index 3
  emptyCell, // index 4
  emptyCell, // index 5
  // 3rd line
  emptyCell, // index 6
  emptyCell, // index 7
  emptyCell, // index 8
];

function checkWinner() {
  if (board[0] == board[1] && board[0] == board[2] && board[0] != emptyCell) {
    // 0 1 2
    alert("Winner is:" + board[0]);
  }

  if (board[3] == board[4] && board[3] == board[5] && board[3] != emptyCell) {
    // 3 4 5
    alert("Winner is:" + board[3]);
  }

  if (board[6] == board[7] && board[6] == board[8] && board[6] != emptyCell) {
    // 6 7 8
    alert("Winner is:" + board[6]);
  }

  if (board[0] == board[3] && board[0] == board[6] && board[0] != emptyCell) {
    // 0 3 6
    alert("Winner is:" + board[0]);
  }

  if (board[1] == board[4] && board[1] == board[7] && board[1] != emptyCell) {
    // 1 4 7
    alert("Winner is:" + board[1]);
  }

  if (board[2] == board[5] && board[2] == board[8] && board[2] != emptyCell) {
    // 2 5 8
    alert("Winner is:" + board[2]);
  }

  if (board[0] == board[4] && board[0] == board[8] && board[0] != emptyCell) {
    // 0 4 8
    alert("Winner is:" + board[0]);
  }

  if (board[2] == board[4] && board[2] == board[6] && board[2] != emptyCell) {
    // 2 4 6
    alert("Winner is:" + board[2]);
  }
}
function getRandomInt(max) {
  // get a random number: [0, max);  e.g.   if max = 5,  it will get a number from [0, 1, 2, 3, 4]
  // learn more about it: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random
  return Math.floor(Math.random() * max);
}

function setBoardX(index) {
  // This is a dummy AI
  if (board[index] == emptyCell) {
    board[index] = "x";
    const cell = document.getElementById(index + 1);
    cell.innerText = "❌";
    return;
  }
  if (index == 9) {
    setBoardX(0);
  } else {
    setBoardX(index + 1);
  }
  checkWinner();
}

function cellClick(index) {
  const cell = document.getElementById(index);
  cell.innerText = "⭕";
  board[index - 1] = "o";
  const computerMove = getRandomInt(9);
  setBoardX(computerMove);
  console.log(board);
  checkWinner();
}

function checkWinner() {
  let message;
  if (board[0] == board[1] && board[0] == board[2] && board[0] != emptyCell) {
    // 0 1 2
    message = "Winner is:" + board[0];
  }

  if (board[3] == board[4] && board[3] == board[5] && board[3] != emptyCell) {
    // 3 4 5
    message = "Winner is:" + board[3];
  }

  if (board[6] == board[7] && board[6] == board[8] && board[6] != emptyCell) {
    // 6 7 8
    message = "Winner is:" + board[6];
  }

  if (board[0] == board[3] && board[0] == board[6] && board[0] != emptyCell) {
    // 0 3 6
    message = "Winner is:" + board[0];
  }

  if (board[1] == board[4] && board[1] == board[7] && board[1] != emptyCell) {
    // 1 4 7
    message = "Winner is:" + board[1];
  }

  if (board[2] == board[5] && board[2] == board[8] && board[2] != emptyCell) {
    // 2 5 8
    message = "Winner is:" + board[2];
  }

  if (board[0] == board[4] && board[0] == board[8] && board[0] != emptyCell) {
    // 0 4 8
    message = "Winner is:" + board[0];
  }

  if (board[2] == board[4] && board[2] == board[6] && board[2] != emptyCell) {
    // 2 4 6
    message = "Winner is:" + board[2];
  }

  
  if ( message)
  {
    const cell = document.getElementById('message');
    cell.innerText = message;
  }
}
```