---
layout: base
title: Elliot's Home 
description: Home Page
hide: true
---

<h1>Welcome to my Homepage!</h1>

<p style="font-family: 'Times New Roman', sans-serif;">Here are some fun videos, songs, and more that are motivating or entertaining.</p>

<h2>Do you ever feel burnt out?</h2>
<p>
  There are many cases when students are tired with school and have no motivation to work.
  <br> There can be many reasons for this lack of motivation, such as not getting the grades they want, or maybe even trying to escape things like homework by spending time on social media.
  <br> In my personal case, I scroll on social media and waste a lot of time. 
  <br> However, every once in a while, I come across videos that remind me of the work that I need to do and help me get back on track.
  <br> Here's some encouragement and motivation.
</p>
<button onclick="window.open('https://www.youtube.com/watch?v=hTSZ-fDdF1Y', '_blank');">Here's some Motivation</button>

<h2>What should I listen to?</h2>
<p>Here's a playlist that I often listen to while studying or just chilling.</p>
<iframe style="border-radius:12px" src="https://open.spotify.com/embed/playlist/37i9dQZF1EIgKXhXqo61vc?utm_source=generator" width="70%" height="200" frameBorder="0" allowfullscreen="" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture" loading="lazy"></iframe>

<h2>Bored?</h2>
<body>
  When I'm bored, I often watch videos on YouTube. Most of the content that I watch are either informational; specifically for having healthier study habits and exercise, or about nature.</body>
<break>
  <a href="https://www.youtube.com/watch?v=zwrKUqFvi3A" target="_blank">Snorkeling at Night</a>
  |
  <a href="https://www.youtube.com/watch?v=vD-dEl7R2Bg" target="_blank">Excercise Tier List</a>
  |
  <a href="https://www.youtube.com/watch?v=_w2ZL0dJSZk" target="_blank">How to Manage time as a Student</a>

<div>
  <table>
    <tr>
      <td><a href="{{site.baseurl}}/hw1/">3.2</a></td>
      <td><a href="{{site.baseurl}}/hw2/">3.10</a></td>
      <td><a href="/Sprint2blog/">Sprint 2 Review Blog</a></td>
      
    </tr>
  </table>
</div>

<!-- Mario Running Animation -->
<img src="https://i.gifer.com/origin/ac/acf3abb6da430dd78cc99f925bb52d49_w200.webp" alt="Mario running" class="mario">

<style>
  body {
    margin: 0;
    overflow-x: hidden; /* Prevents horizontal scrolling */
  }
  .mario {
    position: fixed;
    top: 100%; /* Aligns Mario to the bottom of the screen */
    left: -200px; 
    transform: translateY(-100%); /* Keeps Mario visible just above the bottom edge */
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
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Subpage - Dropdown Project Links</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f9;
            margin: 20px;
            padding: 0;
        }
        h1 {
            color: #4CAF50;
        }
        .dropdown {
            position: relative;
            display: inline-block;
        }
        .dropdown button {
            background-color: #4CAF50;
            color: white;
            padding: 10px 20px;
            font-size: 16px;
            border: none;
            cursor: pointer;
        }
        .dropdown button:hover {
            background-color: #45a049;
        }
        .dropdown-content {
            display: none;
            position: absolute;
            background-color: #f9f9f9;
            min-width: 200px;
            box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.2);
            z-index: 1;
        }
        .dropdown-content a {
            background-color: #4CAF50;
            color: white;
            padding: 15px 30px;
            display: block;
            text-align: center;
            border-radius: 8px;
            margin-top: 20px;
            text-decoration: none;
        }
        .dropdown-content a:hover {
            background-color: #45a049;
        }
        .show {
            display: block;
        }
    </style>
</head>
<body>
    <h1>Subpages</h1>
    <!-- Dropdown Button -->
    <div class="dropdown">
        <button class="dropdown-button" onclick="toggleDropdown()">
            Games and Notebooks
        </button>
        <div class="dropdown-content" id="myDropdown">
            <a href="cookieclicker">Cookie Clicker</a>
            <a href="calculator">Binary Calculator</a>
            <a href="snakegame">Snake Game</a>
            <a href="notebook1">Notebook 1</a>
            <a href="notebook2">Notebook 2</a>
            <a href="notebook3">Notebook 3</a>
        </div>
    </div>
    <p><a href="index.html">Back to Index</a></p>
    <script>
        // Toggle between showing and hiding the dropdown content
        function toggleDropdown() {
            document.getElementById("myDropdown").classList.toggle("show");
        }
        // Close the dropdown if the user clicks outside of it
        window.onclick = function(event) {
            if (!event.target.matches('.dropdown-button')) {
                var dropdowns = document.getElementsByClassName("dropdown-content");
                for (var i = 0; i < dropdowns.length; i++) {
                    var openDropdown = dropdowns[i];
                    if (openDropdown.classList.contains('show')) {
                        openDropdown.classList.remove('show');
                    }
                }
            }
        }
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