
<script>
import * as THREE from "three";
import { OrbitControls } from "three/examples/jsm/controls/OrbitControls";


let time = 0;

let increase = document.querySelector(".increase");
let decrease = document.querySelector(".decrease");

increase.addEventListener("click", () => {
  time += 0.0002;
})
decrease.addEventListener("click", () => {
  time -= 0.0002;
})


const scene = new THREE.Scene();
const camera = new THREE.PerspectiveCamera(25, window.innerWidth / window.innerHeight, 0.1, 10000);

const renderer = new THREE.WebGLRenderer({

  antialias: true
});
// scene.background = new THREE.Color(0x002035);
renderer.setSize(window.innerWidth, window.innerHeight);

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

var Geometry = new THREE.RingGeometry(259.5, 260.5, 100);
var Material = new THREE.MeshBasicMaterial({ map: uranusTexture, side: THREE.DoubleSide });
var orbit = new THREE.Mesh(Geometry, Material);

var neptuneGeometry = new THREE.SphereGeometry(4.66, 50, 50);
var neptuneMaterial = new THREE.MeshStandardMaterial({ map: neptuneTexture });
var neptune = new THREE.Mesh(neptuneGeometry, neptuneMaterial);
const neptuneAngularSpeed = 0.0012;
const neptuneRadius = 500;
let neptuneAngle = 0;

var uranusGeometry = new THREE.SphereGeometry(4.94, 50, 50);
var uranusMaterial = new THREE.MeshStandardMaterial({ map: uranusTexture });
var uranus = new THREE.Mesh(uranusGeometry, uranusMaterial);
const uranusAngularSpeed = 0.0016;
const uranusRadius = 450;
let uranusAngle = 0;

var saturnGeometry = new THREE.SphereGeometry(16.85, 50, 50);
var saturnMaterial = new THREE.MeshPhongMaterial({ map: saturnTexture });
var saturn = new THREE.Mesh(saturnGeometry, saturnMaterial);
const saturnAngularSpeed = 0.0018;
const saturnRadius = 400;
let saturnAngle = 0;

var ringsGeometry = new THREE.RingGeometry(18, 40, 100);
var ringsMaterial = new THREE.MeshPhongMaterial({ map: ringsTexture, side: THREE.DoubleSide, alphaTest: 0.5 });
var rings = new THREE.Mesh(ringsGeometry, ringsMaterial);
const ringsAngularSpeed = 0.0018;
const ringsRadius = 400;
let ringsAngle = 0;

var jupiterGeometry = new THREE.SphereGeometry(20, 50, 50);
var jupiterMaterial = new THREE.MeshPhongMaterial({ map: jupiterTexture });
var jupiter = new THREE.Mesh(jupiterGeometry, jupiterMaterial);
const jupiterAngularSpeed = 0.002;
const jupiterRadius = 350;
let jupiterAngle = 0;


var marsGeometry = new THREE.SphereGeometry(0.78, 50, 50);
var marsMaterial = new THREE.MeshLambertMaterial({ map: marsTexture });
var mars = new THREE.Mesh(marsGeometry, marsMaterial);
const marsAngularSpeed = 0.0023;
const marsRadius = 290;
let marsAngle = 0;

var earthGeometry = new THREE.SphereGeometry(1.098, 50, 50);
var earthMaterial = new THREE.MeshLambertMaterial({ map: earthTexture });
var earth = new THREE.Mesh(earthGeometry, earthMaterial);
const earthAngularSpeed = 0.0024;
const earthRadius = 280;
let earthAngle = 0;

var venusGeometry = new THREE.SphereGeometry(1.04, 50, 50);
var venusMaterial = new THREE.MeshLambertMaterial({ map: venusTexture });
var venus = new THREE.Mesh(venusGeometry, venusMaterial);
const venusAngularSpeed = 0.0025;
const venusRadius = 280;
let venusAngle = 0;

var mercuryGeometry = new THREE.SphereGeometry(0.41, 50, 50);
var mercuryMaterial = new THREE.MeshLambertMaterial({ map: mercuryTexture });
var mercury = new THREE.Mesh(mercuryGeometry, mercuryMaterial);
const mercuryAngularSpeed = 0.0026;
const mercuryRadius = 260;
let mercuryAngle = 0;



var sunGeometry = new THREE.SphereGeometry(196, 100, 100);
var sunMaterial = new THREE.MeshBasicMaterial({ map: sunTexture });
var sun = new THREE.Mesh(sunGeometry, sunMaterial);


