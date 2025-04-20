---
title: Week 5, 2
published_at: 2025-04-08
snippet: Test on three.js 
disable_html_sanitization: true
allow_math: true
---
[HOME](https://kc-yeo-creative-co-37.deno.dev/)

1. [three.js](#threejs)
2. [Sabato Visconti](#sabato-visconti)

## three.js
import statements three.js into library. `*` means everything as an object (like a name). bare specifier, importing into a bunch of spaces no. Import map, 
`..` = file path, jumps back one folder. 

<div id="three.js_container"></div>

<script type="module">
    import * as THREE from "/250408/three.js/build/three.module.js"

    const container = document.getElementById (`three.js_container`)
    const width = container.parentNode.scrollWidth
    const height = width * 9 / 16

	import { OrbitControls } from '/250408/three.js/examples/jsm/controls/OrbitControls.js';
	import { TeapotGeometry } from '/250408/three.js/examples/jsm/geometries/TeapotGeometry.js';

	const teapotSize = 300

	let teapot
	let material

	//render();


	const canvasWidth = width;
	const canvasHeight = height;

	// TEXTURE MAP
	const textureMap = new THREE.TextureLoader().load( '/250408/three.js/examples/textures/uv_grid_opengl.jpg' );
	textureMap.wrapS = textureMap.wrapT = THREE.RepeatWrapping;
	textureMap.anisotropy = 16;
	textureMap.colorSpace = THREE.SRGBColorSpace;

	// REFLECTION MAP
	const path = '/250408/three.js/examples/textures/cube/pisa/';
	const urls = [ 'px.png', 'nx.png', 'py.png', 'ny.png', 'pz.png', 'nz.png' ];

	const textureCube = new THREE.CubeTextureLoader().setPath( path ).load( urls );

	const materials = {}

	materials[ 'wireframe' ] = new THREE.MeshBasicMaterial( { wireframe: true } );
	materials[ 'flat' ] = new THREE.MeshPhongMaterial( { specular: 0x000000, flatShading: true, side: THREE.DoubleSide } );
	materials[ 'smooth' ] = new THREE.MeshLambertMaterial( { side: THREE.DoubleSide } );
	materials[ 'glossy' ] = new THREE.MeshPhongMaterial( { color: 0xc0c0c0, specular: 0x404040, shininess: 300, side: THREE.DoubleSide } );
	materials[ 'textured' ] = new THREE.MeshPhongMaterial( { map: textureMap, side: THREE.DoubleSide } );
	materials[ 'reflective' ] = new THREE.MeshPhongMaterial( { envMap: textureCube, side: THREE.DoubleSide } );

	const rand_el = a => a[Math.floor (Math.random () * a.length)]

	const rand_tess = () => rand_el ([ 20, 30, 40, 50])

	// CAMERA
	const camera = new THREE.PerspectiveCamera( 45, width / height, 1, 80000 );
	camera.position.set( - 600, 550, 1300 );

	// LIGHTS
	const ambientLight = new THREE.AmbientLight( 0x7c7c7c, 2.0 );

	const light = new THREE.DirectionalLight( 0xFFFFFF, 2.0 );
	light.position.set( 0.32, 0.39, 0.7 );

	// RENDERER
	const renderer = new THREE.WebGLRenderer( { antialias: true } );
	renderer.setPixelRatio( window.devicePixelRatio );			
	renderer.setSize( canvasWidth, canvasHeight );
	container.appendChild( renderer.domElement );
	
	// CONTROLS
	const cameraControls = new OrbitControls( camera, renderer.domElement );
	// cameraControls.addEventListener( 'change', render );

	// scene itself
	const scene = new THREE.Scene();
	scene.background = new THREE.Color( 0xAAAAAA );

	scene.add( ambientLight );
	scene.add( light );

	material = materials[ 'wireframe' ]
	console.log ('material', material)

	const mutate_geometry = (g, p) => {
		const p_is_positive = p >= 0.5

		const length = g.index.array.length
		const glitch_amount = Math.abs ((p * 2) - 1) ** 5
		const glitch_length = Math.floor (glitch_amount * length)
		const glitch_location = Math.floor (
			Math.random () * (length - glitch_length)
		)

		const mutation = p_is_positive
			? () => Math.floor (Math.random () * 8189)
			: () => 0
		
		const front = g.index.array.slice (0, glitch_location)
		const middle = new Uint16Array (glitch_length)
			.fill (0)
			.map (mutation)

		const back = g.index.array.slice (glitch_location + glitch_length)
		const mutated = new Uint16Array (length)
		mutated.set (front)
		mutated.set (middle, front.length)
		mutated.set (back, front.length + middle.length)
		g.index.array = mutated 
		}

	let next_glitch_time = 0
	let is_glitching = false
	let geometry = new TeapotGeometry (
		300, // teapotSize
		50,  // tess
		true,
		true,
		true,
		false,
		false,
	)


// Whenever the teapot changes, the scene is rebuilt from scratch (not much to it).
const draw_teapot = ms => {

	if (teapot !== undefined) {
		teapot.geometry.dispose ()
		scene.remove (teapot)
	}

	const t = ms / 1000

	if (t > next_glitch_time) {
		const period = Math.random () ** 24 * 6
		next_glitch_time = t + period

		is_glitching = !is_glitching

		if (is_glitching) {
			mutate_geometry (geometry, Math.random ())
		}

		else {
			geometry = new TeapotGeometry (
				teapotSize,
				rand_tess (), // tess,
				Math.random () < 0.8,
				Math.random () < 0.8,
				true,
				true, //Math.random () < 0.5,
				true  //Math.random () < 0.5
			)

			const type = rand_el ([ 
				`wireframe`, 
				`flat`, 
				`smooth`, 
				`glossy`, 
				`textured`, 
				`reflective` 
			])
			// const i = Math.floor (Math.random () * types.length)
			// const type = types[i]
			material = materials[type]

			scene.background = type == `reflective` 
				? textureCube
				: null

		}
	}

	teapot = new THREE.Mesh (geometry, material)
	scene.add (teapot)

	// render ()


	renderer.render (scene, camera)

	requestAnimationFrame (draw_teapot)
}

requestAnimationFrame (draw_teapot)
</script>

## Sabato Visconti