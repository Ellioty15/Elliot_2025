--- 
layout: base
title: Snake
description: Play a version of snake
hide: false
---

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Snake Game (Anaconda)</title>
  <style>
    body {
      background-color: #222;
      color: white;
      font-family: Arial, sans-serif;
      text-align: center;
    }

    h1 {
      margin-top: 20px;
    }

    canvas {
      background-color: #333;
      display: block;
      margin: 20px auto;
      border: 2px solid #fff;
    }

    .score {
      font-size: 24px;
    }
  </style>
</head>
<body>
  <h1>Snake Game - Anaconda Edition</h1>
  <canvas id="gameCanvas" width="400" height="400"></canvas>
  <p class="score">Score: <span id="score">0</span></p>

  <script>
    // Basic settings for the canvas and game
    const canvas = document.getElementById('gameCanvas');
    const ctx = canvas.getContext('2d');
    const gridSize = 20;  // Size of each grid square
    let score = 0;

    // Snake object representing the anaconda
    const snake = {
      body: [{ x: 100, y: 100 }],  // Initial position
      direction: { x: gridSize, y: 0 },  // Moves to the right initially
      grow: false,  // Flag to check if the snake should grow
    };

    // Watermelon position
    let watermelon = { x: 200, y: 200 };

    // Function to generate a random position for the watermelon
    function randomPosition() {
      const x = Math.floor(Math.random() * (canvas.width / gridSize)) * gridSize;
      const y = Math.floor(Math.random() * (canvas.height / gridSize)) * gridSize;
      return { x, y };
    }

    // Function to draw the snake (anaconda)
    function drawSnake() {
      ctx.fillStyle = '#4CAF50';  // Anaconda's green color
      snake.body.forEach(segment => {
        ctx.fillRect(segment.x, segment.y, gridSize, gridSize);
      });
    }

    // Function to draw the watermelon
    function drawWatermelon() {
      ctx.fillStyle = '#FF6347';  // Watermelon red color
      ctx.fillRect(watermelon.x, watermelon.y, gridSize, gridSize);
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
      } else {
        snake.body.pop();  // Remove the tail unless it grows
      }
    }

    // Reset the game when snake dies
    function resetGame() {
      snake.body = [{ x: 100, y: 100 }];
      snake.direction = { x: gridSize, y: 0 };
      score = 0;
      document.getElementById('score').textContent = score;
      watermelon = randomPosition();  // Reset watermelon position
    }

    // Function to update the game (main game loop)
    function update() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);  // Clear the canvas
      moveSnake();
      drawSnake();
      drawWatermelon();
    }

    // Set the snake direction based on key input
    document.addEventListener('keydown', function (event) {
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

    // Run the game loop every 100ms
    setInterval(update, 100);
  </script>
</body>
</html>
