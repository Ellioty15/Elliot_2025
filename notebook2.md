---
layout: base
title: About
description: Golf Jokes
hide: false
---

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript Golf Joke Shell</title>
</head>
<body>
    <h1>JavaScript Golf Joke Shell</h1>
    <p>This shell lets you run some golf jokes using JavaScript. Click the button below to show a random joke about golf.</p>

    <!-- Display joke here -->
    <p id="jokeDisplay"></p>

    <!-- Button to trigger a new joke -->
    <button onclick="tellGolfJoke()">Tell a Golf Joke!</button>

    <script>
        // Array of golf jokes
        let golfJokes = [
          "Why did the golfer bring two pairs of pants? In case he got a hole in one!",
          "Golf is a lot like taxes: you drive hard to get to the green and then wind up in the hole.",
          "Why do golfers always bring an extra pair of socks? Because they might get a hole in one.",
          "What’s a golfer’s favorite type of music? Swing!"
        ];

        // Variable to track the last joke shown
        let lastJokeIndex = -1;

        // Function to display a new joke
        function tellGolfJoke() {
            let newJokeIndex;
            
            // Loop to make sure a new joke is chosen
            do {
                newJokeIndex = Math.floor(Math.random() * golfJokes.length);
            } while (newJokeIndex === lastJokeIndex);
            
            // Update last joke index
            lastJokeIndex = newJokeIndex;
            
            // Display the new joke in the <p> element
            document.getElementById("jokeDisplay").innerText = golfJokes[newJokeIndex];
        }
    </script>
</body>
</html>
