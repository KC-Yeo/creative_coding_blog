---
title: Week 4, 2
published_at: 2025-04-01
snippet: Glitch art.
disable_html_sanitization: true
allow_math: true
---
[HOME](https://kc-yeo-creative-co-37.deno.dev/)

## Self-portrait

<canvas id="glitch_selfie"></canvas>

<script type="module">

   const cnv = document.getElementById (`glitch_selfie`)
   cnv.width = cnv.parentNode.scrollWidth
   cnv.height = cnv.width * 9 / 16
   cnv.style.backgroundColor = `deeppink`

   const ctx = cnv.getContext (`2d`)

   let img_data

   const draw = i => ctx.drawImage (i, 0, 0, cnv.width, cnv.height)

   const img = new Image ()
   img.onload = () => {
      cnv.height = cnv.width * (img.height / img.width)
      draw (img)
      img_data = cnv.toDataURL ("image/jpeg")
      add_glitch ()
   }
   img.src = `/250401/selfie.jpg`

   const rand_int = max => Math.floor (Math.random () * max)

   const glitchify = (data, chunk_max, repeats) => {
      const chunk_size = rand_int (chunk_max / 4) * 4
      const i = rand_int (data.length - 24 - chunk_size) + 24
      const front = data.slice (0, i)
      const back = data.slice (i + chunk_size, data.length)
      const result = front + back
      return repeats == 0 ? result : glitchify (result, chunk_max, repeats - 1)
   }

   const glitch_arr = []

   const add_glitch = () => {
      const i = new Image ()
      i.onload = () => {
         glitch_arr.push (i)
         if (glitch_arr.length < 12) add_glitch ()
         else draw_frame ()
      }
      i.src = glitchify (img_data, 96, 6)
   }

   let is_glitching = false
   let glitch_i = 0

   const draw_frame = () => {
      if (is_glitching) draw (glitch_arr[glitch_i])
      else draw (img)

      const prob = is_glitching ? 0.05 : 0.02
      if (Math.random () < prob) {
         glitch_i = rand_int (glitch_arr.length)
         is_glitching = !is_glitching
      }

      requestAnimationFrame (draw_frame)
   }

</script>

```javascript
<canvas id="glitch_selfie"></canvas>

<script type="module">

   const cnv = document.getElementById (`glitch_selfie`)
   cnv.width = cnv.parentNode.scrollWidth
   cnv.height = cnv.width * 9 / 16
   cnv.style.backgroundColor = `deeppink`

   const ctx = cnv.getContext (`2d`)

   let img_data

   const draw = i => ctx.drawImage (i, 0, 0, cnv.width, cnv.height)

   const img = new Image ()
   img.onload = () => {
      cnv.height = cnv.width * (img.height / img.width)
      draw (img)
      img_data = cnv.toDataURL ("image/jpeg")
      add_glitch ()
   }
   img.src = `/250401/selfie.jpg`

   const rand_int = max => Math.floor (Math.random () * max)

   const glitchify = (data, chunk_max, repeats) => {
      const chunk_size = rand_int (chunk_max / 4) * 4
      const i = rand_int (data.length - 24 - chunk_size) + 24
      const front = data.slice (0, i)
      const back = data.slice (i + chunk_size, data.length)
      const result = front + back
      return repeats == 0 ? result : glitchify (result, chunk_max, repeats - 1)
   }

   const glitch_arr = []

   const add_glitch = () => {
      const i = new Image ()
      i.onload = () => {
         glitch_arr.push (i)
         if (glitch_arr.length < 12) add_glitch ()
         else draw_frame ()
      }
      i.src = glitchify (img_data, 96, 6)
   }

   let is_glitching = false
   let glitch_i = 0

   const draw_frame = () => {
      if (is_glitching) draw (glitch_arr[glitch_i])
      else draw (img)

      const prob = is_glitching ? 0.05 : 0.02
      if (Math.random () < prob) {
         glitch_i = rand_int (glitch_arr.length)
         is_glitching = !is_glitching
      }

      requestAnimationFrame (draw_frame)
   }

</script>
```

Use techniques from Glitch, or Pixel Sort, or both, to render a self-portrait on your blog.
show your commented code in a syntax-highlighted code-block
How does rendering your likeness in this way affect its aesthetic register?  In your discussion, please refer to:
* one or more readings from "Glitch Readings"

***A Phenomenology of Glitch Art:***
  In the reading of "A Phenomenology of Glitch Art", there is a paragraph that describes how glitch art relies on the errors in the system to trigger the flow. This means glitch art is done my actively disturbing the system with something. In

 ***Glitch is Skin:***

  The reading of "Glitch is Skin" gives perspetive of how easy it is to manipulate the view of yourseld in others eyes. Much like how we programme a system to make it view as is on a flat screen. The passage includes that the glitch of a skin shows the reality of things, how it exposes the works of things. It reminds me of a series called 'Black Mirror' on Netlix, one of the episode is called - 'USS Callister' [^1] and it depicts an game designer that clones his coworkers illegally and unconsented without their knowledge into this game he built. The clones in the game wears and acts how he desires. And when they finally escapes his domain, they all changed the outfits and skins to default. 

[^1]: [USS Callister](https://en.wikipedia.org/wiki/USS_Callister)

* one or more readings from "Net Art Readings"


* the concept of effective complexity


* Ngai's three aesthetic registers

