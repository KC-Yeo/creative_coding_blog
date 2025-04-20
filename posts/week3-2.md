---
title: Week 3, 2
published_at: 2025-03-21
snippet: Concepts, Draft of A1
disable_html_sanitization: true
allow_math: true
---
[HOME](https://kc-yeo-creative-co-37.deno.dev/)

1. [Concepts](#concepts)
2. [Draft](#draft)

## Concepts
Please describe how your AT1 will use each of the following concepts:
*variables*
* `jelly`: I plan to use a variable to assign and empty `array[]` to store the values of new jellies being formed. The list in the array will add more and more values of newly formed jellies. 
* `popSounds`: I also used `array[]` for the sound audios so that I can loop through the list randomly when I click to create a new jelly each time. 

*functions*
* `random()`: I plan to use `random()` function for the colours of my jelly. Each jelly formed will be filled with a random colour from the colour wheel in the HSB colour mode. 
* `mousePresseed()`: Using `mousePressed()`, I can enhance the inetractivity of the sketch. When the mouse is pressed, new jelly will be formed along with playing the audio files randomly through the list. 

*iteration*
*  `for()`: I will use the `for loop()` for the iterations to create new jellies everytime I press the mouse. I will also use this with the gradient method that I will define in the `class()` function.

*boolean logic*
* `clearCanvasFunction()`: I also want to clear the canvas when there is too much going on the canvas. So I defined a `clearCanvasFunction()`, so when the `space` key is pressed, the canvas is cleared. This also act as the Boolean toggle. If the key is pressed, the jelly array is cleared and therefore starts anew. 

*arrays*
* `array[]`: I use empty arrays to input new values of the jelly when they form. I also use `.push{()` for new objects to be formed IN the array itself. It is for forming new jellies as well as playing the audio files. 

*classes*
* `class()`: to act as the coookie-cutter for every jelly being formed on the canvas. The jelly will be in gradient method, which can be downloaded in p5.reference. 

## Draft
<iframe id="A1_ver1" src="https://editor.p5js.org/KC-Yeo/full/Ma8ehas4E"></iframe>

<script type="module">

    const iframe  = document.getElementById (`A1_ver1`)
    iframe.width  = iframe.parentNode.scrollWidth
    iframe.height = iframe.width * 9 / 16 + 42

</script>

The initial version of A1, with main structure of 'jelly' working. The code was made with the strong guidance of Thomas, as I am a newbie when it comes to coding. 

*achieved?*
I think in terms of cuteness, I can definitely improve on the dynamic of the movements and maybe the dynmaic of the background visually. Maybe the background could be a different colour, or the circles could move in a different way. I could maybe add in cute sound designs like the example of RR's work. Having cartoon-ish sounds to embrace the cuteness of my sketch. 

*communitites*
I definitely relied heavily on the help of YouTube for self-learning, and also self-practice on the things I learned. Thomas definitely helped me on this part as well. I also asked my friends from different coursees a lot of what I don't understand, or asked them any feedback on my work. I also used p5.reference and mdn web docs for anything that I'm unsure of. Last but not least, I also used AI to help me understand the codes that I couldn't pin together. Some codes were actually discovered when I was using AI and the idea gave me the creative freedom to think that it's possible to make things. 

I think what I like most about the process of this is discovering different ways to do similar sketches. During the learning process of this, I came across an ample amount of ways that p5 included in their library, interestinf effects like the Perlin noise and the Worley noise effects. I even found out that we could use our camera for effects as well! Which I think unlocks a whole new other creative freedom for me, and I'm abslutely excited to learn about. But small steps. 

I think for the most part, I'm still struggling with putting things together, when to initialize variables or define functions. Slowly but surely, I hope to improve to code effectively and make more creative designs, visuallu, sonically, and interactively.