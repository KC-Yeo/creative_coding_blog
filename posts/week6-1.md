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
All 3 libraries uses WEBGL rendered to render sketches.

* q5.js
From my understanding, it seems like q5 is most similar to p5. It is used for interactive sketches. Not compatible with module.

* c2.js
Simplified canvas drawings? Not compatible with module.

* svg.js
Scalable vector graphics. Used for rendering any grpahics without losing the quality. It is compatible with module.

## esm.sh
Esm is a type of cdn that imports libraries with a url link directly without needing the users to download the raw file. It is useful for users so they don't use a lot of storage for their codes and they can use the network to help support the codes.

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
    import Q5 from 'scripts/q5.js'
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
*Information and Thinking by Michel Serres*
  The reading discusses how people take in things, and processes them. People also use the information they received to emit and store them based on what our brains already know from experience. Using what we already know to make sense of things. It also discusses how we're not the only species that does that in fact, everything recieves, emits, process, and stores information that is known. 

*What Is It Like To Be A Fungus by Merlin Sheldrake*
  Reading through the text, I was inspired by the way it describes everything is connected. Like how some fungi make their own microclimate. And looking at some examples of mycelium, I became in awe of all the different types of patterns they create organically without any system implanted. They grow irregularly? but at the same time creates something of a pattern of some sort. Fungus is everywhere. They make up everything and exist everywhere. It mentions how the bases of ecosystems are fungi related, no ecosystems found are without fungi. With fungus, it can be both a disease or a treatment depending on the use of it.
  <br>
  <br>
 




