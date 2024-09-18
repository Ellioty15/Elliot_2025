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
  <title>Javascript Calculator</title>

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
  <footer class="site-footer">
    <div class="wrapper">
      <p>&copy; 2024 My Handy Calculator</p>
    </div>
  </footer>
</body>
</html>
