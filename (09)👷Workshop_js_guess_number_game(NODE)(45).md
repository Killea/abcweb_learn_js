
# Workshop Guess Number Game

[<- Home](README.md)

Let's review this code:
```js
let sum = 0; // define a variable - sum, to store the sum

for (let i = 0; i <= 1000; i++) {
  // console log to show what the 'sum', 'i', 'sum+i' is in each loop (this is only for debugging)
  console.log(sum, i, sum + i);

  // each time we add the previous value 'sum' and the current value 'i', to get a sum
  // new_sum equals to the previous_sum plus the current_i
  sum = sum + i;
  
  if (sum > 400) {
    // when sum is bigger than 400, stop the loop.
    break;
  }
}

// output the result
console.log(sum);
```


🎮Also, In this lesson, we will try to develop a simple game and review ```loop``` and ```if condition```.


try create a folder, such as ```guess_number_game```  or ```gn```

then go to this folder to open vs code.

Then run 

```bash
npm install prompt-sync
```

ℹ️What is npm?
These are libraries built by the **awesome** community which will solve most of your generic problems. npm (Node package manager) has packages you can use in your apps to make your development faster and efficient.



```js
// workshop9.js or gn.js
// npm install prompt-sync
const terminal = require('prompt-sync')();

const randomNumber = Math.round(Math.random() * 11);  // generate a random number between 0 and 10, less than 11
let lives = 5;

while (true) {
    const answer = terminal("Guess the number! (0-10): ");


    let answerNum = parseInt(answer);

    if (answerNum > randomNumber) {
        console.log('Too high!😭');
        console.log('You have ' + lives + ' lives left');
    }

    else if (answerNum < randomNumber) {
        console.log('Too low!😭');
        console.log('You have ' + lives + ' lives left');
    }

    else if (answerNum === randomNumber) {
        console.log('W I N N E R !🏆');
        // bug ? why? how to fix?   hint: what if I didn't lose any lives?
        console.log('You lost only ' + (5 - lives) + ' lives');
        process.exit(0);
    }

    else {
        console.log("That wasn't a number I recognize");
        console.log('You have ' + lives + ' lives');
    }

    lives = lives -1;
    if (lives == 0) {
        console.log('G A M E  O V E R ! ! !');
        process.exit(0);
    }
}
```