---
layout: base
title: Calculator
description: Elliot Yang's Calculator
hide: false
---
<html lang='en'>
<head>
  <meta charset="utf-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Javascript Calculator, Binary Calculator</title>

  <meta name="description" content="A common way to become familiar with a language is to build a calculator. This calculator shows off button with actions." />
  <!-- Include CSS for styling -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/Primer/15.2.0/primer.css" integrity="sha512-xTz2ys4coGAOz8vuV1NcQBkgVmKhsSEtjbqyMJbBHRplFuvKIUo6xhLHpAyPt9mfR6twHJgn9OgVLuqOvjeBhg==" crossorigin="anonymous" />
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.14.0/css/all.min.css" integrity="sha512-1PKOgIY59xJ8Co8+NE6FZ+LOAZKjy+KY8iq0G4B3CyeY6wYHN3yt9PW0XpSriVlkMXe40PTKnXrLnZ9+fkDaog==" crossorigin="anonymous" />
  <style>
    body {
      background-color: #2B2B2B; /* Dark background to mimic calculator case */
      font-family: Arial, sans-serif;
      color: white;
    }

    .calculator-container {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      grid-gap: 10px;
      padding: 20px;
      background-color: #000000; /* Dark background for calculator body */
      border-radius: 15px;
      width: 300px;
      margin: 100px auto;
      border: 5px solid #333; /* To simulate calculator edges */
    }

    .calculator-output {
      grid-column: span 4;
      background-color: #333; /* Dark gray for the display */
      color: #00FF00; /* Green digits */
      border-radius: 10px;
      padding: 0.25em;
      font-size: 28px;
      text-align: right;
      padding-right: 15px;
      border: 2px solid #555; /* Frame around the display */
    }

    .calculator-number, .calculator-operation, .calculator-clear, .calculator-equals {
      background-color: #f2f2f2; /* Light gray for buttons */
      color: black;
      border-radius: 5px;
      padding: 20px;
      font-size: 18px;
      text-align: center;
      border: 1px solid #999; /* Slight border for buttons */
      cursor: pointer;
    }

    .calculator-operation, .calculator-clear, .calculator-equals {
      background-color: #FFA500; /* Orange buttons for operations like on TI calculators */
    }

    .calculator-number:hover, .calculator-operation:hover, .calculator-clear:hover, .calculator-equals:hover {
      background-color: #e0e0e0; /* Hover effect on buttons */
    }
  </style>
</head>
<body>
  <main class="page-content" aria-label="Content">
    <div class="wrapper">
      <article class="post">
       <u><h1>Javascript Calculator</h1></u>
        <div id="animation">
          <div class="calculator-container">
            <div class="calculator-output" id="output">0</div>
            <div class="calculator-number">1</div>
            <div class="calculator-number">2</div>
            <div class="calculator-number">3</div>
            <div class="calculator-operation">+</div>
            <div class="calculator-number">4</div>
            <div class="calculator-number">5</div>
            <div class="calculator-number">6</div>
            <div class="calculator-operation">-</div>
            <div class="calculator-number">7</div>
            <div class="calculator-number">8</div>
            <div class="calculator-number">9</div>
            <div class="calculator-operation">*</div>
            <div class="calculator-clear">A/C</div>
            <div class="calculator-number">0</div>
            <div class="calculator-number">.</div>
            <div class="calculator-operation">/</div> <!-- Added the division operation -->
            <div class="calculator-equals">=</div>
          </div>
        </div>

        <!-- JavaScript Logic -->
        <script>
          let firstNumber = null;
          let operator = null;
          let nextReady = true;
          const output = document.getElementById("output");

          const numbers = document.querySelectorAll(".calculator-number");
          const operations = document.querySelectorAll(".calculator-operation");
          const clear = document.querySelectorAll(".calculator-clear");
          const equals = document.querySelectorAll(".calculator-equals");

          numbers.forEach(button => {
            button.addEventListener("click", function() {
              number(button.textContent);
            });
          });

          function number(value) {
            if (nextReady) {
              output.innerHTML = value;
              nextReady = false;
            } else {
              if (!(output.innerHTML === "0" && value === "0")) {
                output.innerHTML += value;
              }
            }
          }

          operations.forEach(button => {
            button.addEventListener("click", function() {
              operation(button.textContent);
            });
          });

          function operation(choice) {
            if (firstNumber === null) {
              firstNumber = parseFloat(output.innerHTML);
            } else if (!nextReady) {
              firstNumber = calculate(firstNumber, parseFloat(output.innerHTML), operator);
              output.innerHTML = firstNumber.toString();
            }
            operator = choice;
            nextReady = true;
          }

          function calculate(first, second, operator) {
            switch (operator) {
              case "+":
                return first + second;
              case "-":
                return first - second;
              case "*":
                return first * second;
              case "/":
                return second !== 0 ? first / second : "Error"; // Prevent division by zero
              default:
                return second;
            }
          }

          equals.forEach(button => {
            button.addEventListener("click", function() {
              equal();
            });
          });

          function equal() {
            if (firstNumber !== null && operator !== null) {
              const secondNumber = parseFloat(output.innerHTML);
              const result = calculate(firstNumber, secondNumber, operator);
              output.innerHTML = result;
              firstNumber = null; // Reset for next calculation
              operator = null;
              nextReady = true;
            }
          }

          clear.forEach(button => {
            button.addEventListener("click", function() {
              clearCalc();
            });
          });

          function clearCalc() {
            firstNumber = null;
            operator = null;
            output.innerHTML = "0";
            nextReady = true;
          }
        </script>
      </article>
    </div>
  </main>
