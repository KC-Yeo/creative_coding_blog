---
title: Week 1, 2
published_at: 2024-03-07
snippet: An example of a blog post.
disable_html_sanitization: true
allow_math: true
---
[HOME](https://kc-yeo-creative-co-37.deno.dev/)

# Discussions
1. Minami:
Hello KC! 
I think what’s happening here is:
* 2 arrays that each store the colors for the sky and the ground
* function to get a random color from the array and assigns it to the fill
* draw a square with that color
* The second and third step are run twice, to draw the sky (width, height * 3/4) and the ground (width, height / 4) using separate fills and squares!

The concepts needed to replicate this in p5 would be:
* `array`
* `random`
* `rect()`

Helpful resources would be:
* p5.js reference
* color picker tool
* YouTube

2. Rania
What do you think is going on under the hood? 

That's a great question! Although I don't know much about JavaScript, I would assume that Rafael utilised `mouseClicked()` and `random()` functions to create the interactive artwork of Horizons. I believe Rafael added multiple rectangles in different colours and animated them to change colour using `mouseClicked()` and `random()` functions, which is what I assume is going on under the hood of the digital artwork called “Horizons.”

What concepts would I need to understand to replicate this work in p5?

To replicate Rafael’s work in p5.js, you should understand:
Shapes: Using `rect()` and `square()` to create geometric forms.
Color Manipulation: Applying `fill()`, `stroke()`, `colour ()`, and `lerpColor()` for dynamic color effects.
Randomization: Utilizing `random()` to vary colors and sizes.
Interactivity: Implementing `mouseClicked()` for interactive colour changes.
These key concepts will help you effectively recreate Rafael’s artistic style in p5.js.

What resources might help me to learn those concepts?

I frequently consult various resources for information, including the p5.js reference documentation, Reddit discussions, Stack Overflow for programming questions, ChatGPT for code I couldn't find anywhere else or to clean up unnecessary code and W3Schools for JavaScript tutorials and YouTube tutorials are a big help for understanding code lookup coding train, I found it quite helpful. I believe utilising these resources will help us learn new concepts. 

# 81 Horizon by Rafaël Rozendaal

*I have commented on p5 sketch itself on how the code is working*

* [The Coding Train](https://shorturl.at/PQCfr)
The playlist helped in teaching me on the `rand()` function that is crucial for this sketch. I also learned the function, mousePressed(), for the interactivity of the mouse and the colour change. As for the position of the rectangle, it was a bit of trial and error as I approached it without using the correct size. 

I firstly did the square like you would to position a static object, `(x, y, size)`, according to the canvas size. Then I changed the canvas to be windowWidth and windowHeight so users can view the sketch according to their screen. Then, I used some math components to arrange the size and positon similar to Rafaël Rozendaal's work, 81 Horizon.

* mdn web docs
I used this website as a dictionary on how some function works. 

* ChatGPT
I used the AI platform to help me understand the code itself and how it works. As I am a newbie when it comes to JS language, I did so to strengthen my understanding on the codes as to not fall behind on the lectures. 

<iframe id="random_color_generator" src="https://editor.p5js.org/KC-Yeo/full/vnL9hfQua"></iframe>

<script type="module">

    const iframe  = document.getElementById (`random_color_generator`)
    iframe.width  = iframe.parentNode.scrollWidth
    iframe.height = iframe.width * 9 / 16 + 42

</script>

