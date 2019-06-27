```js
	var camera, scene, renderer;

	init();
	setInterval(loop, 1000 / 60);

	function init()
	{
		camera = new Camera(0, 0, 1000);

		scene = new Scene();
	
		renderer = new CanvasRenderer();
		renderer.setSize(window.innerWidth, window.innerHeight);

		for (var i = 0; i < 1000; i++)
		{
			var particle = new Particle( new ColorMaterial(Math.random() * 0x808008 + 0x808080, 1) );
			particle.position.x = Math.random() * 2000 - 1000;
			particle.position.y = Math.random() * 2000 - 1000;
			particle.position.z = Math.random() * 2000 - 1000;
			particle.size = Math.random() * 10 + 5;
			particle.updateMatrix();
			scene.add( particle );
		}

		document.body.appendChild(renderer.viewport);
	}

	function loop()
	{
		renderer.render(scene, camera);
	}
```
