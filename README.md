# Interactive-Box-movement-using-JS
This project demonstrates a simple interactive box movement using JavaScript. The box changes its position based on arrow key inputs and updates its appearance when keys are pressed and released.

## Features
- Move the box using arrow keys (Up, Down, Left, Right).
- Change the box's background color and emoji when keys are pressed and released.

## Code Explanation
```javascript
const myBox = document.getElementById('myBox');

const moveAmount = 10;
let x = 0;
let y = 0;

document.addEventListener("keydown", event => {
    myBox.style.backgroundColor = "tomato";
    myBox.textContent = "😲";
});

document.addEventListener("keyup", event => {
    myBox.style.backgroundColor = "lightBlue";
    myBox.textContent = "😄";
});

document.addEventListener("keydown", event => {
    if(event.key.startsWith("Arrow")){

        event.preventDefault();

        switch(event.key){
            case "ArrowUp":
                y -= moveAmount;
                break;
            case "ArrowDown":
                y += moveAmount;
                break;
            case "ArrowLeft":
                x -= moveAmount;
                break;
            case "ArrowRight":
                x +=moveAmount;
                break;
        }

        myBox.style.top = `${y}px`;
        myBox.style.left = `${x}px`;
    }
});
