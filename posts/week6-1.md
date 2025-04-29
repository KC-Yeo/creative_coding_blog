---
title: Week 6, 1
published_at: 2025-04-10
snippet: Different libraries
disable_html_sanitization: true
allow_math: true
---
[HOME](https://kc-yeo-creative-co-37.deno.dev/)

1. [Libraries](#use-of-each-library)
2. [esm.sh](#esmsh)
3. [q5](#q5-demonstration)
4. [Readings summary](#readings)



## Use of each library
* q5.js

* c2.js

* svg.js

## esm.sh

## q5 demonstration
<div id="q5_test"></div>

<script type="module">
   import Q5 from '/scripts/q5.js'
   const div = document.getElementById (`q5_test`)
   const width = div.parentNode.scrollWidth
   const height = width * 9 / 16 

   const q = new Q5 ("instance")
   console.log (q)

   const pos = { 
      x: 0, 
      y: height / 2 - 50,
      v: 12,
   }

   q.setup = () => {
      q.createCanvas (width, height)
      q.noStroke ()
      q.fill (`deeppink`)
   }

   q.draw = () => {
      q.background (`turquoise`)
      q.square (pos.x, pos.y, 100)

      pos.x += pos.v

      if (pos.x > width - 100) {
         pos.x = width - 100
         pos.v *= -1
      } else if (pos.x < 0) {
         pos.x = 0
         pos.v *= -1
      }
   }
</script>

<div id="q5_test"></div>

<script type="module">
    import Q5 from '/scripts/q5.js'
    const div = document.getElementById (`q5_test`)
    const width = div.parentNode.scrollWidth
    const height = width * 9 / 16

    const q = new Q5 ("instance")
    console.log (q)
    
    let mouseX = 0
    let mouseY = 0

    q.setup = () => {
        q.createCanvas(width, height)
        q.fill(`pink`)
        q.noStroke()
    }

    q.mouseMoved = () => {
        mouseX = q.mouseX
        mouseY = q.mouseY
    }

    q.draw = () => {
        q.background(200)
        q.circle(mouseX, mouseY, 100)
        
    }

</script>

```javascript
<div id="q5_test"></div>

<script type="module">
    import Q5 from '/scripts/q5.js'
    const div = document.getElementById (`q5_test`)
    const width = div.parentNode.scrollWidth
    const height = width * 9 / 16

    const q = new Q5 ("instance")
    console.log (q)
    
    let mouseX = 0
    let mouseY = 0

    q.setup = () => {
        q.createCanvas(width, height)
        q.fill(`pink`)
        q.noStroke()
    }

    q.mouseMoved = () => {
        mouseX = q.mouseX
        mouseY = q.mouseY
    }

    q.draw = () => {
        q.background(200)
        q.circle(mouseX, mouseY, 100)
        
    }

</script>
```

## Readings

Please consider the following javascript libraries:

q5.jsLinks to an external site.
c2.jsLinks to an external site.
svg.jsLinks to an external site.
... and attend to the following questions / tasks:

What is each library for? 
In what ways are they different?
Can we use these libraries from within a javascript moduleLinks to an external site.? Explain why / why not.
In what situations might a tool like esm.shLinks to an external site. be useful?
Use one of these libraries on your blog to demonstrate how to use a signal or envelope to make something change over time.
In your own words, please give a brief summary of the following texts:
Information & Thinking by Michel Serres
What Is It Like to Be A Fungus? by Merlin Sheldrake
Xenofemenism: A Politics for Alienation by Laboria Cuboniks