</body>
</html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Binary Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }
        .calculator {
            display: inline-block;
            margin-top: 20px;
        }
        .binary-display {
            margin: 20px 0;
            font-size: 24px;
        }
        .controls {
            margin: 10px;
        }
        .color-display {
            width: 100px;
            height: 100px;
            margin: 20px auto;
            border: 1px solid #000;
        }
    </style>
</head>
<body>
    <h1>Binary Calculator</h1>
    <div class="calculator">
        <!-- Binary Manipulation Section 1 -->
        <div>
            <h2>Binary Section 1</h2>
            <div class="binary-display" id="binary1">00000000</div>
            <div class="controls">
                <button onclick="addBinary(1)">Add 1</button>
                <button onclick="subtractBinary(1)">Subtract 1</button>
            </div>
        </div>

        <!-- Binary Manipulation Section 2 -->
        <div>
            <h2>Binary Section 2</h2>
            <div class="binary-display" id="binary2">00000000</div>
            <div class="controls">
                <button onclick="addBinary(2)">Add 1</button>
                <button onclick="subtractBinary(2)">Subtract 1</button>
            </div>
        </div>

        <!-- Binary Manipulation Section 3 -->
        <div>
            <h2>Binary Section 3</h2>
            <div class="binary-display" id="binary3">00000000</div>
            <div class="controls">
                <button onclick="addBinary(3)">Add 1</button>
                <button onclick="subtractBinary(3)">Subtract 1</button>
            </div>
        </div>

        <!-- RGB Color Display -->
        <h2>Color Display (RGB)</h2>
        <div class="color-display" id="colorDisplay"></div>
    </div>

    <script>
        // Initialize values for each binary section (8-bit binary max 255, min 0)
        let binaryValues = [0, 0, 0]; // Holds values for binary1, binary2, binary3

        // Function to update the binary display and color
        function updateDisplay() {
            document.getElementById('binary1').textContent = decimalToBinary(binaryValues[0]);
            document.getElementById('binary2').textContent = decimalToBinary(binaryValues[1]);
            document.getElementById('binary3').textContent = decimalToBinary(binaryValues[2]);

            // Update RGB color display based on the binary values
            document.getElementById('colorDisplay').style.backgroundColor = `rgb(${binaryValues[0]}, ${binaryValues[1]}, ${binaryValues[2]})`;
        }

        // Function to convert a decimal value to 8-bit binary (padding with zeros)
        function decimalToBinary(decimal) {
            return ('00000000' + decimal.toString(2)).slice(-8);
        }

        // Function to add 1 to the binary value (with overflow check)
        function addBinary(section) {
            if (binaryValues[section - 1] < 255) {
                binaryValues[section - 1]++;
            } else {
                binaryValues[section - 1] = 0; // Reset to 0 on overflow
            }
            updateDisplay();
        }

        // Function to subtract 1 from the binary value (with underflow check)
        function subtractBinary(section) {
            if (binaryValues[section - 1] > 0) {
                binaryValues[section - 1]--;
            } else {
                binaryValues[section - 1] = 255; // Reset to 255 on underflow
            }
            updateDisplay();
        }

        // Initial display update
        updateDisplay();
    </script>
</body>
</html>
