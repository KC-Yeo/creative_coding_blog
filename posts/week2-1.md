---
title: Week 2, 1
published_at: 2024-03-12
snippet: Concepts, Techniques
disable_html_sanitization: true
allow_math: true
---
[HOME](https://kc-yeo-creative-co-37.deno.dev/)

1. [Concepts](#concepts)
2. [Techniques](#techniques)

## Concepts

*cute visuals*

<iframe id="cute_visuals" src="https://editor.p5js.org/KC-Yeo/full/6lDkLMXh5"></iframe>

<script type="module">

    const iframe  = document.getElementById (`cute_visuals`)
    iframe.width  = iframe.parentNode.scrollWidth
    iframe.height = iframe.width * 9 / 16 + 42

</script>

For the visuals, I've opted using simple shape like a circle to capture the essence of a ball. The ball is a translucent colour that you can see  through. From my sketch, I used a method by Jorge Moreno [^1] that I downloaded from p5.js, particularly the 'radial' gradient to achieve the effect. From the reference, we know that we have to input values from the colour wheel to get the effect. 

```
fillGradient('radial', {
    from : [200, 200, 0], // x, y, radius
    to : [200, 200, 200], // x, y, radius
    steps : [
        color(255),
        color(0, 96, 164),
        color(0)
    ] // Array of p5.color objects or arrays containing [p5.color Object, Color Stop (0 to 1)]
});

```
The idea is to have the object following the mouse as well, like a chasing game where it captures the mouse. 

[^1]: [p5.fillGradient](https://shorturl.at/FXooo) *(courtesy of Thomas :joy:)*

*cute sounds*

<iframe id="cute_sounds" src="https://editor.p5js.org/KC-Yeo/full/ykk4TKOMl"></iframe>

<script type="module">

    const iframe  = document.getElementById (`cute_sounds`)
    iframe.width  = iframe.parentNode.scrollWidth
    iframe.height = iframe.width * 9 / 16 + 42

</script>

For sound design, I used the library of Freesound.org [^2], where there are multiple audios that I was interested in. I initally wanted the sound to have an ambience music as my initial design was suppose to be lights, but halfway through I reconsidered the options and opted for bubbles popping sound. Circling back to the Orbeeze (water beads), I wanted to make my sketch more interactive with sounds as well. So I used `mousePressed()` function to recall the sounds. 

[^2]: [Freesound](https://freesound.org/people/Funky_Audio/sounds/698818/?)

*cute interactions*

<iframe id="cute_interactions" src="https://editor.p5js.org/KC-Yeo/full/dZEN1vi1T"></iframe>

<script type="module">

    const iframe  = document.getElementById (`cute_interactions`)
    iframe.width  = iframe.parentNode.scrollWidth
    iframe.height = iframe.width * 9 / 16 + 42

</script>

For the interactions, I had a few ideas but I definitely wanted something to do with the `random()` function inspired my Rafael Rozendaal's [81 Horizons](https://www.newrafael.com/81-horizons/). It was the first ever JS project that I worked on and that really inspired my idea of assignment on using `random()` function. As you can see from my p5 sketches that there are 2 examples of `random()` function being used, the colour and the diameter of the circle.

<iframe id="random()" src="https://editor.p5js.org/KC-Yeo/full/jZ5FDqAet"></iframe>

<script type="module">

    const iframe  = document.getElementById (`random()`)
    iframe.width  = iframe.parentNode.scrollWidth
    iframe.height = iframe.width * 9 / 16 + 42

</script>

The concept of my assignment would surround with colourful jellies as an offering to my younger self. The ideas is to have a playful and fun concept that focuses on the feeling of joy. I hope from the explanations, it gives you an idea on what my offering looks like.

## Techniques

The techniques are commented in the p5 sketches itself:
> `class()` to make a cookie-cutter for the object
> `rand()` for random unexpected colours
> `sound` for more interactions with senses other than eyes
> `mousePressed()` to have interaction with the mouse
>`array[]` to loop through the list 
> `if` statement for dynamic background