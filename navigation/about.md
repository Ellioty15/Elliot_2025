---
layout: page
title: About
permalink: /about/
---

<button onclick="window.location.href='http://127.0.0.1:4100/elliot_2025/';">
  Go back Home
</button>

<body>
  <h1>Who am I?</h1>
  <p>
    My name is Elliot.<br>
    I am 16 years old, and I am currently a junior (11th grade) at Del Norte High School. 
    My favorite color is purple, and my favorite subjects in school are STEM related.
  </p>

  <!-- Container for iframes with flexbox to align them side by side -->
  <div style="display: flex; gap: 20px;">
    <iframe src="https://drive.google.com/file/d/12tmknhCUo937JAZRRmsLIIToEcfTuSOW/preview" 
            width="320" height="240" allow="autoplay"></iframe>
    <iframe src="https://drive.google.com/file/d/1rnNbTv1WR5XN2diFMqgKqEqz4H6tyzo1/preview" 
            width="320" height="240" allow="autoplay"></iframe>
  </div>

  <h3>My Identity</h3>
  <ul>
    <li>I am the oldest of 5 brothers and I am Korean American.</li>
    <li>I was born in the United States, but both of my parents are from Korea.</li>
    <li>I am Christian.</li>
  </ul>

  <!-- Flex container for images -->
  <div style="display: flex; gap: 20px;">
    <!-- South Korean Flag -->
    <div class="image-container">
      <img src="https://upload.wikimedia.org/wikipedia/commons/0/09/Flag_of_South_Korea.svg" 
           alt="South Korean Flag" class="resized-image" style="width: 200px; height: auto;">
    </div>
    <!-- Christian Cross -->
    <div class="image-container">
      <img src="https://www.shutterstock.com/image-vector/christian-cross-vector-260nw-1154133316.jpg" 
           alt="Cross" class="resized-image" style="width: 200px; height: 180px;">
    </div>
  </div>

  <h3>My Values</h3>
  <ul>
    <li>I value responsibility and accountability.</li>
    <li>I dislike it when people lie, and I try to be as genuine as I can when I talk to people.</li>
    <li>I believe that in whatever I do, I should put as much effort as I can and take all the opportunities that I can get.</li>
  </ul>

  <h3>My Hobbies and Interests</h3>
  <ul>
    <li>🏌️I have been playing golf since I was very young, and I also play on the Del Norte Varsity Golf Team.</li>
    <li>🎵 I have been playing cello for around 8 years, and I have been in multiple groups inside and outside of our school.</li>
    <li>🎸I have also been learning to play guitar for around a year.</li>
    <li>🎤My favorite genre of music is always changing, but I enjoy listening to Hip Hop and Pop.</li>
    <li>🏋️I enjoy going to the gym and have been going consistently for around 2 months, looking forward to the results to come.</li>
    <li>🚗I want to learn to drive.</li>
    <li>👨‍💻I want to learn to code.</li>
    <li>🧜🏼‍♂️For college, I want to stay in San Diego.</li>
  </ul>

  <style>
    .image-container {
      width: 200px;
      height: auto;
    }
    .resized-image {
      width: 100%;
      height: auto;
      object-fit: cover;
      object-position: center;
    }
  </style>
</body>
