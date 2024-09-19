--- 
layout: base
title: Snake
description: Play a version of snake
hide: false
---

<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Snake Game (Anaconda)</title>
  <style>
    body {
      background-color: black;
      color: white;
      font-family: Arial, sans-serif;
      text-align: center;
      margin: 0;
    }

    h1 {
      margin-top: 20px;
    }

    canvas {
      background-color: black;
      display: block;
      margin: 20px auto;
      border: 2px solid #fff;
    }

    .score {
      font-size: 24px;
    }

    /* Allow scrolling */
    body {
      overflow: auto;
    }
  </style>
</head>
<body>
  <h1>Snake Game - Anaconda Edition</h1>
  <canvas id="gameCanvas" width="600" height="600"></canvas>
  <p class="score">Score: <span id="score">0</span></p>

  <script>
    // Basic settings for the canvas and game
    const canvas = document.getElementById('gameCanvas');
    const ctx = canvas.getContext('2d');
    const gridSize = 60;  // Set grid size proportional to image size
    let score = 0;
    let growBy = 0; // To handle the power-up snake growth
    let powerupActive = false; // Track if powerup is active or not
    let powerupTimer; // Timer for powerup appearance

    // Load images for the snake (anaconda), watermelon, and power-up (rat)
    const snakeImg = new Image();
    snakeImg.src = "https://www.worldatlas.com/upload/a4/91/91/shutterstock-1708408498.jpg";  // Snake image

    const watermelonImg = new Image();
    watermelonImg.src = "https://www.kroger.com/product/images/large/top/0000000003421";  // Watermelon image

    const powerupImg = new Image();
    powerupImg.src = "https://www.flapest.com/wp-content/uploads/2021/02/norway-rat.jpg";  // Rat image as power-up

    // Snake object representing the anaconda
    const snake = {
      body: [  // Start with 3 segments
        { x: 180, y: 180 },
        { x: 120, y: 180 },
        { x: 60, y: 180 }
      ],
      direction: { x: gridSize, y: 0 },  // Moves to the right initially
      grow: false,  // Flag to check if the snake should grow
    };

    // Watermelon and power-up positions
    let watermelon = { x: 300, y: 300 };
    let powerup = null;  // Power-up starts off the screen

    // Function to generate a random position on the grid
    function randomPosition() {
      const x = Math.floor(Math.random() * (canvas.width / gridSize)) * gridSize;
      const y = Math.floor(Math.random() * (canvas.height / gridSize)) * gridSize;
      return { x, y };
    }

    // Function to spawn power-up 5 seconds after consuming the first watermelon or power-up
    function spawnPowerup() {
      powerupActive = true;
      powerup = randomPosition();  // Place power-up on the grid
    }

    // Function to draw the snake (anaconda) with a blue outline around the head
    function drawSnake() {
      snake.body.forEach((segment, index) => {
        if (index === 0) {
          ctx.strokeStyle = 'blue';  // Outline the head in blue
          ctx.lineWidth = 4;
          ctx.strokeRect(segment.x, segment.y, gridSize, gridSize);  // Blue outline
        }
        ctx.drawImage(snakeImg, segment.x, segment.y, gridSize, gridSize);  // Draw snake
      });
    }

    // Function to draw the watermelon using the watermelon image
    function drawWatermelon() {
      ctx.drawImage(watermelonImg, watermelon.x, watermelon.y, gridSize, gridSize);  // Draw larger watermelon
    }

    // Function to draw the power-up (rat)
    function drawPowerup() {
      if (powerupActive && powerup) {
        ctx.drawImage(powerupImg, powerup.x, powerup.y, gridSize, gridSize);  // Draw power-up image (rat)
      }
    }

    // Function to move the snake
    function moveSnake() {
      const newHead = {
        x: snake.body[0].x + snake.direction.x,
        y: snake.body[0].y + snake.direction.y
      };

      // Check if snake collides with walls (game over)
      if (newHead.x < 0 || newHead.x >= canvas.width || newHead.y < 0 || newHead.y >= canvas.height) {
        resetGame();  // Restart the game
        return;
      }

      // Check if snake collides with itself
      if (snake.body.some(segment => segment.x === newHead.x && segment.y === newHead.y)) {
        resetGame();
        return;
      }

      // Add the new head to the snake's body
      snake.body.unshift(newHead);

      // Check if the snake eats the watermelon
      if (newHead.x === watermelon.x && newHead.y === watermelon.y) {
        score++;
        document.getElementById('score').textContent = score;
        watermelon = randomPosition();  // Generate new watermelon position

        if (!powerupActive) {
          // Start the 5-second timer to spawn the power-up after the first watermelon is eaten
          powerupTimer = setTimeout(spawnPowerup, 5000);  // Spawn power-up after 5 seconds
        }
      } else if (powerup && newHead.x === powerup.x && newHead.y === powerup.y) {
        // Snake collects the power-up and grows by 3 segments
        growBy += 3;
        powerup = null;  // Remove power-up from the grid
        powerupActive = false;

        // Start the 5-second timer to spawn the next power-up
        powerupTimer = setTimeout(spawnPowerup, 5000);
      } else if (growBy > 0) {
        growBy--;
      } else {
        snake.body.pop();  // Remove the tail unless it grows
      }
    }

    // Reset the game when snake dies
    function resetGame() {
      snake.body = [  // Reset to a 3-segment snake
        { x: 180, y: 180 },
        { x: 120, y: 180 },
        { x: 60, y: 180 }
      ];
      snake.direction = { x: gridSize, y: 0 };
      score = 0;
      growBy = 0;  // Reset growth
      powerup = null;  // Reset power-up position
      powerupActive = false;
      document.getElementById('score').textContent = score;
      watermelon = randomPosition();  // Reset watermelon position
      clearTimeout(powerupTimer);  // Clear any existing power-up timers
    }

    // Function to update the game (main game loop)
    function update() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);  // Clear the canvas
      moveSnake();
      drawSnake();
      drawWatermelon();
      drawPowerup();
    }

    // Set the snake direction based on key input
    document.addEventListener('keydown', function (event) {
      // Prevent arrow keys from scrolling the page
      if (["ArrowUp", "ArrowDown", "ArrowLeft", "ArrowRight"].includes(event.key)) {
        event.preventDefault();
      }

      switch (event.key) {
        case 'ArrowUp':
          if (snake.direction.y === 0) snake.direction = { x: 0, y: -gridSize };
          break;
        case 'ArrowDown':
          if (snake.direction.y === 0) snake.direction = { x: 0, y: gridSize };
          break;
        case 'ArrowLeft':
          if (snake.direction.x === 0) snake.direction = { x: -gridSize, y: 0 };
          break;
        case 'ArrowRight':
          if (snake.direction.x === 0) snake.direction = { x: gridSize, y: 0 };
          break;
      }
    });

    // Run the game loop every 300ms (to make the snake slower)
    setInterval(update, 300);
  </script>
</body>
</html>
