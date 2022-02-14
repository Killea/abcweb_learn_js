```js
// run `npm install prompt-sync` in your bash
const prompt = require("prompt-sync")();
//
// get input from the user.
//

const emptyCell = "   ";
const vLine = " | ";
const hLine = "-";

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
console.log("Game start!");

/*
Index of the array
0 | 1 | 2
---------
3 | 4 | 5
---------
6 | 7 | 8 
*/

function checkWinner() {
  if (board[0] == board[1] && board[0] == board[2] && board[0] != emptyCell) {
    // 0 1 2
    console.log("Winner is:" + board[0]);
    process.exit(0);
  }

  if (board[3] == board[4] && board[3] == board[5] && board[3] != emptyCell) {
    // 3 4 5
    console.log("Winner is:" + board[3]);
    process.exit(0);
  }

  if (board[6] == board[7] && board[6] == board[8] && board[6] != emptyCell) {
    // 6 7 8
    console.log("Winner is:" + board[6]);
    process.exit(0);
  }

  if (board[0] == board[3] && board[0] == board[6] && board[0] != emptyCell) {
    // 0 3 6
    console.log("Winner is:" + board[0]);
    process.exit(0);
  }

  if (board[1] == board[4] && board[1] == board[7] && board[1] != emptyCell) {
    // 1 4 7
    console.log("Winner is:" + board[1]);
    process.exit(0);
  }

  if (board[2] == board[5] && board[2] == board[8] && board[2] != emptyCell) {
    // 2 5 8
    console.log("Winner is:" + board[2]);
    process.exit(0);
  }

  if (board[0] == board[4] && board[0] == board[8] && board[0] != emptyCell) {
    // 0 4 8
    console.log("Winner is:" + board[0]);
    process.exit(0);
  }

  if (board[2] == board[4] && board[2] == board[6] && board[2] != emptyCell) {
    // 2 4 6
    console.log("Winner is:" + board[2]);
    process.exit(0);
  }
}

function showBoard() {
  console.clear()
  console.log(board[0] + vLine + board[1] + vLine + board[2]);
  console.log(hLine.repeat(15));
  console.log(board[3] + vLine + board[4] + vLine + board[5]);
  console.log(hLine.repeat(15));
  console.log(board[6] + vLine + board[7] + vLine + board[8]);
  checkWinner();
}

function getRandomInt(max) {
  // get a random number: [0, max);  e.g.   if max = 5,  it will get a number from [0, 1, 2, 3, 4]
  // learn more about it: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random
  return Math.floor(Math.random() * max);
}

function userInput() {
  const turn = prompt("Your turn, please type a number:");
  board[turn - 1] = " o ";
}

function setBoardX(index) {
  // This is a Smart AI!
  if (board[index] == emptyCell) {
    board[index] = " x ";
    return;
  }
  if (index == 9) {
    setBoardX(0);
  } else {
    setBoardX(index + 1);
  }
}

showBoard();

userInput();
showBoard();


let computerTurn = getRandomInt(9);
setBoardX(computerTurn);
showBoard();

userInput();
showBoard();

computerTurn = getRandomInt(9);
setBoardX(computerTurn);
showBoard();

userInput();
showBoard();

computerTurn = getRandomInt(9);
setBoardX(computerTurn);
showBoard();

userInput();
showBoard();

computerTurn = getRandomInt(9);
setBoardX(computerTurn);
showBoard();

userInput();
showBoard();

```