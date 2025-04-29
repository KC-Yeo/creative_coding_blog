---
title: Week 7, 1
published_at: 2025-04-17
snippet: sounds?
disable_html_sanitization: true
allow_math: true
---
[HOME](https://kc-yeo-creative-co-37.deno.dev/)

1. [Shader]()
2. []()
3. []()
4. []()\

## 

## 

how will you make the sound design for your AT2 function in a chaotic aesthetic register?  What does it mean to be chaotic in the sonic domain? In your discussion, please make reference to:
effective complexity, paying particular attention to:
structure - what structures our perception of sound? 
noise - what differentiates noise from sound, or music?
voice - what makes voice a separate category of sound?
the role of de-familiarisation (as per Natalie Loveless' talk From Relational to Ecological FormLinks to an external site.)
three examples, which can (but don't have to) be taken from the following list:
MyNoise Generators: JungleLinks to an external site. / WaterLinks to an external site. / FireLinks to an external site. / ThunderLinks to an external site. / StormLinks to an external site.
Pink TromboneLinks to an external site.
How to Kill a ZombieLinks to an external site.
implement an interactive sound design experiment in your blog.
you will need to get some form of user gesture for Web Audio API to run.
you can use a library, such as Tone.jsLinks to an external site. or Pizzicato.jsLinks to an external site., or you can use Web Audio APILinks to an external site., or AudioWorkletLinks to an external site..
use a sinusoid to push your sound design into chaos and back every 24 seconds.
explain your code with the help of syntax-highlighted, commented code blocks
evaluate the success of your experiment with reference to your discussion in task 1

<div id="three.js_container"></div>

<script type="module">
    import * as THREE from "./250408/three.js/build/three.module.js"

    const container = document.getElementById (`three.js_container`)
    const width = container.parentNode.scrollWidth
    const height = width * 9 / 16

	import { OrbitControls } from './250408/three.js/examples/jsm/controls/OrbitControls.js';
	import getStarfield from "./250417/src/getStarfield.js";

    const w = window.innerWidth;
    const h = window.innerHeight;
    const scene = new THREE.Scene();
    const camera = new THREE.PerspectiveCamera(75, w / h, 0.1, 1000);
    camera.position.z = 5;
    const renderer = new THREE.WebGLRenderer({ antialias: true});
    renderer.setSize(w, h);
    document.body.appendChild(renderer.domElement);
    renderer.toneMapping = THREE.ACESFilmicToneMapping;
    renderer.outputColorSpace = THREE.LinearSRGBColorSpace;

    const earthGroup = new THREE.Group();
    earthGroup.rotation.z = -23.4 * Math.PI / 180;
    scene.add(earthGroup);
    new OrbitControls(camera, renderer.domElement);
    const detail = 12;
    const loader = new THREE.TextureLoader();
    const geometry = new THREE.IcosahedronGeometry(1, detail);
    const material = new THREE.MeshPhongMaterial({
    map: loader.load("./250417/textures/sunmap.jpg"),
    // specularMap: loader.load("./textures/02_earthspec1k.jpg"),
    // bumpMap: loader.load("./textures/01_earthbump1k.jpg"),
    // bumpScale: 0.04,
    });
    // material.map.colorSpace = THREE.SRGBColorSpace;
    const earthMesh = new THREE.Mesh(geometry, material);
    earthGroup.add(earthMesh);

    // const lightsMat = new THREE.MeshBasicMaterial({
    // map: loader.load("./textures/03_earthlights1k.jpg"),
    // blending: THREE.AdditiveBlending,
    // });
    // const lightsMesh = new THREE.Mesh(geometry, lightsMat);
    // earthGroup.add(lightsMesh);

    // const cloudsMat = new THREE.MeshStandardMaterial({
    // map: loader.load("./textures/04_earthcloudmap.jpg"),
    // transparent: true,
    // opacity: 0.8,
    // blending: THREE.AdditiveBlending,
    // alphaMap: loader.load('./textures/05_earthcloudmaptrans.jpg'),
    // // alphaTest: 0.3,
    // });
    // const cloudsMesh = new THREE.Mesh(geometry, cloudsMat);
    // cloudsMesh.scale.setScalar(1.003);
    // earthGroup.add(cloudsMesh);

    // const fresnelMat = getFresnelMat();
    // const glowMesh = new THREE.Mesh(geometry, fresnelMat);
    // glowMesh.scale.setScalar(1.01);
    // earthGroup.add(glowMesh);

    const stars = getStarfield({numStars: 2000});
    scene.add(stars);

    // const sunLight = new THREE.DirectionalLight(0xffffff, 2.0);
    // sunLight.position.set(-2, 0.5, 1.5);
    // scene.add(sunLight);

    function animate() {
    requestAnimationFrame(animate);

    earthMesh.rotation.y += 0.002;
    // lightsMesh.rotation.y += 0.002;
    // cloudsMesh.rotation.y += 0.0023;
    // glowMesh.rotation.y += 0.002;
    stars.rotation.y -= 0.0002;
    renderer.render(scene, camera);
    }

    animate();

    function handleWindowResize () {
    camera.aspect = window.innerWidth / window.innerHeight;
    camera.updateProjectionMatrix();
    renderer.setSize(window.innerWidth, window.innerHeight);
    }
    window.addEventListener('resize', handleWindowResize, false);

</script>

        