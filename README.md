[calculator.html](https://github.com/user-attachments/files/30876921/calculator.html)


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Calculator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #d9c8f0; /* light purple background */
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }
    .calculator {
      background: #ffffff; /* white body */
      padding: 20px;
      border-radius: 15px;
      box-shadow: 0px 4px 15px rgba(0,0,0,0.2);
      text-align: center;
      width: 320px;
    }
    h1 {
      margin-bottom: 15px;
      color: #4a3c8c;
    }
    #display {
      width: 100%;
      height: 60px;
      font-size: 1.8em;
      text-align: right;
      margin-bottom: 20px;
      padding: 10px;
      border: none;
      background: #f9f9f9;
      border-radius: 10px;
    }
    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      grid-gap: 15px;
    }
    button {
      height: 60px;
      font-size: 1.2em;
      border: none;
      border-radius: 50%; /* circular buttons */
      background: #eceafc;
      cursor: pointer;
      transition: background 0.2s;
    }
    button:hover {
      background: #dcdaf5;
    }
    .equal {
      background: #ff7eb9; /* pink button */
  color: #fff;
  border-radius: 30px; /* pill shape instead of circle */
  grid-column: span 2; /* make it take 2 columns */
    }
  </style>
</head>
<body>
  <div class="calculator">
    <h1>Calculator</h1>
    <input type="text" id="display" disabled value="0">
    <div class="buttons">
      <button onclick="clr()">clr</button>
      <button onclick="del()">DEL</button>
      <button onclick="append('%')">%</button>
      <button onclick="append('/')">/</button>
      <button onclick="append('7')">7</button>
      <button onclick="append('8')">8</button>
      <button onclick="append('9')">9</button>
      <button onclick="append('*')">*</button>
      <button onclick="append('4')">4</button>
      <button onclick="append('5')">5</button>
      <button onclick="append('6')">6</button>
      <button onclick="append('-')">-</button>
      <button onclick="append('1')">1</button>
      <button onclick="append('2')">2</button>
      <button onclick="append('3')">3</button>
      <button onclick="append('+')">+</button>
      <button onclick="append('.')">.</button>
      <button onclick="append('0')">0</button>
      <button class="equal" onclick="calculate()">=</button>
    </div>
  </div>

  <script>
    let display = document.getElementById("display");

    function append(value) {
      if (display.value === "0" || display.value === "Error") {
        display.value = value;
      } else {
        display.value += value;
      }
    }

    function clr() {
      display.value = "0";
    }

    function del() {
      display.value = display.value.slice(0, -1);
      if (display.value === "") {
        display.value = "0";
      }
    }

    function calculate() {
      try {
        display.value = eval(display.value);
      } catch {
        display.value = "Error";
      }
    }
  </script>
</body>
</html>
