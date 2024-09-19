---
layout: base
title: CookieClicker
description: plan
hide: false
---
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Cookie Clicker Game</title>
  <style>
    body {
      text-align: center;
      font-family: Arial, sans-serif;
    }
    #cookie {
      width: 150px;
      cursor: pointer;
      margin: 20px;
    }
    #score {
      font-size: 24px;
    }
    #shop {
      margin-top: 20px;
    }
    .shop-item {
      margin: 10px;
      border: 1px solid black;
      padding: 10px;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <h1>Cookie Clicker Game</h1>
  <!-- Cookie Image -->
  <img id="cookie" src="https://bromabakery.com/wp-content/uploads/2022/05/Single-Serve-Double-Chocolate-Chip-Cookie-3.jpg" alt="Cookie" />
  <!-- Score Display -->
  <p id="score">Cookies: 0</p>
  <!-- Shop Section -->
  <div id="shop">
    <h2>Shop</h2>
    <div class="shop-item" id="worker">Buy Worker (Cost: 10 Cookies)</div>
    <div class="shop-item" id="click-upgrade">Click Upgrade (Cost: 20 Cookies)</div>
  </div>
  <!-- Audio for Click Sound -->
  <audio id="clickSound">
    <source src="click.mp3" type="audio/mpeg">
  </audio>
  <script>
    // JavaScript for Cookie Clicker Game
    let score = 0;
    let cookiesPerSecond = 0;
    let cookiesPerClick = 1;
    let workerCost = 10;
    let clickUpgradeCost = 20;
    // Update the score display
    function updateScore() {
      document.getElementById('score').innerText = `Cookies: ${score}`;
    }
    // Play click sound
    function playClickSound() {
      const clickSound = document.getElementById('clickSound');
      clickSound.play();
    }
    // Handle cookie click
    document.getElementById('cookie').addEventListener('click', function() {
      score += cookiesPerClick;
      updateScore();
      playClickSound();
    });
    // Shop - Buy a worker
    document.getElementById('worker').addEventListener('click', function() {
      if (score >= workerCost) {
        score -= workerCost;
        cookiesPerSecond += 1;
        workerCost = Math.floor(workerCost * 1.5);  // Increase cost for next worker
        updateScore();
        document.getElementById('worker').innerText = `Buy Worker (Cost: ${workerCost} Cookies)`;
      }
    });
    // Shop - Buy a click upgrade
    document.getElementById('click-upgrade').addEventListener('click', function() {
      if (score >= clickUpgradeCost) {
        score -= clickUpgradeCost;
        cookiesPerClick += 1;  // Increase the number of cookies per click
        clickUpgradeCost = Math.floor(clickUpgradeCost * 2);  // Increase cost for next upgrade
        updateScore();
        document.getElementById('click-upgrade').innerText = `Click Upgrade (Cost: ${clickUpgradeCost} Cookies)`;
      }
    });
    // Add cookies passively for workers
    setInterval(function() {
      score += cookiesPerSecond;
      updateScore();
    }, 1000);  // Increase cookies every second based on the number of workers
  </script>
</body>
</html>

<script src="https://utteranc.es/client.js"
        repo="Ellioty15/Elliot_2025"
        issue-term="pathname"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>