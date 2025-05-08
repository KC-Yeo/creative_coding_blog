---
title: Week 4, 1
published_at: 2025-03-26
snippet: High Effective Complexity
disable_html_sanitization: true
allow_math: true
---
[HOME](https://kc-yeo-creative-co-37.deno.dev/)

1. [Compositions](#compositions)
2. [Plan to achieve cuteness](#at1)
3. [Feedbacks](#feedbacks)

# Compositions

***high compressibility***
<iframe id = "high-compress" src="https://editor.p5js.org/KC-Yeo/full/YfcaZelIZ"></iframe>

<script type="module">

    const iframe  = document.getElementById (`high-compress`)
    iframe.width  = iframe.parentNode.scrollWidth
    iframe.height = iframe.width * 9 / 16 + 42

</script>

***low compressibility***


***high effective complexity*** 
  My idea of high effective complexity is something between total chaos and total order. I've asked ChatGPT to visualize the concept of high effective complexity and this is what it came up with.

![high  effective complexity](effective_complexity.png)

  Then following the video on youtube by Coding Train, I embbeded the sketch of an L-system. From my understanding of L-system, it's how the next generation becomes another type of string according to rules. At first I thought it was like human blood types like how a couple's blood type effect the result of a child's blood type but after doing some research is defnitely not. Visualy it seems similar but fundamentally not. L-system rewrites the rules everytime it loops through another generation. That's what's giving the complexity of the bigger picture. 

```javascript

// declaring angle
var angle;

// declaring axiom and assigning it as "F"
// 'axiom' = start of the system
var axiom = "F";

// declaring sentence and assigning to axoim
var sentence = axiom;

// declaring len and assigning to 100 pixels
// length of line
var len = 100;

// rules assigned empty array
var rules = [];

// strings of the rules 
// that will be turned into lines
rules[0] = {
  a: "F",
  b: "[F+F+F]+[F-F-F]++FF"
}

// new lines forming according
// to the new rule of the system
function generate() {

  // shrinking the lenght to fit canvas
  len *= 0.5;

  // empty string to store new sentence
  // from rule
  var nextSentence = "";

  // for loop for sentence
  for (var i = 0; i < sentence.length; i ++) {

    // charAt converts index to an integer
    // that can be visualized on canvas
    var current = sentence.charAt(i);
    
    var found = false;

    // another for loop for lines
    for (var j = 0; j < rules.length; j ++) {

      // if current line is "F" and true
      // then next sentence is "[F+F+F]+[F-F-F]++FF"
      if (current == rules[j].a) {
        found = true;
        nextSentence += rules[j].b;

        // getting out of the loop 
        break;
      }
    }

    // if no rules are found,
    // keep current line
    if (!found) {
      nextSentence += current;
    }
  }
  sentence = nextSentence;

  // the canvas for sentence??
  createP(sentence);

  // run turtle function
  turtle();
}

// defining the function turtle
// also the visualization of the canvas
function turtle() {
  background(51);
  resetMatrix();

  // making the object in the middle
  translate(width / 2, height / 2);
  stroke(255);

  // this is a loop that generates everytime 
  // when button is clicked
  for (var i = 0; i < sentence.length; i ++) {

    // retrieving strong information and replacing 
    // at the index
    var current = sentence.charAt(i)
    if (current == "F") {
      line(0, 0, 0, -len)
      translate(0, -len)
    } else if (current == "+") {
      rotate(PI / 6)
    } else if (current == "-") {
      rotate(-PI / 6)
    } else if (current == "[") {
      push()
    } else if (current == "]") {
      pop()
    }
  }
}

function setup() {
  createCanvas(400, 400);
  angle = radians(25);
  background(51);

  // start of the sentence
  // "F"
  createP(axiom);

  // run turtle function
  turtle();
}

// when mouse is clicked, 
// run generate function
// which also runs the turtle function
function mousePressed() {
  generate()
}
```

<iframe id="L-system" src="https://editor.p5js.org/KC-Yeo/full/7KBcn_V4n"></iframe>

<script type="module">

    const iframe  = document.getElementById (`L-system`)
    iframe.width  = iframe.parentNode.scrollWidth
    iframe.height = iframe.width * 9 / 16 + 42

</script>
 <br>
 <br>
 