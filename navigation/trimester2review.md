---
layout: base
title: Trimester 2 Final Review
description: My blogs for the Trimester 2 Final Review
permalink: /trimester2review/
---

<div class="container">
    <h1>Trimester 2 Final Review</h1>
    <p>Explore the key ideas covered in this trimester:</p>
    <div class="button-container">
        <a href="../big_idea_1/" class="btn big-idea-1">Big Idea 1 Blog</a>
        <a href="../big_idea_3/" class="btn big-idea-3">Big Idea 3 Blog</a>
        <a href="../big_idea_4/" class="btn big-idea-4">Big Idea 4 Blog</a>
        <a href="../CSApractice/" class="btn AP-CSA-MC">AP CSA Multiple Choice Practice</a>
        <a href="../5things/" class="btn five-things">5 Things That I Did</a>
</div>

</div>

<style>

    .container {
        text-align: center;
        padding: 40px;
    }

    p {
        font-size: 18px;
        color: #5A4A42; /* Muted Desert Brown */
    }

    /* Button Styling */
    .button-container {
        display: flex;
        justify-content: center;
        gap: 20px;
        margin-top: 20px;
        flex-wrap: wrap;
    }

    .btn {
        display: inline-block;
        padding: 15px 30px;
        font-size: 18px;
        color: white;
        text-decoration: none;
        border-radius: 8px;
        border: none;
        cursor: pointer;
        text-align: center;
        transition: background-color 0.3s ease, transform 0.2s ease;
    }

    .btn:hover {
        transform: scale(1.05);
    }

    /* Earthy Desert Tones for Buttons */
    .big-idea-1 { background-color: #D2691E; }  /* Reddish-Brown (Canyon Rock) */
    .big-idea-3 { background-color: #C2B280; }  /* Sand Dune Beige */
    .big-idea-4 { background-color: #556B2F; }  /* Cactus Green */
    .AP-CSA-MC { background-color: #709F34; }  /* Sage Green */
    .five-things { background-color: #8B4513;} /* SaddleBrown (Rusty Earth Tone) */
    /* Hover Effects */
    .big-idea-1:hover { background-color: #A0522D; } /* Darker Canyon */
    .big-idea-3:hover { background-color: #B0A16A; } /* Deeper Sand */
    .big-idea-4:hover { background-color: #44582A; } /* Darker Green */
    .AP-CSA-MC:hover { background-color: #81BD33; } /* Brighter Sage */
    .five-things:hover { background-color: #A0522D; }/* Darker Brown */




    /* Footer (Optional) */
    .footer {
        text-align: center;
        padding: 20px;
        background-color: #A0522D; /* Reddish-Brown Rock */
        color: white;
        position: absolute;
        width: 100%;
        bottom: 0;
    }
</style>
