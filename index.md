---
layout: base
title: Student Home 
description: Home Page
hide: true
---

My journey starts here.
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mario Running</title>
  <style>
    body {
      margin: 0;
      overflow: hidden;
    }
    .mario {
      position: absolute;
      top: 50%;
      left: -200px; 
      transform: translateY(70%);
      width: 100px;
      animation: runAcross 5s linear infinite;
    }
    @keyframes runAcross {
      from {
        left: -200px; 
      }
      to {
        left: 100vw; 
      }
    }
  </style>
</head>
<body>
  <img src="https://i.gifer.com/origin/ac/acf3abb6da430dd78cc99f925bb52d49_w200.webp" alt="Mario running" class="mario">
</body>
</html>

