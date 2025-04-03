---
title: Week 5, 1
published_at: 2024-04-03
snippet: Sketch embed.
disable_html_sanitization: true
allow_math: true
---

<script src="./scripts/p5.js"></script>

<canvas id="p5_example"></canvas>

<script>
    const cnv = document.getElementById ("p5_example")

    function setup () {
        createCanvas (w, h, P2D, cnv)
        const w = cnv.parentNode.scrollWidth
        const h = w * 9 / 16
    }

    function draw () {
        background (`turquoise`)
        console.log (frameCount)
    }
</script>

pick a post-digital artist from our discord channel, or from elsewhere on the internet.  Choose a specific work and describe it, referring to Florian Cramer's essay What is Post-Digital? to justify why you think this artist classifies as post-digital.
what technology are they using to produce their work? 
Hypothetically, if they were using javascript, what APIs & libraries could they use?
use RiTa.jsLinks to an external site. to generate a post-digital poem responding to the work in your blog.
< b o n u s ~ r o u n d > incorporate one or more libraries you found in 2, in the presentation your post-digital poem.