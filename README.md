# omani-prsedent-livery
livery addon ghaith26
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>3D View of Boeing 747-8</title>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
</head>
<body style="margin: 0; overflow: hidden;">

<script>
  // Basic Three.js scene setup
  const scene = new THREE.Scene();
  const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
  const renderer = new THREE.WebGLRenderer();
  renderer.setSize(window.innerWidth, window.innerHeight);
  document.body.appendChild(renderer.domElement);

  // Add lighting to scene
  const light = new THREE.AmbientLight(0x404040); // Ambient light
  scene.add(light);

  // Load a 3D model of the aircraft (replace with your own model URL)
  const loader = new THREE.GLTFLoader();
  loader.load('your-model-path-here.glb', function(gltf) {
    const model = gltf.scene;
    scene.add(model);
  });

  camera.position.z = 5;

  // Animation loop
  function animate() {
    requestAnimationFrame(animate);
    renderer.render(scene, camera);
  }

  animate();
</script>

</body>
</html>

