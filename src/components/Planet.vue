
<script>
import * as THREE from "three";
import { OrbitControls } from "/node_modules/three/examples/jsm/controls/OrbitControls";


const scene = new THREE.Scene();
const camera = new THREE.PerspectiveCamera(25, window.innerWidth / window.innerHeight, 0.1, 10000);
const renderer = new THREE.WebGLRenderer({
  antialias: true
});

const controls = new OrbitControls(camera, renderer.domElement);
camera.position.set(0, 20, 100);
controls.update();

renderer.setPixelRatio(2);
renderer.setSize(window.innerWidth, window.innerHeight);
document.body.appendChild(renderer.domElement);

// function planet($planet,$size){
// 	var textureLoader = new THREE.TextureLoader();
// 	var Texture = textureLoader.load("sun.jpg");
// 	var Geometry = new THREE.SphereGeometry($size);
// 	var Material = new THREE.MeshBasicMaterial({map:Texture});
// 	var $planet = new THREE.Mesh(Geometry, Material);
// 	scene.add($planet);
// }

var textureLoader = new THREE.TextureLoader();
var neptuneTexture = textureLoader.load('/src/assets/img/neptune.webp');

var textureLoader = new THREE.TextureLoader();
var uranusTexture = textureLoader.load('/src/assets/img/uranus.webp');

var textureLoader = new THREE.TextureLoader();
var saturnTexture = textureLoader.load('/src/assets/img/saturn.webp');

var textureLoader = new THREE.TextureLoader();
var ringsTexture = textureLoader.load('/src/assets/img/rings.png');

var textureLoader = new THREE.TextureLoader();
var sunTexture = textureLoader.load('/src/assets/img/sun.webp');

var textureLoader = new THREE.TextureLoader();
var jupiterTexture = textureLoader.load('/src/assets/img/jupiter.webp');

var textureLoader = new THREE.TextureLoader();
var marsTexture = textureLoader.load('/src/assets/img/mars.webp');

var textureLoader = new THREE.TextureLoader();
var earthTexture = textureLoader.load('/src/assets/img/earth.webp');

var textureLoader = new THREE.TextureLoader();
var venusTexture = textureLoader.load('/src/assets/img/venus.webp');

var textureLoader = new THREE.TextureLoader();
var mercuryTexture = textureLoader.load('/src/assets/img/mercury.webp');



// var fondLoader = new THREE.TextureLoader();
// var fond = fondLoader.load('fond.jpg');
// scene.background = fond;

// renderer.setClearColor(0, 1, 43);

var neptuneGeometry = new THREE.SphereGeometry(4.66, 50, 50);
var neptuneMaterial = new THREE.MeshStandardMaterial({ map: neptuneTexture });
var neptune = new THREE.Mesh(neptuneGeometry, neptuneMaterial);
scene.add(neptune);

var uranusGeometry = new THREE.SphereGeometry(4.94, 50, 50);
var uranusMaterial = new THREE.MeshStandardMaterial({ map: uranusTexture });
var uranus = new THREE.Mesh(uranusGeometry, uranusMaterial);
scene.add(uranus);

var saturnGeometry = new THREE.SphereGeometry(16.85, 50, 50);
var saturnMaterial = new THREE.MeshStandardMaterial({ map: saturnTexture });
var saturn = new THREE.Mesh(saturnGeometry, saturnMaterial);
scene.add(saturn);

var ringsGeometry = new THREE.RingGeometry(18, 40, 100);
var ringsMaterial = new THREE.MeshLambertMaterial({ map: ringsTexture, side: THREE.DoubleSide });
var rings = new THREE.Mesh(ringsGeometry, ringsMaterial);
scene.add(rings);

var jupiterGeometry = new THREE.SphereGeometry(20, 50, 50);
var jupiterMaterial = new THREE.MeshLambertMaterial({ map: jupiterTexture });
var jupiter = new THREE.Mesh(jupiterGeometry, jupiterMaterial);
scene.add(jupiter);

var marsGeometry = new THREE.SphereGeometry(0.78, 50, 50);
var marsMaterial = new THREE.MeshLambertMaterial({ map: marsTexture });
var mars = new THREE.Mesh(marsGeometry, marsMaterial);
scene.add(mars);

var earthGeometry = new THREE.SphereGeometry(1.098, 50, 50);
var earthMaterial = new THREE.MeshLambertMaterial({ map: earthTexture });
var earth = new THREE.Mesh(earthGeometry, earthMaterial);
scene.add(earth);

var venusGeometry = new THREE.SphereGeometry(1.04, 50, 50);
var venusMaterial = new THREE.MeshLambertMaterial({ map: venusTexture });
var venus = new THREE.Mesh(venusGeometry, venusMaterial);
scene.add(venus);

var mercuryGeometry = new THREE.SphereGeometry(0.41, 50, 50);
var mercuryMaterial = new THREE.MeshLambertMaterial({ map: mercuryTexture });
var mercury = new THREE.Mesh(mercuryGeometry, mercuryMaterial);
scene.add(mercury);


var sunGeometry = new THREE.SphereGeometry(196, 50, 100);
var sunMaterial = new THREE.MeshBasicMaterial({ map: sunTexture });
var sun = new THREE.Mesh(sunGeometry, sunMaterial);
scene.add(sun);

mercury.position.x = -260;
venus.position.x = -270;
earth.position.x = -280;
mars.position.x = -290;
jupiter.position.x = -330;
sun.position.x = 0;
rings.position.x = -400;
rings.rotation.x = 30;
rings.rotation.y = 0.2;
saturn.position.x = -400;
uranus.position.x = -450;
neptune.position.x = -500;

camera.position.z = 500;






function animate() {
  requestAnimationFrame(animate)

  controls.update();

  rings.rotation.z += 0.0005;
  sun.rotation.y += 0.0003;
  jupiter.rotation.y += 0.002;
  mars.rotation.y += 0.001;
  earth.rotation.y += 0.003;


  renderer.render(scene, camera);
};

animate();


var light = new THREE.DirectionalLight(0xffffff, 1.1);
light.position.set(20, 0, 5);
light.castShadow = true;
scene.add(light);

</script>

<template>


</template>

<style scoped>
canvas {
  display: flex;
  width: 100%;
  height: 100%;
}
</style>