sun.add(neptune);
sun.add(uranus);
sun.add(rings);
sun.add(saturn);
sun.add(jupiter);
sun.add(mars);
sun.add(earth);
sun.add(venus);
sun.add(mercury);
sun.add(orbit);
scene.add(sun);



sun.position.x = 0;
rings.rotation.x = 30;
rings.rotation.y = 0.2;
orbit.rotation.x = 1.5708;

// const axesHelper = new THREE.AxesHelper(600);
// scene.add(axesHelper);

camera.position.y = 2000;


var light = new THREE.PointLight(0xffffff, 1);
light.position.set(0, 0, 0);
scene.add(light);




function animate() {

  requestAnimationFrame(animate)
  controls.update();


  neptuneAngle += (neptuneAngularSpeed + time);
  var x = neptuneRadius * Math.sin(neptuneAngle);
  var y = 0;
  var z = neptuneRadius * Math.cos(neptuneAngle);
  neptune.position.set(x, y, z);

  uranusAngle += (uranusAngularSpeed + time);
  var x = uranusRadius * Math.sin(uranusAngle);
  var y = 0;
  var z = uranusRadius * Math.cos(uranusAngle);
  uranus.position.set(x, y, z);

  saturnAngle += (saturnAngularSpeed + time);
  var x = saturnRadius * Math.sin(saturnAngle);
  var y = 0;
  var z = saturnRadius * Math.cos(saturnAngle);
  saturn.position.set(x, y, z);

  ringsAngle += (ringsAngularSpeed + time);
  var x = ringsRadius * Math.sin(ringsAngle);
  var y = 0;
  var z = ringsRadius * Math.cos(ringsAngle);
  rings.position.set(x, y, z);

  jupiterAngle += (jupiterAngularSpeed + time);
  var x = jupiterRadius * Math.sin(jupiterAngle);
  var y = 0;
  var z = jupiterRadius * Math.cos(jupiterAngle);
  jupiter.position.set(x, y, z);

  marsAngle += (marsAngularSpeed + time);
  var x = marsRadius * Math.sin(marsAngle);
  var y = 0;
  var z = marsRadius * Math.cos(marsAngle);
  mars.position.set(x, y, z);

  earthAngle += (earthAngularSpeed + time);
  var x = earthRadius * Math.sin(earthAngle);
  var y = 0;
  var z = earthRadius * Math.cos(earthAngle);
  earth.position.set(x, y, z);

  venusAngle += (venusAngularSpeed + time);
  var x = venusRadius * Math.sin(venusAngle);
  var y = 0;
  var z = venusRadius * Math.cos(venusAngle);
  venus.position.set(x, y, z);

  mercuryAngle += (mercuryAngularSpeed + time);
  var x = mercuryRadius * Math.sin(mercuryAngle);
  var y = 0;
  var z = mercuryRadius * Math.cos(mercuryAngle);
  mercury.position.set(x, y, z);



  rings.rotation.z += 0.0005;
  sun.rotation.y += 0.0001;
  jupiter.rotation.y += 0.005
  renderer.render(scene, camera);
};

animate();





var raycaster = new THREE.Raycaster();

// Fonction pour gérer les événements de clic
function onMouseClick(event) {
  // Récupérer la position de la souris dans les coordonnées de la scène
  var mouse = new THREE.Vector2();
  mouse.x = (event.clientX / window.innerWidth) * 2 - 1;
  mouse.y = - (event.clientY / window.innerHeight) * 2 + 1;

  // Mettre à jour le raycaster avec la position de la souris
  raycaster.setFromCamera(mouse, camera);

  // Détecter les intersections entre le rayon et les objets de la scène
  var intersects = raycaster.intersectObjects(scene.children);

  // Si un objet est intersecté, traiter l'événement de clic
  if (intersects.length > 0) {
    var object = intersects[0].object;

    // Vérifier si l'objet intersecté est l'anneau
    if (object === sun) {
      console.log("Soleil")
    }
    if (object === mercury) {
      console.log("Mercure")
    }
    if (object === venus) {
      console.log("Venus")
    }
    if (object === earth) {
      console.log("La terre")
    }
    if (object === mars) {
      console.log("Mars")
    }
    if (object === jupiter) {
      console.log(jupiter)
    }
    if (object === saturn) {
      console.log("Saturne")
    }
    if (object === uranus) {
      console.log("Uranus")
    }
    if (object === neptune) {
      console.log("Neptune")
    }
  }
}
document.addEventListener('click', onMouseClick);
</script>

<template>


</template>

<style scoped>

</style>
