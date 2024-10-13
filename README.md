<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Calculator</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div class="calculator">
    <input type="text" id="display" disabled>

    <div class="buttons">
      <button onclick="clearDisplay()">C</button>
      <button onclick="deleteLast()">DEL</button>
      <button onclick="appendToDisplay('/')">/</button>
      <button onclick="appendToDisplay('*')">*</button>

      <button onclick="appendToDisplay('7')">7</button>
      <button onclick="appendToDisplay('8')">8</button>
      <button onclick="appendToDisplay('9')">9</button>
      <button onclick="appendToDisplay('-')">-</button>

      <button onclick="appendToDisplay('4')">4</button>
      <button onclick="appendToDisplay('5')">5</button>
      <button onclick="appendToDisplay('6')">6</button>
      <button onclick="appendToDisplay('+')">+</button>

      <button onclick="appendToDisplay('1')">1</button>
      <button onclick="appendToDisplay('2')">2</button>
      <button onclick="appendToDisplay('3')">3</button>
      <button onclick="calculate()">=</button>

      <button onclick="appendToDisplay('0')" class="zero">0</button>
      <button onclick="appendToDisplay('.')">.</button>
    </div>
  </div>

  <script src="script.js"></script>
</body>
</html>

CSS (styles.css)

body {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: #f7f7f7;
  font-family: 'Arial', sans-serif;
}

.calculator {
  background-color: #fff;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
}

#display {
  width: 100%;
  height: 60px;
  font-size: 24px;
  text-align: right;
  padding: 10px;
  margin-bottom: 20px;
  border: none;
  background-color: #f0f0f0;
  border-radius: 5px;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}

button {
  padding: 20px;
  font-size: 18px;
  border: none;
  border-radius: 5px;
  background-color: #007BFF;
  color: white;
  cursor: pointer;
  transition: background-color 0.2s;
}

button:hover {
  background-color: #0056b3;
}

button.zero {
  grid-column: span 2;
}

button:active {
  background-color: #003f7f;
}

JavaScript (script.js)


function appendToDisplay(value) {
  document.getElementById("display").value += value;
}

function clearDisplay() {
  document.getElementById("display").value = "";
}

function deleteLast() {
  let currentDisplay = document.getElementById("display").value;
  document.getElementById("display").value = currentDisplay.slice(0, -1);
}

function calculate() {
  let currentDisplay = document.getElementById("display").value;
  if (currentDisplay) {
    document.getElementById("display").value = eval(currentDisplay);
  }
}
